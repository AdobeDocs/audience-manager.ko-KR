---
description: Audience Manager DIL(Data Integration Library) 코드가 페이지에서 픽셀을 보내도록 하지 않고 Analytics 데이터를 Audience Manager에 전달하려면 Audience Management 모듈을 Adobe Analytics AppMeasurement에 추가합니다.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Audience Manager DIL(Data Integration Library) 코드가 페이지에서 픽셀을 보내도록 하지 않고 Analytics 데이터를 Audience Manager에 전달하려면 Audience Management 모듈을 Adobe Analytics AppMeasurement에 추가합니다.
seo-title: 대상 관리 모듈 구현
solution: Audience Manager
title: 대상 관리 모듈 구현
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 1b7c29c0637432a320b2a7573a3f5a7fb4cdcb81

---


# 대상 관리 모듈 구현 {#implement-the-audience-management-module}

Audience [!UICONTROL Audience Management Module] Manager ( [!DNL Adobe Analytics] ) 코드가 페이지에서 픽셀을 전송하도록 하는 대신 Audience Manager에 [!UICONTROL AppMeasurement] 데이터를 전달하는 [!DNL Analytics] 대상을 [!UICONTROL Data Integration Library][!UICONTROL DIL]추가합니다.

>[!NOTE]
>
>이 페이지의 지침은 Adobe Digital Tag [Manager(DTM)](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) 또는 기타 태그 관리 솔루션을 사용한 구현을 참조하며, Adobe Launch를 ** 제외한 [모든](https://docs.adobe.com/content/help/en/launch/using/overview.html)태그 관리 솔루션을참조합니다. Adobe Launch를 사용하는 것이 좋습니다. 을 [!DNL Launch]사용하면 이 페이지에 표시된 것처럼 코드를 수동으로 복사하지 않아도 [!UICONTROL AppMeasurement]됩니다.

## 전제 조건 {#prereqs}

이 문서에 설명된 코드를 구현하는 것 외에도 다음을 수행해야 합니다.

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* 에서 보고서 세트에 [!UICONTROL Server-Side Forwarding] 대해 활성화합니다 [!UICONTROL Adobe Analytics Admin Console].

## 구현 {#implementation}

다음을 구현하려면 [!UICONTROL Audience Management Module]다음을 수행하십시오.

1. Analytics 코드 관리자를 [!UICONTROL AppMeasurement] 사용하여 [다운로드합니다](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (버전 1.5 이상 필요).
1. 다운로드한 zip 파일에 포함된 버전으로 [!UICONTROL AppMeasurement] 코드를 업데이트합니다.
1. zip 파일에서 모든 코드를 `AppMeasurement_Module_AudienceManagement.js` 복사합니다. 텍스트 바로 위에 `appMeasurement.js` 파일에 붙여넣고 `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 이전 `s.loadModule("AudienceManagement");`단계에서 추가한 `AppMeasurement_Module_AudienceManagement.js` 코드 바로 위에 코드를 추가합니다.
1. 아래 코드를 업데이트 및 복사하여 `doPlugins` 파일의 `AppMeasurement.js` 함수에 추가합니다.

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
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
>이 `audienceManagement.setup` 함수는 이 코드에서 구성할 수 있는 Audience Manager `DIL.create` 함수와 매개 변수를 공유합니다. 이러한 매개 변수에 대한 자세한 내용은 DIL [만들기를](../../dil/dil-class-overview/dil-create.md#dil-create)참조하십시오.

## 코드 요소 정의 {#code-elements-defined}

다음 표에서는 코드 샘플에서 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. Adobe에서 할당한 파트너 이름입니다. 이를 "파트너 ID" 또는 "파트너 하위 도메인"이라고도 합니다.  파트너 이름을 모르는 [경우 Adobe 컨설턴트나 고객](https://helpx.adobe.com/marketing-cloud/contact-support.html) 지원 센터에 문의하십시오. |
| `containerNSID` | 필수. 대부분의 고객은 설정할 수 `"containerNSID":0` 있습니다. 그러나 회사에서 ID를 다른 컨테이너와 동기화해야 하는 경우 여기에서 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항입니다. 이 구성을 사용하면 퍼스트 파티 도메인에서 Adobe 쿠키를 설정할 수 있습니다. 이 쿠키에는 UUID가 [포함되어 있습니다](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 필수. AudienceManagement 모듈을 `namespace` [!UICONTROL AppMeasurement] 버전 2.10 이상 버전과 함께 번들로 사용하는 경우 이 매개 변수가 필요합니다. 이 [!UICONTROL AudienceManagement] 모듈에서는 [!UICONTROL Experience Cloud ID Service] 3.3 이상을 사용해야 합니다. <br> 이 [!UICONTROL Experience Cloud Organization ID] ID는 회사가 Adobe Creative Cloud에 가입하면 제공되는 [!UICONTROL Experience Cloud]ID입니다. 조직 및 계정 연결에서 회사의 조직 [ID를 확인합니다](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## 결과:Audience Manager로 데이터 전달 {#results-data-forwarding}

구현에서 다음을 수행한 후 Audience Manager로 데이터를 전송합니다. [!DNL Analytics]

* 활성화됨 [!UICONTROL Server-Side Forwarding] (이 기능에 대해 컨설턴트에게 문의);
* ID 서비스를 구현했습니다.
* 를 [!UICONTROL Audience Management Module]설치했습니다.

이 프로세스에서는 다음 주소로 데이터를 전송합니다. [!DNL Audience Manager]

* 페이지 보기 호출 시;
* 추적된 링크에서;
* 비디오 이정표 및 하트비트 비디오 보기에서

>[!NOTE]
>
>특수 접두사를 사용하기 위해 Audience Manager로 전송된 [!DNL Analytics] 변수입니다. Audience Manager 트레이트를 만들 때 이러한 접두사를 이해하고 고려해야 합니다. 이러한 접두사에 대한 자세한 내용은 키 변수의 [접두사 요구 사항을 참조하십시오](../../features/traits/trait-variable-prefixes.md).