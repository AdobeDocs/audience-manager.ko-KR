---
description: 이 페이지에서는 웹 기반 Audience Manager 대상 세그먼트를 Facebook으로 전송하기 위한 목적으로 투명도가 향상된 온라인 광고 타깃팅을 위해 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 과정을 보여 줍니다.
seo-description: 이 페이지에서는 웹 기반 Audience Manager 대상 세그먼트를 Facebook으로 전송하기 위한 목적으로 투명도가 향상된 온라인 광고 타깃팅을 위해 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 과정을 보여 줍니다.
seo-title: Facebook WCA 통합
solution: Audience Manager
title: Facebook WCA 통합
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 6%

---


# [!DNL Facebook WCA] 통합 {#facebook-wca-integration}

이 페이지에서는 투명도가 향상된 온라인 광고 타깃팅을 위해 웹 기반 [!DNL Facebook Website Custom Audiences] 대상 세그먼트를[!DNL WCA][!DNL Audience Manager] [!DNL Facebook]로 보낼 목적으로 픽셀을 만드는 과정을 보여 줍니다.

## 개요 {#overview}

[WCA(Facebook Website Custom Audiences)](https://www.facebook.com/business/help/449542958510885) 기능을 사용하면 특정 페이지를 방문했거나 웹 사이트에서 특정 작업을 수행한 사람의 목록을 만들 수 있습니다. [!DNL Audience Manager] 타깃팅을 위해 웹 기반 대상을 보내도록 사용자 정의 픽셀 기반 통합을 구성할 수 있는 대상 [!DNL WCA] 을 [!DNL URL] [!DNL Facebook] 사용하여 활성화할 수 있습니다.

![Facebook WCA 통합](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 이 기능을 사용하려면 [!UICONTROL Website] URL 대상의 소셜 플랫폼 [대상 옵션을 선택해야 합니다](/help/using/features/destinations/create-url-destination.md). 소셜 플랫폼은 레퍼러 정보를 플랫폼으로 보낼 때 마스크가 해제되어야 합니다. 이것은 대상 플랫폼/파트너가 레퍼러에서 정보를 볼 수 있음을 의미합니다 [!DNL URL].

## 사전 요구 사항 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 세그먼트, 새 [!DNL Facebook] 대상에 할당할 준비가 되었습니다. 다음은 [UI에서 세그먼트를](/help/using/features/segments/segment-builder.md) 만드는 [!DNL Audience Manager] 방법입니다.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]버전 4.1.0 이상. Download the latest version **[here](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]버전 9.0 이상, **[여기에서 다운로드할 수 있습니다](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 또는 SSF([Server-Side Forwarding)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)를 사용하여 데이터를[!DNL Audience Manager]가져올 경우 AppMeasurement 버전 2.12 이상을 사용해야합니다. Download[!DNL AppMeasurement]using the[Analytics Code Manager](https://docs.adobe.com/content/help/ko-KR/analytics/admin/admin-tools/code-manager-admin.html).

Adobe Experience Platform 실행 또는 [Adobe 다이내믹 태그 관리를 사용하여 3단계와 4단계의 라이브러리를](https://docs.adobelaunch.com/) 설치하거나 업그레이드하는 것이 좋습니다 [](https://docs.adobe.com/content/help/ko-KR/dtm/using/dtm-home.html).

## 1단계 - Create a [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

새 [!UICONTROL URL Destination] in을 만들고 이름을 [!DNL Audience Manager] 지정합니다 [!DNL Facebook Website Custom Audiences]. 대상을 만들 때는 아래 설정을 사용하십시오. URL 대상 구성 [페이지를 참조할 수도](/help/using/features/destinations/create-url-destination.md) 있습니다.

### 기본 정보

* **[!UICONTROL Category]**: 사용자 지정
* **[!UICONTROL Type]**: [!DNL URL]
* 확인란을 **[!UICONTROL Auto-fill Destination Mapping]** 선택하고 선택합니다 **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

옵션을 선택합니다 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> 이 내보내기 레이블은 장치 그래프에서 파생된 타사 데이터와 데이터가 세그먼트에 포함되지 않도록 합니다.

### 구성

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 이 [!UICONTROL URL Type] 옵션을 선택하면 [!DNL Audience Manager] 픽셀 [!DNL URL] 을 실행할 때 레퍼러 [!DNL Facebook WCA] 정보가 숨겨지지 않습니다.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 및 **[!UICONTROL Base URL]** 필드에 **[!UICONTROL Secure URL]** [!DNL Facebook WCA] 픽셀을 입력합니다.
* **[!UICONTROL Delimiter]**: `,`

기본 [!DNL URL] 예: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

페이지에서 실행된 픽셀 예. 이 예에서는 ID가 3401321, 2993399, 3263410인 세 개의 [!DNL Audience Manager] 세그먼트에 대해 자격이 있는 사용자를 보여줍니다.

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 매개 변수 | 설명 |
---------|----------|
| `id` | 대상 픽셀을 만들 때 사용자 인터페이스에서 찾을 수 있는 [!DNL Facebook] [!DNL Facebook Ad Manager] 픽셀 ID입니다. |
| `ev` | Event.     이 값은 픽셀이 사이트에서 실행되기 시작하면 [!DNL Facebook Ad Manager] 사용자 인터페이스에 표시됩니다. 자세한 내용은 3 [!UICONTROL Include] 단계 [](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)의 항목을 참조하십시오. |
| `cd[segID]` | 사이트에서 픽셀이 실행되기 시작하면 [!DNL Facebook Ad Manager] 사용자 인터페이스 내에 채워지기 시작하는 추가 매개 변수입니다. `segID` 또한 임의의 값이 있습니다. |
| `%ALIAS%` | 매크로 [!DNL Audience Manager] - 사이트 방문자가 자격이 되는 [!DNL Audience Manager] [!UICONTROL segment] ID로 동적으로 대체되며 쉼표(,)로 구분됩니다. |

아래 [!UICONTROL URL destination] 이미지에는 구성이 있어야 합니다.

![대상 구성](/help/using/integration/assets/facebook-wca.png)

Save the [!UICONTROL destination]. 그런 다음 **세그먼트 매핑** 단계로 진행할 수 있습니다.

## 2단계 - 세그먼트 매핑 - 세그먼트를 대상에 매핑 {#step-2-segment-mappings}

URL [대상](/help/using/features/destinations/create-url-destination.md) 구성 워크플로우에서 해당 세그먼트를 새로 만든 세그먼트에 매핑합니다 [!UICONTROL destination]. 매핑 값이 로 자동 [!DNL Audience Manager] 채워집니다 [!UICONTROL segment ID].

종료 날짜를 입력합니다(해당되는 경우). 종료 날짜가 없는 경우는 비워 둡니다.

## 3단계 - 내부 [!UICONTROL Audience] 만들기 [!DNL Facebook Ads Manager] {#step-3-create-audience}

도움말 [설명서에서 웹 사이트 사용자 지정 대상](https://www.facebook.com/business/help/666509013483225) 만들기를 [!DNL Facebook] 참조하십시오. 아래 표에서 [!UICONTROL Create Audience] 옵션을 선택합니다.

| 항목 | 설명 |
---------|----------|
| 웹 사이트 트래픽 | 사용자 지정 조합 |
| 포함 | <ul><li>> 선택 **[!UICONTROL Event]** 을 선택합니다 **[!UICONTROL Adobe-Audience-Manager-Segment]**. 1단계에서 예제 픽셀에 있는 `ev` 매개 변수의 값입니다. 픽셀을 아직 실행하지 않은 경우 **[!UICONTROL Event]** 옵션이나 옵션이 **[!UICONTROL Adobe-Audience-Manager-Segment]** 사용자 인터페이스에 표시되지 [!DNL Facebook] 않을 수 있습니다.</li><li>매개 변수 추가: 선택합니다 `segID`.</li><li><p>포함 **연산자를** 선택합니다.</p><p>방문자가 여러 세그먼트를 사용할 수 있음을 고려할 때 픽셀 매개 변수 [!UICONTROL segment IDs] 에 여러 개가 있을 수 있습니다. 같음(`=`) 연산자를 사용하면 방문자의 잠재력이 저하될 수 있으며 사용자는 더 낮은 볼륨을 관찰하게 됩니다.</p></li><li>값 추가: 세그먼트 ID를 [!DNL Audience Manager] 입력합니다.</li></ul> |
| 새 조건 추가 | 선택적 설정입니다. |
| 마지막 | 선택적 설정입니다. |
| 대상 이름 | 이 대상에 추가 조건을 추가하지 않는 한 일관성을 위해 동일한 세그먼트 이름을 사용하는 것이 좋습니다. [!DNL Audience Manager] |

## 4단계 - [!UICONTROL Audience] [!UICONTROL Campaign] [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

광고 캠페인 [!DNL Custom Audience]을 만든 후 광고 캠페인에 할당합니다. 새 캠페인을 만들거나 기존 캠페인을 편집하면 새로 만든 대상이 [!DNL Facebook] 사용자 인터페이스에 나열됩니다. 세그먼트에 광고 캠페인이 포함된 경우 사이트를 방문할 때 브라우저에서 픽셀 단위로 화재가 발생한 사용자를 타깃팅합니다. [!DNL Audience Manager]

## 요약 {#summary}

세그먼트를 대상에 할당하면 해당 세그먼트 사용자 [!DNL Audience Manager] 에게 해당 세그먼트 ID가 포함된 [!DNL Facebook WCA] 픽셀을 선택적으로 [!DNL Audience Manager] 실행하여 해당 세그먼트를 채웁니다 [!DNL Facebook WCA] [!DNL Facebook Audience]. 이로 인해 사이트의 해당 [!DNL Facebook Audience] 사용자에게 태그가 더 많이 실행될수록 점차적으로 증가하게 됩니다.

>[!NOTE]
>
> 사용자가 [!DNL Audience Manager] 세그먼트를 벗어나는 경우, 현재 사용자가 [!DNL Audience Manager] 에서 [!DNL Facebook] 제거되었음을 알리는 방법이 없습니다 [!DNL Custom Audience].

