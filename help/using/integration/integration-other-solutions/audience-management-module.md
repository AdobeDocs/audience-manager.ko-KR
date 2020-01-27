---
description: Audience Manager DIL(Data Integration Library) 코드가 페이지에서 픽셀을 보내도록 하지 않고 Analytics 데이터를 Audience Manager에 전달하려면 Audience Management 모듈을 Adobe Analytics AppMeasurement에 추가합니다.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Audience Manager DIL(Data Integration Library) 코드가 페이지에서 픽셀을 보내도록 하지 않고 Analytics 데이터를 Audience Manager에 전달하려면 Audience Management 모듈을 Adobe Analytics AppMeasurement에 추가합니다.
seo-title: 대상 관리 모듈 구현
solution: Audience Manager
title: 대상 관리 모듈 구현
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 7e8ba292f2f901b1323d30d682066b49df885a0c

---


# Adobe Analytics에서 Audience Manager로 데이터를 전달하는 방법 {#implement-the-audience-management-module}

이 자습서의 단계에 따라 Audience Manager [!DNL Analytics] ( [!UICONTROL Data Integration Library][!UICONTROL DIL]) 코드가 페이지에서 픽셀을 전송하도록 하는 대신 데이터를 Audience Manager로 전달하십시오.

>[!TIP]
>
>데이터를 Audience Manager [!UICONTROL Adobe Launch] [!UICONTROL Analytics] 로 전달하는 데 사용하는 것이 좋습니다. 을 [!UICONTROL Launch]사용하면 이 페이지에 표시된 것처럼 코드를 수동으로 복사하지 않아도 [!UICONTROL AppMeasurement]됩니다.

## 전제 조건 {#prereqs}

확장 기능을 활성화하거나 이 문서에 설명된 코드를 구현하는 것 외에도 다음을 수행해야 합니다.

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* 에서 [보고서 세트에](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 대해 서버측 전달을 활성화합니다 [!UICONTROL Adobe Analytics Admin Console].

## 구현 {#implementation}

사용하는 태그 관리 솔루션에 따라 Adobe Analytics에서 Audience Manager로 데이터 전달을 구현하는 방법에는 두 가지가 있습니다.

### Adobe Launch를 사용한 구현

Adobe에서는 Launch [확장 기능을 사용하여](https://docs.adobe.com/content/help/en/launch/using/overview.html) Adobe Analytics 및 Audience Manager를 속성에 구현하는 것이 좋습니다. 이 경우 코드를 수동으로 복사할 필요가 없습니다. 대신 아래 이미지와 같이 Analytics Launch 확장 프로그램에서 데이터 공유를 활성화해야 합니다. Adobe Analytics 확장 [설명서를](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 참조하십시오.

>[!TIP]
>
>Adobe Analytics 익스텐션을 설치하는 경우 Audience Manager 익스텐션도 설치하지 *마십시오* . Analytics 확장 기능에서 데이터를 전달하면 Audience Manager 확장 기능이 대체됩니다.

![Adobe Analytics 익스텐션에서 Audience Manager로 데이터 공유를 활성화하는 방법](/help/using/integration/assets/analytics-to-aam.png)

### Adobe DTM(Digital Tag Management) 또는 기타 태그 관리 솔루션을 사용한 구현


>[!WARNING]
>
>Adobe는 2020년 말까지 DTM을 종료할 계획을 발표했습니다. 자세한 내용 및 예약은 Adobe 커뮤니티 포럼의 DTM Plans for a Sunset [을](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)참조하십시오.

Adobe DTM [!UICONTROL Audience Management Module] 또는 [다른 태그 관리 솔루션을 사용하여](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) 구현하려면 다음을 수행하십시오.

1. Analytics 코드 관리자를 [!UICONTROL AppMeasurement] 사용하여 [다운로드합니다](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (버전 1.5 이상 필요).
1. 다운로드한 zip 파일에 포함된 버전으로 [!UICONTROL AppMeasurement] 코드를 업데이트합니다.
1. zip 파일에서 모든 코드를 `AppMeasurement_Module_AudienceManagement.js` 복사합니다. 텍스트 바로 위에 `appMeasurement.js` 파일에 붙여넣고 `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. 이전 `s.loadModule("AudienceManagement");`단계에서 추가한 `AppMeasurement_Module_AudienceManagement.js` 코드 바로 위에 코드를 추가합니다.
1. 아래 코드를 업데이트 및 복사하여 `doPlugins` 파일의 `AppMeasurement.js` 함수에 추가합니다.

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
>이 `audienceManagement.setup` 함수는 이 코드에서 구성할 수 있는 Audience Manager `DIL.create` 함수와 매개 변수를 공유합니다. 이러한 매개 변수에 대한 자세한 내용은 DIL [만들기를](../../dil/dil-class-overview/dil-create.md#dil-create)참조하십시오.

## 코드 요소 정의 {#code-elements-defined}

다음 표에서는 코드 샘플에서 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. Adobe에서 할당한 파트너 이름입니다. 이를 &quot;파트너 ID&quot; 또는 &quot;파트너 하위 도메인&quot;이라고도 합니다.  파트너 이름을 모르는 [경우 Adobe 컨설턴트나 고객](https://helpx.adobe.com/marketing-cloud/contact-support.html) 지원 센터에 문의하십시오. |
| `containerNSID` | 필수. 대부분의 고객은 설정할 수 `"containerNSID":0` 있습니다. 그러나 회사에서 ID를 다른 컨테이너와 동기화해야 하는 경우 여기에서 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항입니다. 이 구성을 사용하면 퍼스트 파티 도메인에서 Adobe 쿠키를 설정할 수 있습니다. 이 쿠키에는 UUID가 [포함되어 있습니다](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 필수. AudienceManagement 모듈을 `namespace` [!UICONTROL AppMeasurement] 버전 2.10 이상 버전과 함께 번들로 사용하는 경우 이 매개 변수가 필요합니다. 이 [!UICONTROL AudienceManagement] 모듈에서는 [!UICONTROL Experience Cloud ID Service] 3.3 이상을 사용해야 합니다. <br> 이 [!UICONTROL Experience Cloud Organization ID] ID는 회사가 Adobe Creative Cloud에 가입하면 제공되는 [!UICONTROL Experience Cloud]ID입니다. 조직 및 계정 연결에서 회사의 조직 [ID를 확인합니다](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## 결과:Audience Manager로 데이터 전달 {#results-data-forwarding}

구현에서 다음을 수행한 후 Audience Manager로 데이터를 전송합니다. [!DNL Analytics]

* 활성화됨 [!UICONTROL Server-Side Forwarding] (이 기능에 대해 컨설턴트에게 문의);
* Experience Cloud ID 서비스를 구현했습니다.
* 이 자습서의 구현 단계를 따릅니다.

이 프로세스에서는 다음 주소로 데이터를 전송합니다. [!DNL Audience Manager]

* 페이지 보기 호출 시;
* 추적된 링크에서;
* 비디오 이정표 및 하트비트 비디오 보기에서

>[!NOTE]
>
>특수 접두사를 사용하기 위해 Audience Manager로 전송된 [!DNL Analytics] 변수입니다. Audience Manager 트레이트를 만들 때 이러한 접두사를 이해하고 고려해야 합니다. 이러한 접두사에 대한 자세한 내용은 키 변수의 [접두사 요구 사항을 참조하십시오](../../features/traits/trait-variable-prefixes.md).