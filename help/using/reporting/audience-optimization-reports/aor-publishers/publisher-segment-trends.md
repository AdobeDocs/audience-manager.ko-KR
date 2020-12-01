---
description: 세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다. 선택한 지표의 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-description: 세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다. 선택한 지표의 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.
seo-title: 세그먼트 트렌드 보고서
solution: Audience Manager
title: 세그먼트 트렌드 보고서
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---


# 세그먼트 트렌드 보고서{#segment-trend-report}

세그먼트 트렌드 보고서는 시간에 따라 매핑되고 매핑되지 않은 세그먼트의 노출 및 클릭스루 비율에 대한 데이터를 반환합니다.

매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다.

선택한 지표의 트렌드와 볼륨을 비교하여 시간이 지남에 따라 고객의 행동을 보다 정확하게 파악할 수 있습니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment Trend] 보고서를 사용하여 시간의 경과에 따른 세그먼트의 성과를 확인하고 강력한 성능 또는 비율에 따른 트렌드를 파악할 수 있습니다.

이 보고서를 사용하면 급감 또는 잘못된 증가 및 문제 해결을 표시하는 웹 속성을 이해할 수 있습니다. 이 보고서는 [!UICONTROL Segment Performance] 보고서에서 보고 있는 성능이 강력하거나 좋지 않은지 확인하기 위해 관심 있는 고객을 식별한 다음 단계입니다. [!UICONTROL Segment Performance] 탭에서 시간이 지남에 따라 일관됩니다.

## 세그먼트 트렌드 보고서 사용 {#using-the-report}

대상에 매핑된 세그먼트를 선택하려면 **[!UICONTROL Mapped]**&#x200B;과 **[!UICONTROL Unmapped]** 간을 전환합니다. 보고서에 모든 세그먼트를 포함하려면 **[!UICONTROL All]**&#x200B;을 선택합니다.

**[!UICONTROL Date Through]** 슬라이더를 사용하여 뒤로 보기를 조정합니다.

**[!UICONTROL Date Through]** 슬라이더 아래의 세그먼트를 클릭하여 보고서에 해당 세그먼트만 유지하거나 제외하는 옵션을 표시합니다.

**[!UICONTROL Line Item]** 드롭다운 상자를 사용하여 정보를 반환할 포트폴리오의 속성을 선택합니다.

**[!UICONTROL Segment Data Source]** 드롭다운 상자에서 보고서에 표시할 세그먼트가 포함된 데이터 소스를 선택합니다.

**[!UICONTROL Segment]** 드롭다운 상자를 사용하여 보고서에 표시할 세그먼트를 선택합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때는 [Google Ad Manager 가져오기(이전 DFP) 데이터 파일을 Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)으로 가져오기 3단계에 설명된 대로 [!UICONTROL Line Item] ID에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서가 웹 속성을 [!UICONTROL Line Item] ID 대신 [!UICONTROL Line Item](으)로 상세 정보로 지정하는지 확인합니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Segment Trend] 보고서는 14일 간격에 대해서만 라인 그래프로 데이터를 반환합니다. 이 예에서 보고서는 매핑되고 매핑되지 않은 세그먼트 집합에 대한 노출 및 클릭스루 트렌드를 보여줍니다.

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
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
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
