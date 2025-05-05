---
description: 세그먼트 빌더에서 트레이트를 추가 및 제거하여 실제 및 예상 세그먼트 인구 데이터와 함께 실제 트레이트 인구를 확인합니다. 예상 모집단 크기 데이터를 사용하면 캠페인에 적합한 세그먼트를 만드는 데 도움이 됩니다.
seo-description: Add and remove traits in Segment Builder to see actual trait populations along with actual and estimated segment population data. The estimated population size data helps you build the right segment for your campaign.
seo-title: Trait and Segment Population Data in Segment Builder
solution: Audience Manager
title: 세그먼트 빌더의 트레이트 및 세그먼트 인구 데이터
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
feature: Segments
exl-id: f8953d10-8a31-4c07-8d96-169c30a21de0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# [!UICONTROL Segment Builder]의 [!UICONTROL Trait] 및 [!UICONTROL Segment] 모집단 데이터 {#trait-and-segment-population-data-in-segment-builder}

실제 및 예상 세그먼트 모집단 데이터와 함께 실제 [!UICONTROL trait] 모집단을 보려면 [!UICONTROL Segment Builder]에서 [!UICONTROL traits]을(를) 추가하고 제거하십시오. 예상 모집단 크기 데이터를 사용하면 캠페인에 적합한 세그먼트를 만드는 데 도움이 됩니다.

## [!UICONTROL Trait] 모집단 데이터 {#trait-population-data}

[!UICONTROL Segment Builder]은(는) 세그먼트에 [!UICONTROL trait]을(를) 추가하는 마지막 날의 [!UICONTROL Total Trait Population]을(를) 표시합니다. 이 데이터는 [!UICONTROL Basic View] 섹션에서 선택한 [!UICONTROL trait] 주변의 파란색 필드에 표시됩니다.

![](assets/trait-size.png)

다음 표는 트레이트 채우기 지표를 정의합니다.


| 지표 | 설명 |
|---------|----------|
| [!UICONTROL Total Trait Population] | 프로필에서 선택한 트레이트가 있는 고유 ID 수입니다. |


## 실제 및 예상 세그먼트 모집단 계산 {#calculating-real-estimated-populations}

새 세그먼트를 만들거나 기존 세그먼트를 변경할 때 Audience Manager은 실제 실시간 및 총 세그먼트 모집단에 대한 결과를 표시하는 데 최대 24시간이 걸립니다.

하지만 Audience Manager은 즉시 세그먼트의 실시간 및 총 인구 크기를 예측할 수 있습니다. 이러한 추정치는 샘플링된 내역 데이터 및 95% 신뢰 구간에서 반환된 결과를 기반으로 합니다.

![](assets/confidence-interval.png)

[!UICONTROL Segment Builder]에서 예상 모집단 그래프의 파란색 막대가 세그먼트 크기의 가능한 상위 및 하위 범위를 나타냅니다. 과거 성능이 미래 결과를 보장하지는 않지만 예상 데이터를 통해 새 세그먼트나 편집된 세그먼트의 잠재적 크기를 파악할 수 있습니다.

## 세그먼트 모집단 데이터 개요 {#segment-populations}

세그먼트를 만들고 편집할 때 [!UICONTROL Segment Builder]에 세그먼트 모집단 데이터가 표시됩니다.

* 예상 세그먼트 모집단 데이터(실시간 및 전체)의 경우 [!UICONTROL Segment Builder]은(는) 세그먼트에 트레이트를 추가하거나 제거할 때 그래프를 자동으로 업데이트하지 않습니다. 예상 모집단 수를 보거나 새로 고치려면 **[!UICONTROL Calculate Estimates]**&#x200B;을(를) 클릭합니다.

* 실제(실시간 및 전체) 세그먼트 채우기 데이터의 경우 [!UICONTROL Segment Builder]은(는) 기존 세그먼트를 로드할 때 세그먼트 그래프를 자동으로 업데이트합니다. 새 세그먼트의 경우 또는 기존 세그먼트에 새 트레이트를 추가할 때 실제 모집단 데이터는 세그먼트가 생성된 후 24시간이 지나야 업데이트됩니다.

![](assets/segment-data.png)

