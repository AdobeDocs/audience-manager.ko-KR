---
description: 이 페이지에서는 향상된 투명도를 통해 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook으로 전송하는 목적으로 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 프로세스를 보여줍니다.
seo-description: 이 페이지에서는 향상된 투명도를 통해 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook으로 전송하는 목적으로 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 프로세스를 보여줍니다.
seo-title: Facebook WCA 통합
solution: Audience Manager
title: Facebook WCA 통합
translation-type: tm+mt
source-git-commit: 28d1292140a56cf1627a8921876d9483221876ca

---


# Facebook WCA 통합 {#facebook-wca-integration}

이 페이지에서는 향상된 투명도를 통해 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook으로 전송하는 목적으로 Facebook 웹 사이트 사용자 지정 대상(WCA) 픽셀을 만드는 프로세스를 보여줍니다.

## 개요 {#overview}

[Facebook 웹 사이트 사용자 지정 대상자(WCA)](https://www.facebook.com/business/help/449542958510885) 를 사용하면 특정 페이지를 방문했거나 웹 사이트에서 특정 작업을 수행한 사람들의 목록을 만들 수 있습니다. Audience Manager를 사용하면 URL 대상을 사용하여 WCA에서 활성화할 수 있습니다. 이 URL은 타깃팅을 위해 웹 기반 고객을 Facebook으로 보내도록 사용자 정의 픽셀 기반 통합을 구성할 수 있습니다.

![Facebook WCA 통합](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 이 기능을 사용하려면 URL 대상의 소셜 플랫폼용 웹 사이트 대상자를 선택해야 [합니다](/help/using/features/destinations/create-url-destination.md). 소셜 플랫폼은 레퍼러 정보를 플랫폼으로 보낼 때 마스크가 해제되어야 합니다. 이것은 대상 플랫폼/파트너가 레퍼러 URL에서 정보를 볼 수 있음을 의미합니다.

## 전제 조건 {#prerequisites}

1. Facebook 광고 계정
2. Audience Manager 세그먼트를 새 Facebook 대상에 할당할 준비가 되었습니다. 다음은 Audience Manager UI에서 세그먼트를 [만드는](/help/using/features/segments/segment-builder.md) 방법입니다.
3. Adobe Experience Cloud ID Service(ECID) 버전 4.1.0 이상 최신 버전을 **[여기에서](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**&#x200B;다운로드하십시오.
4. DIL(Audience Manager Data Integration Library) 버전 9.0 이상, **[여기에서](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;다운로드할 수 있습니다. 또는 SSF [를 사용하여 데이터를 Audience Manager로](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) 가져오는 경우 AppMeasurement 버전 2.12 이상을 사용해야 합니다. Analytics 코드 관리자를 사용하여 [AppMeasurement를 다운로드합니다](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

Adobe Launch 또는 Adobe 다이내믹 태그 관리를 사용하여 3단계와 4단계의 라이브러리를 [설치하거나](https://docs.adobelaunch.com/) 업그레이드하는 [것이 좋습니다](https://marketing.adobe.com/resources/help/en_US/dtm/).

## 1단계 - Audience Manager에서 Facebook 대상 만들기 {#step-1-create-facebook-destination}

Audience Manager에서 새 URL 대상을 만들고 Facebook 웹 사이트 사용자 지정 대상의 이름을 지정합니다. 대상을 만들 때 아래 설정을 사용하십시오. URL 대상 구성 [페이지를 참조할 수도](/help/using/features/destinations/create-url-destination.md) 있습니다.

**기본 정보**

* **카테고리**:사용자 지정
* **유형**:URL
* 대상 **매핑 자동 채우기** 확인란을 선택한 다음 세그먼트 ID를 **선택합니다**.

**데이터 내보내기 레이블**

이 대상은 **개인 식별 정보(PII)와**&#x200B;결합할 수 있음 옵션을 선택합니다.

>[!NOTE]
>
> 이 내보내기 레이블은 장치 그래프에서 파생된 데이터와 타사 데이터가 세그먼트에 포함되지 않도록 합니다.

**구성**

* **URL 유형**:소셜 **플랫폼의**&#x200B;웹 사이트 대상자를 선택합니다. 이 URL 유형 옵션을 선택하면 Audience Manager가 Facebook WCA 픽셀을 실행할 때 레퍼러 URL 정보를 가리지 않습니다.
* **일련화**:활성화를 **선택합니다**.
* 기본 **URL** 및 **보안 URL** 필드에 Facebook WCA 픽셀을 입력합니다.
* **구분 기호**: ,

기본 URL 예: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

페이지에서 실행된 픽셀의 예. 이 예에서는 ID가 3401321, 2993399, 3263410인 세 개의 Audience Manager 세그먼트를 자격을 갖춘 사용자를 보여줍니다.

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 매개 변수 | 설명 |
---------|----------|
| `id` | 대상 픽셀을 만들 때 Facebook 광고 관리자 UI에서 찾을 수 있는 Facebook 픽셀 ID입니다. |
| `ev` | 이벤트. 이 값은 임의의 값으로, 사이트에서 픽셀이 시작되면 Facebook 광고 관리자 UI에 나타납니다. 자세한 내용은 3단계의 [항목](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)포함을 참조하십시오. |
| `cd[segID]` | 사이트에서 픽셀이 실행되기 시작하면 Facebook 광고 관리자 UI 내에 채워지기 시작하는 추가 매개 변수입니다. `segID` 또한 임의 |
| `%ALIAS%` | Audience Manager 매크로. 이 매크로는 사이트 방문자가 자격을 얻은 Audience Manager 세그먼트 ID로 동적으로 대체되며, 쉼표로 구분됩니다. |

URL 대상 구성은 아래 이미지와 같아야 합니다.

![대상 구성](/help/using/integration/assets/facebook-wca.png)

대상을 저장합니다. 그런 다음 세그먼트 매핑 **단계로 진행할 수** 있습니다.

## 2단계 - 세그먼트 매핑 - 세그먼트를 대상에 매핑 {#step-2-segment-mappings}

URL [대상](/help/using/features/destinations/create-url-destination.md) 구성 워크플로우에서 해당 세그먼트를 새로 만든 대상에 매핑합니다. 매핑 값이 Audience Manager 세그먼트 ID로 자동 채워집니다.

종료 날짜를 입력합니다(해당하는 경우). 종료 날짜가 없으면 비워 둡니다.

## 3단계 - Facebook 광고 관리자에서 대상자 만들기 {#step-3-create-audience}

Facebook [도움말 문서에서 웹 사이트](https://www.facebook.com/business/help/666509013483225) 사용자 지정 대상 만들기를 참조하십시오. 아래 표에서 대상자 만들기 옵션을 선택합니다.


| 항목 | 설명 |
---------|----------|
| 웹 사이트 트래픽 | 사용자 지정 조합 |
| 포함 | <ul><li>이벤트 **** &gt; Adobe- **Audience-Manager-세그먼트 선택을 선택합니다**. 1단계에서 예제 픽셀에 있는 ev 매개 변수의 값입니다. 픽셀을 아직 실행하지 않은 경우 이벤트 **옵션** 또는 **Adobe-Audience-Manager-** Segment가 FacebookUI에 나타나지 않을 수 있습니다.</li><li>매개 변수 추가:을 `segID`선택합니다.</li><li><p>포함 **연산자를 선택합니다** .</p><p>방문자가 여러 세그먼트를 사용할 수 있음을 고려할 때 픽셀 매개 변수에 여러 개의 세그먼트 ID가 있을 수 있으므로 중요합니다. 같음(=) 연산자를 사용하면 방문자가 대상에 적합하지 않을 수 있으며, 사용자는 더 낮은 볼륨을 관찰할 수 있습니다.</p></li><li>값 추가:Audience Manager 세그먼트 ID를 입력합니다.</li></ul> |
| 새 조건 추가 | 선택적 설정입니다. |
| 마지막 | 선택적 설정입니다. |
| 대상 이름 | 이 대상에 추가 조건을 추가하지 않는 한 일관성을 위해 동일한 Audience Manager 세그먼트 이름을 사용하는 것이 좋습니다. |

## 4단계 - Facebook 광고 관리자에서 캠페인에 대상 할당 {#step-4-assign-audience-to-campaign}

사용자 지정 대상을 만든 후 광고 캠페인에 할당합니다. 새 캠페인을 만들거나 기존 캠페인을 편집하면 Facebook UI에 새로 만든 대상이 나열됩니다. Audience Manager가 세그먼트에 포함하는 경우, 광고 캠페인은 사이트를 방문할 때 브라우저에서 픽셀 화재를 본 사용자를 타깃팅합니다.

## 요약 {#summary}

이제 Audience Manager 세그먼트를 Facebook WCA 대상에 지정했으므로 Audience Manager는 Facebook WCA 픽셀을 해당 세그먼트 ID로 지정된 세그먼트 사용자에게 선택적으로 실행하여 Facebook 대상을 채웁니다. 이로 인해 Facebook 사용자의 수가 점차적으로 증가하면 사이트의 해당 대상자에게 태그가 더 많이 실행됩니다.

>[!NOTE]
>
> 사용자가 Audience Manager 세그먼트를 벗어나는 경우, 현재 Audience Manager가 Facebook에 사용자 지정 대상으로부터 사용자를 제거하도록 알릴 수 있는 방법이 없습니다.

