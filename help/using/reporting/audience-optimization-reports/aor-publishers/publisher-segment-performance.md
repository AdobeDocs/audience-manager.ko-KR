---
description: 세그먼트 성과 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 횟수 및 실시간 세그먼트 고유 수에 따라 비교합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다. 보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅을 위해 대상에 보낼 수 있는 간과된 세그먼트를 찾을 수 있습니다.
seo-description: 세그먼트 성과 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 횟수 및 실시간 세그먼트 고유 수에 따라 비교합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다. 보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅을 위해 대상에 보낼 수 있는 간과된 세그먼트를 찾을 수 있습니다.
seo-title: 세그먼트 성과 보고서
solution: Audience Manager
title: 세그먼트 성과 보고서
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 2%

---


# 세그먼트 성과 보고서{#segment-performance-report}

세그먼트 성과 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 횟수 및 실시간 세그먼트 고유 수에 따라 비교합니다.

매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상에 보내지 않은 세그먼트입니다.

보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅을 위해 대상에 보낼 수 있는 간과된 세그먼트를 찾을 수 있습니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment Performance] 보고서를 사용하여 다음을 수행할 수 있습니다.

* 규모 또는 성과를 높이는 매핑된 고객 세그먼트를 식별합니다.
* 대상의 과거 성과에 대한 기여도를 기반으로 향후 캠페인에 도입할 매핑되지 않은 세그먼트를 식별합니다.

## 세그먼트 성과 보고서 사용 {#using-segment-performance-report}

대상에 매핑된 세그먼트를 선택하려면 **[!UICONTROL Mapped]**&#x200B;과 **[!UICONTROL Unmapped]** 간을 전환합니다. 보고서에 모든 세그먼트를 포함하려면 **[!UICONTROL All]**&#x200B;을 선택합니다.

**일 범위** 및 **Date Through** 컨트롤을 사용하여 룩백 범위를 조정합니다. 7일 및 30일 룩백 기간은 일요일 날짜에만 사용할 수 있습니다.

**[!UICONTROL Line Item]** 드롭다운 상자를 사용하여 정보를 반환할 웹 속성을 선택합니다.

**[!UICONTROL Segment Data Source]** 드롭다운 상자에서 보고서에 표시할 세그먼트가 포함된 데이터 소스를 선택합니다.

**[!UICONTROL Segment]** 드롭다운 상자를 사용하여 보고서에 표시할 세그먼트를 선택합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때는 [Google Ad Manager 가져오기(이전 DFP) 데이터 파일을 Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)으로 가져오는 3단계에 설명된 대로 [!UICONTROL Line Item IDs]에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서가 웹 속성을 [!UICONTROL Line Item ID] 대신 [!UICONTROL Line Item](으)로 상세 정보로 지정하는지 확인합니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Segment Performance] 보고서가 아래 보고서와 유사할 수 있습니다. 보고서에서 버블을 클릭하여 기본 데이터를 봅니다. 샘플 보고서 아래 표에 나와 있는 추가 정보는 설명을 참조하십시오.

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
   <td colname="col2"> <p>이 세그먼트의 고유 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>라인 항목 </p> </td> 
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>클릭 수 </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 웹 속성의 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>노출 횟수 </p> </td> 
   <td colname="col2"> <p>이 특성 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. </p> <p>이 지표는 클릭으로 이어지는 노출 횟수를 나타냅니다. 클릭을 노출 횟수로 나누어 이 지표를 가져옵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>실시간 세그먼트 채우기 </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 보고, 해당 세그먼트에 자격을 갖춘 실제 고유 방문자 수입니다(<span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## 매핑된 세그먼트 결과를 읽는 방법 {#read-mapped-segment}

보고서에서 매핑된 세그먼트의 위치는 성과가 좋은 세그먼트와 조정이 필요한 위치에 대해 많은 것을 알 수 있습니다.

보고서를 읽으려면 결과를 가상의 선(빨간색)과 아래 샘플 보고서에 표시된 카테고리로 네 개의 섹션으로 나누는 데 도움이 됩니다. 예제의 레이블은 세그먼트 성능과 이러한 결과에 응답하는 방법을 이해하는 데 도움이 될 수 있습니다.

![](assets/publisher_segment_performance_mapped.png)

## 매핑되지 않은 세그먼트 결과를 읽는 방법 {#read-unmapped-segment}

[!UICONTROL Segment Performance] 보고서에서 매핑되지 않은 세그먼트를 보는 것은 타깃팅할 필요가 없는 새 세그먼트를 찾는 좋은 방법입니다. 실제로 이러한 세그먼트 중 일부는 매핑된 세그먼트보다 성과가 높을 수 있습니다.

이 보고서를 읽으려면 아래 샘플 보고서에 표시된 가상 선(빨간색)과 카테고리가 있는 네 개의 섹션으로 결과를 나누는 데 도움이 됩니다.

![](assets/publisher_segment_performance_unmapped.png)
