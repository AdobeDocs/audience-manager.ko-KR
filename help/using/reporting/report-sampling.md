---
description: 일부 보고서에 사용된 샘플링 방법론, 샘플링 오류 비율, 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록 등에 대한 요약입니다.
seo-description: 일부 보고서에 사용된 샘플링 방법론, 샘플링 오류 비율, 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록 등에 대한 요약입니다.
seo-title: 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율
solution: Audience Manager
title: 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 8%

---


# 선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

일부 보고서에 사용된 샘플링 방법론, 샘플링 오류 비율, 샘플링된 데이터를 기반으로 정보를 반환하는 보고서 목록 등에 대한 요약입니다.

## 데이터 샘플링 비율 및 최소 요구 사항 {#data-sampling-ratio}

일부 [!DNL Audience Manager] 보고서에는 사용 가능한 데이터의 총 양을 샘플링한 세트를 기반으로 결과가 표시됩니다. 샘플링된 데이터 비율은 1:54입니다. 샘플링된 데이터를 사용하는 보고서의 경우, 결과는 54개의 레코드 집합 중 1개의 레코드를 기반으로 합니다.

이러한 보고서는 결과를 생성하기 위해 엄청난 양의 컴퓨팅 능력이 필요하기 때문에 샘플링된 데이터를 사용합니다. 샘플링을 통해 컴퓨팅 요구가 줄어들고 시스템 성능을 유지하며 정확한 결과를 얻을 수 있습니다.

최소 고유 방문자 요구 사항을 충족하지 않을 때 샘플링 제외 트레이트와 세그먼트를 사용하는 보고서입니다. 이러한 최소 요구 사항은 다음과 같습니다.

* 트레이트: 14일 동안 [고유한 특성](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) 인식
* 세그먼트: 14일 동안 실시간 사용자 70,000명

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

## 샘플링된 데이터를 사용하는 보고서 {#reports-using-sampled-data}

샘플링된 데이터를 사용하는 [!DNL Audience Manager] 보고서에는 다음이 포함됩니다.

* [보고서](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 겹치기(트레이트-투-트레이트, 세그먼트-세그먼트)
* [대응 가능 대상](../features/addressable-audiences.md) 데이터(고객 및 세그먼트 수준 데이터)
* 한 [장치의](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) 총 장치 [!UICONTROL Profile Merge Rule]지표입니다.
* [데이터 탐색기](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) 는 탭 및 모든 탭에서 [!UICONTROL Search] 샘플링된 데이터를 사용합니다 [!UICONTROL Saved Searches].