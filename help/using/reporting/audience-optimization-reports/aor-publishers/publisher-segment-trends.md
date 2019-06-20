---
description: 세그먼트 트렌드 보고서는 시간이 지남에 따라 매핑되지 않은 세그먼트와 매핑되지 않은 세그먼트의 노출 횟수 및 클릭스루 비율을 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 대상을 만들고 대상으로 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타깃팅을 위해 대상으로 보내지 않은 세그먼트입니다. 선택한 지표에 대한 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-description: 세그먼트 트렌드 보고서는 시간이 지남에 따라 매핑되지 않은 세그먼트와 매핑되지 않은 세그먼트의 노출 횟수 및 클릭스루 비율을 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 대상을 만들고 대상으로 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타깃팅을 위해 대상으로 보내지 않은 세그먼트입니다. 선택한 지표에 대한 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-title: 세그먼트 트렌드 보고서
solution: Audience Manager
title: 세그먼트 트렌드 보고서
uuid: F 84 E 8 D 0 A -74 E 5-430 C-B 61 C-EFB 696 FAEE 93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

세그먼트 트렌드 보고서는 시간이 지남에 따라 매핑되지 않은 세그먼트와 매핑되지 않은 세그먼트의 노출 횟수 및 클릭스루 비율을 반환합니다.

매핑된 세그먼트는 타깃팅을 위해 대상을 만들고 대상으로 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타깃팅을 위해 대상으로 보내지 않은 세그먼트입니다.

선택한 지표에 대한 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment Trend] 보고서를 사용하여 시간의 경과에 따른 세그먼트의 성능을 확인하고 강력한 성능 또는 규모를 기반으로 트렌드를 파악할 수 있습니다.

이 보고서를 사용하면 필요한 경우 DIP 또는 잘못된 증가 및 문제를 웹 속성에 표시할 수 있습니다. This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

**[!UICONTROL Date Through]** 슬라이더 아래의 세그먼트를 클릭하면 해당 세그먼트만 보고서에 유지하거나 제외하는 옵션이 표시됩니다.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

**[!UICONTROL Segment Data Source]** 드롭다운 상자에서 보고서에 표시할 세그먼트가 들어 있는 데이터 소스를 선택합니다.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

[!UICONTROL Segment Trend] 보고서는 14 일 간격에만 라인 그래프로 데이터를 반환합니다. 이 예에서는 매핑되지 않은 세그먼트와 매핑되지 않은 세그먼트 세트에 대한 노출 횟수 및 클릭스루 트렌드를 보여줍니다.

특정 세그먼트 트렌드에 대한 자세한 정보를 얻으려면 아무 라인이나 마우스로 가리킵니다. 샘플 보고서 아래 표의 추가 정보는 설명을 참조하십시오.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 항목 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트</span> </p> </td> 
   <td colname="col2"> <p>이 세그먼트에 할당한 영숫자 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 ID</span> </p> </td> 
   <td colname="col2"> <p>이 세그먼트의 고유 ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 라인 항목</span> </p> </td> 
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 클릭 수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트 구성원이 웹 속성에서 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 노출 횟수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. 이 지표는 클릭 수에 따른 노출 횟수의 백분율을 릴레이합니다. 이 지표를 얻으려면 노출 횟수로 클릭 수를 나눠야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 고유 방문자</span> </p> </td> 
   <td colname="col2"> <p>지난 30 일 이내의 세그먼트 구성원 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
