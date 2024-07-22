---
description: 세그먼트 트렌드 보고서는 시간 경과에 따른 매핑된 세그먼트와 매핑되지 않은 세그먼트의 노출수 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 만들고 타겟팅을 위해 대상으로 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타겟팅을 위해 대상으로 보내지 않은 세그먼트입니다. 선택한 지표에 대한 트렌드와 볼륨을 비교하여 대상자가 시간에 따라 어떻게 행동하는지 더 잘 이해합니다.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: 세그먼트 트렌드 보고서
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# 세그먼트 트렌드 보고서{#segment-trend-report}

세그먼트 트렌드 보고서는 시간 경과에 따른 매핑된 세그먼트와 매핑되지 않은 세그먼트의 노출수 및 클릭스루 비율에 대한 데이터를 반환합니다.

매핑된 세그먼트는 만들고 타겟팅을 위해 대상으로 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타겟팅을 위해 대상으로 보내지 않은 세그먼트입니다.

선택한 지표에 대한 트렌드와 볼륨을 비교하여 대상자가 시간에 따라 어떻게 행동하는지 더 잘 이해합니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment Trend] 보고서를 사용하여 시간 경과에 따른 세그먼트의 성능을 확인하고 강력한 성능 또는 규모에 따라 트렌드를 정확하게 파악할 수 있습니다.

이 보고서를 사용하면 급감 또는 잘못된 증가를 보여 주는 웹 속성을 이해하고 필요에 따라 문제를 해결할 수 있습니다. 이 보고서는 [!UICONTROL Segment Performance] 보고서에서 관심 대상을 식별한 다음 단계로, [!UICONTROL Segment Performance] 탭에서 확인한 강력하거나 낮은 성과가 시간이 지남에 따라 일관되도록 합니다.

## 세그먼트 트렌드 보고서 사용 {#using-the-report}

**[!UICONTROL Mapped]**&#x200B;과(와) **[!UICONTROL Unmapped]** 사이를 전환하여 대상에 매핑되거나 매핑되지 않은 세그먼트를 선택합니다. 보고서에 모든 세그먼트를 포함하려면 **[!UICONTROL All]**&#x200B;을(를) 선택하십시오.

**[!UICONTROL Date Through]** 슬라이더로 룩백 창을 조정합니다.

보고서에 해당 세그먼트만 유지하거나 제외하는 옵션을 표시하려면 **[!UICONTROL Date Through]** 슬라이더 아래의 세그먼트를 클릭하십시오.

**[!UICONTROL Line Item]** 드롭다운 상자를 사용하여 정보를 반환할 포트폴리오의 속성을 선택합니다.

**[!UICONTROL Segment Data Source]** 드롭다운 상자에서 보고서에 표시할 세그먼트가 포함된 데이터 원본을 선택합니다.

보고서에 표시할 세그먼트를 선택하려면 **[!UICONTROL Segment]** 드롭다운 상자를 사용합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때 [Google 광고 관리자(이전의 DFP) 데이터 파일을 Audience Manager으로 가져오기](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)의 3단계에 설명된 대로 [!UICONTROL Line Item] ID에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서에 웹 속성이 [!UICONTROL Line Item] ID 대신 [!UICONTROL Line Item](으)로 자세히 설명되어 있습니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Segment Trend] 보고서는 14일 간격 동안만 선 그래프로 데이터를 반환합니다. 이 예에서 보고서는 매핑되고 매핑되지 않은 세그먼트 세트의 노출 횟수 및 클릭스루 트렌드를 보여 줍니다.

특정 세그먼트 트렌드에 대한 자세한 내용을 보려면 모든 줄을 마우스로 가리킵니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col2"> <p>이 세그먼트에 지정한 영숫자 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 ID</span> </p> </td> 
   <td colname="col2"> <p>해당 세그먼트에 대한 고유 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 라인 항목</span> </p> </td> 
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">번의 클릭수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 웹 속성의 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle">개 노출 횟수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 멤버가 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. 이 지표는 클릭 수에 따른 노출 비율을 전달합니다. 클릭수를 노출수로 나누어 이 지표를 얻습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 고유 수</span> </p> </td> 
   <td colname="col2"> <p>지난 30일 이내의 세그먼트 멤버 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
