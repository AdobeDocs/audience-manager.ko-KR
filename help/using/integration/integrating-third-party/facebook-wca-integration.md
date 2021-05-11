---
description: 이 페이지에서는 향상된 투명도의 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook으로 보낼 목적으로 Facebook WCA(Website Custom Audiences) 픽셀을 만드는 프로세스를 보여 줍니다.
seo-description: 이 페이지에서는 향상된 투명도의 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook으로 보낼 목적으로 Facebook WCA(Website Custom Audiences) 픽셀을 만드는 프로세스를 보여 줍니다.
seo-title: Facebook WCA 통합
solution: Audience Manager
title: Facebook WCA 통합
feature: 타사 통합
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 5%

---

# [!DNL Facebook WCA] 통합 {#facebook-wca-integration}

이 페이지에서는 투명도가 향상된 온라인 광고 타깃팅을 위해 웹 기반 [!DNL Audience Manager] 대상 세그먼트를 [!DNL Facebook]에 보낼 목적으로 [!DNL Facebook Website Custom Audiences]([!DNL WCA]) 픽셀을 만드는 과정을 보여 줍니다.

## 개요 {#overview}

[Facebook WCA(Website Custom Audiences)를 ](https://www.facebook.com/business/help/449542958510885) 사용하면 특정 페이지를 방문했거나 웹 사이트에서 특정 작업을 수행한 사람의 목록을 만들 수 있습니다. [!DNL Audience Manager] 대상 [!DNL WCA] 을 사용하여 활성화할 수 있습니다. 대상을  [!DNL URL] 사용하여 활성화하면 웹 기반 대상을 타깃팅용으로 보내도록 사용자 정의 픽셀 기반 통합을 구성할 수  [!DNL Facebook] 있습니다.

![Facebook WCA 통합](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 이 기능을 사용하려면 [URL 대상](/help/using/features/destinations/create-url-destination.md)에서 소셜 플랫폼의 [!UICONTROL Website] 대상 옵션을 선택해야 합니다. 소셜 플랫폼은 레퍼러 정보를 해당 플랫폼으로 보낼 때 마스크 처리를 해제해야 합니다. 이것은 대상 플랫폼/파트너가 레퍼러 [!DNL URL]에 있는 정보를 볼 수 있음을 의미합니다.

## 사전 요구 사항 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 세그먼트를 만듭니다. 새 대상에 할당할 준비가  [!DNL Facebook] 되었습니다. 다음은 [!DNL Audience Manager] UI에서 세그먼트](/help/using/features/segments/segment-builder.md)을 만드는 방법입니다.[
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) 버전 4.1.0 이상. 최신 버전 **[여기](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**&#x200B;를 다운로드합니다.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]여기에서 다운로드할 수 있는 버전 9.0 이상 **[](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 또는 [서버측 포워딩(SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)을 사용하여 데이터를 [!DNL Audience Manager]로 가져오는 경우 AppMeasurement 버전 2.12 이상을 사용해야 합니다. [분석 코드 관리자](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)를 사용하여 [!DNL AppMeasurement]을(를) 다운로드합니다.

[Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html)을 사용하여 3단계와 4단계의 라이브러리를 설치하거나 업그레이드하는 것이 좋습니다.

## 1단계 - [!DNL Audience Manager] {#step-1-create-facebook-destination}에 [!UICONTROL Facebook Destination] 만들기

[!DNL Audience Manager]에 새 [!UICONTROL URL Destination]을 만들고 이름을 [!DNL Facebook Website Custom Audiences]로 지정합니다. 대상을 만들 때 아래 설정을 사용하십시오. [URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 페이지를 참조할 수도 있습니다.

### 기본 정보

* **[!UICONTROL Category]**: 사용자 지정
* **[!UICONTROL Type]**: [!DNL URL]
* **[!UICONTROL Auto-fill Destination Mapping]** 확인란을 선택한 다음 **[!UICONTROL Segment ID]**&#x200B;을 선택합니다.

### [!UICONTROL Data Export Labels]

**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]** 옵션을 선택합니다.

>[!NOTE]
>
> 이 내보내기 레이블은 장치 그래프에서 파생된 제3자 데이터와 데이터가 세그먼트에 포함되지 않도록 합니다.

### 구성

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. [!UICONTROL URL Type] 옵션을 선택하면 [!DNL Facebook WCA] 픽셀을 실행할 때 [!DNL Audience Manager] 레퍼러 [!DNL URL] 정보가 표시되지 않습니다.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* **[!UICONTROL Base URL]** 및 **[!UICONTROL Secure URL]** 필드에 [!DNL Facebook WCA] 픽셀을 입력합니다.
* **[!UICONTROL Delimiter]**:  `,`

기본 [!DNL URL] 예:`https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

페이지에서 실행된 픽셀 예. 이 예는 ID가 3401321, 2993399, 3263410, 다음 세 개의 [!DNL Audience Manager] 세그먼트에 대해 자격이 있는 사용자를 보여줍니다.

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 매개 변수 | 설명 |
---------|----------|
| `id` | 대상 픽셀을 만들 때 [!DNL Facebook Ad Manager] 사용자 인터페이스에서 찾을 수 있는 [!DNL Facebook] 픽셀 ID. |
| `ev` | Event.     이 값은 픽셀이 사이트에서 실행되기 시작하면 [!DNL Facebook Ad Manager] 사용자 인터페이스에 표시됩니다. 자세한 내용은 [단계 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)의 [!UICONTROL Include] 항목을 참조하십시오. |
| `cd[segID]` | 사이트에서 픽셀이 시작되면 [!DNL Facebook Ad Manager] 사용자 인터페이스 내에 채워지기 시작하는 추가 매개 변수입니다. `segID` 또한 임의적입니다. |
| `%ALIAS%` | [!DNL Audience Manager] 매크로는 사이트 방문자가 받을 수 있는 [!DNL Audience Manager] [!UICONTROL segment] ID로 동적으로 대체되며 쉼표()로 구분됩니다. |

[!UICONTROL URL destination] 구성은 아래 이미지에 있어야 합니다.

![대상 구성](/help/using/integration/assets/facebook-wca.png)

[!UICONTROL destination]을(를) 저장합니다. 그런 다음 **세그먼트 매핑** 단계로 진행할 수 있습니다.

## 2단계 - 세그먼트 매핑 - 세그먼트를 대상 {#step-2-segment-mappings}에 매핑

[URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 워크플로우에서 해당 세그먼트를 새로 만든 [!UICONTROL destination]에 매핑합니다. 매핑 값이 [!DNL Audience Manager] [!UICONTROL segment ID]으로 자동 채워집니다.

해당하는 경우 종료 날짜를 입력하고, 종료 날짜가 없는 경우에는 비워 둡니다.

## 3단계 - [!DNL Facebook Ads Manager] {#step-3-create-audience} 내에 [!UICONTROL Audience] 만들기

[!DNL Facebook] 도움말 설명서에서 [웹 사이트 사용자 지정 대상 만들기](https://www.facebook.com/business/help/666509013483225)를 참조하십시오. 아래 표에서 [!UICONTROL Create Audience] 옵션을 선택합니다.

| 항목 | 설명 |
---------|----------|
| 웹 사이트 트래픽 | 사용자 지정 조합 |
| 포함 | <ul><li>**[!UICONTROL Event]** > **[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;을 선택합니다. 1단계에서 예제 픽셀에 있는 `ev` 매개 변수의 값입니다. 픽셀이 아직 실행되지 않은 경우 **[!UICONTROL Event]** 옵션 또는 **[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;은 [!DNL Facebook] 사용자 인터페이스에 표시되지 않을 수 있습니다.</li><li>매개 변수 추가:`segID`을 선택합니다.</li><li><p>**contains** 연산자를 선택합니다.</p><p>방문자가 여러 세그먼트를 사용할 자격이 있음을 고려할 때 픽셀 매개 변수에 [!UICONTROL segment IDs]이 여러 개 있을 수 있으므로 중요합니다. 같음(`=`) 연산자를 사용하면 방문자의 대상 자격이 주어지지 않을 수 있으며, 사용자는 더 낮은 볼륨을 관찰하게 됩니다.</p></li><li>값을 추가합니다.[!DNL Audience Manager] 세그먼트 ID를 입력합니다.</li></ul> |
| 새 조건 추가 | 선택적 설정입니다. |
| 마지막 부분에서 | 선택적 설정입니다. |
| 대상자 이름 | 이 대상에 추가 조건을 추가하지 않는 한 일관성을 위해 동일한 [!DNL Audience Manager] 세그먼트 이름을 사용하는 것이 좋습니다. |

## 4단계 - [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}의 [!UICONTROL Campaign]에 [!UICONTROL Audience]을(를) 할당합니다.

[!DNL Custom Audience]을(를) 만든 후 광고 캠페인에 할당합니다. 새 캠페인을 만들거나 기존 캠페인을 편집하면 새로 만든 대상이 [!DNL Facebook] 사용자 인터페이스에 표시됩니다. [!DNL Audience Manager]이(가) 세그먼트에 포함되어 있는 경우, 광고 캠페인은 사이트를 방문할 때 브라우저에서 픽셀이 불에 타는 사용자를 타깃팅합니다.

## 요약 {#summary}

[!DNL Audience Manager] 세그먼트를 [!DNL Facebook WCA] 대상에 할당했으므로 [!DNL Audience Manager]는 픽셀에 해당 세그먼트 ID가 있는 [!DNL Facebook WCA] 픽셀을 선택적으로 사용하여 [!DNL Facebook Audience]를 채웁니다. 이로 인해 [!DNL Facebook Audience]의 점진적 증가가 일어나므로 사이트의 해당 대상자에게 태그가 더 많이 실행됩니다.

>[!NOTE]
>
> 사용자가 [!DNL Audience Manager] 세그먼트를 벗어나는 경우, 현재 [!DNL Audience Manager]이 [!DNL Custom Audience]에서 사용자를 제거하도록 [!DNL Facebook]에게 알릴 방법이 없습니다.

