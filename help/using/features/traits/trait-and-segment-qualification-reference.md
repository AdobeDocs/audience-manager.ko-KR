---
description: 특성 자격 또는 특성 깨달음은 특성 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: 특성 자격 또는 특성 깨달음은 특성 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.
seo-title: 트레이트 자격 참조
solution: Audience Manager
title: 트레이트 자격 참조
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---


# 트레이트 및 세그먼트 자격 참조 {#trait-qualification-reference}

특성 자격 또는 특성 깨달음은 특성 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 [유형 자격에 대한 자세한 내용은 트레이트 유형별](#trait-type) 트레이트 자격 을 참조하십시오.

또한 세그먼트 자격 [에 대한 자세한 내용은 실시간 세그먼트 모집단](#real-time-segment) 및 총 세그먼트 모집단을 참조하십시오.



## 특성 유형별 특성 자격 {#trait-type}

| 특성 유형 | 자격 조건 |
|---|---|
| 규칙 기반 특성 | 사용자가 브라우저에서 트레이트를 이용할 수 있으므로 트레이트 자격 조건은 실시간으로 발생합니다. UI에서 트레이트를 [만든 후 약 4시간 후에 사용자가 규칙 기반 트레이트](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) 자격을 시작합니다. 규칙 기반의 트레이트를 사용하면 [최근 및 빈도](../segments/recency-and-frequency.md) 컨트롤을 사용하여 광고 빈도 매핑 및 기타 사용 사례를 수행할 수 있습니다. |
| 온보드 트레이트 | 특성 자격은 인바운드 파일이 처리된 후에 발생합니다(예: 인바운드 파일을 Audience Manager [로](../../faq/faq-inbound-data-ingestion.md) 가져오면). 이는 트레이트 자격 문제가 발생할 때 발생합니다. 처리를 위해 인바운드 파일을 업로드하기 전에 온보드 트레이트를 만든 후 약 4시간을 기다려야 합니다. 온보드 트레이트의 경우 사용자 프로필의 최대 자격 조건은 1입니다. |
| 알고리즘 특성 | 알고리즘 특성의 경우 사용자 프로필의 최대 자격 조건은 1입니다. |
| 폴더 트레이트 | 폴더 트레이트는 포함된 트레이트의 특성 자격을 합산합니다. 폴더 [트레이트 읽기: 정보](about-folder-traits.md) . |
| 활성 대상 트레이트 및 데이터 소스 동기화된 트레이트 | 트레이트는 Audience Manager 계정에서 관리 중인 모든 장치를 포함합니다. [!UICONTROL Active Audience] [!UICONTROL Data Source Synced Traits] 데이터 소스와 연관된 모든 사용자를 추적합니다. 활성 [고객 트레이트 및 데이터 소스 동기화된 트레이트에 대한 자세한 내용을 참조하십시오](client-activity-synced-audience-traits.md). |

## 고유 특성 관계 및 총 특성 인구 {#unique-trait-realizations}

![고유한 특성 인식](assets/trait-graph.png)

그래프에 표시할 결과 유형( [!UICONTROL Device ID] 또는 [!UICONTROL Cross-Device ID]로 필터링됨)에 따라 지표는 다른 의미를 가집니다.

결과를 필터링하는 방법: [!UICONTROL Device ID]

* [!UICONTROL Unique Trait Realizations] 는 다른 시간 범위 내에서 프로필에 특성을 추가한 익명 장치 방문자 수입니다.
* [!UICONTROL Total Trait Population] 는 이 특성이 프로필에 있는 익명 장치 방문자 수입니다.

결과를 필터링하는 방법: [!UICONTROL Cross-Device ID]

* [!UICONTROL Unique Trait Realizations] 는 다른 시간 범위 내에서 프로필에 특성을 추가한 인증된 방문자의 수입니다.
* [!UICONTROL Total Trait Population] 은 이 특성이 프로필에 있는 인증된 방문자의 수입니다.

숫자를 이렇게 생각해 보세요. 위의 이미지에서 [특성 세부 사항](../../features/traits/trait-details-page.md) 보기에서는 어제 속성을 방문한 활성 장치의 수를 나타냅니다. 55,757 [!UICONTROL Total Trait Population] 은 현재 이 트레이트에 대해 자격이 있는 사용자의 양을 나타냅니다. 이 [!UICONTROL Total Trait Population] 수치는 세그먼테이션/타깃팅에 사용할 수 있는 총 사용자 수를 보여주기 위한 것입니다. 일반적으로 사용자는 120일 동안 트레이트의 일부로 남습니다.

두 인구를 계산하기 위해 두 가지 서로 다른 계산 작업을 하기 때문에, [!UICONTROL Total Trait Population] 항상 24시간 [!UICONTROL Unique Trait Realizations] 에 뒤쳐집니다. 위의 그래프에서 당신은 2월 5일 약 90,400 [!UICONTROL Unique Trait Realizations] 과 [!UICONTROL Total Trait Population] 약 90,300을 볼 수 있습니다. 그 다음 날 90,400개의 프로필 [!UICONTROL Total Trait Population] 이 추가됩니다.

집까지 향해서, 만약 당신이 지금 10,000명의 방문자를 경험했다면, 그들은 내일 [!UICONTROL Unique Trait Realizations]에 나타났지만, 단지 24시간 후에 그 곳에 나타날 것입니다 [!UICONTROL Total Trait Population].

특성 실현의 모든 변경 사항은 세그먼트 모집단을 반영합니다.

## 실시간 세그먼트 모집단 및 총 세그먼트 모집단 {#real-time-segment}

![고유한 특성 인식](assets/segment-graph.png)

선택한 세그먼트 [!UICONTROL Real-time Segment Population] 에 자격을 부여하여 선택한 시간 간격 내에 속성에 도달한 장치의 수를 카운트합니다.

선택한 [!UICONTROL Total Segment Population] 시간 범위 내에서 선택한 세그먼트에 자격이 있는 장치의 수를 카운트합니다. 이 [!UICONTROL 1 Day] 보고서는 최신 세그먼트 인구 수를 나타냅니다.

숫자를 이렇게 생각해 보세요. 위의 이미지에서 [세그먼트 세부 사항](../../features/segments/segment-summary-view.md) 보기에서 9,993은 어제 속성을 방문하고 세그먼트에 적합한 활성 장치의 수를 나타냅니다. 699,532 [!UICONTROL Total Segment Population] 는 현재 이 세그먼트에 자격이 있는 총 장치 수를 나타냅니다. 이 [!UICONTROL Total Segment Population] 수치는 세그먼테이션/타깃팅에 사용할 수 있는 총 장치 수를 보여주기 위한 것입니다.

두 인구를 계산하기 위해 두 가지 서로 다른 계산 작업을 하기 때문에, [!UICONTROL Total Segment Population] 항상 24시간 [!UICONTROL Real-time Segment Population] 에 뒤쳐집니다. 위의 그래프에서 당신은 2월 2일 [!UICONTROL Real-time Segment Population] 의 8,116 [!UICONTROL Total Segment Population] 과 742,000을 볼 수 있습니다. 8,116개의 프로필이 그 다음날 [!UICONTROL Total Segment Population] 에 추가됩니다.

집까지 향해서, 만약 당신이 지금 10,000명의 방문자를 경험했다면, 그들은 내일 [!UICONTROL Real-time Segment Population]에 나타났지만, 단지 24시간 후에 그 곳에 나타날 것입니다 [!UICONTROL Total Segment Population].

## 특성 자격 제한 {#trait-qualification-limit}

인증된 프로필(DPUUID[) 또는 장치 ID(](../../reference/ids-in-aam.md)UUID[](../../reference/ids-in-aam.md))이든 각 사용자 프로필에 대해 150,000개의 트레이트 자격 제한을 적용합니다. DPUUID는 특정 인스턴스 [!DNL Audience Manager]에 고유하지만 플랫폼 간에 UUID가 [!DNL Audience Manager] 공유됩니다. 우선 [!UICONTROL UUID]트레이트 자격을 저장하는 공정성이 요구된다. 알고리즘은 프로필의 모든 인스턴스에 대해 동일한 공유를 사용할 수 있도록 [!UICONTROL UUID] 합니다 [!DNL Audience Manager].

