---
description: 세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-description: 세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-title: 세그먼트-세그먼트 Overlap Reports
solution: Audience Manager
title: 세그먼트-세그먼트 Overlap Reports
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 11%

---


# 세그먼트-세그먼트 Overlap Reports{#segment-to-segment-overlap-report}

세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹치기 보고서는 RBAC 원칙을 따릅니다. 사용자가 속한 [RBAC 사용자 그룹](/help/using/features/administration/administration-overview.md)을 기반으로 액세스할 수 있는 데이터 소스의 세그먼트만 볼 수 있습니다.

<!-- 

c_segment_segment_overlap.xml

 -->

## 개요

[!UICONTROL Segment-to-Segment Overlap] 보고서를 통해 다음을 수행할 수 있습니다.

* 요구 사항에 따라 겹치거나 낮은 세그먼트를 식별할 수 있습니다. 겹치는 트레이트는 타깃팅된 대상이지만 고유 방문자 수는 줄어듭니다. 오버랩이 낮은 트레이트는 더 크고 고유한 방문자 세트에 도달하는 데 유용합니다.
* 예상치 않은 겹치기 정보를 찾아 고성능 새로운 세그먼트를 작성합니다.

## 샘플 보고서

다음 그림은 [!UICONTROL Segment-to-Segment Overlap] 보고서의 수준 높은 개요를 제공합니다.

>[!NOTE]
>
>[!UICONTROL Segment-to-Segment Overlap] 보고서는 동일한 세그먼트를 자신과 비교할 때 빈 필드를 반환합니다.

![](assets/segment-to-segment-overlap.png)

## 개별 데이터 포인트 드릴다운

개별 포인트를 선택하여 팝업 창에서 데이터 세부 사항을 봅니다. 클릭 작업은 보고서에 표시된 데이터를 자동으로 업데이트합니다.

## 세그먼트에서 세그먼트로 겹치는 데이터 팝 필드 정의 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

[!UICONTROL Segment-to-Segment Overlap] 보고서의 팝업에 아래 지표가 포함되어 있습니다. 표의 고유 수 지표는 *실시간 사용자*&#x200B;를 나타냅니다.

| 지표 | 설명 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 보고서 결과에 나타나는 세그먼트의 고유 숫자 ID. 세그먼트에 대한 행 ID로 나타납니다. |
| **[!UICONTROL Base Segment Name]** | 보고서 결과 행에 표시되는 세그먼트의 이름입니다. |
| **[!UICONTROL Overlapping Segment ID]** | 보고서를 실행할 때 선택하는 세그먼트의 고유 숫자 ID. 세그먼트에 대한 열 ID로 나타납니다. |
| **[!UICONTROL Overlapping Segment Name]** | 보고서를 실행할 때 선택하는 세그먼트의 이름입니다. 보고서 결과 열에 나타납니다. |
| **[!UICONTROL Base Segment Uniques]** | 기본 세그먼트의 고유 방문자 수. |
| **[!UICONTROL Base Segment Uniques]** | 겹치는 세그먼트에서 고유 방문자 수. |
| **[!UICONTROL Overlapping Uniques]** | 비교 세그먼트 간에 공유된 고유 방문자 수. |
| **[!UICONTROL Overlap %]** | 겹침 %를 가져오려면 Audience Manager에서 다음 공식을 사용합니다.겹치는 고유 수 /(기본 세그먼트 고유 수 + 겹치는 세그먼트 고유 수 - 겹치는 고유 수) |



>[!MORELIKETHIS]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [대화형 보고서에 사용되는 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlap Reports: 일정 및 최소 세그먼트 크기 업데이트](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [Overlap Reports에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)