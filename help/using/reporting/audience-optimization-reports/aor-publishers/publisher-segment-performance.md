---
description: 세그먼트 성과 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 수와 실시간 세그먼트 고유 수로 비교합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상으로 전송하지 않은 세그먼트입니다. 보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅을 위해 대상에 보낼 수 있는 간과된 세그먼트를 찾을 수 있습니다.
seo-description: 세그먼트 성과 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 수와 실시간 세그먼트 고유 수로 비교합니다. 매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상으로 전송하지 않은 세그먼트입니다. 보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅을 위해 대상에 보낼 수 있는 간과된 세그먼트를 찾을 수 있습니다.
seo-title: 세그먼트 성과 보고서
solution: Audience Manager
title: 세그먼트 성과 보고서
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 세그먼트 성과 보고서{#segment-performance-report}

세그먼트 성과 보고서는 매핑된 세그먼트와 매핑되지 않은 세그먼트를 노출 수와 실시간 세그먼트 고유 수로 비교합니다.

매핑된 세그먼트는 타깃팅을 위해 만들어 대상에 전송하는 세그먼트입니다. 매핑되지 않은 세그먼트는 사용자가 만들었지만 타깃팅을 위해 대상으로 전송하지 않은 세그먼트입니다.

보고서 내 및 보고서 간에 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고 타깃팅을 위해 대상에 보낼 수 있는 간과된 세그먼트를 찾을 수 있습니다.

## 사용 사례 {#use-cases}

보고서를 사용하여 [!UICONTROL Segment Performance] 다음을 수행할 수 있습니다.

* 비율 또는 성과를 높이는 매핑된 고객 세그먼트를 식별합니다.
* 대상의 과거 성과에 대한 기여도를 기반으로 향후 캠페인에서 도입할 매핑되지 않은 세그먼트를 식별합니다.

## 세그먼트 성과 보고서 사용 {#using-segment-performance-report}

대상에 매핑되어 **[!UICONTROL Mapped]** 있는지 여부에 관계없이 및 **[!UICONTROL Unmapped]** 선택 간에 전환합니다. 보고서에 모든 세그먼트를 **[!UICONTROL All]** 포함하려면 선택합니다.

일 **범위** 및 **날짜** 스루 컨트롤을 사용하여 룩백 범위를 조정합니다. 7일 및 30일 룩백 기간은 일요일 날짜에만 사용할 수 있습니다.

드롭다운 상자를 사용하여 정보를 반환할 웹 속성을 선택합니다. **[!UICONTROL Line Item]**

드롭다운 **[!UICONTROL Segment Data Source]** 상자에서 보고서에 표시할 세그먼트가 들어 있는 데이터 소스를 선택합니다.

드롭다운 **[!UICONTROL Segment]** 상자를 사용하여 보고서에 표시할 세그먼트를 선택합니다.

>[!IMPORTANT]
>
>활성화할 [!UICONTROL Audience Optimization for Publishers]때 DFP 데이터 파일을 Audience Manager로 가져오기 3단계에 설명된 [!UICONTROL Line Item IDs]대로 [에 대한 설명 메타데이터를 포함해야 합니다](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). 이렇게 하면 보고서가 웹 속성이 [!UICONTROL Line Item] 아닌 웹 속성에 대한 세부 정보를 알 수 [!UICONTROL Line Item ID]있습니다.

## 결과 해석 {#interpreting-results}

보고서가 아래 보고서와 유사할 수 [!UICONTROL Segment Performance] 있습니다. 보고서에서 버블을 클릭하여 기본 데이터를 봅니다. 샘플 보고서 아래 표에 나와 있는 추가 정보는 설명을 참조하십시오.

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
   <td colname="col1"> <p> 세그먼트 ID </p> </td> 
   <td colname="col2"> <p>이 세그먼트의 고유 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>라인 항목 </p> </td> 
   <td colname="col2"> <p>이 보고서가 표시되는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>클릭 수 </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 웹 속성의 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>노출 횟수 </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. </p> <p>이 지표는 클릭 수에 따른 노출 비율을 나타냅니다. 클릭을 노출 횟수로 나누어 이 지표를 가져옵니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>실시간 세그먼트 채우기 </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 표시되고 Audience Manager가 본 순간에 세그먼트에 자격을 갖춘 실제 고유 방문자 <span class="keyword"> 수입니다</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 매핑된 세그먼트 결과를 읽는 방법 {#read-mapped-segment}

보고서에서 매핑된 세그먼트의 위치는 어떤 세그먼트가 잘 수행되고 있으며, 어떤 부분을 조정해야 할지 알려줍니다.

보고서를 읽으려면, 결과를 가상의 선(빨간색)과 아래 샘플 보고서에 표시된 카테고리로 네 개의 섹션으로 나눌 수 있습니다. 예제의 레이블은 세그먼트 성능과 이러한 결과에 응답하는 방법을 이해하는 데 도움이 될 수 있습니다.

![](assets/publisher_segment_performance_mapped.png)

## 매핑되지 않은 세그먼트 결과를 읽는 방법 {#read-unmapped-segment}

보고서에서 매핑되지 않은 세그먼트를 보는 것은 타깃팅하지 않은 새 세그먼트를 찾는 좋은 방법입니다. [!UICONTROL Segment Performance] 실제로 이러한 세그먼트 중 일부는 매핑된 세그먼트보다 성과가 클 수 있습니다.

이 보고서를 읽으려면 아래 샘플 보고서에 표시된 가상의 선(빨간색)과 카테고리가 있는 네 개의 섹션으로 결과를 나눌 수 있습니다.

![](assets/publisher_segment_performance_unmapped.png)