예상 및 실제 세그먼트 모집단 데이터에 대한 자세한 내용은 아래 정의를 참조하십시오.

## 정의된 예상 세그먼트 모집단 데이터 {#estimated-segment-population}

다음 표는 예상 모집단 지표를 정의합니다.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 예상 실시간 모집단(잠재적) </span> </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 확인되었으며, Audience Manager에 의해 확인되었을 때 세그먼트에 대한 자격이 있는 예상 고유 방문자 수입니다. </p> <p><span class="wintitle"> 세그먼트 빌더</span>에서 트레이트(<span class="wintitle"> 총 트레이트 인구</span>)에 대한 마지막 30일 인구는 실시간으로 평가되는 트레이트 및 세그먼트에 대해 다를 수 있습니다. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">트레이트의 경우 지난 30일 지표는 지난 30일 동안 해당 트레이트에 대한 자격이 있는 고유 사용자의 수를 계산합니다. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">실시간으로 평가된 세그먼트의 경우, 마지막 30일 지표는 과거 어느 시점에서 트레이트(해당 세그먼트에서)에 대한 자격이 있고 지난 30일 이내에 Audience Manager에서 다시 본 사용자의 수를 계산합니다. 예를 들어 60일 전에 트레이트에 대한 자격이 있고 10일 전에 다시 조회된 사용자가 있다고 가정해 보겠습니다. 데이터에서 이 사용자는 30일 이상 전에 트레이트에 대한 자격이 처음 있으므로 트레이트 수에 추가되지 않습니다. 하지만 실시간으로 평가되는 세그먼트의 마지막 30일 수에 포함됩니다. 이는 30일 시간 간격 내에 세그먼트에 대한 자격이 있기 때문입니다. </li>
     </ul> </p> <p> <p>참고: <span class="wintitle"> 예상 실시간 모집단</span> 지표에는 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 장치 그래프 옵션</a>을(를) 사용하는 <span class="wintitle"> 프로필 병합 규칙</span>에서 제공한 연결을 기반으로 세그먼트에 적합한 장치가 포함되지 않습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">개의 예상 총 모집단(잠재적)</span> </p> </td> 
   <td colname="col2"> <p>새 세그먼트나 수정된 세그먼트에 있을 수 있는 예상 고유 방문자 수입니다. 거의 모든 예측과 마찬가지로 과거 성과가 미래 결과를 보장하지는 않지만 예상 합계를 사용하여 다음을 수행할 수 있습니다. </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">세그먼트를 작성할 때 새 세그먼트나 수정된 세그먼트에 도달할 수 있는 사람 수를 확인합니다. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">목표에 따라 세그먼트를 조정합니다. 예를 들어 큰 세그먼트는 브랜드 인지도 캠페인에 유용하고 작은 세그먼트는 집중 타겟팅 또는 재타겟팅 캠페인에 유용합니다. </li> 
     </ul> </p> <p> <p>참고: <span class="wintitle"> 예상 총 인구</span> 지표에는 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 장치 그래프 옵션</a>을(를) 사용하는 <span class="wintitle"> 프로필 병합 규칙</span>에서 제공한 연결을 기반으로 세그먼트에 적합한 장치가 포함되지 않습니다. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 기존(실제) 세그먼트 모집단 데이터가 정의됨 {#existing-segment-population}

[!UICONTROL Profile Merge Rules]은(는) 실제 실시간 및 총 모집단 수에 영향을 줍니다. 이러한 합계는 세그먼트가 속한 [!UICONTROL Profile Merge Rule]이(가) 장치 그래프 옵션을 사용하는지 여부에 따라 달라집니다. [정의된 프로필 병합 규칙 옵션](../../features/profile-merge-rules/merge-rule-definitions.md)도 참조하세요.

### [!UICONTROL Device Graph Option]이(가) 없는 [!UICONTROL Merge Rules]의 세그먼트 채우기 데이터

다음 표는 [!UICONTROL device graph] 옵션 없이 만든 [!UICONTROL Profile Merge Rule]에서 세그먼트를 사용할 때의 실제 실시간 및 총 모집단 지표를 정의합니다. 장치 옵션 설정 **[!UICONTROL No Device Options]** 및 **[!UICONTROL Current Device Proflie]**&#x200B;입니다.

<table id="table_A18C973855DB46A0B39B81F32E0E7540"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 실시간 모집단(기존)</span> </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 확인되었으며, Audience Manager에 의해 확인되는 순간 세그먼트에 대한 자격이 되는 실제 고유 방문자 수입니다. </p> <p><span class="wintitle"> 세그먼트 빌더</span>에서 트레이트(<span class="wintitle"> 총 트레이트 인구</span>)에 대한 마지막 30일 인구는 실시간으로 평가되는 트레이트 및 세그먼트에 대해 다를 수 있습니다. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">트레이트의 경우 지난 30일 지표는 지난 30일 동안 해당 트레이트에 대한 자격이 있는 고유 사용자의 수를 계산합니다. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">실시간으로 평가된 세그먼트의 경우, 마지막 30일 지표는 과거 어느 시점에서 트레이트(해당 세그먼트에서)에 대한 자격이 있고 지난 30일 이내에 Audience Manager에서 다시 본 사용자의 수를 계산합니다. 예를 들어 60일 전에 트레이트에 대한 자격이 있고 10일 전에 다시 조회된 사용자가 있다고 가정해 보겠습니다. 데이터에서 이 사용자는 30일 이상 전에 트레이트에 대한 자격이 처음 있으므로 트레이트 수에 추가되지 않습니다. 하지만 실시간으로 평가되는 세그먼트의 마지막 30일 수에 포함됩니다. 이는 30일 시간 간격 내에 세그먼트에 대한 자격이 있기 때문입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">개의 총 모집단(기존)</span> </p> </td> 
   <td colname="col2"> <p>어제까지 세그먼트에 대한 자격이 확인된 실제 고유 방문자 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Device Graph] 옵션이 있는 [!UICONTROL Merge Rules]에 대한 세그먼트 채우기 데이터

