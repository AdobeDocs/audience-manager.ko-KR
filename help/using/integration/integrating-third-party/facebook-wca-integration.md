---
description: 이 페이지에서는 투명도가 향상된 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook에 보낼 목적으로 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 프로세스를 보여 줍니다.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA 통합
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# [!DNL Facebook WCA] 통합 {#facebook-wca-integration}

이 페이지에서는 투명도가 향상된 온라인 광고 타깃팅을 위해 웹 기반 [!DNL Audience Manager] 대상 세그먼트를 [!DNL Facebook]에 보낼 목적으로 [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) 픽셀을 만드는 프로세스를 보여 줍니다.

>[!IMPORTANT]
>
>이는 Audience Manager과 Facebook 간에 제품화된 통합이 아닙니다.

## 개요 {#overview}

[Facebook 웹 사이트 사용자 지정 대상(WCA)](https://www.facebook.com/business/help/610516375684216?id=2469097953376494)을 사용하면 웹 사이트에서 특정 페이지를 방문하거나 특정 작업을 수행한 사용자의 목록을 만들 수 있습니다. [!DNL Audience Manager]을(를) 사용하면 [!DNL URL]개의 대상을 사용하여 [!DNL WCA]에서 활성화할 수 있습니다. 이 대상을 통해 사용자 지정 픽셀 기반 통합을 구성하여 타깃팅을 위해 웹 기반 대상을 [!DNL Facebook]에 보낼 수 있습니다.

![Facebook WCA 통합](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 이 기능을 사용하려면 [URL 대상](/help/using/features/destinations/create-url-destination.md)에서 소셜 플랫폼에 대한 [!UICONTROL Website] 대상을 선택해야 합니다. 소셜 플랫폼을 사용하려면 해당 플랫폼으로 전송할 때 레퍼러 정보가 마스크 해제되어야 합니다. 이는 대상 플랫폼/파트너가 레퍼러 [!DNL URL]에서 정보를 볼 수 있음을 의미합니다.

## 전제 조건 {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager]개 세그먼트, 새 [!DNL Facebook] 대상에 할당할 준비가 되었습니다. 다음은 [!DNL Audience Manager] UI에서 [세그먼트를 만드는 방법](/help/using/features/segments/segment-builder.md)입니다.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) 버전 4.1.0 이상 최신 버전 **[여기](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**&#x200B;를 다운로드하십시오.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) 버전 9.0 이상, **[여기](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;에서 다운로드할 수 있습니다. 또는 [SSF(서버측 전달)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=ko)을 사용하여 데이터를 [!DNL Audience Manager] (으)로 가져오는 경우 AppMeasurement 버전 2.12 이상을 사용해야 합니다. [Analytics 코드 관리자](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=ko)를 사용하여 [!DNL AppMeasurement]을(를) 다운로드합니다.

[Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ko)를 사용하여 3단계와 4단계의 라이브러리를 설치하거나 업그레이드하는 것이 좋습니다.

## 1단계 - [!DNL Audience Manager]에 [!UICONTROL Facebook Destination] 만들기 {#step-1-create-facebook-destination}

[!DNL Audience Manager]에 새 [!UICONTROL URL Destination]을(를) 만들고 이름을 [!DNL Facebook Website Custom Audiences]로 지정합니다. 대상을 만들 때 아래 설정을 사용하십시오. [URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 페이지를 참조할 수도 있습니다.

### 기본 정보

* **[!UICONTROL Category]**: 사용자 지정
* **[!UICONTROL Type]**: [!DNL URL]
* **[!UICONTROL Auto-fill Destination Mapping]** 확인란을 선택한 다음 **[!UICONTROL Segment ID]**&#x200B;을(를) 선택합니다.

### [!UICONTROL Data Export Labels]

**[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]** 옵션을 선택하십시오.

>[!NOTE]
>
> 이 내보내기 레이블은 타사 데이터 및 장치 그래프에서 파생된 데이터가 세그먼트에 포함되지 않도록 합니다.

### 구성

* **[!UICONTROL URL type]**: **[!UICONTROL Website audience for social platforms]** 선택. 이 [!UICONTROL URL Type] 옵션을 선택하면 [!DNL Audience Manager]이(가) [!DNL Facebook WCA] 픽셀을 실행할 때 레퍼러 [!DNL URL] 정보를 가리지 않습니다.
* **[!UICONTROL Serialize]**: **[!UICONTROL Enable]** 선택.
* **[!UICONTROL Base URL]** 및 **[!UICONTROL Secure URL]** 필드에 [!DNL Facebook WCA] 픽셀을 입력합니다.
* **[!UICONTROL Delimiter]**: `,`

기본 [!DNL URL] 예: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

페이지에서 실행된 예제 픽셀입니다. 다음 예에서는 ID가 3401321, 2993399, 3263410인 세 개의 [!DNL Audience Manager] 세그먼트에 대한 자격이 있는 사용자를 보여 줍니다.

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| 매개 변수 | 설명 |
|---------|----------|
| `id` | 대상 픽셀을 만들 때 [!DNL Facebook Ad Manager] 사용자 인터페이스에 있는 [!DNL Facebook] 픽셀 ID입니다. |
| `ev` | 이벤트. 임의의 값으로, 사이트에서 픽셀이 실행되기 시작하면 [!DNL Facebook Ad Manager] 사용자 인터페이스에 표시됩니다. 자세한 내용은 [3단계](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)에서 [!UICONTROL Include] 항목을 참조하십시오. |
| `cd[segID]` | 추가 매개 변수. 픽셀이 사이트에서 실행되기 시작하면 [!DNL Facebook Ad Manager] 사용자 인터페이스 내에서 채워집니다. `segID`도 임의 요소입니다. |
| `%ALIAS%` | 사이트 방문자가 사용할 수 있는 [!DNL Audience Manager] [!UICONTROL segment] ID로 동적으로 대체되는 [!DNL Audience Manager] 매크로는 쉼표로 구분됩니다. |

[!UICONTROL URL destination] 구성은 아래 그림과 같아야 합니다.

![대상 구성](/help/using/integration/assets/facebook-wca.png)

[!UICONTROL destination] 저장. 그런 다음 **세그먼트 매핑** 단계로 진행할 수 있습니다.

## 2단계 - 세그먼트 매핑 - 세그먼트를 대상에 매핑 {#step-2-segment-mappings}

[URL 대상 구성](/help/using/features/destinations/create-url-destination.md) 워크플로에서 해당 세그먼트를 새로 만든 [!UICONTROL destination]에 매핑합니다. 매핑 값이 [!DNL Audience Manager] [!UICONTROL segment ID] (으)로 자동 채워집니다.

해당하는 경우 종료 일자를 입력하고, 그렇지 않은 경우 종료 일자가 없는 경우 공백으로 두십시오.

## 3단계 - [!DNL Facebook Ads Manager] 내에 [!UICONTROL Audience] 만들기 {#step-3-create-audience}

[!DNL Facebook] 도움말 설명서에서 [웹 사이트 사용자 지정 대상 만들기](https://www.facebook.com/business/help/666509013483225)를 참조하십시오. 아래 표에서 [!UICONTROL Create Audience] 옵션을 선택하십시오.

| 항목 | 설명 |
|---------|----------|
| 웹 사이트 트래픽 | 사용자 정의 조합 |
| 포함 | <ul><li>**[!UICONTROL Event]** > **[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;을(를) 선택합니다. 1단계의 예제 픽셀에서 `ev` 매개 변수의 값입니다. 픽셀이 아직 실행되지 않은 경우 **[!UICONTROL Event]** 옵션 또는 **[!UICONTROL Adobe-Audience-Manager-Segment]**&#x200B;이(가) [!DNL Facebook] 사용자 인터페이스에 나타나지 않을 수 있습니다.</li><li>매개 변수 추가: `segID`을(를) 선택합니다.</li><li><p>**포함** 연산자를 선택하십시오.</p><p>방문자가 여러 세그먼트를 사용할 수 있는 경우 픽셀 매개 변수에 [!UICONTROL segment IDs]이(가) 여러 개 있을 수 있으므로 이 작업이 중요합니다. equals (`=`) 연산자를 사용하면 방문자를 대상에 한정하지 않을 수 있으므로 더 낮은 볼륨을 관찰하게 됩니다.</p></li><li>값 추가: [!DNL Audience Manager] 세그먼트 ID를 입력합니다.</li></ul> |
| 새 상태 추가 | 선택적 설정입니다. |
| 마지막 | 선택적 설정입니다. |
| 대상자 이름 | 이 대상에 조건을 추가하지 않는 한 일관성을 위해 동일한 [!DNL Audience Manager] 세그먼트 이름을 사용하는 것이 좋습니다. |

## 4단계 - [!DNL Facebook Ads Manager]의 [!UICONTROL Campaign]에 [!UICONTROL Audience] 할당 {#step-4-assign-audience-to-campaign}

[!DNL Custom Audience]을(를) 만든 후 광고 캠페인에 지정하십시오. 새 캠페인을 만들거나 기존 캠페인을 편집하면 새로 만든 대상자가 [!DNL Facebook] 사용자 인터페이스에 나열됩니다. [!DNL Audience Manager]이(가) 세그먼트에 포함할 경우 광고 캠페인은 사이트를 방문할 때 브라우저에서 픽셀 실행 횟수를 본 사용자를 타겟팅합니다.

## 요약 {#summary}

[!DNL Audience Manager] 세그먼트를 [!DNL Facebook WCA] 대상에 할당했으므로 [!DNL Audience Manager]이(가) 해당 세그먼트의 사용자에게 해당 픽셀의 해당 세그먼트 ID로 [!DNL Facebook WCA] 픽셀을 선택적으로 실행하여 [!DNL Facebook Audience]을(를) 채웁니다. 이렇게 하면 사이트의 해당 대상자에게 태그가 더 많이 실행될수록 [!DNL Facebook Audience]이(가) 점차적으로 증가합니다.

>[!NOTE]
>
> 사용자가 [!DNL Audience Manager] 세그먼트에서 벗어나는 경우 현재 [!DNL Audience Manager]에서 [!DNL Facebook]에게 알려 [!DNL Custom Audience]에서 사용자를 제거할 수 있는 방법이 없습니다.
>
