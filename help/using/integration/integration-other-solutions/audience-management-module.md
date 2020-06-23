---
description: DIL(Audience Manager Data Integration Library) 코드가 페이지에서 픽셀을 보내는 대신 Analytics 데이터를 Audience Manager으로 전달하려면 Adobe Analytics AppMeasurement에 대상 관리 모듈을 추가합니다.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: DIL(Audience Manager Data Integration Library) 코드가 페이지에서 픽셀을 보내는 대신 Analytics 데이터를 Audience Manager으로 전달하려면 Adobe Analytics AppMeasurement에 대상 관리 모듈을 추가합니다.
seo-title: 대상 관리 모듈 구현
solution: Audience Manager
title: 대상 관리 모듈 구현
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 5%

---


# 데이터를 받는 방법 [!DNL Adobe Analytics] 으로 [!DNL Audience Manager] {#implement-the-audience-management-module}

이 튜토리얼의 단계에 따라 페이지에서 [!DNL Analytics] 픽셀을 전송하도록 하는 대신 데이터 [!DNL Audience Manager] 를 전달하려면 이 [!DNL Audience Manager] 의 [!UICONTROL Data Integration Library] 단계를[!DNL DIL]따르십시오.

>[!TIP]
>
>데이터를 전달하 [!DNL Adobe Experience Platform Launch] 는 데 사용하는 것이 좋습니다 [!UICONTROL Analytics] [!DNL Audience Manager]. 이 페이지 [!UICONTROL Launch]와 같이 코드를 수동으로 복사하지 않아도 [!DNL AppMeasurement]됩니다.

## 사전 요구 사항 {#prereqs}

이 문서에 설명된 확장 기능을 활성화하거나 코드를 구현하는 것 외에도 다음을 수행해야 합니다.

