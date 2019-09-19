---
description: 세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상으로 전송하지 않은 세그먼트입니다. 선택한 지표의 트렌드와 볼륨을 비교하여 시간의 경과에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-description: 세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상으로 전송하지 않은 세그먼트입니다. 선택한 지표의 트렌드와 볼륨을 비교하여 시간의 경과에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-title: 세그먼트 트렌드 보고서
solution: Audience Manager
title: 세그먼트 트렌드 보고서
uuid: f84e8d0a-74e5-43 파섹
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 세그먼트 트렌드 보고서{#segment-trend-report}

세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다.

매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상으로 전송하지 않은 세그먼트입니다.

선택한 지표의 트렌드와 볼륨을 비교하여 시간의 경과에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.

## 사용 사례 {#use-cases}

이 보고서를 사용하여 시간의 경과에 따른 세그먼트의 성과를 확인하고 강력한 성능 또는 규모에 따라 트렌드를 파악할 수 있습니다 [!UICONTROL Segment Trend] .

이 보고서를 사용하면 급감 또는 결함이 있는 웹 속성 중 어떤 웹 속성이 증가를 보이는지 파악하고 필요에 따라 문제를 해결할 수 있습니다. 이 보고서는 [!UICONTROL Segment Performance] 보고서에 관심 있는 대상을 식별한 후 다음 단계로, [!UICONTROL Segment Performance] 탭에서 확인한 성능이 시간이 지남에 따라 일관되도록 합니다.

## 세그먼트 트렌드 보고서 사용 {#using-the-report}

대상에 매핑되어 **[!UICONTROL Mapped]** 있는지 여부에 관계없이 및 **[!UICONTROL Unmapped]** 선택 간에 전환합니다. 보고서에 모든 세그먼트를 **[!UICONTROL All]** 포함하려면 선택합니다.

슬라이더를 사용하여 뒤쪽 창을 조정합니다. **[!UICONTROL Date Through]**

슬라이더 아래의 세그먼트를 클릭하면 보고서에 해당 세그먼트만 유지하거나 제외하는 옵션이 표시됩니다. **[!UICONTROL Date Through]**

드롭다운 상자를 사용하여 정보를 반환할 포트폴리오의 속성을 선택합니다. **[!UICONTROL Line Item]**

드롭다운 **[!UICONTROL Segment Data Source]** 상자에서 보고서에 표시할 세그먼트가 들어 있는 데이터 소스를 선택합니다.

드롭다운 **[!UICONTROL Segment]** 상자를 사용하여 보고서에 표시할 세그먼트를 선택합니다.

>[!IMPORTANT]
>
>활성화할 [!UICONTROL Audience Optimization for Publishers]때 Audience Manager로 DFP 데이터 파일 가져오기 3단계에 설명된 [!UICONTROL Line Item] 대로 ID에 [대한 설명 메타데이터를 포함해야 합니다](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서가 ID [!UICONTROL Line Item] 대신 웹 속성에 대한 세부 정보를 알 수 [!UICONTROL Line Item] 있습니다.

## 결과 해석 {#interpreting-results}

이 [!UICONTROL Segment Trend] 보고서는 14일 간격에 대해서만 라인 그래프로 데이터를 반환합니다. 이 예에서 보고서는 매핑되고 매핑되지 않은 세그먼트 집합에 대한 노출 및 클릭스루 트렌드를 보여줍니다.

특정 세그먼트 트렌드에 대한 자세한 정보를 얻으려면 임의의 줄을 마우스로 가리킵니다. 샘플 보고서 아래 표에 나와 있는 추가 정보는 설명을 참조하십시오.

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
   <td colname="col2"> <p>이 세그먼트의 고유 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 라인 항목</span> </p> </td> 
   <td colname="col2"> <p>이 보고서가 표시되는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 클릭 수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 웹 속성의 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 노출 횟수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. 이 지표는 클릭 수에 따른 노출 비율을 나타냅니다. 클릭을 노출 횟수로 나누어 이 지표를 가져옵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 고유</span> </p> </td> 
   <td colname="col2"> <p>지난 30일 이내의 세그먼트 구성원 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
