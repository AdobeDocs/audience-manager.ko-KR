---
description: 세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다. 선택한 지표의 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-description: 세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다. 선택한 지표의 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-title: 세그먼트 트렌드 보고서
solution: Audience Manager
title: 세그먼트 트렌드 보고서
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 3%

---


# 세그먼트 트렌드 보고서{#segment-trend-report}

세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다.

매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다.

선택한 지표의 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.

## 사용 사례 {#use-cases}

이 보고서를 [!UICONTROL Segment Trend] 사용하여 시간의 경과에 따른 세그먼트 성과를 확인하고 강력한 성능 또는 규모에 따라 트렌드를 파악할 수 있습니다.

이 보고서를 사용하면 급감 또는 잘못된 증가 및 문제 해결을 표시하는 웹 속성을 이해할 수 있습니다. 이 보고서는 탭에 나타난 성능 또는 성능이 시간의 경과에 따라 일관되도록 하기 위해 [!UICONTROL Segment Performance] 보고서에 관심 있는 대상을 식별한 다음 [!UICONTROL Segment Performance] 단계입니다.

## 세그먼트 트렌드 보고서 사용 {#using-the-report}

대상 **[!UICONTROL Mapped]** 에 **[!UICONTROL Unmapped]** 매핑되거나 설정되지 않은 세그먼트를 선택할 수 있도록 전환합니다. 보고서에 모든 세그먼트 **[!UICONTROL All]** 를 포함하려면 선택합니다.

슬라이더를 사용하여 뒤쪽 창을 **[!UICONTROL Date Through]** 조정합니다.

슬라이더 아래의 세그먼트 중 **[!UICONTROL Date Through]** 하나를 클릭하여 보고서에 해당 세그먼트만 유지하거나 제외하는 옵션을 표시합니다.

포트폴리오 **[!UICONTROL Line Item]** 에서 정보를 반환할 속성을 선택하려면 드롭다운 상자를 사용합니다.

드롭다운 **[!UICONTROL Segment Data Source]** 상자에서 보고서에 표시할 세그먼트가 들어 있는 데이터 소스를 선택합니다.

드롭다운 **[!UICONTROL Segment]** 상자를 사용하여 보고서에 표시할 세그먼트를 선택합니다.

>[!IMPORTANT]
>
>활성화할 [!UICONTROL Audience Optimization for Publishers]때 DFP 데이터 파일을 Audience Manager으로 [!UICONTROL Line Item] 가져오기 3단계에 설명된 대로 [ID에 대한 설명 메타데이터를 포함해야 합니다](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서가 ID 대신 웹 속성 [!UICONTROL Line Item] 을 자세히 알 수 [!UICONTROL Line Item] 있습니다.

## 결과 해석 {#interpreting-results}

보고서는 [!UICONTROL Segment Trend] 14일 간격에만 대한 라인 그래프로 데이터를 반환합니다. 이 예에서 보고서는 매핑되고 매핑되지 않은 세그먼트 집합에 대한 노출 및 클릭스루 트렌드를 보여줍니다.

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
   <td colname="col2"> <p>이 특성 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. 이 지표는 클릭으로 이어지는 노출 횟수를 나타냅니다. 클릭을 노출 횟수로 나누어 이 지표를 가져옵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 세그먼트 고유</span> </p> </td> 
   <td colname="col2"> <p>지난 30일 이내의 세그먼트 구성원 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
