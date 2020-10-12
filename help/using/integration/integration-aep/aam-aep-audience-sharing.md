---
description: 이 문서에서는 Audience Manager과 Adobe Experience Platform 사이에 대상이 공유되는 방식을 설명합니다.
seo-description: 이 문서에서는 Audience Manager과 Adobe Experience Platform 사이에 대상이 공유되는 방식을 설명합니다.
seo-title: Audience Manager와 Adobe Experience Platform 간의 대상 공유
solution: Audience Manager
title: Audience Manager와 Adobe Experience Platform 간의 대상 공유
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 6a9a48aa6d3a7a5d871ea9aabbca2c2ec1229c0e
workflow-type: tm+mt
source-wordcount: '1492'
ht-degree: 2%

---


# Audience Manager 및 기타 Experience Cloud 솔루션과 Experience Platform 세그먼트 공유 {#aam-aep-audience-sharing}

>[!NOTE]
>
> 이 기능에 대한 액세스 권한을 부여하려면 Adobe 영업 담당자에게 문의하십시오.

## 개요 {#overview}

Audience Manager과 Adobe Experience Platform 간의 대상 공유 기능을 사용하면 Audience Manager 특성과 세그먼트를 Adobe Experience Platform과 공유할 수 있고 그 반대의 경우도 가능합니다. Audience Manager [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) 와 Adobe Experience Platform 간에 고객 공유를 사용하려면

Experience Platform의 Audience Manager 트레이트 및 세그먼트를 사용하여 고객 프로필에 Audience Manager 데이터를 추가하고 Experience Platform [세분화 서비스를 활용할 수 있습니다](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md).

