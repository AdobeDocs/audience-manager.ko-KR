---
description: 사용하지 않은 주요 트레이트는 트레이트 유형, 데이터 소스 및 성능에 따라 아직 세그먼트의 멤버가 아닌 트레이트의 분산형 다이어그램으로 표현됩니다.
seo-description: 사용하지 않은 주요 트레이트는 트레이트 유형, 데이터 소스 및 성능에 따라 아직 세그먼트의 멤버가 아닌 트레이트의 분산형 다이어그램으로 표현됩니다.
seo-title: 사용하지 않은 주요 특징
solution: Audience Manager
title: 사용하지 않은 주요 특징
uuid: 90 BCD 333-41 B 8-416 E-AA 4 E-A 8661891 DF 50
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Top Unused Traits{#top-unused-traits}

사용하지 않은 주요 트레이트는 트레이트 유형, 데이터 소스 및 성능에 따라 아직 세그먼트의 멤버가 아닌 트레이트의 분산형 다이어그램으로 표현됩니다.

## 사용 사례 {#use-cases}

[!UICONTROL Top Unused Traits] 보고서와 함께, 세그먼트에 매핑되지 않은 첫 번째 및 타사 트레이트의 성과를 분석하고 비교할 수 있습니다. 이 보기는 캠페인 최적화 또는 새로운 기회를 위해 대상 세그먼트에서 사용할 최상의 트레이트를 가리킬 수 있습니다.

## Using the Top Unused Traits Report {#using-the-report}

**[!UICONTROL Data Provider Type]** 컨트롤을 사용하여 자사 트레이트와 타사 특성 간에 전환합니다. Select **[!UICONTROL All]** to return first and third party traits in the report.

**[!UICONTROL Impressions]** 슬라이더를 사용하여 반환된 노출 횟수에 대한 최소 및 최대값을 선택할 수 있습니다. 설정한 제한을 초과하거나 초과하는 모든 트윗은 보고서에 표시되지 않습니다.

**[!UICONTROL Day Range]** AND **[!UICONTROL Date Through]** 컨트롤을 사용하여 룩백 범위를 조정합니다. 이 보고서에는 30 일 룩백 기간만 사용할 수 있습니다.

Use the **[!UICONTROL Order]** drop-down box to select the web properties in your portfolio for which you want to return information.

**[!UICONTROL Data Provider]** 드롭다운 상자에서 보고서에 표시할 트레이트가 들어 있는 데이터 소스를 선택합니다.

**[!UICONTROL Traits]** 드롭다운 상자를 사용하여 보고서에서 표시할 트레이트를 선택합니다.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Order IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Order] instead of the [!UICONTROL Order ID].

## Interpreting the Results {#interpreting-results}

**샘플 보고서**

[!UICONTROL Top Unused Traits] 보고서가 아래 나와 표시될 수 있습니다. 보고서에서 거품을 클릭하여 기본 데이터를 봅니다.

샘플 보고서 아래 표의 추가 정보는 설명을 참조하십시오.

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
   <td colname="col2"> <p>선택한 데이터 소스에 타사 트레이트가 포함되어 있는지 또는 타사 트레이트가 포함되어 있는지를 지정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 특성 ID</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 고유 ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 특성 이름</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트 또는 데이터 공급자가 지정한 영숫자 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 주문</span> </p> </td> 
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 노출 횟수</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 특성 고유 방문자</span> </p> </td> 
   <td colname="col2"> <p>지난 30 일 이내의 트레이트 구성원 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

보고서에서 트레이트의 위치를 사용하면 기존 고객 세그먼트를 최적화하는 데 사용할 수 있는 트레이트에 대해 많이 알 수 있습니다.

노출 축에 더 높은 특성을 갖는 특징은 캠페인에 사용할 수 있습니다. 노출 횟수가 적은 트레이트에 대해 DFP 데이터를 기반으로 웹 속성에서 이 고객에게 도달할 가능성은 거의 없습니다.

Look to the left of the [!UICONTROL Unique Trait Realizations] axis for highly accurate traits and to the right for traits that can drive scale.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> position </th> 
   <th colname="col2" class="entry"> 배치 표시 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>왼쪽 위</b> </p> </td> 
   <td colname="col2"> <p>노출 횟수가 많고 트레이트 실현률이 낮습니다. </p> <p>이는 아직 세그먼트의 멤버가 아닌 매우 정확한 대상입니다. 타깃팅을 고려합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>왼쪽 아래</b> </p> </td> 
   <td colname="col2"> <p>노출 횟수가 적고 트레이트 실현률이 낮습니다. </p> <p> 멤버가 웹 속성에 대한 노출 횟수에 기여하지 않으므로 이러한 트레이트를 배제합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 상단</b> </p> </td> 
   <td colname="col2"> <p>노출 수가 많고 트레이트 실현률이 높습니다. </p> <p>세그먼트에 아직 표시되지 않은 고객에 대한 도달 수 높음 이 대상은 높은 노출 횟수와 척도로 인해 타깃팅을 위한 우수 대상입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 하단</b> </p> </td> 
   <td colname="col2"> <p>노출 횟수가 적고 트레이트 실현률이 높습니다. </p> <p> 멤버가 웹 속성에서 노출 횟수에 기여하지 않으므로 이러한 트레이트를 제외할 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
