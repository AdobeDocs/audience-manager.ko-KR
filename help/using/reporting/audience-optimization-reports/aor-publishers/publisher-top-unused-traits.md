---
description: 사용하지 않는 상위 트레이트는 트레이트 유형, 데이터 소스 및 성과를 기반으로, 아직 세그먼트의 구성원이 아닌 트레이트의 분산형 다이어그램으로 표시됩니다.
seo-description: 사용하지 않는 상위 트레이트는 트레이트 유형, 데이터 소스 및 성과를 기반으로, 아직 세그먼트의 구성원이 아닌 트레이트의 분산형 다이어그램으로 표시됩니다.
seo-title: 상위 사용하지 않는 특성
solution: Audience Manager
title: 상위 사용하지 않는 특성
uuid: 90bcd333-41b8-416e-aa4e-a8661891df50
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 2%

---


# 상위 사용하지 않는 특성{#top-unused-traits}

사용하지 않는 상위 트레이트는 트레이트 유형, 데이터 소스 및 성과를 기반으로, 아직 세그먼트의 구성원이 아닌 트레이트의 분산형 다이어그램으로 표시됩니다.

## 사용 사례 {#use-cases}

[!UICONTROL Top Unused Traits] 보고서를 사용하여 현재 세그먼트에 매핑되지 않은 첫 번째 및 타사 트레이트의 성과를 분석하고 비교할 수 있습니다. 이 보기는 캠페인 최적화 또는 새로운 기회를 창출하기 위해 대상 세그먼트에서 사용할 최상의 트레이트를 가리킬 수 있습니다.

## 사용하지 않는 상위 특성 보고서 사용 {#using-the-report}

**[!UICONTROL Data Provider Type]** 컨트롤을 사용하여 자사 트레이트와 타사 트레이트 간을 전환합니다. 보고서에서 첫 번째 및 타사 트레이트를 반환하려면 **[!UICONTROL All]**&#x200B;을 선택합니다.

**[!UICONTROL Impressions]** 슬라이더를 사용하여 반환되는 임프레션에 대한 최소값과 최대값을 선택할 수 있습니다. 설정한 제한보다 작거나 많은 특성에 대한 책임이 있는 모든 트레이트는 보고서에 표시되지 않습니다.

**[!UICONTROL Day Range]** 및 **[!UICONTROL Date Through]** 컨트롤을 사용하여 뒤로 보기를 조정합니다. 이 보고서에서는 30일 룩백 기간만 사용할 수 있습니다.

**[!UICONTROL Order]** 드롭다운 상자를 사용하여 정보를 반환할 포트폴리오의 웹 속성을 선택합니다.

**[!UICONTROL Data Provider]** 드롭다운 상자에서 보고서에 표시할 트레이트가 포함된 데이터 소스를 선택합니다.

**[!UICONTROL Traits]** 드롭다운 상자를 사용하여 보고서에 표시할 트레이트를 선택합니다.

>[!IMPORTANT]
>
>[!UICONTROL Audience Optimization for Publishers]을(를) 활성화할 때는 [Google Ad Manager 가져오기(이전 DFP) 데이터 파일을 Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md)으로 가져오는 3단계에 설명된 대로 [!UICONTROL Order IDs]에 대한 설명 메타데이터를 포함해야 합니다. 이렇게 하면 보고서가 웹 속성을 [!UICONTROL Order ID] 대신 [!UICONTROL Order](으)로 상세 정보로 지정하는지 확인합니다.

## 결과 해석 {#interpreting-results}

**샘플 보고서**

[!UICONTROL Top Unused Traits] 보고서가 아래 보고서와 유사할 수 있습니다. 보고서에서 버블을 클릭하여 기본 데이터를 봅니다.

샘플 보고서 아래 표에 나와 있는 추가 정보는 설명을 참조하십시오.

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
   <td colname="col2"> <p>선택한 데이터 소스에 자사 또는 타사 트레이트가 포함되어 있는지 여부를 지정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 특성 ID</span> </p> </td> 
   <td colname="col2"> <p>이 트레이트의 고유 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 특성 이름</span> </p> </td> 
   <td colname="col2"> <p>사용자 또는 이 트레이트에 지정된 데이터 제공자의 영숫자 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 주문</span> </p> </td> 
   <td colname="col2"> <p>이 보고서를 보고 있는 웹 속성입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 노출 횟수</span> </p> </td> 
   <td colname="col2"> <p>이 특성 구성원이 인벤토리에 노출된 횟수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 특성 고유</span> </p> </td> 
   <td colname="col2"> <p>지난 30일 이내의 트레이트 멤버 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

![](assets/publisher_unused_traits_final.png)

보고서에서 트레이트의 위치는 기존 대상 세그먼트를 최적화하는 데 사용할 수 있는 트레이트에 대해 많은 것을 알 수 있습니다.

노출 수 축에 더 높은 트레이트는 캠페인에 사용할 트레이트입니다. 노출 횟수가 적은 트레이트의 경우, [!DNL Google Ad Manager] 데이터를 기반으로 웹 속성에서 이 대상에게 도달할 가능성은 거의 없습니다.

[!UICONTROL Unique Trait Realizations] 축의 왼쪽을 보면 매우 정확한 트레이트가 표시되고, 오른쪽에는 스케일을 구동할 수 있는 트레이트가 표시됩니다.

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
   <td colname="col2"> <p>노출 수, 트레이트 재조정 수 감소. </p> <p>세그먼트에 아직 포함되지 않은 매우 정확한 대상입니다. 타깃팅을 고려합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>왼쪽 아래</b> </p> </td> 
   <td colname="col2"> <p>노출 횟수, 트레이트 재조정 수 낮음. </p> <p> 멤버가 웹 속성에 대한 노출에 기여하지 않으므로 이러한 트레이트를 제외합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 위</b> </p> </td> 
   <td colname="col2"> <p>높은 노출 수, 높은 수의 트레이트 관계 </p> <p>세그먼트에 아직 표시되지 않은 대상에 대한 높은 도달 노출 수와 비율이 높기 때문에 이 대상은 타깃팅할 수 있는 주요 대상입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오른쪽 아래</b> </p> </td> 
   <td colname="col2"> <p>노출 횟수, 트레이트 실현률 증가 수 </p> <p> 멤버가 웹 속성에 대한 노출에 기여하지 않으므로 이러한 트레이트를 제외할 수 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
