---
description: Audience Manager Data Integration Library(DIL) 코드가 페이지에서 픽셀을 보내도록 하지 않고 Analytics 데이터를 Audience Manager에 전달하도록 Audience Management 모듈을 Adobe Analytics AppMeasurement에 추가합니다.
keywords: 대상 분석;analytics;ssf;서버 측 전달
seo-description: Audience Manager Data Integration Library(DIL) 코드가 페이지에서 픽셀을 보내도록 하지 않고 Analytics 데이터를 Audience Manager에 전달하도록 Audience Management 모듈을 Adobe Analytics AppMeasurement에 추가합니다.
seo-title: 대상 관리 모듈 구현
solution: Audience Manager
title: 대상 관리 모듈 구현
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 5%

---

# [!DNL Adobe Analytics]의 데이터를 [!DNL Audience Manager] {#implement-the-audience-management-module}(으)로 전달하는 방법

이 자습서의 절차에 따라 [!DNL Audience Manager] [!UICONTROL Data Integration Library]([!DNL DIL]) 코드가 페이지에서 픽셀을 보내는 대신 [!DNL Analytics] 데이터를 [!DNL Audience Manager]으로 전달하십시오.

>[!TIP]
>
>[!DNL Adobe Experience Platform Launch]을 사용하여 [!UICONTROL Analytics] 데이터를 [!DNL Audience Manager]로 전달하는 것이 좋습니다. [!UICONTROL Launch]을 사용하면 이 페이지에 표시된 것처럼 코드를 [!DNL AppMeasurement]에 수동으로 복사할 필요가 없습니다.

## 사전 요구 사항 {#prereqs}

이 문서에 설명된 코드를 구현하거나 익스텐션을 활성화하는 것 외에도 다음을 수행해야 합니다.

* [Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html)를 구현합니다.
* [!UICONTROL Adobe Analytics Admin Console]의 보고서 세트에 대해 [서버측 전달](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)을 활성화합니다.

## 구현 {#implementation}

사용하는 태그 관리 솔루션에 따라 [!DNL Adobe Analytics]에서 [!DNL Audience Manager](으)로 데이터 전달을 구현하는 방법에는 두 가지가 있습니다.

### [!DNL Adobe Experience Platform Launch]을(를) 사용한 구현

