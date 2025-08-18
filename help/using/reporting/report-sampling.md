---
description: 일부 보고서에 사용된 샘플링 방법론, 샘플링 오류율 및 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록에 대한 요약입니다.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

일부 보고서에 사용된 샘플링 방법론, 샘플링 오류율 및 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록에 대한 요약입니다.

## 데이터 샘플링 비율 {#data-sampling-ratio}

일부 [!DNL Audience Manager] 보고서는 사용 가능한 총 데이터의 샘플링 집합을 기반으로 결과를 표시합니다. 샘플링된 데이터 비율은 1:54입니다. 샘플링된 데이터를 사용하는 보고서의 경우 이는 결과가 54개의 모든 레코드 집합 중 1개의 레코드를 기반으로 함을 의미합니다.

이러한 보고서는 결과를 생성하기 위해 엄청난 양의 컴퓨팅 성능이 필요하기 때문에 통계적으로 샘플링된 데이터를 사용합니다. 샘플링은 컴퓨터 요구량 감소와 시스템 성능 유지, 정확한 결과 제공을 균형 있게 하는 데 도움이 됩니다.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## 오류율 {#error-rates}

중복 데이터를 생성하는 보고서에서 오류가 발생할 수 있습니다. 오류는 다음과 같은 레코드의 백분율로 정의됩니다.

* 보고서에 포함되지 않았어야 했는데 어쨌든 추가되었습니다.
* 보고서에 포함해야 하지만 제외되었습니다.

테스트 및 모델은 오류율 *이(가) 데이터 세트의 레코드 수에 반비례하여 감소*&#x200B;됨을 보여 줍니다. 레코드가 적은 데이터 집합보다 레코드가 많은 데이터 집합에서 오류가 적게 발생합니다. 이 주장을 좀 더 양적으로 살펴보자. 다음 표에 표시된 것처럼, 설정된 레코드 수에 대해 보고서 결과의 95%가 특정 오류율 미만이 됩니다.

| 레코드 수 | 오류율 |
|--- |--- |
| 500 - 1,000 | 95%는 42%의 오류율 아래에 있습니다. |
| 1,000 - 1,500 | 95%는 34%의 오류율 아래에 있습니다. |
| 10,000 - 50,000 | 95%는 14%의 오류율 아래에 있습니다. |
| 50,000 | 95%는 6%의 오류율 아래에 있습니다. |
| 100,000 | 95%는 4%의 오류율 아래에 있습니다. |
| 500,000(이상) | 95%는 2%의 오류율 아래에 있습니다. |

## Minhash 샘플링 방법론 사용 {#minhash}

[Minhash](https://en.wikipedia.org/wiki/MinHash) 샘플링 방법론을 기반으로 Audience Manager은 새로운 방법을 사용하여 하나의 순열 해싱 데이터 스케치 위에서 트레이트 및 세그먼트 추정치를 계산합니다. 이 새로운 방법은 Jaccard 유사성에 대한 표준 추정량보다 낮은 분산을 생성한다. 이 방법을 사용하는 보고서에 대해서는 아래 섹션을 참조하십시오.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 샘플링된 데이터를 사용하는 보고서 {#reports-using-sampled-data}

통계적으로 샘플링된 데이터와 Minhash 샘플링 방법을 사용하는 [!DNL Audience Manager] 보고서는 다음과 같습니다.

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 통계적 샘플링 | Minhash 샘플링 방식 |
|--- |--- |
| [대응 가능 대상](../features/addressable-audiences.md) 데이터(고객 및 세그먼트 수준 데이터). | [겹치기 보고서](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)(특성 대 특성, 세그먼트 대 특성 및 세그먼트 대 세그먼트) |
| [에 대한 ](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics)총 장치[!UICONTROL Profile Merge Rule] 지표입니다. | [트레이트 추천](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md)은(는) [!UICONTROL Search] 탭과 [!UICONTROL Saved Searches]에서 샘플링된 데이터를 사용합니다. | [Audience Marketplace 권장 사항](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
