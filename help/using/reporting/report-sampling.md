---
description: 일부 보고서에 사용된 샘플링 방법론, 샘플링 오류 비율, 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록 등에 대한 요약입니다.
seo-description: 일부 보고서에 사용된 샘플링 방법론, 샘플링 오류 비율, 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록 등에 대한 요약입니다.
seo-title: 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율
solution: Audience Manager
title: 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 397be3f44bf865633140bb45630a78be0a0d2219
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

일부 보고서에 사용된 샘플링 방법론, 샘플링 오류 비율, 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록 등에 대한 요약입니다.

## 데이터 샘플링 비율 {#data-sampling-ratio}

일부 [!DNL Audience Manager] 보고서에는 사용 가능한 데이터의 총 양을 샘플링한 세트를 기반으로 결과가 표시됩니다. 샘플링된 데이터 비율은 1:54입니다. 샘플링된 데이터를 사용하는 보고서의 경우, 결과는 54개의 레코드 집합 중 1개의 레코드를 기반으로 합니다.

이러한 보고서는 결과를 생성하기 위해 엄청난 양의 컴퓨팅 능력이 필요하기 때문에 통계 샘플링 데이터를 사용합니다. 샘플링을 통해 컴퓨팅 요구가 줄어들고 시스템 성능을 유지하며 정확한 결과를 얻을 수 있습니다.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## 오류 비율 {#error-rates}

중복 데이터를 생성하는 보고서에서 오류가 발생할 수 있습니다. 오류는 다음과 같은 레코드 비율로 정의됩니다.

* 보고서에 포함되지 말았어야 했지만, 어쨌든 추가되었다.
* 보고서에 포함되어야 했지만 제외되었습니다.

테스트 및 모델에 따르면 오류 비율이 데이터 세트의 레코드 수에 *비해* 반대 비율로 감소한다는 것을 알 수 있습니다. 레코드가 많은 데이터 세트는 적은 수의 레코드가 있는 집합보다 오류가 적게 발생합니다. 이 주장을 보다 양적으로 살펴보자. 다음 표에 표시된 대로, 레코드 세트의 경우 보고서 결과의 95%가 특정 오류 비율 아래에 있게 됩니다.

| 레코드 수 | 오류 비율 |
|--- |--- |
| 500 - 1,000 | 95%는 42% 오류 비율 미만입니다. |
| 1,000 - 1,500 | 95%는 34% 오류 비율 미만입니다. |
| 10,000 - 50,000 | 95%는 14% 오류 비율 미만입니다. |
| 50,000 | 95%는 6% 오류 비율 미만입니다. |
| 100,000 | 95%는 4% 오류 비율 미만입니다. |
| 500,000(이상) | 95%는 2% 오류율 아래에 있다. |

## 민해시 샘플링 방법론 사용 {#minhash}

Minhash [샘플링 방법을 기반으로](https://en.wikipedia.org/wiki/MinHash) Audience Manager은 원퍼블리싱 해싱 데이터 스케치 위에 트레이트와 세그먼트 견적 도구를 계산하는 새로운 방법을 사용합니다. 이 새 방법은 Java 유사성에 대한 표준 견적 도구보다 낮은 분산을 생성합니다. 이 방법을 사용하는 보고서에 대해서는 아래 섹션을 참조하십시오.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## 샘플링된 데이터를 사용하는 보고서 {#reports-using-sampled-data}

통계 샘플링 데이터 및 Minhash 샘플링 방법을 사용하는 보고서에는 다음과 같은 내용이 포함되어 있습니다. [!DNL Audience Manager]

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| 통계 샘플링 | 민해시 샘플링 방법론 |
|--- |--- |
| [대응 가능 대상](../features/addressable-audiences.md) 데이터(고객 및 세그먼트 수준 데이터) | [보고서](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 겹치기(트레이트-투-트레이트, 세그먼트-세그먼트) |
| 한 [장치의](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 총 장치 [!UICONTROL Profile Merge Rule]지표입니다. | [트레이트 추천](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) [!UICONTROL Search] 는 탭 및 모든 [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