[!DNL Adobe] 속성 [](https://docs.adobe.com/content/help/en/launch/using/overview.html) 을 계기  [!DNL Adobe Analytics] 및 [!DNL Audience Manager] 는 Launchextension을 사용하는 것이 좋습니다. 이 경우 코드를 수동으로 복사할 필요가 없습니다. 대신 아래 이미지와 같이 [!DNL Analytics Launch] 확장에서 데이터 공유를 활성화해야 합니다. [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 설명서도 참조하십시오.

>[!TIP]
>
>[!DNL Adobe Analytics] 확장을 설치하는 경우 *도* 확장자를 설치하지 마십시오. [!DNL Audience Manager] [!DNL Analytics] 확장에서 데이터를 전달하는 것은 [!DNL Audience Manager] 확장 기능을 대체합니다.

![Adobe Analytics 익스텐션에서 Audience Manager으로 데이터 공유를 활성화하는 방법](/help/using/integration/assets/analytics-to-aam.png)

### [!DNL Adobe Digital Tag Management (DTM)] 또는 기타 태그 관리 솔루션을 사용한 구현

>[!WARNING]
>
>[!DNL Adobe] 2020년 말까지 일몰을  [!DNL DTM] 만들 계획을 발표했다. 자세한 내용 및 일정을 보려면 [Adobe 커뮤니티 포럼](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)에서 [!DNL DTM] 일몰 계획을 참조하십시오.

[Adobe DTM](https://docs.adobe.com/content/help/ko-KR/dtm/using/dtm-home.html) 또는 다른 태그 관리 솔루션을 사용하여 [!UICONTROL Audience Management Module]을(를) 구현하려면:

1. [분석 코드 관리자](https://docs.adobe.com/content/help/ko-KR/analytics/admin/admin-tools/code-manager-admin.html)를 사용하여 [!UICONTROL AppMeasurement](버전 1.5 이상 필요)을 다운로드합니다.
1. [!UICONTROL AppMeasurement] 코드를 다운로드한 zip 파일에 포함된 버전으로 업데이트합니다.
1. zip 파일에서 `AppMeasurement_Module_AudienceManagement.js`의 모든 코드를 복사합니다. 텍스트 바로 위 `appMeasurement.js` 파일에 붙여 넣습니다. `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 이전 단계에서 추가한 `AppMeasurement_Module_AudienceManagement.js` 코드 바로 위에 `s.loadModule("AudienceManagement");` 코드를 추가합니다.
1. 아래 코드를 업데이트 및 복사하여 `AppMeasurement.js` 파일의 `doPlugins` 함수에 추가합니다.

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
>`audienceManagement.setup` 함수는 매개 변수를 [!DNL Audience Manager] `DIL.create` 함수와 공유하므로 이 코드에서 구성할 수 있습니다. 이러한 매개 변수에 대한 자세한 내용은 [DIL 만들기](../../dil/dil-class-overview/dil-create.md#dil-create)를 참조하십시오.

## 코드 요소 정의 {#code-elements-defined}

다음 표는 코드 샘플에서 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. 이 이름은 [!DNL Adobe]에서 사용자에게 할당된 파트너 이름입니다. 이것은 [!UICONTROL partner ID] 또는 파트너 하위 도메인이라고도 합니다.  파트너 이름을 모르는 경우 [!DNL Adobe] 컨설턴트 또는 [고객 지원 센터](https://helpx.adobe.com/kr/marketing-cloud/contact-support.html)에 문의하십시오. |
| `containerNSID` | 필수. 대부분의 고객은 `"containerNSID":0`만 설정할 수 있습니다. 그러나 회사가 다른 컨테이너와 ID를 사용자 정의해야 하는 경우 여기에서 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항입니다. 이 구성을 사용하여 자사 도메인에 [!DNL Adobe] 쿠키를 설정할 수 있습니다. 이 [!DNL cookie]에는 [UUID](../../reference/ids-in-aam.md)가 포함되어 있습니다. |
| `visitorService` - `namespace` | 필수. [!DNL AudienceManagement] 모듈을 [!UICONTROL AppMeasurement] 버전 2.10 이하와 번들로 제공하는 경우 `namespace` 매개 변수가 필요합니다. 이 [!UICONTROL AudienceManagement] 모듈에서는 [!UICONTROL Adobe Experience Platform Identity Service] 3.3 이상을 사용해야 합니다. <br><br>이  [!UICONTROL Experience Cloud Organization ID] ID는 회사 등록 시 제공되는 ID입니다 [!UICONTROL Experience Cloud]. [조직 및 계정 연결](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)에서 회사의 조직 ID를 확인합니다. |

## 결과:[!DNL Audience Manager] {#results-data-forwarding}로 데이터 전달

[!DNL Analytics] 구현은 다음을 수행한 후 [!DNL Audience Manager]에 데이터를 보냅니다.

* 활성화된 [!UICONTROL Server-Side Forwarding](이 기능에 대해 컨설턴트에게 문의);
* [!DNL Adobe Experience Platform Identity Service]; 구현됨
* 이 자습서의 구현 단계를 따릅니다.

이 프로세스는 데이터를 [!DNL Audience Manager]으로 보냅니다.

* 페이지 보기 호출에서;
* 추적된 링크에서;
* 비디오 이정표 및 하트비트 비디오 보기에서.

>[!NOTE]
>
>[!DNL Analytics]에서 [!DNL Audience Manager]으로 전송된 변수는 특수 접두어를 사용합니다. [!DNL Audience Manager] 트레이트를 만들 때 이러한 접두어를 이해하고 고려해야 합니다. 이러한 접두어에 대한 자세한 내용은 [키 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)을 참조하십시오.
