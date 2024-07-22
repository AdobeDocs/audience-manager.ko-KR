---
description: 트레이트 자격 또는 트레이트 실현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 트레이트 자격에 대한 자세한 내용은 아래 표를 참조하십시오.
keywords: 트레이트 자격,트레이트 실현,고유 트레이트 실현,UTR,총 트레이트 인구,TTP
seo-description: Trait qualification, or trait realization, is treated differently in Audience Manager, depending on trait type. See the table below for detailed information on trait qualification.
seo-title: Trait Qualification Reference
solution: Audience Manager
title: 트레이트 자격 참조
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
feature: Traits
exl-id: 223f5fc6-c939-4bc6-94a3-5d953abc601a
source-git-commit: c844ce5ed85e9071227df67b5b20e6ee674408be
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 0%

---

# 트레이트 및 세그먼트 자격 참조 {#trait-qualification-reference}

트레이트 자격 또는 트레이트 실현은 트레이트 유형에 따라 Audience Manager에서 다르게 처리됩니다. 특성 유형 자격에 대한 자세한 내용은 [특성 유형별 특성 자격](#trait-type)을 참조하십시오.

또한 세그먼트 자격에 대한 자세한 내용은 [실시간 세그먼트 채우기 및 총 세그먼트 채우기](#real-time-segment)를 참조하십시오.



## 트레이트 유형별 트레이트 자격 {#trait-type}

| 트레이트 유형 | 자격 기준 |
|---|---|
| 규칙 기반 트레이트 | 사용자가 브라우저에서 트레이트에 대한 자격을 얻으면 트레이트 자격이 실시간으로 발생합니다. UI에서 [특성을 만들기](create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)한 후 약 4시간 후에 사용자가 규칙 기반 특성에 대한 자격을 갖추기 시작합니다. 규칙 기반 특성을 사용하면 광고 빈도 제한 및 기타 사용 사례에 [최신성 및 빈도](../segments/recency-and-frequency.md) 컨트롤을 사용할 수 있습니다. |
| 온보딩된 트레이트 | 트레이트 자격은 인바운드 파일이 처리된 후에 발생합니다(예: 인바운드 파일이 [Audience Manager으로 가져옴](../../faq/faq-inbound-data-ingestion.md)). 이 때 트레이트 자격이 발생합니다. 처리를 위해 인바운드 파일을 업로드하기 전에 온보딩된 트레이트를 만든 후 약 4시간을 기다려야 합니다. 온보딩된 트레이트의 경우 사용자 프로필에 대한 최대 자격 수는 1입니다. |
| 알고리즘 트레이트 | 알고리즘 트레이트의 경우 사용자 프로필에 대한 최대 자격 수는 1입니다. |
| 폴더 트레이트 | 폴더 트레이트는 포함된 트레이트의 트레이트 자격을 요약합니다. 자세한 내용은 [폴더 특성: 정보](about-folder-traits.md)을(를) 참조하십시오. |
| 활성 대상 트레이트 및 데이터 Source 동기화된 트레이트 | [!UICONTROL Active Audience] 트레이트에는 Audience Manager 계정에서 관리 중인 모든 장치가 포함되어 있습니다. [!UICONTROL Data Source Synced Traits]에서 데이터 원본과 연결된 모든 사용자를 추적합니다. [활성 대상 트레이트 및 데이터 Source 동기화 트레이트](client-activity-synced-audience-traits.md)에 대해 자세히 알아보십시오. |

## 고유 트레이트 실현 및 총 트레이트 인구 {#unique-trait-realizations}

![고유 특성 실현](assets/trait-graph.png)

그래프를 표시할 결과 유형([!UICONTROL Device ID] 또는 [!UICONTROL Cross-Device ID](으)로 필터링)에 따라 지표의 의미가 다릅니다.

결과를 [!UICONTROL Device ID](으)로 필터링하는 경우:

* [!UICONTROL Unique Trait Realizations]은(는) 다른 시간 범위 내에서 프로필에 트레이트를 추가한 익명 장치 방문자의 수입니다.
* [!UICONTROL Total Trait Population]은(는) 프로필에 이 특성이 있는 익명 장치 방문자의 수입니다.

결과를 [!UICONTROL Cross-Device ID](으)로 필터링하는 경우:

* [!UICONTROL Unique Trait Realizations]은(는) 다른 시간 범위 내에서 프로필에 트레이트를 추가한 인증된 방문자 수입니다.
* [!UICONTROL Total Trait Population]은(는) 프로필에 이 특성이 있는 인증된 방문자의 수입니다.

숫자를 이렇게 생각해 보세요. 위의 이미지에서 [트레이트 세부 정보](../../features/traits/trait-details-page.md) 보기의 90,173은 어제 속성을 방문한 활성 장치 수를 나타냅니다. 55,757개의 [!UICONTROL Total Trait Population]은(는) 현재 이 트레이트에 대해 자격이 있는 사용자의 수를 나타냅니다. [!UICONTROL Total Trait Population] 수치는 세분화/타깃팅에 사용할 수 있는 총 사용자 수를 표시하기 위한 것입니다. 일반적으로 사용자는 120일 동안 트레이트의 일부로 유지됩니다.

두 모집단을 계산하기 위해 두 개의 다른 계산 작업을 실행하기 때문에 [!UICONTROL Total Trait Population]은(는) 항상 [!UICONTROL Unique Trait Realizations]보다 24시간 늦습니다. 위의 그래프에서 2월 5일에 약 90,400 [!UICONTROL Unique Trait Realizations]과(와) 약 90,300 중 [!UICONTROL Total Trait Population]을(를) 볼 수 있습니다. 90,400개의 프로필이 다음 날 [!UICONTROL Total Trait Population]에 추가됩니다.

더 나아가 집까지 가기 위해, 지금 방문자가 10,000명 급증한 경우 내일 [!UICONTROL Unique Trait Realizations]에 표시되지만, 24시간 후인 [!UICONTROL Total Trait Population]에만 표시됩니다.

트레이트 실현의 모든 변경 사항은 세그먼트 모집단에 반영됩니다.

## 실시간 세그먼트 채우기 및 총 세그먼트 채우기 {#real-time-segment}

![고유 특성 실현](assets/segment-graph.png)

[!UICONTROL Real-time Segment Population]은(는) 선택한 세그먼트에 대해 자격이 있고 선택한 시간 간격 내에 사용자의 속성에 도달한 장치 수를 계산합니다.

[!UICONTROL Total Segment Population]은(는) 선택한 시간 범위 내에서 선택한 세그먼트에 적합한 장치 수를 계산합니다. [!UICONTROL 1 Day] 보고서는 가장 최신의 세그먼트 모집단 수를 나타냅니다.

숫자를 이렇게 생각해 보세요. 위의 이미지에서 [세그먼트 세부 정보](../../features/segments/segment-summary-view.md) 보기의 9,993은 어제 속성을 방문했으며 세그먼트에 적합한 활성 장치 수를 나타냅니다. 699,532의 [!UICONTROL Total Segment Population]은(는) 현재 이 세그먼트에 적합한 총 장치 수를 나타냅니다. [!UICONTROL Total Segment Population] 수치는 세분화/타깃팅에 사용할 수 있는 총 장치 수를 보여 주기 위한 것입니다.

두 모집단을 계산하기 위해 두 개의 다른 계산 작업을 실행하기 때문에 [!UICONTROL Total Segment Population]은(는) 항상 [!UICONTROL Real-time Segment Population]보다 24시간 늦습니다. 위의 그래프에서 2월 2일에 대해 8,116 [!UICONTROL Real-time Segment Population]과(와) 742,000개 중 [!UICONTROL Total Segment Population]을(를) 볼 수 있습니다. 8,116개의 프로필이 다음 날 [!UICONTROL Total Segment Population]에 추가됩니다.

더 나아가 집까지 가기 위해, 지금 방문자가 10,000명 급증한 경우 내일 [!UICONTROL Real-time Segment Population]에 표시되지만, 24시간 후인 [!UICONTROL Total Segment Population]에만 표시됩니다.

## 트레이트 자격 제한 {#trait-qualification-limit}

인증된 프로필([DPUUID](../../reference/ids-in-aam.md))이든 장치 ID([UUID](../../reference/ids-in-aam.md))이든 각 사용자 프로필에 대해 150,000개의 트레이트 자격 제한을 적용합니다. DPUUID가 [!DNL Audience Manager]의 특정 인스턴스에 대해 고유한 반면 UUID는 [!DNL Audience Manager] 플랫폼에서 공유됩니다. [!UICONTROL UUID]의 경우 트레이트 자격을 저장할 때 공정 정책을 적용합니다. 알고리즘에서는 [!DNL Audience Manager]의 모든 인스턴스에 대해 [!UICONTROL UUID] 프로필의 동일한 공유를 사용할 수 있도록 합니다.
