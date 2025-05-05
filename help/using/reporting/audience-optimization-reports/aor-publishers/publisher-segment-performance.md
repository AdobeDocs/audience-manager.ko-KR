---
description: 세그먼트 성능 보고서는 노출 횟수와 실시간 세그먼트 고유성별로 매핑된 세그먼트와 매핑되지 않은 세그먼트를 비교합니다. 매핑된 세그먼트는 만들고 타겟팅을 위해 대상으로 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타겟팅을 위해 대상으로 보내지 않은 세그먼트입니다. 보고서 내 및 보고서 간의 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고, 타깃팅을 위해 대상에 전송하려는 간과된 세그먼트를 찾는 데 도움이 됩니다.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: 게시자에 대한 세그먼트 성과 보고서
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# 세그먼트 성과 보고서{#segment-performance-report}

세그먼트 성능 보고서는 노출 횟수와 실시간 세그먼트 고유성별로 매핑된 세그먼트와 매핑되지 않은 세그먼트를 비교합니다.

매핑된 세그먼트는 만들고 타겟팅을 위해 대상으로 보내는 세그먼트입니다. 매핑되지 않은 세그먼트는 만들었지만 타겟팅을 위해 대상으로 보내지 않은 세그먼트입니다.

보고서 내 및 보고서 간의 이러한 서로 다른 세그먼트 유형을 비교하면 기존 캠페인을 최적화하고, 타깃팅을 위해 대상에 전송하려는 간과된 세그먼트를 찾는 데 도움이 됩니다.

## 사용 사례 {#use-cases}

[!UICONTROL Segment Performance] 보고서를 사용하여 다음을 수행할 수 있습니다.

* 규모나 성능을 주도하는 매핑된 대상자 세그먼트를 식별합니다.
* 과거 성과에 대한 대상자의 기여도를 기반으로 향후 캠페인에 도입할 매핑되지 않은 세그먼트를 식별합니다.

## 세그먼트 성과 보고서 사용 {#using-segment-performance-report}

**[!UICONTROL Mapped]**&#x200B;과(와) **[!UICONTROL Unmapped]** 사이를 전환하여 대상에 매핑되거나 매핑되지 않은 세그먼트를 선택합니다. 보고서에 모든 세그먼트를 포함하려면 **[!UICONTROL All]**&#x200B;을(를) 선택하십시오.

**일 범위** 및 **날짜 범위** 컨트롤을 사용하여 전환 확인 범위를 조정하세요. 7일 및 30일 전환 확인 기간은 일요일 날짜에만 사용할 수 있습니다.

**[!UICONTROL Line Item]** 드롭다운 상자를 사용하여 정보를 반환할 웹 속성을 선택합니다.

**[!UICONTROL Segment Data Source]** 드롭다운 상자에서 보고서에 표시할 세그먼트가 포함된 데이터 원본을 선택합니다.

보고서에 표시할 세그먼트를 선택하려면 **[!UICONTROL Segment]** 드롭다운 상자를 사용합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때 [Google 광고 관리자(이전의 DFP) 데이터 파일을 Audience Manager으로 가져오기](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)의 3단계에 설명된 대로 [!UICONTROL Line Item IDs]에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서에 웹 속성이 [!UICONTROL Line Item ID] 대신 [!UICONTROL Line Item] (으)로 자세히 설명되어 있습니다.

## 결과 해석 {#interpreting-results}

[!UICONTROL Segment Performance] 보고서는 아래 보고서와 유사할 수 있습니다. 보고서에서 버블을 클릭하여 기본 데이터를 봅니다. 샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

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
   <td colname="col2"> <p>이 세그먼트에 지정한 영숫자 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>세그먼트 ID </p> </td> 
   <td colname="col2"> <p>해당 세그먼트에 대한 고유 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>라인 항목 </p> </td> 
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>클릭수 </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 웹 속성의 항목을 클릭한 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>노출 횟수 </p> </td> 
   <td colname="col2"> <p>이 트레이트의 멤버가 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>클릭스루 비율. </p> <p>이 지표는 클릭 수에 따른 노출 비율을 전달합니다. 클릭을 노출수로 나누어 이 지표를 얻습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>실시간 세그먼트 채우기 </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>이(가) 열람한 시점에 지정된 시간 범위 동안 실시간으로 열람하고 세그먼트에 적합한 고유 방문자의 실제 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 매핑된 세그먼트 결과를 읽는 방법 {#read-mapped-segment}

보고서에서 매핑된 세그먼트의 위치는 성과가 좋은 세그먼트와 일부 조정을 수행해야 하는 위치에 대한 많은 정보를 알려 줄 수 있습니다.

보고서를 읽기 위해서는 가상 선 (빨간색)과 아래 샘플 보고서에 표시된 범주가 있는 네 개의 섹션으로 결과를 구분하는 것이 좋습니다. 예제의 레이블은 세그먼트 성능 및 이러한 결과에 응답하는 방법을 이해하는 데 도움이 될 수 있습니다.

![](assets/publisher_segment_performance_mapped.png)

## 매핑되지 않은 세그먼트 결과를 읽는 방법 {#read-unmapped-segment}

[!UICONTROL Segment Performance] 보고서에서 매핑되지 않은 세그먼트를 확인하는 것은 타깃팅으로 고려하지 않은 새 세그먼트를 찾는 좋은 방법입니다. 실제로 이러한 세그먼트 중 일부는 매핑된 세그먼트보다 뛰어난 성능을 발휘할 수 있습니다.

이 보고서를 읽으려면 아래 샘플 보고서에 표시된 범주와 가상 선(빨간색)으로 결과를 네 개의 섹션으로 구분하는 것이 좋습니다.

![](assets/publisher_segment_performance_unmapped.png)
