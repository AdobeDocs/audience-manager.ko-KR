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
source-wordcount: '535'
ht-degree: 2%

---

# 세그먼트 트렌드 보고서{#segment-trend-report}

세그먼트 트렌드 보고서는 시간 경과에 따른 매핑된 세그먼트와 매핑되지 않은 세그먼트의 노출수 및 클릭스루 비율에 대한 데이터를 반환합니다.

매핑된 세그먼트는 만들고 타겟팅을 위해 대상으로 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타겟팅을 위해 대상으로 보내지 않은 세그먼트입니다.

선택한 지표에 대한 트렌드와 볼륨을 비교하여 대상자가 시간에 따라 어떻게 행동하는지 더 잘 이해합니다.

## 사용 사례 {#use-cases}

사용 [!UICONTROL Segment Trend] 보고 를 통해 시간에 따른 세그먼트의 성능을 확인하고 강력한 성능 또는 규모를 기반으로 트렌드를 정확하게 파악할 수 있습니다.

이 보고서를 사용하면 급감 또는 잘못된 증가를 보여 주는 웹 속성을 이해하고 필요에 따라 문제를 해결할 수 있습니다. 이 보고서는 관심 대상을 식별한 다음 단계입니다. [!UICONTROL Segment Performance] 보고서에서 확인한 강력하거나 낮은 성과를 확인합니다. [!UICONTROL Segment Performance] 탭은 시간이 지남에 따라 일관됩니다.

## 세그먼트 트렌드 보고서 사용 {#using-the-report}

전환 **[!UICONTROL Mapped]** 및 **[!UICONTROL Unmapped]** 대상에 매핑된 세그먼트를 선택하거나 선택하지 않습니다. 선택 **[!UICONTROL All]** 를 클릭하여 보고서에 모든 세그먼트를 포함합니다.

를 사용하여 룩백 창 조정 **[!UICONTROL Date Through]** 슬라이더.

아래의 세그먼트를 클릭합니다. **[!UICONTROL Date Through]** 슬라이더를 사용하여 보고서에 해당 세그먼트만 유지하거나 제외하는 옵션을 표시합니다.

사용 **[!UICONTROL Line Item]** 포트폴리오에서 정보를 반환할 속성을 선택하는 드롭다운 상자입니다.

다음에서 **[!UICONTROL Segment Data Source]** 드롭다운 상자에서, 보고서에 표시하려는 세그먼트가 포함된 데이터 소스를 선택합니다.

사용 **[!UICONTROL Segment]** 보고서에 표시할 세그먼트를 선택하는 드롭다운 상자입니다.

>[!IMPORTANT]
>
>활성화 시 [!UICONTROL Audience Optimization for Publishers], 다음에 대한 설명 메타데이터를 포함해야 합니다. [!UICONTROL Line Item] 의 3단계에 설명된 ID [Google Ad Manager(이전의 DFP) 데이터 파일을 Audience Manager에 가져오기](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서에서 다음과 같이 웹 속성을 자세히 알 수 있습니다. [!UICONTROL Line Item] 대신 [!UICONTROL Line Item] ID

## 결과 해석 {#interpreting-results}

다음 [!UICONTROL Segment Trend] 보고서는 14일 간격에 대해서만 선 그래프로 데이터를 반환합니다. 이 예에서 보고서는 매핑되고 매핑되지 않은 세그먼트 세트의 노출 횟수 및 클릭스루 트렌드를 보여 줍니다.

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
   <td colname="col1"> <p><span class="wintitle"> 클릭 수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 웹 속성의 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 노출 횟수</span> </p> </td> 
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