* Implement the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html).
* 의 [보고서 세트에](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 대해 서버측 전달을 활성화합니다 [!UICONTROL Adobe Analytics Admin Console].

## 구현 {#implementation}

사용하는 태그 관리 솔루션에 따라 데이터 전달을 두 가지 방법 [!DNL Adobe Analytics] 으로 구현할 [!DNL Audience Manager]수 있습니다.

### 구현에서 [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] 속성 [에서 Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) 확장 [!DNL Adobe Analytics] 을 사용하는 것이 좋습니다 [!DNL Audience Manager] . 이 경우 코드를 수동으로 복사할 필요가 없습니다. 대신 아래 이미지와 같이 확장자에서 데이터 공유를 [!DNL Analytics Launch] 활성화해야 합니다. 또한 [Adobe Analytics 익스텐션](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 설명서를 참조하십시오.

>[!TIP]
>
>익스텐션을 [!DNL Adobe Analytics] 설치한 경우에는 익스텐션도 *설치하지 마십시오* [!DNL Audience Manager] . 확장 기능에서 데이터를 [!DNL Analytics] 전달하면 [!DNL Audience Manager] 확장 기능이 대체됩니다.

![Adobe Analytics 확장 프로그램에서 Audience Manager으로 데이터 공유를 활성화하는 방법](/help/using/integration/assets/analytics-to-aam.png)

### 기타 태그 관리 솔루션 [!DNL Adobe Digital Tag Management (DTM)] 을 사용한 구현

>[!WARNING]
>
>[!DNL Adobe] 노을지는 2020년 말 [!DNL DTM] 에 발표된다. 자세한 내용 및 일정을 보려면 [!DNL DTM] Adobe 커뮤니티 포럼 [에서 일몰을 위한 계획을 참조하십시오](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Adobe [!UICONTROL Audience Management Module] DTM [또는 다른 태그 관리 솔루션을 사용하여](https://docs.adobe.com/content/help/ko-KR/dtm/using/dtm-home.html) 구현하려면:

1. Analytics 코드 관리자 [!UICONTROL AppMeasurement] (버전 1.5 이상 필요)를 사용하여 [](https://docs.adobe.com/content/help/ko-KR/analytics/admin/admin-tools/code-manager-admin.html) 다운로드하십시오.
1. 다운로드한 zip 파일에 포함된 버전으로 [!UICONTROL AppMeasurement] 코드를 업데이트합니다.
1. zip 파일의 모든 코드 `AppMeasurement_Module_AudienceManagement.js` 를 복사합니다. 텍스트 바로 위에 `appMeasurement.js` 파일에 붙여넣고 `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 이전 단계 `s.loadModule("AudienceManagement");`에서 방금 추가한 `AppMeasurement_Module_AudienceManagement.js` 코드 바로 위에 코드를 추가합니다.
1. 아래 코드를 업데이트 및 복사하여 파일의 `doPlugins` 함수에 `AppMeasurement.js` 추가합니다.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>이 `audienceManagement.setup` 함수는 매개 변수를 이 코드에서 구성할 수 있는 [!DNL Audience Manager] `DIL.create` 함수와 공유합니다. 이러한 매개 변수에 대한 자세한 내용은 [DIL 만들기를 참조하십시오](../../dil/dil-class-overview/dil-create.md#dil-create).

## 코드 요소 정의 {#code-elements-defined}

다음 표는 코드 샘플의 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. 이 이름은 사용자에게 할당된 파트너 이름입니다 [!DNL Adobe]. 이것은 귀하의 [!UICONTROL partner ID] 또는 파트너 하위 도메인이라고도 합니다.  파트너 이름을 모르는 경우 [!DNL Adobe] 컨설턴트나 [고객 지원](https://helpx.adobe.com/kr/marketing-cloud/contact-support.html) 센터에 문의하십시오. |
| `containerNSID` | 필수. 대부분의 고객은 간편하게 설정할 수 있습니다 `"containerNSID":0` . 그러나 회사에서 ID를 다른 컨테이너와 동기화해야 하는 경우 여기에서 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항입니다. 이 구성을 사용하면 퍼스트 파티 도메인에서 [!DNL Adobe] 쿠키를 설정할 수 있습니다. 여기에는 [!DNL cookie] UUID가 [포함됩니다](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 필수. 버전 2.10 이상 `namespace` 과 함께 번들로 제공되는 [!DNL AudienceManagement] 모듈을 사용하는 경우 매개 변수가 [!UICONTROL AppMeasurement] 필요합니다. 이 [!UICONTROL AudienceManagement] 모듈에서는 [!UICONTROL Adobe Experience Platform Identity Service] 3.3 이상을 사용해야 합니다. <br><br>이 [!UICONTROL Experience Cloud Organization ID] 는 회사가 제품 등록 시 제공하는 ID입니다 [!UICONTROL Experience Cloud]. 조직 및 계정 연결에서 회사 조직 [ID를 확인합니다](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## 결과: 데이터 전달 대상 [!DNL Audience Manager] {#results-data-forwarding}

구현에서 다음을 수행한 [!DNL Analytics] [!DNL Audience Manager] 후 데이터를 전송합니다.

* 활성화됨 [!UICONTROL Server-Side Forwarding] (이 기능에 대해 컨설턴트에게 문의);
* 구현됨 [!DNL Adobe Experience Platform Identity Service];
* 이 자습서의 구현 단계를 따릅니다.

이 프로세스에서는 다음 주소로 데이터를 보냅니다. [!DNL Audience Manager]

* 페이지 보기 호출;
* 추적된 링크에서;
* 비디오 마일스톤 및 하트비트 비디오 보기에서

>[!NOTE]
>
>에서 전송된 변수는 특수 접두사를 [!DNL Audience Manager] [!DNL Analytics] 사용합니다. 트레이트를 만들 때 이러한 접두사를 이해하고 고려해야 [!DNL Audience Manager] 합니다. 이러한 접두사에 대한 자세한 내용은 키 변수의 [접두사 요구 사항을 참조하십시오](../../features/traits/trait-variable-prefixes.md).
