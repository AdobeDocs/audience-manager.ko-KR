---
description: 세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-description: 세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-title: 세그먼트-세그먼트 중복 보고서
solution: Audience Manager
title: 세그먼트-세그먼트 중복 보고서
uuid: 0339eb6c-6355-44a3-9c46-f15948549d1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# 세그먼트-세그먼트 중복 보고서{#segment-to-segment-overlap-report}

세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 중복 보고서는 RBAC 원칙을 준수합니다. 사용자가 속한 RBAC 사용자 그룹을 기준으로 액세스할 수 있는 데이터 [소스에서만 세그먼트를](/help/using/features/administration/administration-overview.md) 볼 수 있습니다.

<!-- 

c_segment_segment_overlap.xml

 -->

## 개요

이 [!UICONTROL Segment-to-Segment Overlap] 보고서를 통해 다음과 같은 이점을 얻을 수 있습니다.

* 필요에 따라 겹치거나 낮은 겹치는 세그먼트를 식별합니다. 겹치는 트레이트는 타깃팅된 대상이지만 고유 방문자 수는 적습니다. 오버랩이 낮은 트레이트는 더 크고 고유한 방문자 세트에 도달하는 데 유용합니다.
* 예기치 않은 오버랩을 찾아 해당 정보를 사용하여 새로운 고성능 세그먼트를 작성합니다.

## 샘플 보고서

다음 그림은 [!UICONTROL Segment-to-Segment Overlap] 보고서에 대한 고급 개요를 제공합니다.

>[!NOTE]
>
>보고서는 동일한 세그먼트를 자신과 비교할 때 빈 필드를 반환합니다 [!UICONTROL Segment-to-Segment Overlap] .

![](assets/segment-to-segment-overlap.png)

## 개별 데이터 포인트 드릴다운

개별 포인트를 선택하여 팝업 창에서 데이터 세부 사항을 봅니다. 클릭 작업은 보고서에 표시된 데이터를 자동으로 업데이트합니다.

## 세그먼트에서 세그먼트로 겹치기 데이터 팝업 필드 정의 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

보고서의 팝업에 [!UICONTROL Segment-to-Segment Overlap] 아래 지표가 포함되어 있습니다. 표의 고유 수 지표는 *실시간 사용자를*&#x200B;나타냅니다.

| 지표 | 설명 |
|---|---|
| **[!UICONTROL Segment ID1]** | 보고서 결과에 표시되는 세그먼트의 고유 숫자 ID입니다. 세그먼트의 행 ID로 나타납니다. |
| **[!UICONTROL Segment ID2]** | 보고서를 실행할 때 선택하는 세그먼트의 고유 숫자 ID. 세그먼트의 열 ID로 나타납니다. |
| **[!UICONTROL Segment Name1]** | 보고서 결과 행에 표시되는 세그먼트의 이름입니다. |
| **[!UICONTROL Segment Name2]** | 보고서를 실행할 때 선택하는 세그먼트의 이름입니다. 보고서 결과 열에 나타납니다. |
| **[!UICONTROL Overlap %]** | 겹치는 비율을 얻기 위해 Audience Manager는 다음 공식을 사용합니다.겹치는 고유 수 /(기본 세그먼트 고유 수 + 겹치는 세그먼트 고유 수 - 겹치는 고유 수) |
| **[!UICONTROL Overlap Uniques]** | 비교 세그먼트 간에 공유된 고유 방문자 수. |
| **[!UICONTROL Segment Uniques1]** | 세그먼트 1의 고유 방문자 수. |
| **[!UICONTROL Segment Uniques2]** | 세그먼트 2의 고유 방문자 수. |

>[!MORELIKE_THIS]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [대화형 보고서에 사용된 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [중복 보고서:업데이트 일정 및 최소 세그먼트 크기](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서의 데이터 샘플링 및 오류 비율...](../../reporting/report-sampling.md)
>* [중복 보고서에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)