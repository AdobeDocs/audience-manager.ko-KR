---
description: 세그먼트 빌더에서 트레이트를 추가 및 제거하여 실제 및 예상 세그먼트 모집단 데이터와 함께 실제 트레이트 모집단을 봅니다. 예상 모집단 크기 데이터를 사용하면 캠페인에 적합한 세그먼트를 만들 수 있습니다.
seo-description: 세그먼트 빌더에서 트레이트를 추가 및 제거하여 실제 및 예상 세그먼트 모집단 데이터와 함께 실제 트레이트 모집단을 봅니다. 예상 모집단 크기 데이터를 사용하면 캠페인에 적합한 세그먼트를 만들 수 있습니다.
seo-title: 세그먼트 빌더의 트레이트 및 세그먼트 모집단 데이터
solution: Audience Manager
title: 세그먼트 빌더의 트레이트 및 세그먼트 모집단 데이터
uuid: e1e59c0a-b4c7-4cad-8485-3667e0a95e83
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Trait and Segment Population Data in Segment Builder {#trait-and-segment-population-data-in-segment-builder}

에 트레이트를 추가 및 제거하여 실제 및 예상 세그먼트 인구 데이터와 함께 실제 트레이트 모집단을 [!UICONTROL Segment Builder] 볼 수 있습니다. 예상 모집단 크기 데이터를 사용하면 캠페인에 적합한 세그먼트를 만들 수 있습니다.

## 특성 인구 데이터 {#trait-population-data}

[!UICONTROL Segment Builder] 세그먼트에 트레이트를 추가할 [!UICONTROL Total Trait Population] 마지막 날을 보여줍니다. 이 데이터는 [!UICONTROL Basic View] 섹션에서 선택한 트레이트 주위의 파란색 필드에 나타납니다.

![](assets/trait-size.png)

다음 표에서는 특성 인구 지표를 정의합니다

<table id="table_9D837CF9ACA04D04BEE5925EC0B4A5D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 총 트레이트 인구</span> </p> </td>
   <td colname="col2"> <p>프로필에 선택된 트레이트가 있는 고유 ID 수입니다. </p> </td>
  </tr> 
 </tbody> 
</table>

## 실제 및 예상 세그먼트 모집단 계산 {#calculating-real-estimated-populations}

새 세그먼트를 만들거나 기존 세그먼트를 변경하면 Audience Manager가 실제 실시간 및 총 세그먼트 모집단의 결과를 표시하는 데 최대 24시간이 걸립니다.

하지만 Audience Manager는 세그먼트의 실시간 및 총 인구 크기를 즉시 예측할 수 있습니다. 이러한 추정은 95% 신뢰 구간의 샘플 내역 데이터와 반환 결과를 기반으로 합니다.

![](assets/confidence-interval.png)

에서 [!UICONTROL Segment Builder]예상 모집단 그래프의 파란색 막대는 세그먼트 크기의 가능한 상한 및 하한 범위를 나타냅니다. 이전 성능은 향후 결과를 보장하지 않지만 예상 데이터는 새 세그먼트나 편집된 세그먼트의 잠재적인 크기를 이해하는 데 도움이 될 수 있습니다.

## 세그먼트 모집단 데이터 개요 {#segment-populations}

[!UICONTROL Segment Builder] 세그먼트를 만들고 편집할 때 세그먼트 모집단 데이터를 보여줍니다.

* 예상 세그먼트 모집단 데이터(실시간 및 합계)의 경우, 세그먼트에서 트레이트를 추가하거나 제거할 때 그래프를 자동으로 업데이트하지 [!UICONTROL Segment Builder] 않습니다. 을 **[!UICONTROL Calculate Estimates]** 클릭하여 예상 인구 수를 보거나 새로 고칩니다.

* 실제(실시간 및 합계) 세그먼트 모집단 데이터의 경우, 기존 세그먼트를 로드할 때 세그먼트 그래프를 자동으로 [!UICONTROL Segment Builder] 업데이트합니다. 새 세그먼트의 경우 또는 기존 세그먼트에 새 트레이트를 추가하면, 세그먼트가 생성된 후 24시간이 경과할 때까지 실제 인구 데이터가 업데이트되지 않습니다.

![](assets/segment-data.png)

예상 및 실제 세그먼트 모집단 데이터에 대한 자세한 내용은 아래 정의를 참조하십시오.

## 정의된 예상 세그먼트 모집단 데이터 {#estimated-segment-population}

다음 표에서는 예상 인구 지표를 정의합니다.

<table id="table_B24503F372E34B6BBDF5204181701A59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 예상 실시간 인구(잠재적) </span> </p> </td> 
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 표시되고 Audience Manager에서 보았던 당시 세그먼트에 자격을 갖춘 예상 고유 방문자 수입니다. </p> <p>세그먼트 <span class="wintitle"> 빌더에서</span>트레이트에 대한 마지막 30일 모집단(<span class="wintitle"> 총 트레이트 모집단</span>)은 실시간으로 평가된 트레이트 및 세그먼트에 대해 다를 수 있습니다. </p> <p>
     <ul id="ul_CAE803D09913462CAD413A665D85C1A2"> 
      <li id="li_3E64330D6F5B4D2F8F3456730A86894F">트레이트의 경우, 지난 30일 지표는 지난 30일 동안 해당 트레이트에 대해 자격이 부여된 고유한 사용자의 수를 계산합니다. </li>
      <li id="li_FF3CACD0B6C742CDB94D66200D77CE06">실시간으로 평가된 세그먼트의 경우, 지난 30일 지표는 과거의 특정 시점에서 트레이트(해당 세그먼트)에 대해 자격이 있고 지난 30일 동안 Audience Manager에서 다시 본 사용자의 수를 카운트합니다. 예를 들어 60일 전에 트레이트 자격을 얻었고 10일 전에 다시 본 사용자가 있다고 가정해 봅시다. 이 사용자는 30일 전에 트레이트에 대해 처음으로 자격을 얻었기 때문에 데이터에서 트레이트 수에 추가되지 않습니다. 하지만, 이러한 세그먼트는 실시간으로 평가된 세그먼트에 대한 마지막 30일 수에 포함됩니다. 이는 30일 시간 간격 내에 세그먼트에 대한 자격이 있기 때문입니다. </li>
     </ul> </p> <p> <p>참고:예상 <span class="wintitle"> 실시간 모집단</span> 지표는 장치 그래프 옵션을 <span class="wintitle"> 사용하는 프로필 병합 규칙에서 제공하는 연결을 기반으로 한 세그먼트에 대한 자격이 있는 장치를</span> 포함하지 않습니다 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"></a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 예상 총 인구(잠재적)</span> </p> </td> 
   <td colname="col2"> <p>새 세그먼트나 수정된 세그먼트에 있을 수 있는 예상 고유 방문자 수입니다. 거의 모든 예상 결과와 마찬가지로, 과거 성능은 향후 결과를 보장하지 않지만, 예상 총계를 사용하여 다음을 수행할 수 있습니다. </p> <p> 
     <ul id="ul_0490DD08C7C8493DADFB11B5872A73BC"> 
      <li id="li_AE38C8C8A4B24021BAC724B51A4799E2">세그먼트를 만들 때 새 세그먼트나 수정된 세그먼트에 도달하는 사람 수를 확인할 수 있습니다. </li> 
      <li id="li_E830EC2B12DC46D4B0A4DD807A8936F6">목표에 따라 세그먼트를 조정합니다. 예를 들어, 큰 세그먼트는 브랜드 인식 캠페인에 유용하며 작은 세그먼트는 집중적인 타깃팅 또는 재타깃팅 캠페인에 유용합니다. </li> 
     </ul> </p> <p> <p>참고:예상 <span class="wintitle"> 총 모집단</span> 지표는 <span class="wintitle"> 장치 그래프 옵션을</span> 사용하는 프로필 병합 규칙에서 제공하는 연결을 기반으로 한 세그먼트에 대한 자격이 있는 장치를 <a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 포함하지 않습니다</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 기존(실제) 세그먼트 모집단 데이터 정의 {#existing-segment-population}

[!UICONTROL Profile Merge Rules] 실제 실시간 및 전체 인구 수에 영향을 줍니다. 이러한 합계는 세그먼트가 속한 [!UICONTROL Profile Merge Rule] 경우 장치 그래프 옵션을 사용하는지 여부에 따라 달라집니다. 프로필 병합 [규칙 옵션이 정의됨을 참조하십시오](../../features/profile-merge-rules/merge-rule-definitions.md).

### 장치 그래프 옵션이 없는 병합 규칙에 대한 세그먼트 모집단 데이터

다음 표에서는 장치 그래프 옵션 없이 [!UICONTROL Profile Merge Rule] 만든 세그먼트가 사용될 때 실제 실시간 및 총 모집단 지표를 정의합니다. 장치 옵션 설정 **[!UICONTROL No Device Options]** 및 **[!UICONTROL Current Device Proflie]**&#x200B;입니다.

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
   <td colname="col2"> <p>지정된 시간 범위 동안 실시간으로 표시되고 Audience Manager가 본 순간에 세그먼트에 자격을 갖춘 실제 고유 방문자 수입니다. </p> <p>세그먼트 <span class="wintitle"> 빌더에서</span>트레이트에 대한 마지막 30일 모집단(<span class="wintitle"> 총 트레이트 모집단</span>)은 실시간으로 평가된 트레이트 및 세그먼트에 대해 다를 수 있습니다. </p> <p> 
     <ul id="ul_50D1528DDDF347858F17DA3C033B0E3F"> 
      <li id="li_ABA2BFE68FF4430DBB425C4661E1836A">트레이트의 경우, 지난 30일 지표는 지난 30일 동안 해당 트레이트에 대해 자격이 부여된 고유한 사용자의 수를 계산합니다. </li> 
      <li id="li_1519068CBB1445E893657D12E8FE42AC">실시간으로 평가된 세그먼트의 경우, 지난 30일 지표는 과거의 특정 시점에서 트레이트(해당 세그먼트)에 대해 자격이 있고 지난 30일 동안 Audience Manager에서 다시 본 사용자의 수를 카운트합니다. 예를 들어 60일 전에 트레이트 자격을 얻었고 10일 전에 다시 본 사용자가 있다고 가정해 봅시다. 이 사용자는 30일 전에 트레이트에 대해 처음으로 자격을 얻었기 때문에 데이터에서 트레이트 수에 추가되지 않습니다. 하지만, 이러한 세그먼트는 실시간으로 평가된 세그먼트에 대한 마지막 30일 수에 포함됩니다. 이는 30일 시간 간격 내에 세그먼트에 대한 자격이 있기 때문입니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 총 모집단(기존)</span> </p> </td> 
   <td colname="col2"> <p>어제 현재 세그먼트에 자격을 부여받은 실제 고유 방문자 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 장치 그래프를 사용한 규칙 병합 옵션을 위한 세그먼트 모집단 데이터

다음 표에서는 장치 그래프 옵션으로 [!UICONTROL Profile Merge Rule] 만든 세그먼트가 사용될 때 실제 실시간 및 총 모집단 지표를 정의합니다. 이러한 설정은 장치 옵션 설정 [!UICONTROL Profile Link Device Graph], [!DNL Adobe] 장치 그래프 및 사용자가 사용할 수 있는 기타 타사 장치 그래프 설정입니다.

<table id="table_157EC6E5B5C44EB899854CA10B090F60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 지표 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 실시간 모집단(기존)</span> </p> </td> 
   <td colname="col2"> <p>디바이스 그래프로 연결된 최대 3개의 다른 디바이스 프로파일과 결합할 때 Audience Manager에서 볼 때 세그먼트에 적용할 수 있는 트레이트가 포함되어 있는 현재 프로파일을 통해 실시간으로 표시되는 실제 디바이스 <span class="keyword"> 수입니다</span>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 총 모집단(기존)</span> </p> </td> 
   <td colname="col2"> <p>장치 그래프로 연결된 최대 3개의 다른 장치 프로파일과 병합했을 때 세그먼트에 대한 자격이 부여된 프로파일이 있는 총 장치 수입니다. </p> </td>
  </tr>
 </tbody>
</table>

### 최근 및 빈도 표현으로 인한 세그먼트 모집단 추정

[!UICONTROL Segment Builder] 은 최대 4개의 최근 및 빈도 표현식을 포함하는 세그먼트 규칙에 대한 세그먼트 크기 추정값을 지원합니다. 세그먼트 규칙을 작성할 때 최근 및 빈도 표현식을 4개 이상 선택하면 세그먼트 견적 도구에서 모집단 추정을 할 때 오류가 표시됩니다.

### 세그먼트 모집단을 계산할 때 병합 규칙으로 인한 제한

현재 세그먼트 크기 견적 도구는 프로필 병합 규칙을 고려하지 않으므로 알려진 제한이 있습니다. 예를 들어 인증된 프로필 없음 + **현재 장치 프로필**[병합 규칙이](../../features/profile-merge-rules/merge-rule-definitions.md)있는 세그먼트를 봅니다. 현재 세그먼트 추정 숫자를 계산하는 방법 때문에 예상 모집단에는 인증된 프로파일이 포함됩니다. 그러나 기존 세그먼트 모집단에서는 인증된 프로필을 올바로 무시합니다.

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 및 장치 그래프 FAQ](../../faq/faq-profile-merge.md)
>* [프로필 링크](../../features/profile-merge-rules/merge-rules-overview.md)

