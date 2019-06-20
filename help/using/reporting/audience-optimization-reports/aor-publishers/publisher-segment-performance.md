---
description: 세그먼트 성과 보고서는 노출 횟수 및 실시간 세그먼트 고유 수를 기준으로 매핑되지 않은 세그먼트와 매핑되지 않은 세그먼트를 비교합니다. 매핑된 세그먼트는 타깃팅을 위해 대상을 만들고 대상으로 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타깃팅을 위해 대상으로 보내지 않은 세그먼트입니다. 보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅하기 위해 대상으로 전송할 간과된 세그먼트를 찾을 수 있습니다.
seo-description: 세그먼트 성과 보고서는 노출 횟수 및 실시간 세그먼트 고유 수를 기준으로 매핑되지 않은 세그먼트와 매핑되지 않은 세그먼트를 비교합니다. 매핑된 세그먼트는 타깃팅을 위해 대상을 만들고 대상으로 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타깃팅을 위해 대상으로 보내지 않은 세그먼트입니다. 보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅하기 위해 대상으로 전송할 간과된 세그먼트를 찾을 수 있습니다.
seo-title: 세그먼트 성능 보고서
solution: Audience Manager
title: 세그먼트 성능 보고서
uuid: c 9 a 1 e 9 ad -4 f 3 f -4334-a 3 ff -0 f 241 c 7303 c 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Performance Report{#segment-performance-report}

세그먼트 성과 보고서는 노출 횟수 및 실시간 세그먼트 고유 수를 기준으로 매핑되지 않은 세그먼트와 매핑되지 않은 세그먼트를 비교합니다.

매핑된 세그먼트는 타깃팅을 위해 대상을 만들고 대상으로 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타깃팅을 위해 대상으로 보내지 않은 세그먼트입니다.

보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅하기 위해 대상으로 전송할 간과된 세그먼트를 찾을 수 있습니다.

## 사용 사례 {#use-cases}

With the [!UICONTROL Segment Performance] report, you can:

* 확장 또는 성과를 유도하는 매핑된 고객 세그먼트를 식별합니다.
* 이전 성과에 대한 대상의 기여도를 기반으로 향후 캠페인에 소개할 매핑되지 않은 세그먼트를 식별합니다.

## Using the Segment Performance Report {#using-segment-performance-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. 7 일과 30 일 룩백 기간은 일요일 날짜에 대해서만 사용할 수 있습니다.

Use the **[!UICONTROL Line Item]** drop-down box to select the web properties for which you want to return information.

**[!UICONTROL Segment Data Source]** 드롭다운 상자에서 보고서에 표시할 세그먼트가 들어 있는 데이터 소스를 선택합니다.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item ID].

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Performance] 보고서가 아래 나와 표시될 수 있습니다. 보고서에서 거품을 클릭하여 기본 데이터를 봅니다. 샘플 보고서 아래 표의 추가 정보는 설명을 참조하십시오.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 항목 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>세그먼트 </p> </td> 
   <td colname="col2"> <p>이 세그먼트에 할당한 영숫자 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>세그먼트 ID </p> </td> 
   <td colname="col2"> <p>이 세그먼트의 고유 ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>라인 항목 </p> </td> 
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>클릭 수 </p> </td> 
   <td colname="col2"> <p>이 트레이트 구성원이 웹 속성에서 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>노출 횟수 </p> </td> 
   <td colname="col2"> <p>이 트레이트 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. </p> <p>이 지표는 클릭 수에 따른 노출 횟수의 백분율을 릴레이합니다. 이 지표를 얻으려면 노출 횟수로 클릭 수를 나눠야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>실시간 세그먼트 모집단 </p> </td> 
   <td colname="col2"> <p>The actual number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Mapped Segment Results {#read-mapped-segment}

보고서에서 매핑된 세그먼트의 위치는 성과가 좋은 세그먼트 및 일부 조정을 수행해야 하는 부분을 알 수 있습니다.

보고서를 읽으려면 결과를 가상 줄 (빨간색) 와 아래의 샘플 보고서에 표시된 카테고리로 나누는 데 도움이 됩니다. 예제의 레이블은 세그먼트 성능과 이러한 결과에 응답하는 방법을 이해하는 데 도움이 됩니다.

![](assets/publisher_segment_performance_mapped.png)

## How to Read Your Unmapped Segment Results {#read-unmapped-segment}

[!UICONTROL Segment Performance] 보고서에서 매핑되지 않은 세그먼트를 보면 타깃팅으로 간주하지 않은 새 세그먼트를 찾을 수 있습니다. 실제로 이러한 세그먼트 중 일부는 매핑된 세그먼트를 능가할 수 있습니다.

이 보고서를 읽으려면 결과를 아래의 샘플 보고서에 표시된 가상 라인 (빨간색) 와 카테고리에서 4 개의 섹션으로 나누는 것이 도움이 됩니다.

![](assets/publisher_segment_performance_unmapped.png)
