---
description: 이 페이지에서는 투명도가 향상된 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook에 보낼 목적으로 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 프로세스를 보여줍니다.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA 통합
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 3%

---

# [!DNL Facebook WCA] 통합 {#facebook-wca-integration}

이 페이지에서는 생성 프로세스를 보여줍니다 [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) 웹 기반 전송을 위한 픽셀 [!DNL Audience Manager] 대상 세그먼트 [!DNL Facebook]: 투명도가 향상된 온라인 광고 타깃팅용.

## 개요 {#overview}

[Facebook 웹 사이트 사용자 지정 대상(WCA)](https://www.facebook.com/business/help/449542958510885) 특정 페이지를 방문하거나 웹 사이트에서 특정 작업을 수행한 사람 목록을 만들 수 있습니다. [!DNL Audience Manager] 에서 활성화 사용 [!DNL WCA] 사용 [!DNL URL] 대상 - 웹 기반 대상을 로 보내도록 사용자 지정 픽셀 기반 통합을 구성할 수 있습니다. [!DNL Facebook] 타겟팅할 수 있습니다.

![Facebook WCA 통합](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 이 기능을 사용하려면 [!UICONTROL Website] 의 social platform 옵션을 대상 [URL 대상](/help/using/features/destinations/create-url-destination.md). 소셜 플랫폼에서는 레퍼러 정보가 플랫폼으로 전송될 때 마스크가 해제되어야 합니다. 즉, 대상 플랫폼/파트너가 레퍼러에서 정보를 볼 수 있습니다 [!DNL URL].

## 사전 요구 사항 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 세그먼트, 새 세그먼트에 할당할 준비 [!DNL Facebook] 대상. 여기 있습니다 [세그먼트를 만드는 방법](/help/using/features/segments/segment-builder.md) 에서 [!DNL Audience Manager] UI.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) 버전 4.1.0 이상. 최신 버전을 다운로드합니다 **[여기](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) 버전 9.0 이상에서 다운로드할 수 있습니다. **[여기](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 또는, [SSF(서버 측 전달)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 로 데이터를 가져옵니다. [!DNL Audience Manager]를 사용하려면 AppMeasurement 버전 2.12 이상을 사용해야 합니다. 다운로드 [!DNL AppMeasurement] 사용 [Analytics 코드 관리자](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

라이브러리를 3단계 및 4단계에서 설치하거나 [Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## 1단계 - 만들기 [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

새 만들기 [!UICONTROL URL Destination] in [!DNL Audience Manager] 이름을 지정합니다 [!DNL Facebook Website Custom Audiences]. 대상을 만들 때 아래 설정을 사용하십시오. 또한 [URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 페이지.

### 기본 정보

* **[!UICONTROL Category]**: 사용자 지정
* **[!UICONTROL Type]**: [!DNL URL]
* 을(를) 선택합니다 **[!UICONTROL Auto-fill Destination Mapping]** 확인란을 선택한 다음 **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

옵션을 선택합니다 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> 이 내보내기 레이블은 장치 그래프에서 파생된 데이터와 타사 데이터가 세그먼트에 포함되지 않도록 합니다.

### 구성

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 다음을 선택하여 [!UICONTROL URL Type] 옵션, [!DNL Audience Manager] 레퍼러를 가리지 않습니다 [!DNL URL] 실행 시 정보 [!DNL Facebook WCA] 픽셀.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 에서 **[!UICONTROL Base URL]** 및 **[!UICONTROL Secure URL]** 필드에 를 입력합니다. [!DNL Facebook WCA] 픽셀.
* **[!UICONTROL Delimiter]**: `,`

기본 [!DNL URL] 예: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

페이지에서 실행된 픽셀 예. 다음 예에서는 세 명 자격을 가진 사용자를 보여줍니다 [!DNL Audience Manager] 세그먼트(ID 3401321, 2993399, 3263410)

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 매개 변수 | 설명 |
|---------|----------|
| `id` | 사용자 [!DNL Facebook] 에서 찾을 수 있는 픽셀 ID [!DNL Facebook Ad Manager] 대상 픽셀을 만들 때 사용자 인터페이스를 사용합니다. |
| `ev` | Event.     이 값은 [!DNL Facebook Ad Manager] 픽셀이 사이트에서 실행되기 시작하면 사용자 인터페이스입니다. 자세한 내용은 [!UICONTROL Include] 항목 [3단계](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)를 참조하십시오. |
| `cd[segID]` | 추가 매개 변수는 [!DNL Facebook Ad Manager] 픽셀이 사이트에서 실행되기 시작하면 사용자 인터페이스입니다. `segID` 또한 임의적입니다. |
| `%ALIAS%` | An [!DNL Audience Manager] 매크로, 동적으로 [!DNL Audience Manager] [!UICONTROL segment] 사이트 방문자가 받을 ID를 쉼표로 구분하여 입력합니다 |

사용자 [!UICONTROL URL destination] 구성은 아래 이미지와 유사해야 합니다.

![대상 구성](/help/using/integration/assets/facebook-wca.png)

를 저장합니다 [!UICONTROL destination]. 그런 다음 **세그먼트 매핑** 단계.

## 2단계 - 세그먼트 매핑 - 대상에 세그먼트 매핑 {#step-2-segment-mappings}

에서 [URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 워크플로우에서 해당 세그먼트를 새로 만든 세그먼트에 매핑합니다 [!UICONTROL destination]. 매핑 값이 [!DNL Audience Manager] [!UICONTROL segment ID].

해당하는 경우 종료 일자를 입력하고, 종료 일자를 지정하지 않으면 종료 일자를 비워 둡니다.

## 3단계 - 만들기 [!UICONTROL Audience] within [!DNL Facebook Ads Manager] {#step-3-create-audience}

자세한 내용은 [웹 사이트 사용자 지정 대상 만들기](https://www.facebook.com/business/help/666509013483225) 에서 [!DNL Facebook] 도움말 설명서입니다. 을(를) 선택합니다 [!UICONTROL Create Audience] 아래 표에 있는 옵션:

| 항목 | 설명 |
|---------|----------|
| 웹 사이트 트래픽 | 사용자 지정 조합 |
| 포함 | <ul><li>선택 **[!UICONTROL Event]** > Select **[!UICONTROL Adobe-Audience-Manager-Segment]**. 이 값은 `ev` 매개 변수(1단계의 예제 픽셀)를 참조하십시오. 픽셀을 아직 실행하지 않은 경우 **[!UICONTROL Event]** 옵션 또는 **[!UICONTROL Adobe-Audience-Manager-Segment]** 에 나타나지 않을 수 있음 [!DNL Facebook] 사용자 인터페이스.</li><li>매개 변수 추가: 선택 `segID`.</li><li><p>을(를) 선택합니다 **다음 포함** 연산자를 사용할 수 있습니다.</p><p>방문자가 여러 세그먼트에 대한 자격이 있음을 고려할 때 여러 세그먼트가 있을 수 있으므로 중요합니다 [!UICONTROL segment IDs] 를 입력합니다. 다음과 같음(`=`) 연산자는 방문자에게 대상에 대한 자격을 부여할 수 없으며 더 낮은 볼륨을 관찰할 수 있습니다.</p></li><li>값 추가: 을(를) 입력합니다. [!DNL Audience Manager] 세그먼트 ID.</li></ul> |
| 새 조건 추가 | 선택적 설정입니다. |
| 마지막 | 선택적 설정입니다. |
| 대상 이름 | 동일한 항목을 사용하는 것이 좋습니다 [!DNL Audience Manager] 이 대상에 추가 조건을 추가하지 않는 한 일관성을 위한 세그먼트 이름입니다. |

## 4단계 - 할당 [!UICONTROL Audience] 변환 후 [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

만들기 후 [!DNL Custom Audience]를 광고 캠페인에 지정합니다. 새 캠페인을 만들거나 기존 캠페인을 편집하십시오. 그러면 새로 만든 대상이 [!DNL Facebook] 사용자 인터페이스. 광고 캠페인은 사이트를 방문할 때 브라우저에서 픽셀 화소가 발생하는 사용자를 타깃팅합니다(있는 경우) [!DNL Audience Manager] 세그먼트에 포함할 수 있습니다.

## 요약 {#summary}

이제, [!DNL Audience Manager] 세그먼트를 [!DNL Facebook WCA] 대상, [!DNL Audience Manager] 선택적으로 [!DNL Facebook WCA] 픽셀에서 각 세그먼트 ID로 지정된 세그먼트의 사용자에게 픽셀 값을 입력하여 [!DNL Facebook Audience]. 이것은 그 결과 [!DNL Facebook Audience] 사이트의 적용 가능한 대상자에게 태그가 더 많이 실행됩니다.

>[!NOTE]
>
> 사용자가 [!DNL Audience Manager] 세그먼트이면, 현재 [!DNL Audience Manager] 정보를 [!DNL Facebook] 에서 사용자를 제거하려면 [!DNL Custom Audience].
