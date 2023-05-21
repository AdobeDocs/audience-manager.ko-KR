---
description: 테스트 그룹 보고 섹션은 테스트 그룹 전환에 대한 정보를 반환하여 테스트 세그먼트 효과를 쉽게 비교할 수 있습니다. 데이터 시각화에 다양한 필터 및 차원을 사용할 수 있습니다.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: 테스트 그룹 보고
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 2%

---

# 테스트 그룹 보고 {#test-group-reporting}

테스트 그룹 보고 섹션은 테스트 그룹 전환에 대한 정보를 반환하여 테스트 세그먼트 효과를 쉽게 비교할 수 있습니다. 데이터 시각화에 다양한 필터 및 차원을 사용할 수 있습니다.

[!UICONTROL Audience Lab] 은 사용자가 만든 테스트 세그먼트에 대한 자세한 보고 정보를 반환하며 보고 데이터를 다음과 같이 저장할 수 있습니다. [!DNL CSV] 파일. 다음 중 하나를 선택할 수 있습니다. **[!UICONTROL Aggregate Reporting]** 및 **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** 테스트 세그먼트에 대한 절대값을 반환합니다. **[!UICONTROL Trend Reporting]** 트렌드의 그래프를 반환합니다. *특정 기간에 걸쳐*. 4개의 탭을 사용하여 보고서를 사용자 지정할 수 있습니다.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 모집단 전환율</span></b> </p> </td> 
   <td colname="col2"> <p>변환된 특정 테스트 세그먼트에 속하는 장치의 백분율을 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 변환기</span></b> </p> </td> 
   <td colname="col2"> <p>테스트 그룹에서 선택한 전환 트레이트를 보였던 장치 수를 반환합니다. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 이 비디오 보기</a> 변환 특성을 만드는 방법을 알아봅니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 총 전환 수</span></b> </p> </td> 
   <td colname="col2"> <p>테스트 세그먼트에서 생성된 전환 수를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 테스트 세그먼트 모집단</span></b> </p> </td> 
   <td colname="col2"> <p>테스트 세그먼트에 속하는 장치 수를 반환합니다. 전환 <b><span class="uicontrol"> 총 모집단</span></b> 또는 <b><span class="uicontrol"> 실시간 모집단</span></b>. 차이점은 다음에서 설명합니다. <a href="../../faq/faq-reporting.md"> 보고 FAQ</a> . </p> </td>
  </tr>
 </tbody>
</table>

보고서를 생성할 특정 전환 트레이트를 선택하거나 결합된 모든 트레이트를 선택할 수 있습니다. 정보를 반환해야 하는 날짜 범위를 정의하고 보고서를 로 내보낼 수 있습니다. [!DNL CSV] 파일.

>[!NOTE]
>
>* 테스트 그룹에 대한 보고는 시작 일자 다음 날에 채워집니다.
>* 전환은 테스트 시작 날짜 이후 및 장치가 테스트 세그먼트에 추가된 후에만 장치에 대해 계산됩니다. 테스트 그룹에 할당되기 전에 해당 디바이스에 대해 전환이 발생하는 경우 전환이 계산되지 않습니다.


A 반환됨 **[!UICONTROL Aggregate Reporting]** 차트는 다음과 같이 표시될 수 있습니다.

![](assets/aggregate-reporting.PNG)

A 반환됨 **[!UICONTROL Trend Reporting]** 차트는 아래 차트와 비슷할 수 있습니다. 선택 **[!UICONTROL Normalized]** 절대 숫자를 무시하고 테스트 세그먼트 트렌드에 초점을 맞추려면 이 확인란을 선택합니다.

![](assets/trend-reporting.PNG)