다음 표는 [!DNL device graph] 옵션으로 만든 [!UICONTROL Profile Merge Rule]에서 세그먼트를 사용할 때의 실제 실시간 및 총 모집단 지표를 정의합니다. 사용 가능한 [!UICONTROL Profile Link Device Graph], [!DNL Adobe] [!DNL device graph] 및 기타 타사 [!DNL device graph] 선택 항목에 대한 장치 옵션 설정입니다.


| 열 A | 열 B |
|---------|----------|
| [!UICONTROL Real-Time Population (Existing)] | 장치 그래프에 의해 연결된 최대 100개의 다른 장치 프로필과 병합될 때 Audience Manager에 의해 표시되는 순간에 세그먼트에 적합한 트레이트가 포함된 현재 프로필로 실시간으로 표시되는 실제 장치 수입니다. |
| [!UICONTROL Total Population (Existing)] | 장치 그래프에 의해 연결된 최대 100개의 다른 장치 프로필과 병합될 때 모두 세그먼트에 적합한 프로필이 있는 총 장치 수입니다. |

### 세그먼트 모집단 예상 시 최신성 및 빈도 표현식으로 인한 제한 사항

[!UICONTROL Segment Builder]은(는) 최대 4개의 최신성과 빈도 식을 포함하는 세그먼트 규칙에 대한 세그먼트 크기 예측을 지원합니다. 세그먼트 규칙을 작성할 때 최신성 및 빈도 표현식을 4개 이상 선택하면 모집단을 추정할 때 세그먼트 추정기에 오류가 표시됩니다.

### 세그먼트 모집단을 추정할 때 [!UICONTROL Merge Rules] (으)로 인한 제한

현재 세그먼트 크기 예측기가 [!UICONTROL profile merge rules]을(를) 설명하지 않으므로 알려진 제한 사항이 있습니다. 예를 들어, **[!UICONTROL No Authenticated Profile + Current Device Profile]** [병합 규칙](../../features/profile-merge-rules/merge-rule-definitions.md)이 있는 세그먼트를 확인합니다. 현재 세그먼트 예상 수를 계산하는 방법 때문에 예상 모집단에는 인증된 프로필이 포함됩니다. 그러나 기존 세그먼트 모집단은 인증된 프로필을 올바로 무시합니다.

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 및 장치 그래프 FAQ](../../faq/faq-profile-merge.md)
>* [프로필 링크](../profile-merge-rules/merge-rules-overview.md)
