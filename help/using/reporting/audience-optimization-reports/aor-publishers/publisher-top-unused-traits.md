---
description: 상위 사용하지 않는 트레이트는 트레이트 유형, 데이터 소스 및 성능에 따라 세그먼트의 아직 구성원이 아닌 트레이트의 분산형 다이어그램으로 표시됩니다.
seo-description: 상위 사용하지 않는 트레이트는 트레이트 유형, 데이터 소스 및 성능에 따라 세그먼트의 아직 구성원이 아닌 트레이트의 분산형 다이어그램으로 표시됩니다.
seo-title: 상위 사용하지 않는 특성
solution: Audience Manager
title: 상위 사용하지 않는 특성
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: 대상 최적화 보고서
exl-id: d0ae72c0-1fb1-423a-a7e6-de955bd7f3c5
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 2%

---

# 상위 사용하지 않는 특성{#top-unused-traits}

상위 사용하지 않는 트레이트는 트레이트 유형, 데이터 소스 및 성능에 따라 세그먼트의 아직 구성원이 아닌 트레이트의 분산형 다이어그램으로 표시됩니다.

## 사용 사례 {#use-cases}

[!UICONTROL Top Unused Traits] 보고서를 사용하여 현재 세그먼트에 매핑되지 않은 자사 트레이트와 타사 트레이트의 성과를 분석하고 비교할 수 있습니다. 이 보기는 캠페인 최적화 또는 새로운 기회를 위해 대상 세그먼트에서 사용할 최상의 트레이트를 가리킬 수 있습니다.

## 사용하지 않는 상위 특성 보고서 사용 {#using-the-report}

**[!UICONTROL Data Provider Type]** 컨트롤을 사용하여 자사 트레이트와 타사 트레이트 간을 전환합니다. 보고서에서 자사 및 타사 트레이트를 반환하려면 **[!UICONTROL All]** 을 선택합니다.

**[!UICONTROL Impressions]** 슬라이더를 사용하여 반환된 노출에 대한 최소값과 최대값을 선택할 수 있습니다. 설정한 제한보다 작거나 더 많은 트레이트를 담당하는 모든 트레이트는 보고서에 표시되지 않습니다.

**[!UICONTROL Day Range]** 및 **[!UICONTROL Date Through]** 컨트롤을 사용하여 전환 확인 범위를 조정합니다. 이 보고서에는 30일 전환 확인 기간만 사용할 수 있습니다.

**[!UICONTROL Order]** 드롭다운 상자를 사용하여 정보를 반환할 포트폴리오의 웹 속성을 선택합니다.

**[!UICONTROL Data Provider]** 드롭다운 상자에서 보고서에 표시할 트레이트가 포함된 데이터 소스를 선택합니다.

**[!UICONTROL Traits]** 드롭다운 상자를 사용하여 보고서에 표시할 트레이트를 선택합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때, [!UICONTROL Order IDs]에 대한 설명 메타데이터를 포함해야 합니다. 자세한 내용은 [Google Ad Manager 가져오기(이전 DFP) 데이터 파일을 Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)에 가져오는 단계에 설명되어 있습니다. 이렇게 하면 보고서에 웹 속성이 [!UICONTROL Order ID] 대신 [!UICONTROL Order](으)로 자세히 설명되어 있는지 확인합니다.

## 결과 해석 {#interpreting-results}

**샘플 보고서**

[!UICONTROL Top Unused Traits] 보고서는 아래 보고서와 유사할 수 있습니다. 보고서에서 버블을 클릭하여 기본 데이터를 확인합니다.

샘플 보고서 아래 표에 있는 추가 정보에 대해서는 설명을 참조하십시오.

![](assets/publisher_unused_traits.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 항목 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 데이터 공급자 유형</span> </p> </td> 
   <td colname="col2"> <p>선택한 데이터 소스에 자사 트레이트가 포함되어 있는지 아니면 타사 트레이트가 포함되어 있는지 지정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 트레이트 ID</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 고유 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 트레이트 이름</span> </p> </td> 
   <td colname="col2"> <p>사용자 또는 데이터 공급자가 이 트레이트에 할당한 영숫자 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 주문</span> </p> </td> 
   <td colname="col2"> <p>이 보고서가 표시되는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 노출 횟수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 구성원이 인벤토리에 노출되는 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 트레이트 고유 사항</span> </p> </td> 
   <td colname="col2"> <p>지난 30일 이내의 트레이트 멤버 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

보고서에서 트레이트의 위치는 기존 대상 세그먼트를 최적화하는 데 사용할 수 있는 트레이트에 대해 많은 것을 알 수 있습니다.

노출 수 축에 더 높은 트레이트는 캠페인에서 사용할 트레이트입니다. 노출 수가 적은 트레이트의 경우 [!DNL Google Ad Manager] 데이터를 기반으로 웹 속성의 이 대상자에 도달하는 것은 거의 불가능합니다.

[!UICONTROL Unique Trait Realizations] 축의 왼쪽에 있는 정확한 트레이트를 확인하고 오른쪽에 있는 스케일을 구동할 수 있는 트레이트를 찾습니다.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 위치 </th> 
   <th colname="col2" class="entry"> 배치 표시 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>왼쪽 위</b> </p> </td> 
   <td colname="col2"> <p>노출 수가 많음, 트레이트 실현률이 적음. </p> <p>아직 세그먼트 멤버가 아닌 매우 정확한 대상입니다. 타깃팅을 고려합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>왼쪽 아래</b> </p> </td> 
   <td colname="col2"> <p>노출 횟수가 적으며, 트레이트 실현률이 적습니다. </p> <p> 구성원이 웹 속성의 노출에 기여하지 않으므로 이러한 트레이트를 제외합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 위</b> </p> </td> 
   <td colname="col2"> <p>노출 수가 많음, 트레이트 실현률이 높습니다. </p> <p>아직 세그먼트에서 언급되지 않은 대상에 대한 높은 도달 범위. 이 대상자는 노출 수와 비율 때문에 타깃팅에 적합한 후보자입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 아래</b> </p> </td> 
   <td colname="col2"> <p>노출 횟수가 적으며, 트레이트 실현률이 높습니다. </p> <p> 구성원이 웹 속성의 노출에 기여하지 않으므로 이러한 트레이트를 제외할 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
