---
description: 이 문서에서는 Audience Manager와 Adobe Experience Platform에서 대상을 공유하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Manager와 Adobe Experience Platform에서 대상을 공유하는 방법에 대해 설명합니다.
seo-title: Audience Manager와 Adobe Experience Platform 간의 고객 공유
solution: Audience Manager
title: Audience Manager와 Adobe Experience Platform 간의 고객 공유
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing
translation-type: tm+mt
source-git-commit: e27ce2f607cadd7318a171359a5ae4daa071c486

---


# Audience Manager와 Adobe Experience Platform 간의 고객 공유 {#aam-aep-audience-sharing}

>[!NOTE]
>
> 이 페이지에 설명된 기능은 Audience Manager 및 Adobe Experience Platform 고객이 사용할 수 있습니다.
>
> 이 기능에 대한 액세스 권한을 받으려면 Adobe 세일즈 담당자에게 문의하십시오.

## 개요 {#overview}

Audience Manager와 Adobe Experience Platform 간의 고객 공유 기능을 사용하면 Adobe Experience Platform에서 Audience Manager 트레이트 및 세그먼트를 공유할 수 있고 그 반대의 경우도 가능합니다.

Adobe Experience Platform에서 Audience Manager 트레이트 및 세그먼트를 사용하여 고객 프로파일에 Audience Manager 데이터를 추가하고 Experience Platform [세분화 서비스를](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)활용할 수 있습니다.

Audience Manager에서는 다음과 같은 데이터 관리 플랫폼 사용 사례에 Experience Platform 세그먼트를 사용할 수 있습니다.
* 세그먼트에 [타사 데이터](/help/using/overview/data-types-collected.md#third-party-data) 추가;
* [알고리즘 모델링](/help/using/features/algorithmic-models/understanding-models.md);
* 현재 경험 플랫폼에서 지원되지 않는 대상에 세그먼트 활성화를 참조하십시오.

또한, 귀하의 경험 플랫폼 세그먼트는 코어 서비스를 통해 다른 Experience Cloud 솔루션과 공유됩니다 [](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html).

<br> 

대상 공유 사용 사례에 대한 개요는 아래 표를 참조하십시오.

| **사용 사례** | **Adobe Experience Platform** | **Audience Manager** | **핵심 서비스** |
---------|----------|---------|---------
| **대상 공유** | <ul><li>Audience Manager 데이터를 사용하여 고객 프로파일 강화</li><li>Adobe Experience Platform 세분화에 Audience Manager 데이터 사용</li></ul> | <ul><li>세그먼트에 타사 데이터 추가</li><li>알고리즘 모델링</li><li>추가 대상에 대한 활성화</li></ul> | Adobe Target 또는 Analytics와 같은 다른 Experience Cloud 솔루션에서 Experience Platform 세그먼트를 사용합니다. |

<br> 

## Adobe Experience Platform의 Audience Manager 세그먼트 및 트레이트 {#aam-segments-traits-in-aep}

Audience Manager 트레이트 및 세그먼트는 세그먼트 워크플로우에서 Experience **Platform** 대상에 표시됩니다. Adobe Experience Platform의 Audience Manager 세그먼트 및 트레이트에 대한 자세한 내용은 다음을 참조하십시오.

* [세그멘테이션 서비스 개요](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [경험 플랫폼 세그먼트 빌더 사용 안내서](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segment-builder-guide.md)

<br> 

## Audience Manager의 Adobe Experience Platform 세그먼트 {#aep-segments-in-aam}

Adobe Experience Platform에서 만든 세그먼트는 Audience Manager 인터페이스에 트레이트 및 세그먼트로 표시되며, 다음 컴포지션 규칙이 있습니다.
* 특성:트레이트 규칙은 경험 플랫폼 세그먼트의 ID입니다.
* 세그먼트:세그먼트는 위에서 설명한 트레이트로 구성됩니다.

### 트레이트 {#aep-segments-as-aam-traits}

Audience Manager는 트레이트 스토리지에 Experience **Platform** 트레이트라는 트레이트 폴더를 자동으로 만듭니다.

![Experience Platform 대시보드의 트레이트](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

세그먼트에서 자동으로 생성된 트레이트를 다른 트레이트와 함께 사용할 수 있습니다. 예를 들어 Adobe Experience Platform 세그먼트에서 생성된 트레이트를 Audience Marketplace를 통해 획득한 타사 트레이트와 혼합할 수 [있습니다](/help/using/features/audience-marketplace/audience-marketplace.md).

경험 플랫폼 세그먼트에서 자동으로 생성된 트레이트의 예는 아래 스크린샷을 참조하십시오.

![경험 플랫폼의 특성](/help/using/integration/integration-aep/assets/aep-trait.png)


| 항목 번호 | 이름 | 설명 |
---------|----------|---------
| 1 | 특성 유형 | Experience Platform 세그먼트에서 생성된 트레이트는 Audience Manager에서 온보드 트레이트로 만들어집니다. |
| 2 | 데이터 소스 | 자동으로 만들어짐 Adobe Experience Platform 세그먼트에서 자동으로 생성된 모든 트레이트 및 세그먼트는 데이터 소스 Adobe Experience Platform **대상 공유에 저장됩니다**. |
| 3 | 통합 코드 | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 4 | 특성 표현식 | 특성 표현입니다 `segID = segment ID in Experience Platform`. |
| 5 | 이 트레이트를 사용하는 세그먼트 | 이 트레이트를 컴포지션으로 사용하는 자동으로 만들어진 세그먼트입니다. |

<br> 

### 세그먼트{#aep-segments-as-aam-segments}를 참조하십시오 

Audience Manager는 세그먼트 저장소에서 경험 플랫폼 **세그먼트라는** 세그먼트 폴더를 자동으로 만듭니다.

![대시보드 스크린샷](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

경험 플랫폼 세그먼트에서 자동으로 생성된 세그먼트의 예는 아래 스크린샷을 참조하십시오.

![세그먼트 스크린샷](/help/using/integration/integration-aep/assets/aep-segment.png)

| 항목 번호 | 이름 | 설명 |
---------|----------|---------
| 1 | 통합 코드 | 통합 코드는 Experience Platform의 세그먼트 ID에 해당합니다. |
| 2 | 데이터 소스 | 자동으로 만들어짐 Adobe Experience Platform 세그먼트에서 자동으로 생성된 모든 트레이트 및 세그먼트는 데이터 소스 Adobe Experience Platform **대상 공유에 저장됩니다**. |
| 3 | 프로필 병합 규칙 | **외부 병합** 정책은 자동으로 생성된 세그먼트가 Experience Platform에서 설정된 병합 정책을 따르도록 합니다. |
| 4 | 세그먼트 규칙 | 세그먼트는 트레이트 섹션에 설명된 트레이트로 [구성됩니다](#aep-segments-as-aam-traits). |