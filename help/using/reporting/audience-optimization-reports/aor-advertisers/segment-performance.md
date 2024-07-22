---
description: 세그먼트 성능 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 및 전환율별로 비교합니다. 매핑된 세그먼트는 만들고 타겟팅을 위해 대상으로 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타겟팅을 위해 대상으로 보내지 않은 세그먼트입니다. 보고서 내 및 보고서 간의 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고, 타깃팅을 위해 대상에 전송하려는 간과된 세그먼트를 찾는 데 도움이 됩니다.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 세그먼트 성과 보고서
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# 세그먼트 성과 보고서{#segment-performance-report}

[!UICONTROL Segment Performance] 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 및 전환율별로 비교합니다. 매핑된 세그먼트는 만들고 타겟팅을 위해 대상으로 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타겟팅을 위해 대상으로 보내지 않은 세그먼트입니다. 보고서 내 및 보고서 간의 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고, 타깃팅을 위해 대상에 전송하려는 간과된 세그먼트를 찾는 데 도움이 됩니다.

## 매핑된 세그먼트 결과를 읽는 방법 {#read-mapped-segment-results}

매핑된 [!UICONTROL Segment Performance] 보고서에는 타깃팅을 위해 만들고 대상으로 보낸 모든 세그먼트가 표시됩니다. 보고서에서 매핑된 세그먼트의 위치는 성과가 좋은 세그먼트와 조정을 수행해야 하는 위치에 대해 많은 정보를 알려 줄 수 있습니다.

보고서를 읽기 위해 가상 선(빨간색)과 아래 샘플 보고서에 표시된 범주가 있는 4개의 섹션으로 결과를 구분하는 데 도움이 됩니다.

![](assets/mapped-segment-performance.png)

예제와 다음 표의 레이블은 세그먼트 성능과 이러한 결과에 응답하는 방법을 이해하는 데 도움이 됩니다.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 위치 </th> 
   <th colname="col2" class="entry"> 배치 표시 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>왼쪽 위</b> </p> </td> 
   <td colname="col2"> <p>전환율이 좋습니다. </p> <p>노출 횟수를 늘리면 더 많은 전환을 얻을 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>왼쪽 아래</b> </p> </td> 
   <td colname="col2"> <p>낮은 전환율. </p> <p>이러한 세그먼트를 타겟팅하는 것을 피하고 싶을 수 있습니다. 이 섹션의 세그먼트는 매핑되지 않은 세그먼트 결과의 세그먼트와 비교할 수 있는 좋은 후보입니다. 매핑되지 않은 세그먼트 중 일부는 이미 타겟팅하는 세그먼트보다 성능이 더 좋을 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 위</b> </p> </td> 
   <td colname="col2"> <p>강력한 성능. 이러한 세그먼트는 그대로 두십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 아래</b> </p> </td> 
   <td colname="col2"> <p>낮은 전환율과 높은 노출 횟수. </p> <p>이 섹션의 세그먼트가 제대로 작동하지 않습니다. 예산을 이러한 세그먼트에서 벗어나 보고서의 왼쪽 상단 사분면에 있는 세그먼트로 이동하려는 경우 이렇게 하면 노출을 줄이고 이 오른쪽 아래 섹션에 있는 세그먼트의 전환율을 개선하는 데 도움이 될 수 있습니다. 또한 이렇게 매핑된 세그먼트를 매핑되지 않은 세그먼트와 비교합니다. 매핑되지 않은 세그먼트 중 일부는 이미 타겟팅하는 세그먼트보다 성능이 더 좋을 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 매핑되지 않은 세그먼트 결과를 읽는 방법 {#read-unmapped-segment-results}

[!UICONTROL Segment Performance] 보고서에서 매핑되지 않은 세그먼트를 확인하는 것은 타깃팅으로 고려하지 않은 새 세그먼트를 찾는 좋은 방법입니다. 실제로 이러한 세그먼트 중 일부는 매핑된 세그먼트보다 뛰어난 성능을 발휘할 수 있습니다. 매핑되지 않은 세그먼트는 이 보고서에 포함할 자격 기준 세트를 충족해야 하기 때문입니다. 이 보고서에 포함되려면 매핑되지 않은 세그먼트가 있어야 합니다.

* 전환율이 매핑된 모든 세그먼트의 평균보다 큽니다.
* 전환율별로 매핑되지 않은 상위 100개 세그먼트에 있어야 합니다.

이 보고서를 읽으려면 아래 샘플 보고서에 표시된 범주와 가상 선(빨간색)이 있는 4개의 섹션으로 결과를 구분하는 데 도움이 됩니다.

![](assets/unmapped-segment-performance.png)

이 보고서에서는 왼쪽 상단 섹션의 매핑되지 않은 세그먼트에 초점을 맞출 수 있습니다. 매핑되지 않은 이러한 세그먼트는 다른 세 섹션의 세그먼트와 비교하여 낮은 노출 수준에 대해 높은 전환율을 나타냅니다.

>[!NOTE]
>
>7일 및 30일 룩백 기간은 일요일 **[!UICONTROL Date Through]** 날짜에만 사용할 수 있습니다.
