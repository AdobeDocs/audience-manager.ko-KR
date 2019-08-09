---
description: 이 페이지에서는 향상된 투명도를 사용한 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook로 전송하기 위한 Facebook 웹 사이트 사용자 지정 대상 (WCA) 픽셀을 만드는 프로세스를 설명합니다.
seo-description: 이 페이지에서는 향상된 투명도를 사용한 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook로 전송하기 위한 Facebook 웹 사이트 사용자 지정 대상 (WCA) 픽셀을 만드는 프로세스를 설명합니다.
seo-title: Facebook WCA 통합
solution: Audience Manager
title: Facebook WCA 통합
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Facebook WCA 통합 {#facebook-wca-integration}

이 페이지에서는 향상된 투명도를 사용한 온라인 광고 타깃팅을 위해 웹 기반 Audience Manager 대상 세그먼트를 Facebook로 전송하기 위한 Facebook 웹 사이트 사용자 지정 대상 (WCA) 픽셀을 만드는 프로세스를 설명합니다.

## 개요 {#overview}

[Facebook 웹 사이트 사용자 지정](https://www.facebook.com/business/help/449542958510885) 대상자 (WCA) 에서는 웹 사이트에서 특정 페이지를 방문했거나 특정 작업을 수행한 사람들의 목록을 만들 수 있습니다. Audience Manager 에서는 URL 타겟을 사용하여 WCA에서 활성화를 활성화할 수 있습니다. 이 대상은 타깃팅을 위해 웹 기반 대상을 Facebook에 보내도록 사용자 지정 픽셀 기반 통합을 구성할 수 있습니다.

![Facebook WCA 통합](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> 이 기능을 사용하려면 [URL 대상의 소셜 플랫폼 대상 웹 사이트 대상을 선택해야](/help/using/features/destinations/create-url-destination.md)합니다. 소셜 플랫폼은 레퍼러 정보가 플랫폼으로 전송될 때 마스크되지 않도록 해야 합니다. 이는 대상 플랫폼/파트너가 레퍼러 URL에서 정보를 볼 수 있음을 의미합니다.

## 전제 조건 {#prerequisites}

1. Facebook 광고 계정
2. Audience Manager 세그먼트에 액세스하여 새 Facebook 대상에 할당할 수 있습니다. Audience [Manager UI에서 세그먼트를](/help/using/features/segments/segment-builder.md) 만드는 방법은 다음과 같습니다.
3. Adobe Experience Cloud ID 서비스 (ECID) 4.1.0 이상. 여기에서 최신 버전을 **[](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**&#x200B;다운로드하십시오.
4. 여기에서 다운로드할 수 있는 Audience Manager 데이터 통합 라이브러리 (DIL) 버전 9.0 **[이상](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 또는 SSF (서버 측 포워딩) 를 사용하여 [데이터를](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) Audience Manager로 가져오는 경우 appmeasurement 버전 2.12 이상을 사용해야 합니다. Analytics 코드 관리자를 사용하여 [appmeasurement를 다운로드합니다](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).

Adobe [Launch](https://docs.adobelaunch.com/) 또는 [Adobe 다이내믹 태그 관리를 사용하여 3 단계와 4 단계에서 라이브러리를 설치하거나 업그레이드하는 것이](https://marketing.adobe.com/resources/help/en_US/dtm/)좋습니다.

## 1 단계 - Audience Manager에서 Facebook 대상 만들기 {#step-1-create-facebook-destination}

Audience Manager에서 새 URL 대상을 만들고 이름을 Facebook 웹 사이트 사용자 지정 대상자로 지정합니다. 대상을 만들 때 아래 설정을 사용하십시오. URL [대상](/help/using/features/destinations/create-url-destination.md) 구성 페이지를 참조할 수도 있습니다.

**기본 정보**

* **카테고리**: 사용자 정의
* ****&#x200B;유형: URL
* 자동 채우기 **대상 매핑** 확인란을 선택한 다음 **세그먼트 ID**&#x200B;를 선택합니다.

**데이터 내보내기 레이블**

이 대상에서 개인 식별 정보 (PII) 와 조합을 활성화할 수 있는 옵션을 **선택합니다**.

>[!NOTE]
>
> 이 내보내기 레이블은 타사 데이터 및 장치 그래프에서 파생된 데이터가 세그먼트에 포함되지 않도록 합니다.

**구성**

* **URL 유형**: 소셜 플랫폼용 **웹 사이트 대상자를 선택합니다**. 이 URL 유형 옵션을 선택하면 Audience Manager에서 Facebook WCA 픽셀을 시작할 때 레퍼러 URL 정보를 가리지 않습니다.
* **일련화**: **활성화를**&#x200B;선택합니다.
* **기본 URL** 및 **보안 URL** 필드에 Facebook WCA 픽셀을 입력합니다.
* **구분 기호**: ,

기본 URL 예: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

페이지에서 실행된 예제 픽셀. 이 예에서는 ID 3401321, 2993399, 3263410를 사용하여 세 개의 Audience Manager 세그먼트를 자격을 부여하는 사용자를 보여줍니다.

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| 매개 변수 | 설명 |
---------|----------|
| `id` | 대상 픽셀을 만들 때 Facebook 광고 관리자 UI에서 찾을 수 있는 Facebook 픽셀 ID 입니다. |
| `ev` | 이벤트. 이것은 임의 값이며, 사이트에서 픽셀을 실행하기 시작하면 Facebook 광고 관리자 UI에 나타납니다. 자세한 내용은 3 단계에서 [포함 항목을 참조하십시오](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | 사이트에서 픽셀을 실행하기 시작하면 Facebook 광고 관리자 UI 내에 채워지는 추가 매개 변수. `segID` 도 임의적입니다. |
| `%ALIAS%` | 쉼표로 구분된 사이트 방문자가 자격을 갖춘 Audience Manager 세그먼트 ID로 동적으로 대체되는 Audience Manager 매크로 |

URL 대상 구성은 아래 이미지에서와 같아야 합니다.

![Destintion 구성](/help/using/integration/assets/facebook-wca.png)

대상을 저장합니다. 그런 다음 **세그먼트 매핑** 단계를 진행할 수 있습니다.

## 2 단계 - 세그먼트 매핑 - 세그먼트를 대상에 매핑 {#step-2-segment-mappings}

URL 대상 [구성](/help/using/features/destinations/create-url-destination.md#) 워크플로우에서 새로 만든 대상에 해당 세그먼트를 매핑합니다. 매핑 값이 Audience Manager 세그먼트 ID로 자동 채워집니다.

해당하는 경우 종료 날짜를 입력하고 종료 날짜는 비워 둡니다.

## 3 단계 - Facebook 광고 관리자 내에서 대상자 만들기 {#step-3-create-audience}

Facebook [도움말 설명서에서 웹 사이트 사용자 지정 대상자](https://www.facebook.com/business/help/666509013483225) 만들기를 참조하십시오. 아래 표에서 대상자 만들기 옵션을 선택합니다.


| 항목 | 설명 |
---------|----------|
| 웹 사이트 트래픽 | 사용자 지정 조합 |
| 포함 | <ul><li>**이벤트** &gt; **Adobe-Audience-Manager-Segment 선택을**&#x200B;선택합니다. 이것은 1 단계의 예제 픽셀에 있는 ev 매개 변수의 값이었습니다. 픽셀이 아직 실행되지 않은 경우 **이벤트** 옵션 또는 **Adobe-Audience-Manager-Segment** 가 Facebook UI에 나타나지 않을 수 있습니다.</li><li>매개 변수 추가: `segID`Select.</li><li><p>**포함** 연산자를 선택합니다.</p><p>방문자가 여러 세그먼트를 적용받을 수 있다는 점을 고려하면, 픽셀 매개 변수에는 여러 세그먼트 ID가 있을 수 있습니다. equals (=) 연산자를 사용하면 대상에 대한 방문자가 정규화되지 않을 수 있으며, 더 낮은 볼륨을 보게 됩니다.</p></li><li>값 추가: Audience Manager 세그먼트 ID를 입력합니다.</li></ul> |
| 새 조건 추가 | 선택적 설정입니다. |
| In the last | 선택적 설정입니다. |
| 대상자 이름 | 이 대상자에게 조건을 추가하는 것이 아니라면 동일한 Audience Manager 세그먼트 이름을 일관성을 위해 사용하는 것이 좋습니다. |

## 4 단계 - Facebook 광고 관리자에서 캠페인에 대상자 할당 {#step-4-assign-audience-to-campaign}

사용자 지정 대상을 만든 후 광고 캠페인에 할당합니다. 새 캠페인을 만들거나 기존 캠페인을 편집하면 새로 만든 대상이 Facebook UI에 나열됩니다. 광고 캠페인은 Audience Manager가 세그먼트에 포함되어 있는 경우 사이트를 방문할 때 브라우저에서 픽셀 화재가 발생한 사용자를 타깃팅합니다.

## 요약 {#summary}

이제 Audience Manager 세그먼트를 Facebook WCA 대상에 할당했으므로 Audience Manager는 해당 세그먼트 ID가 있는 지정된 세그먼트의 사용자에게 Facebook WCA 픽셀을 선택적으로 실행하여 Facebook 대상을 채웁니다. 이로 인해 Facebook 대상의 수가 점진적으로 증가하면서 해당 사이트에서 해당 사용자에게 태그가 더 많이 실행됩니다.

>[!NOTE]
>
> 사용자가 Audience Manager 세그먼트를 벗어나는 경우, 현재 Audience Manager가 Facebook를 사용자 지정 대상에서 제거하도록 알려주는 방법이 없습니다.

