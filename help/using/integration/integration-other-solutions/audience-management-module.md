---
description: Audience Manager에 대상 관리 모듈을 추가하여 Audience Manager 데이터 통합 라이브러리 (DIL) 코드가 페이지에서 픽셀을 전송하는 대신 Analytics 데이터를 Audience Manager로 전달하십시오.
keywords: 고객 분석; Analytics; SSF; 서버측 전달
seo-description: Audience Manager에 대상 관리 모듈을 추가하여 Audience Manager 데이터 통합 라이브러리 (DIL) 코드가 페이지에서 픽셀을 전송하는 대신 Analytics 데이터를 Audience Manager로 전달하십시오.
seo-title: 고객 관리 모듈 구현
solution: Audience Manager
title: 고객 관리 모듈 구현
uuid: 08846427-DEF 3-4 A 15-88 E 5-08882 D 8 D 57 CE
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## 전제 조건 {#prereqs}

이 문서에 설명된 코드를 구현하는 것 외에, 다음 사항도 수행해야 합니다.

* [Experience Cloud ID 서비스](https://marketing.adobe.com/resources/help/en_US/mcvid/)구현
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## 구현 {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

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
>`audienceManagement.setup` 이 함수는 이 코드에서 구성할 수 있는 Audience Manager `DIL.create` 함수와 매개 변수를 공유합니다. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

다음 표는 코드 샘플의 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. Adobe에서 귀하에게 할당한 파트너 이름입니다. 경우에 따라 &quot;파트너 ID&quot; 또는 &quot;파트너 하위 도메인&quot; 이라고도 합니다. Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don&#39;t know your partner name. |
| `containerNSID` | 필수. `"containerNSID":0` 대부분의 고객은 설정할 수 있습니다. 그러나 ID가 다른 컨테이너와 ID를 동기화해야 하는 경우 여기에 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항입니다. 이 구성을 통해 퍼스트 파티 도메인에서 Adobe 쿠키를 설정할 수 있습니다. This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 필수. The `namespace` parameter is required if you use the AudienceManagement module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. [!UICONTROL AudienceManagement] 이 모듈에서는 3.3 이상을 사용해야 [!UICONTROL Experience Cloud ID Service] 합니다. <br>는 [!UICONTROL Experience Cloud Organization ID] 에 등록할 때 회사가 제공하는 ID 입니다 [!UICONTROL Experience Cloud]. Find out your company&#39;s Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

[!DNL Analytics] 구현은 다음 작업을 수행한 후 Audience Manager로 데이터를 보냅니다.

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* ID 서비스 구현;
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* 페이지 보기 호출 시;
* 추적된 링크에서;
* 비디오 마일스톤 및 하트비트 비디오 보기에서 볼 수 있습니다.

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. Audience Manager 트레이트를 만들 때 이러한 접두사를 이해하고 고려해야 합니다. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).