Audience Manager에서는 다음과 같은 데이터 관리 플랫폼 사용 사례에 Experience Platform 세그먼트를 사용할 수 있습니다.
* 세그먼트에 [타사 데이터](/help/using/overview/data-types-collected.md#third-party-data) 추가;
* [알고리즘 모델링](/help/using/features/algorithmic-models/understanding-models.md);
* Experience Platform [대상 카탈로그에서 아직 지원되지 않는 대상에 세그먼트를 활성화합니다](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

또한 Experience Platform 세그먼트는 [핵심 서비스를 통해 다른 Experience Cloud 솔루션에 공유됩니다](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * 위에 언급된 데이터 관리 플랫폼 사용 사례를 활성화하려면 Audience Manager 라이선스가 필요합니다.
> * 핵심 서비스 통합을 통해 Experience Platform 세그먼트를 Adobe Ad Cloud, Adobe Target, 마케팅 및 기타 Experience Cloud 솔루션과 공유하기 위해 Audience Manager 라이선스가 필요하지 *않습니다* .


<br> 

대상 공유 사용 사례에 대한 개요는 아래 표를 참조하십시오.

| **사용 사례** | **Adobe Experience Platform** | **Audience Manager** | **핵심 서비스** |
---------|----------|---------|---------
| **대상 공유** | <ul><li>Audience Manager 데이터로 고객 프로파일 강화</li><li>Experience Platform 세그멘테이션에서 Audience Manager 데이터 사용</li></ul> | <ul><li>세그먼트에 타사 데이터 추가</li><li>알고리즘 모델링</li><li>추가 대상에 대한 활성화</li></ul> | Adobe Target, Ad Cloud 또는 Marketing과 같은 다른 Experience Cloud 솔루션에서 Experience Platform 세그먼트를 사용합니다. |

<br> 

## Adobe Experience Platform의 Audience Manager 세그먼트 및 트레이트 {#aam-segments-traits-in-aep}

Audience Manager 트레이트 및 세그먼트는 세그먼트 워크플로우에서 **대상으로 Experience Platform에** 표시됩니다. Experience Platform의 Audience Manager 세그먼트 및 트레이트에 대한 자세한 내용은 다음을 참조하십시오.

* [세그멘테이션 서비스 개요](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Experience Platform 세그먼트 빌더 사용 안내서](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager 커넥터](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Audience Manager의 Adobe Experience Platform 세그먼트 {#aep-segments-in-aam}

Experience Platform에서 만드는 세그먼트는 다음 컴포지션 규칙을 사용하여 Audience Manager 인터페이스에 신호, 트레이트 및 세그먼트로 나타납니다.

* 신호:각 Experience Platform 세그먼트에 대해 양식에서 신호를 볼 수 있습니다 `segID = segment ID`.
* 특성:특성 규칙은 Experience Platform 세그먼트의 ID입니다.
* 세그먼트:세그먼트는 위에서 설명한 트레이트로 구성됩니다.

### 신호 {#aep-segments-as-aam-signals}

Experience Platform **[!UICONTROL Audience Data > Signals > General Online Data]** 에서 들어오는 신호를 `SegId` 찾으려면 다음을 선택하여 검색합니다. 디버깅을 위해 이 화면을 사용하여 Experience Platform과 Audience Manager 간 통합이 올바르게 설정되어 있는지 확인할 수 있습니다.

![신호 대시보드의 Audience Manager에서 Experience Platform 신호 보기](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### 트레이트 {#aep-segments-as-aam-traits}

Audience Manager은 트레이트 저장소에 **Experience Platform 트레이트라는** 특성 폴더를 자동으로 만듭니다.

![Experience Platform 대시보드의 트레이트](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

다른 트레이트와 함께 세그먼트에 자동으로 생성된 트레이트를 사용할 수 있습니다. 예를 들어 Experience Platform 세그먼트에서 생성된 트레이트를 [Audience Marketplace을 통해 취득한 타사 트레이트와 혼합할 수 있습니다](/help/using/features/audience-marketplace/audience-marketplace.md).

Experience Platform 세그먼트에서 자동으로 생성된 트레이트의 예를 보려면 아래 스크린샷을 참조하십시오.

![Experience Platform의 특성](/help/using/integration/integration-aep/assets/aep-trait.png)


| 항목 번호 | 이름 | 설명 |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Experience Platform 세그먼트에서 생성된 트레이트는 Audience Manager에서 온보드 트레이트로 생성됩니다. |
| 2 | [!UICONTROL Data Source] | 자동으로 생성 Experience Platform 세그먼트에서 자동으로 생성되는 모든 트레이트와 세그먼트는 데이터 소스에 저장됩니다 **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 4 | [!UICONTROL Trait Expression] | 특성 표현입니다 `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | 이 트레이트를 컴포지션으로 사용하는 자동으로 만들어진 세그먼트입니다. |

<br> 

### 세그먼트 {#aep-segments-as-aam-segments}

Audience Manager은 세그먼트 저장소에 **Experience Platform 세그먼트라는 세그먼트 폴더를** 자동으로 만듭니다.

![대시보드 스크린샷](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Experience Platform 세그먼트에서 자동으로 생성된 세그먼트의 예를 보려면 아래 스크린샷을 참조하십시오.

![세그먼트 스크린샷](/help/using/integration/integration-aep/assets/aep-segment.png)

| 항목 번호 | 이름 | 설명 |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 2 | [!UICONTROL Data Source] | 자동으로 생성 Experience Platform 세그먼트에서 자동으로 생성되는 모든 트레이트와 세그먼트는 데이터 소스에 저장됩니다 **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** 자동으로 생성된 세그먼트가 Experience Platform에 설정된 병합 정책을 따르도록 나타냅니다. |
| 4 | [!UICONTROL Segment Rule] | 세그먼트는 트레이트 섹션에 설명된 트레이트로 [구성됩니다](#aep-segments-as-aam-traits). |

## Experience Platform의 Audience Manager 데이터 내보내기 제어 지원 {#aam-data-export-control-in-aep}

Experience Platform에서 데이터 사용 규정을 준수하려면 해당 데이터 세트 및 필드에 적절한 [데이터 사용 레이블을 제공해야 합니다](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html). 또한 [데이터 사용 정책](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) 은 DULE( [Data Usage Labeling and Enforcement) 프레임워크에 설명된 바와 같이 해당 레이블에 대한 특정 마케팅 작업에 대해 활성화되어야 합니다](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework).

Audience Manager과 Experience Platform 간 대상 공유 프로세스에서 Audience Manager 세그먼트에 적용된 모든 데이터 내보내기 컨트롤은 Experience Platform 데이터 거버넌스에서 인식하는 동일한 레이블 및 마케팅 작업으로 변환됩니다.

>[!NOTE]
>
>데이터 내보내기 컨트롤에 대한 자세한 내용은 [데이터 내보내기 컨트롤 설명서를 참조하십시오](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
>
>이 문서에서는 특정 Audience Manager 데이터 내보내기 컨트롤이 플랫폼의 데이터 사용 레이블 및 마케팅 작업에 매핑되는 방법에 대한 참조를 제공합니다.

### 데이터 내보내기 컨트롤을 데이터 사용 레이블로

다음 표에서는 특정 데이터 내보내기 컨트롤이 인식되는 데이터 사용 레이블에 매핑되는 방법에 대해 설명합니다.

| 데이터 내보내기 제어 | 데이터 사용 레이블 |
| --- | --- |
| 개인 식별 정보에는 사용할 수 없습니다. | C3:데이터를 결합하거나 직접 식별 가능한 정보와 함께 사용할 수 없습니다. |
| 오프사이트 광고 타깃팅에 사용할 수 없음 | C5:컨텐츠 또는 광고의 관심 기반, 사이트 간 타깃팅에는 데이터를 사용할 수 없습니다. |
| 온사이트 광고 타깃팅에 사용할 수 없음 | C6:온사이트 광고 타깃팅에 데이터를 사용할 수 없습니다. |
| 온사이트 개인화에 사용할 수 없음 | C7:컨텐츠의 온사이트 타깃팅에 데이터를 사용할 수 없습니다. |

### 마케팅 작업으로 데이터 내보내기 제어

다음 표에서는 특정 데이터 내보내기 레이블이 인식된 마케팅 작업에 매핑되는 방법에 대해 설명합니다.

| 데이터 내보내기 레이블 | 마케팅 활동 |
| --- | --- |
| 이 대상은 PII(개인 식별 정보)와 결합할 수 있습니다. | PII와 결합 |
| 이 대상은 오프사이트 광고 타깃팅에 사용할 수 있습니다. | 사이트 간 타깃팅 |
| 이 대상은 온사이트 광고 타깃팅에 사용할 수 있습니다. | 온사이트 광고 |
| 이 대상은 온사이트 광고 개인화에 사용될 수 있습니다. | 온사이트 개인화 |

## Audience Manager과 Experience Platform 간의 세그먼트 모집단 차이점 이해 {#aep-aam-segment-population-differences}

세그먼트 모집단 수는 Audience Manager 세그먼트와 Experience Platform 세그먼트 간에 다를 수 있습니다. 유사하거나 동일한 대상에 대한 세그먼트 번호는 비슷해야 하지만 모집단 차이는 아래에 나열된 요소 때문일 수 있습니다.

### Experience Platform의 세그먼트 평가

Audience Manager은 인터페이스에서 하루에 한 번 보고 번호를 업데이트합니다.   이 업데이트의 타이밍은 Experience Platform에서 세그먼트 평가 시간에 거의 맞지 않습니다.

### 프로필 병합 규칙과 병합 정책 간의 차이점

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) audience manager과 Experience Platform [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) 에서 서로 다르게 작동하며 각각에 사용되는 ID 그래프가 달라집니다. 이로 인해 세그먼트 모집단 간의 일부 차이가 예상됩니다.

### Experience Platform의 세그먼트 구성

Adobe Experience Platform과 Audience Manager 간의 통합은 모든 고객을 위한 다양한 표준 [ID 네임스페이스를](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) 공유합니다.ECID, IDFA, GAID, 해시된 이메일 주소(EMAIL_LC_SHA256), AdCloud ID 등. Experience Platform 세그먼트가 이러한 프로파일 중 하나를 자격이 있는 프로파일에 대한 기본 ID로 사용하는 경우 프로파일은 Audience Manager 트레이트 및 세그먼트에서 계산됩니다.

또한 Audience Manager은 다음과 같은 경우 Experience Platform 세그먼트에서 사용하는 모든 사용자 지정 ID 네임스페이스에 대해 들어오는 참조를 등록할 수 있습니다.
* ID가 기본 *및*
* audience manager에 해당 장치 간 데이터 소스가 이미 있습니다.

>[!NOTE]
>
> Raw 이메일의 ID가 지정된 Experience Platform의 대상은 Audience Manager에 표시되지 않습니다.

예를 들어 Experience Platform 세그먼트 &quot;모든 내 고객&quot;이 있고 자격이 있는 프로필은 CRM ID, ECID, IDFA, 원시 이메일 주소 및 해시된 이메일 주소인 경우 Audience Manager의 해당 세그먼트에는 CRM ID, ECID, IDFA 및 해시된 이메일 주소만 포함됩니다. Audience Manager의 세그먼트 모집단도 Experience Platform의 세그먼트보다 작습니다.

![Audience Manager 세그먼트 공유 - 세그먼트 구성](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [세그멘테이션 서비스 개요](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform 세그먼트 빌더 사용 안내서](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager 커넥터](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)