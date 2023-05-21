---
description: 이 페이지에서는 투명도가 향상된 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook에 보낼 목적으로 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 프로세스를 보여 줍니다.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA 통합
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 8780083474d68717fe3bd4dc632d96da89929122
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 3%

---

# [!DNL Facebook WCA] 통합 {#facebook-wca-integration}

이 페이지는 작성 프로세스를 보여 줍니다. [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) 웹 기반 전송용 픽셀 [!DNL Audience Manager] 대상 세그먼트 [!DNL Facebook]투명도가 향상된 온라인 광고 타겟팅용 입니다.

## 개요 {#overview}

[Facebook 웹 사이트 사용자 지정 대상(WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) 을(를) 사용하면 웹 사이트에서 특정 페이지를 방문하거나 특정 작업을 수행한 사람의 목록을 만들 수 있습니다. [!DNL Audience Manager] 에서 활성화 활성화 활성화 [!DNL WCA] 사용 [!DNL URL] 대상: 사용자 지정 픽셀 기반 통합을 구성하여 웹 기반 대상을에 보낼 수 있습니다. [!DNL Facebook] 타깃팅용.

![Facebook WCA 통합](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 이 기능을 사용하려면 다음을 선택해야 합니다. [!UICONTROL Website] 의 소셜 플랫폼 대상 옵션 [URL 대상](/help/using/features/destinations/create-url-destination.md). 소셜 플랫폼을 사용하려면 해당 플랫폼으로 전송할 때 레퍼러 정보가 마스크 해제되어야 합니다. 이는 대상 플랫폼/파트너가 레퍼러에서 정보를 볼 수 있음을 의미합니다 [!DNL URL].

## 사전 요구 사항 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] 세그먼트, 새 사용자에게 할당할 준비 완료 [!DNL Facebook] 대상. 여기 있습니다 [세그먼트를 만드는 방법](/help/using/features/segments/segment-builder.md) 다음에서 [!DNL Audience Manager] UI.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) 버전 4.1.0 이상 최신 버전 다운로드 **[여기](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) 버전 9.0 이상, 다운로드 가능 **[여기](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 또는 다음을 사용하는 경우 [SSF(서버측 전달)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 데이터를 로 가져오기 [!DNL Audience Manager], AppMeasurement 버전 2.12 이상을 사용해야 합니다. 다운로드 [!DNL AppMeasurement] 사용 [Analytics 코드 관리자](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

다음을 사용하여 3단계와 4단계의 라이브러리를 설치하거나 업그레이드하는 것이 좋습니다. [Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## 1단계 - 만들기 [!UICONTROL Facebook Destination] 위치: [!DNL Audience Manager] {#step-1-create-facebook-destination}

새로 만들기 [!UICONTROL URL Destination] 위치: [!DNL Audience Manager] 이름을 지정합니다. [!DNL Facebook Website Custom Audiences]. 대상을 만들 때 아래 설정을 사용하십시오. 다음을 참조할 수도 있습니다. [URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 페이지를 가리키도록 업데이트하는 중입니다.

### 기본 정보

* **[!UICONTROL Category]**: 사용자 지정
* **[!UICONTROL Type]**: [!DNL URL]
* 다음 항목 선택 **[!UICONTROL Auto-fill Destination Mapping]** 확인란을 선택한 다음 을 선택합니다 **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

옵션 선택 **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> 이 내보내기 레이블은 타사 데이터 및 장치 그래프에서 파생된 데이터가 세그먼트에 포함되지 않도록 합니다.

### 구성

* **[!UICONTROL URL type]**: Select **[!UICONTROL Website audience for social platforms]**. 다음을 선택: [!UICONTROL URL Type] 옵션, [!DNL Audience Manager] 는 레퍼러를 가리지 않습니다 [!DNL URL] 을(를) 실행할 때의 정보 [!DNL Facebook WCA] 픽셀.
* **[!UICONTROL Serialize]**: Select **[!UICONTROL Enable]**.
* 다음에서 **[!UICONTROL Base URL]** 및 **[!UICONTROL Secure URL]** 필드에 [!DNL Facebook WCA] 픽셀.
* **[!UICONTROL Delimiter]**: `,`

기본 [!DNL URL] 예: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

페이지에서 실행된 예제 픽셀입니다. 이 예는 3개 자격이 있는 사용자를 보여 줍니다 [!DNL Audience Manager] 세그먼트, ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 매개 변수 | 설명 |
|---------|----------|
| `id` | 사용자 [!DNL Facebook] 픽셀 ID, 다음에서 찾을 수 있습니다. [!DNL Facebook Ad Manager] 대상 픽셀을 생성할 때 사용자 인터페이스 |
| `ev` | Event. 이 값은 다음에 나타날 임의의 값입니다. [!DNL Facebook Ad Manager] 사용자 인터페이스 픽셀이 사이트에서 실행되기 시작하면 다음을 참조하십시오. [!UICONTROL Include] 의 항목 [3단계](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)를 참조하십시오. |
| `cd[segID]` | 에서 채워지기 시작하는 추가 매개변수 [!DNL Facebook Ad Manager] 사용자 인터페이스 픽셀이 사이트에서 실행되기 시작하면 `segID` 또한 임의적입니다. |
| `%ALIAS%` | An [!DNL Audience Manager] 매크로입니다. 매크로는 동적으로 [!DNL Audience Manager] [!UICONTROL segment] 사이트 방문자가 사용할 수 있는 ID이며, 쉼표로 구분됩니다. |

사용자 [!UICONTROL URL destination] 구성은 아래 이미지와 같아야 합니다.

![대상 구성](/help/using/integration/assets/facebook-wca.png)

저장 [!UICONTROL destination]. 그런 다음 로 진행할 수 있습니다. **세그먼트 매핑** 단계.

## 2단계 - 세그먼트 매핑 - 세그먼트를 대상에 매핑 {#step-2-segment-mappings}

다음에서 [URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 워크플로우, 적용 가능한 세그먼트를 새로 만든 항목에 매핑 [!UICONTROL destination]. 매핑 값이 로 자동 채워집니다. [!DNL Audience Manager] [!UICONTROL segment ID].

해당하는 경우 종료 일자를 입력하고, 그렇지 않은 경우 종료 일자가 없는 경우 공백으로 두십시오.

## 3단계 - 만들기 [!UICONTROL Audience] 다음 범위 내 [!DNL Facebook Ads Manager] {#step-3-create-audience}

다음을 참조하십시오 [웹 사이트 사용자 지정 대상 만들기](https://www.facebook.com/business/help/666509013483225) 다음에서 [!DNL Facebook] 도움말 문서. 다음 항목 선택 [!UICONTROL Create Audience] 아래 표의 옵션:

| 항목 | 설명 |
|---------|----------|
| 웹 사이트 트래픽 | 사용자 정의 조합 |
| 포함 | <ul><li>선택 **[!UICONTROL Event]** > 선택 **[!UICONTROL Adobe-Audience-Manager-Segment]**. 이 값은 `ev` 1단계의 예제 픽셀에 있는 매개 변수입니다. 픽셀이 아직 실행되지 않은 경우 **[!UICONTROL Event]** 옵션 또는 **[!UICONTROL Adobe-Audience-Manager-Segment]** 에는 나타나지 않을 수 있습니다. [!DNL Facebook] 사용자 인터페이스.</li><li>매개 변수 추가: 선택 `segID`.</li><li><p>다음 항목 선택 **다음 포함** 연산자.</p><p>이는 방문자가 여러 세그먼트에 대한 자격이 될 수 있고 여러 개가 있을 수 있음을 고려하여 중요합니다 [!UICONTROL segment IDs] 픽셀 매개 변수 같음 사용(`=`) 연산자는 방문자에게 대상을 제공할 수 없으며 낮은 볼륨을 관찰하게 됩니다.</p></li><li>값 추가: [!DNL Audience Manager] 세그먼트 ID.</li></ul> |
| 새 상태 추가 | 선택적 설정입니다. |
| 마지막 | 선택적 설정입니다. |
| 대상자 이름 | 동일한 옵션을 사용하는 것이 좋습니다. [!DNL Audience Manager] 이 대상에 추가 조건을 추가하지 않는 한 일관성을 위해 세그먼트 이름을 사용하십시오. |

## 4단계 - 할당 [!UICONTROL Audience] (으)로 [!UICONTROL Campaign] 위치: [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

를 만든 후 [!DNL Custom Audience]을(를) 통해 광고 캠페인에 할당합니다. 새 캠페인을 만들거나 기존 캠페인을 편집하면 새로 만든 대상자가 [!DNL Facebook] 사용자 인터페이스. 광고 캠페인은 다음과 같은 경우 사이트를 방문할 때 브라우저에서 픽셀 불이 발생하는 것을 본 사용자를 타겟팅합니다 [!DNL Audience Manager] 세그먼트에 포함합니다.

## 요약 {#summary}

을(를) 할당했으므로 [!DNL Audience Manager] 세그먼트를 다음에 [!DNL Facebook WCA] 대상, [!DNL Audience Manager] 을(를) 선택적으로 실행합니다. [!DNL Facebook WCA] 픽셀에서 해당 세그먼트 ID를 사용하여 주어진 세그먼트의 사용자에게 픽셀 을 [!DNL Facebook Audience]. 이렇게 하면 다음이 점차적으로 증가합니다. [!DNL Facebook Audience] 더 많은 태그가 사이트의 해당 대상자에게 실행됩니다.

>[!NOTE]
>
> 사용자가 다음에서 제외되는 경우 [!DNL Audience Manager] 세그먼트, 현재에 대한 방법은 없습니다. [!DNL Audience Manager] 알리다 [!DNL Facebook] 에서 사용자를 제거하려면 [!DNL Custom Audience].
