---
description: 세그먼트 트렌드 보고서는 시간에 따른 매핑된 세그먼트와 매핑되지 않은 세그먼트의 노출 횟수 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타겟팅을 위해 만들고 대상에 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타겟팅을 위해 대상에 전송하지 않은 세그먼트입니다. 선택한 지표에 대한 트렌드 및 볼륨을 비교하여 시간이 지남에 따라 대상이 어떻게 작동하는지 더 잘 파악할 수 있습니다.
seo-description: 세그먼트 트렌드 보고서는 시간에 따른 매핑된 세그먼트와 매핑되지 않은 세그먼트의 노출 횟수 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타겟팅을 위해 만들고 대상에 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타겟팅을 위해 대상에 전송하지 않은 세그먼트입니다. 선택한 지표에 대한 트렌드 및 볼륨을 비교하여 시간이 지남에 따라 대상이 어떻게 작동하는지 더 잘 파악할 수 있습니다.
seo-title: 세그먼트 트렌드 보고서
solution: Audience Manager
title: 세그먼트 트렌드 보고서
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: 대상 최적화 보고서
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# 세그먼트 트렌드 보고서{#segment-trend-report}

세그먼트 트렌드 보고서는 시간에 따른 매핑된 세그먼트와 매핑되지 않은 세그먼트의 노출 횟수 및 클릭스루 비율에 대한 데이터를 반환합니다.

매핑된 세그먼트는 타겟팅을 위해 만들고 대상에 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타겟팅을 위해 대상에 전송하지 않은 세그먼트입니다.

선택한 지표에 대한 트렌드 및 볼륨을 비교하여 시간이 지남에 따라 대상이 어떻게 작동하는지 더 잘 파악할 수 있습니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment Trend] 보고서를 사용하여 시간에 따른 세그먼트 성능을 확인하고 강력한 성능 또는 규모에 따른 트렌드를 파악합니다.

이 보고서를 사용하면 딥 또는 오류 증가를 보여 주는 웹 속성 중 하나를 이해하고 필요에 따라 문제를 해결할 수 있습니다. 이 보고서는 [!UICONTROL Segment Performance] 보고서에서 관심 있는 대상을 식별한 후 다음 단계로, [!UICONTROL Segment Performance] 탭에서 본 강력하고 느린 성능이 시간에 따라 일관되는지 확인합니다.

## 세그먼트 트렌드 보고서 사용 {#using-the-report}

**[!UICONTROL Mapped]** 과 **[!UICONTROL Unmapped]** 간을 전환하여 대상에 매핑되거나 매핑되지 않은 세그먼트를 선택합니다. 보고서에 모든 세그먼트를 포함하려면 **[!UICONTROL All]** 을 선택합니다.

**[!UICONTROL Date Through]** 슬라이더를 사용하여 뒤로 보기 창을 조정합니다.

보고서에서 해당 세그먼트만 유지하거나 제외하는 옵션을 표시하려면 **[!UICONTROL Date Through]** 슬라이더 아래의 세그먼트를 클릭합니다.

**[!UICONTROL Line Item]** 드롭다운 상자를 사용하여 정보를 반환할 포트폴리오의 속성을 선택합니다.

**[!UICONTROL Segment Data Source]** 드롭다운 상자에서 보고서에 표시할 세그먼트가 들어 있는 데이터 소스를 선택합니다.

**[!UICONTROL Segment]** 드롭다운 상자를 사용하여 보고서에 표시할 세그먼트를 선택합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때, [!UICONTROL Line Item] ID에 대한 수사적 메타데이터를 포함해야 합니다. 자세한 내용은 [Google Ad Manager 가져오기(이전의 DFP) 데이터 파일을 Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)에 가져오는 단계에 설명되어 있습니다. 이렇게 하면 보고서에 웹 속성이 [!UICONTROL Line Item] ID 대신 [!UICONTROL Line Item]으로 자세히 설명되어 있는지 확인합니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Segment Trend] 보고서는 14일 간격에 대해서만 선 그래프의 데이터를 반환합니다. 이 예에서 보고서는 매핑되고 매핑되지 않은 세그먼트 집합에 대한 노출과 클릭스루 트렌드를 보여줍니다.

마우스를 라인 위로 가져가면 해당 특정 세그먼트 트렌드에 대한 자세한 정보가 표시됩니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col2"> <p>이 세그먼트의 고유 ID입니다. </p> </td> 
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
   <td colname="col2"> <p>이 트레이트의 구성원이 인벤토리에 노출되는 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. 이 지표는 클릭스루로 이어지는 노출 횟수를 보여줍니다. 클릭 수를 노출 횟수로 나누어 이 지표를 가져옵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 고유 사항</span> </p> </td> 
   <td colname="col2"> <p>지난 30일 이내의 세그먼트 멤버 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
