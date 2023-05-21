---
description: 세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: 세그먼트-세그먼트 Overlap Reports
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 10%

---

# 세그먼트-세그먼트 Overlap Reports{#segment-to-segment-overlap-report}

세그먼트 간에 공유되는 고유 사용자 수에 대한 데이터를 반환합니다.

>[!NOTE]
>
>Audience Manager의 겹치기 보고서는 RBAC 원칙을 준수합니다. 를 기반으로 액세스 권한이 있는 데이터 소스의 세그먼트만 볼 수 있습니다. [RBAC 사용자 그룹](/help/using/features/administration/administration-overview.md) 귀하가 속한 회사입니다.

<!-- 

c_segment_segment_overlap.xml

 -->

## 개요

다음 [!UICONTROL Segment-to-Segment Overlap] 보고서는 다음 작업에 유용합니다.

* 필요에 따라 겹치는 부분이 높거나 낮은 세그먼트를 식별합니다. 겹치는 정도가 높은 트레이트는 타깃팅된 대상을 제공하지만 고유 방문자 수는 줄어듭니다. 겹치는 정도가 낮은 트레이트는 더 크고 고유한 방문자 세트에 도달하기 위해 유용할 수 있습니다.
* 예기치 않은 겹침을 찾아 해당 정보를 사용하여 새로운 고성능 세그먼트를 작성하십시오.

## 샘플 보고서

다음 그림은 의 높은 수준의 개요를 제공합니다 [!UICONTROL Segment-to-Segment Overlap] 보고서.

>[!NOTE]
>
>다음 [!UICONTROL Segment-to-Segment Overlap] 보고서는 동일한 세그먼트를 자신과 비교할 때 빈 필드를 반환합니다.

![](assets/segment-to-segment-overlap.png)

## 개별 데이터 포인트 드릴다운

개별 포인트를 선택하여 팝업 창에서 데이터 세부 정보를 봅니다. 클릭 작업은 보고서에 표시된 데이터를 자동으로 업데이트합니다.

## 정의된 세그먼트-세그먼트 중복 데이터 팝업 필드 {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

다음에 대한 팝업 [!UICONTROL Segment-to-Segment Overlap] 보고서에는 아래 지표가 포함되어 있습니다. 표의 고유 수 지표는 다음을 나타냅니다. *실시간 사용자*.

| 지표 | 설명 |
|---|---|
| **[!UICONTROL Base Segment ID]** | 보고서 결과에 표시되는 세그먼트의 고유 숫자 ID입니다. 세그먼트의 행 ID로 표시됩니다. |
| **[!UICONTROL Base Segment Name]** | 보고서 결과 행에 표시되는 세그먼트의 이름입니다. |
| **[!UICONTROL Overlapping Segment ID]** | 보고서를 실행할 때 선택하는 세그먼트에 대한 고유 숫자 ID입니다. 세그먼트의 열 ID로 표시됩니다. |
| **[!UICONTROL Overlapping Segment Name]** | 보고서를 실행할 때 선택하는 세그먼트의 이름입니다. 보고서 결과 열에 나타납니다. |
| **[!UICONTROL Base Segment Uniques]** | 기본 세그먼트의 고유 방문자 수입니다. |
| **[!UICONTROL Base Segment Uniques]** | 겹치는 세그먼트의 고유 방문자 수입니다. |
| **[!UICONTROL Overlapping Uniques]** | 비교된 세그먼트 간에 공유된 고유 방문자의 수입니다. |
| **[!UICONTROL Overlap %]** | 겹침 %를 구하기 위해 Audience Manager은 다음 공식을 사용합니다. 겹침 고유 수 / (기본 세그먼트 고유 수 + 겹침 세그먼트 고유 수 - 겹침 고유) |



>[!MORELIKETHIS]
>
>* [데이터 슬라이더를 사용하여 보고서 결과 필터링](../../reporting/dynamic-reports/data-sliders.md)
>* [대화형 보고서에 사용되는 모양, 색상 및 크기](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [보고서 아이콘 및 도구 설명](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlap Reports: 일정 및 최소 세그먼트 크기 업데이트](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [선택한 Audience Manager 보고서의 데이터 샘플링 및 오류율...](../../reporting/report-sampling.md)
>* [Overlap Reports에 대한 CSV 파일](../../reporting/dynamic-reports/overlap-csv-files.md)

