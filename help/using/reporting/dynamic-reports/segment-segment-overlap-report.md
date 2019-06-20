---
description: 세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-description: 세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-title: 세그먼트-세그먼트 중복 보고서
solution: Audience Manager
title: 세그먼트-세그먼트 중복 보고서
uuid: 0339 EB 6 C -6355-44 A 3-9 C 46-F 159485449 D 1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# 세그먼트-세그먼트 중복 보고서{#segment-to-segment-overlap-report}

세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹침 보고서는 RBAC 원칙을 준수합니다. You can only see segments from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_segment_overlap.xml

 -->

## 개요

[!UICONTROL Segment-to-Segment Overlap] 이 보고서는 다음과 같은 도움을 줍니다.

* 필요에 따라 겹치거나 낮은 오버랩으로 세그먼트를 식별할 수 있습니다. 오버랩이 높은 트레이트는 대상화된 대상이지만 고유 방문자 수는 적습니다. 오버랩이 낮은 트레이트는 고유한 방문자 세트에 도달하는 데 유용합니다.
* 예상치 못한 오버랩을 찾아 해당 정보를 사용하여 새로운 고성능 세그먼트를 구축할 수 있습니다.

## 샘플 보고서

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Segment Overlap] report.

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap] 보고서는 동일한 세그먼트를 자신끼리 비교할 때 빈 필드를 반환합니다.

![](assets/segment-to-segment-overlap.png)

## 개별 데이터 포인트 드릴다운

팝업 창에서 데이터를 볼 개별 지점을 선택합니다. 클릭 동작은 보고서에 표시되는 데이터를 자동으로 업데이트합니다.

## Segment-to-Segment Overlap Data Pop Fields Defined {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Segment Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

| 지표 | 설명 |
|---|---|
| **[!UICONTROL Segment ID1]** | 보고서 결과에 나타나는 세그먼트에 대한 고유한 숫자 ID. 세그먼트에 대한 행 ID로 나타납니다. |
| **[!UICONTROL Segment ID2]** | 보고서를 실행할 때 선택하는 세그먼트에 대한 고유 숫자 ID. 세그먼트에 대한 열 ID로 나타납니다. |
| **[!UICONTROL Segment Name1]** | 보고서 결과 행에 나타나는 세그먼트 이름입니다. |
| **[!UICONTROL Segment Name2]** | 보고서를 실행할 때 선택하는 세그먼트 이름입니다. 은 보고서 결과 열에 나타납니다. |
| **[!UICONTROL Overlap %]** | 겹침 비율을 얻기 위해 Audience Manager는 다음 공식을 사용합니다. 중첩 고유 항목/(기본 세그먼트 고유 항목 + 중복 세그먼트 고유 자릿수 - 고유 방문자 수) |
| **[!UICONTROL Overlap Uniques]** | 비교 세그먼트 간에 공유되는 고유 방문자 수. |
| **[!UICONTROL Segment Uniques1]** | 세그먼트 1의 고유 방문자 수. |
| **[!UICONTROL Segment Uniques2]** | 세그먼트 2의 고유 방문자 수. |

>[!MORE_ like_ this]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [대화형 보고서에 사용된 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [겹침 보고서: 업데이트 예약 및 최소 세그먼트 크기](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서에서 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [중복 보고서에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)