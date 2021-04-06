---
description: 트레이트 유형(Trait Qualification)이나 트레이트 실현은 특성 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.
keywords: 트레이트 자격, 트레이트 인식, 고유한 트레이트 인식, UTR, 총 트레이트 인구, TTP
seo-description: 트레이트 유형(Trait Qualification)이나 트레이트 실현은 특성 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.
seo-title: 트레이트 자격 참조
solution: Audience Manager
title: 트레이트 자격 참조
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: 트레이트
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,85c2d54f-b9d6-4c95-b4b5-466119effc2a,223f5fc6-c939-4bc6-94a3-5d953abc601a
translation-type: tm+mt
source-git-commit: e13f81df9b0d59cd958f4c2a615c31df00ce2cc5
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 2%

---

# 트레이트 및 세그먼트 자격 참조 {#trait-qualification-reference}

트레이트 유형(Trait Qualification)이나 트레이트 실현은 특성 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 유형 자격에 대한 자세한 내용은 [트레이트 유형별 트레이트 자격](#trait-type)을 참조하십시오.

또한 세그먼트 자격에 대한 자세한 내용은 [실시간 세그먼트 모집단 및 총 세그먼트 모집단](#real-time-segment)을 참조하십시오.



## 특성 유형별 특성 자격 {#trait-type}

| 특성 유형 | 자격 조건 |
|---|---|
| 규칙 기반 트레이트 | 사용자가 브라우저에서 트레이트를 적용받을 수 있기 때문에 트레이트 자격은 실시간으로 발생합니다. UI에서 [특성](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)을(를) 만든 후 약 4시간 후에 사용자가 규칙 기반 트레이트에 대한 자격을 갖추기 시작합니다. 규칙 기반 트레이트를 사용하면 광고 빈도 매핑 및 기타 사용 사례에 [최근 및 빈도](../segments/recency-and-frequency.md) 컨트롤을 사용할 수 있습니다. |
| 온보드 트레이트 | 특성 자격은 인바운드 파일이 처리된 후에 발생합니다. 즉, 인바운드 파일은 [Audience Manager](../../faq/faq-inbound-data-ingestion.md)로 가져오며, 이는 트레이트 자격 조건이 발생하는 때입니다. 처리할 인바운드 파일을 업로드하기 전에 온보드 트레이트를 만든 후 약 4시간을 기다려야 합니다. 온보드 트레이트의 경우 사용자 프로필의 최대 자격 조건은 1입니다. |
| 알고리즘 특성 | 알고리즘 트레이트의 경우 사용자 프로필의 최대 자격 조건은 1입니다. |
| 폴더 트레이트 | 폴더 트레이트는 포함된 트레이트의 특성 자격을 합산합니다. [폴더 트레이트 읽기:자세한 내용은 ](about-folder-traits.md) 정보를 참조하십시오. |
| 활성 대상 트레이트 및 데이터 소스 동기화된 트레이트 | [!UICONTROL Active Audience] 트레이트는 Audience Manager 계정에서 관리 중인 모든 장치를 포함합니다. [!UICONTROL Data Source Synced Traits] 데이터 소스와 연관된 모든 사용자를 추적합니다. [활성 대상 트레이트 및 데이터 소스 동기화된 트레이트](client-activity-synced-audience-traits.md)에 대해 자세히 알아보십시오. |

## 고유한 특성 인식 및 총 특성 채우기 {#unique-trait-realizations}

![고유한 특성 인식](assets/trait-graph.png)

그래프에 표시할 결과 유형(예: [!UICONTROL Device ID] 또는 [!UICONTROL Cross-Device ID] 기준으로 필터링됨)에 따라 지표는 다른 의미를 가집니다.

결과를 [!UICONTROL Device ID]별로 필터링할 때:

* [!UICONTROL Unique Trait Realizations] 는 다른 시간 범위 내에서 프로필에 트레이트를 추가한 익명 장치 방문자의 수입니다.
* [!UICONTROL Total Trait Population] 는 이 특성이 프로필에 있는 익명 장치 방문자 수입니다.

결과를 [!UICONTROL Cross-Device ID]별로 필터링할 때:

* [!UICONTROL Unique Trait Realizations] 는 다른 시간 범위 내에서 프로필에 트레이트를 추가한 인증된 방문자의 수입니다.
* [!UICONTROL Total Trait Population] 은 이 특성이 프로필에 있는 인증된 방문자의 수입니다.

이런 식으로 숫자를 생각해 보세요. 위의 이미지에서 [특성 세부 사항](../../features/traits/trait-details-page.md) 보기에서 90,173은 어제 속성을 방문한 활성 장치의 수를 나타냅니다. 55,757의 [!UICONTROL Total Trait Population]은 현재 이 트레이트에 대해 자격이 있는 사용자의 양을 나타냅니다. [!UICONTROL Total Trait Population] 그림은 세그먼테이션/타깃팅에 사용할 수 있는 총 사용자 수를 보여 주기 위한 것입니다. 일반적으로 사용자는 120일 동안 트레이트의 일부로 남습니다.

두 개의 다른 계산 작업을 실행하여 두 모집단을 계산하므로 [!UICONTROL Total Trait Population]은 항상 [!UICONTROL Unique Trait Realizations]에 비해 24시간 늦습니다. 위의 그래프에서 2월 5일 90,400개 [!UICONTROL Unique Trait Realizations]와 90,300개 중 [!UICONTROL Total Trait Population]을 볼 수 있습니다. 다음 날 [!UICONTROL Total Trait Population]에 90,400개의 프로필이 추가됩니다.

이 점을 다시 강조하기 위해, 지금 10,000명의 방문자가 급증한 경우, 방문자는 내일의 [!UICONTROL Unique Trait Realizations]에 표시되지만, 24시간 후 [!UICONTROL Total Trait Population]에 표시됩니다.

트레이트 실현의 모든 변경 사항은 세그먼트 모집단을 반영합니다.

## 실시간 세그먼트 모집단 및 총 세그먼트 모집단 {#real-time-segment}

![고유한 특성 인식](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population]은 선택한 세그먼트에 자격이 있고 속성에 도달한 장치 수를 선택한 시간 간격 내에 카운트합니다.

[!UICONTROL Total Segment Population]은 선택한 시간 범위 내에서 선택한 세그먼트에 자격을 부여받은 장치의 수를 카운트합니다. [!UICONTROL 1 Day] 보고서는 가장 최신 세그먼트 인구 수를 나타냅니다.

이런 식으로 숫자를 생각해 보세요. 위의 이미지에서 [세그먼트 세부 사항](../../features/segments/segment-summary-view.md) 보기에서 9,993은 어제 속성을 방문하고 세그먼트에 자격이 있는 활성 장치의 수를 나타냅니다. 699,532의 [!UICONTROL Total Segment Population]은 현재 이 세그먼트에 자격이 있는 총 장치 수를 나타냅니다. [!UICONTROL Total Segment Population] 그림은 세그먼테이션/타깃팅에 사용할 수 있는 총 장치 수를 보여 주기 위한 것입니다.

두 개의 다른 계산 작업을 실행하여 두 모집단을 계산하므로 [!UICONTROL Total Segment Population]은 항상 [!UICONTROL Real-time Segment Population]에 비해 24시간 늦습니다. 위의 그래프에서 2월 2일에는 8,116개의 [!UICONTROL Real-time Segment Population]과 742,000의 [!UICONTROL Total Segment Population]을 볼 수 있습니다. 다음 날 [!UICONTROL Total Segment Population]에 8,116 프로필이 추가됩니다.

이 점을 다시 강조하기 위해, 지금 10,000명의 방문자가 급증한 경우, 방문자는 내일의 [!UICONTROL Real-time Segment Population]에 표시되지만, 24시간 후 [!UICONTROL Total Segment Population]에 표시됩니다.

## 특성 자격 제한 {#trait-qualification-limit}

인증된 프로필([DPUUID](../../reference/ids-in-aam.md)) 또는 장치 ID([UUID](../../reference/ids-in-aam.md))인지 여부에 따라 각 사용자 프로필에 대해 150,000개의 트레이트 자격 제한이 적용됩니다. DPUUID는 [!DNL Audience Manager]의 특정 인스턴스에만 고유하지만 UUID는 [!DNL Audience Manager] 플랫폼에서 공유됩니다. [!UICONTROL UUID]s는 트레이트 자격 저장 시 공정 정책을 적용합니다. 알고리즘은 [!UICONTROL UUID] 프로필의 동일한 공유를 [!DNL Audience Manager]의 모든 인스턴스에 사용할 수 있도록 합니다.
