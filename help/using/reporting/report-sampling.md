---
description: 일부 보고서에 사용된 샘플링 방법론, 샘플링 오류율 및 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록에 대한 요약입니다.
seo-description: 일부 보고서에 사용된 샘플링 방법론, 샘플링 오류율 및 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록에 대한 요약입니다.
seo-title: 선택한 Audience Manager 보고서에서 데이터 샘플링 및 오류율
solution: Audience Manager
title: 선택한 Audience Manager 보고서에서 데이터 샘플링 및 오류율
uuid: 3 D 8 BD 764-A 9 DA -40 F 1-8794-54304457 BB 9 A
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

일부 보고서에 사용된 샘플링 방법론, 샘플링 오류율 및 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록에 대한 요약입니다.

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. 샘플링된 데이터 비율은 1:54 입니다. 샘플링된 데이터를 사용하는 보고서의 경우, 결과는 54 개 레코드 중 1 개의 레코드를 기준으로 한 1 개의 레코드를 기반으로 합니다.

이러한 보고서는 결과를 생성하기 위한 엄청난 컴퓨팅 능력이 필요하기 때문에 샘플링된 데이터를 사용합니다. 샘플링은 컴퓨팅 수요 감소, 시스템 성능 유지 및 정확한 결과 전달 간의 균형을 맞추는 데 도움이 됩니다.

샘플링을 사용하는 보고서는 최소 고유 방문자 요구 사항을 충족하지 않을 때 트레이트 및 세그먼트를 제외합니다. 최소 요구 사항은 다음과 같습니다.

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* 세그먼트: 14 일 동안 7만 명의 실시간 사용자

## Error Rates {#error-rates}

오류는 겹치는 데이터를 생성하는 보고서에서 발생할 수 있습니다. 오류는 다음과 같은 기록 비율로 정의됩니다.

* 보고서에 포함되지 않았지만 어쨌든 추가되었습니다.
* 보고서에 포함되었지만 제외되었어야 합니다.

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. 레코드가 적은 데이터 세트는 적은 수의 레코드가 있는 세트보다 오류가 적습니다. 이 어설션을 양적 방식으로 살펴보겠습니다. 다음 표에 나타난 바와 같이, 설정된 레코드 수에 대해 보고서 결과의 95%가 특정 오류율 미만이 됩니다.

| 레코드 수 | 오류율 |
|--- |--- |
| 500 - 1,000 | 95%는 42% 오류율입니다. |
| 1,000 - 1,500 | 95%는 34%의 오류율입니다. |
| 10,000 - 50,000 | 95%는 14%의 오류율입니다. |
| 50,000 | 95%는 6%의 오류율입니다. |
| 100,000 | 95%는 4%의 오류율입니다. |
| 500,000 이상 | 95%는 2%의 오류율입니다. |

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [겹침 보고서](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (트레이트, 트레이트, 세그먼트-세그먼트) 를 겹칠 수 있습니다.
* [어드레서블 대상](../features/addressable-audiences.md) 데이터 (고객 및 세그먼트 수준 데이터)
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
