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
source-wordcount: '337'
ht-degree: 0%

---

# 테스트 그룹 보고 {#test-group-reporting}

테스트 그룹 보고 섹션은 테스트 그룹 전환에 대한 정보를 반환하여 테스트 세그먼트 효과를 쉽게 비교할 수 있습니다. 데이터 시각화에 다양한 필터 및 차원을 사용할 수 있습니다.

[!UICONTROL Audience Lab]은(는) 사용자가 만든 테스트 세그먼트에 대한 자세한 보고 정보를 반환하며 보고 데이터를 [!DNL CSV] 파일로 저장할 수 있도록 합니다. **[!UICONTROL Aggregate Reporting]**&#x200B;에서 **[!UICONTROL Trend Reporting]** 중 하나를 선택할 수 있습니다.

**[!UICONTROL Aggregate Reporting]**&#x200B;은(는) 테스트 세그먼트에 대한 절대값을 반환합니다. **[!UICONTROL Trend Reporting]**&#x200B;이(가) 특정 기간&#x200B;*에 대한*&#x200B;트렌드의 그래프를 반환합니다. 4개의 탭을 사용하여 보고서를 사용자 지정할 수 있습니다.

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
   <td colname="col1"> <p> <b><span class="uicontrol">개의 변환기</span></b> </p> </td> 
   <td colname="col2"> <p>테스트 그룹에서 선택한 전환 트레이트를 보였던 장치 수를 반환합니다. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> 이 비디오를 시청</a>하여 전환 특성을 만드는 방법을 알아보십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 총 전환 수 <b><span class="uicontrol">개</span></b> </p> </td> 
   <td colname="col2"> <p>테스트 세그먼트에서 생성된 전환 수를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 테스트 세그먼트 모집단</span></b> </p> </td> 
   <td colname="col2"> <p>테스트 세그먼트에 속하는 장치 수를 반환합니다. <b><span class="uicontrol"> 총 모집단</span></b> 또는 <b><span class="uicontrol"> 실시간 모집단</span></b> 사이를 전환합니다. 차이점은 <a href="../../faq/faq-reporting.md"> 보고 FAQ</a>에 설명되어 있습니다. </p> </td>
  </tr>
 </tbody>
</table>

보고서를 생성할 특정 전환 트레이트를 선택하거나 결합된 모든 트레이트를 선택할 수 있습니다. 정보를 반환해야 하는 날짜 범위를 정의하고 보고서를 [!DNL CSV] 파일로 내보낼 수 있습니다.

>[!NOTE]
>
>* 테스트 그룹에 대한 보고는 시작 일자 다음 날에 채워집니다.
>* 전환은 테스트 시작 날짜 이후 및 장치가 테스트 세그먼트에 추가된 후에만 장치에 대해 계산됩니다. 테스트 그룹에 할당되기 전에 해당 디바이스에 대해 전환이 발생하는 경우 전환이 계산되지 않습니다.

반환된 **[!UICONTROL Aggregate Reporting]** 차트는 다음과 같습니다.

![](assets/aggregate-reporting.PNG)

반환된 **[!UICONTROL Trend Reporting]** 차트는 아래 차트와 비슷합니다. 절대 숫자를 무시하고 테스트 세그먼트 트렌드에 초점을 맞추려면 확인란에서 **[!UICONTROL Normalized]**&#x200B;을(를) 선택하십시오.

![](assets/trend-reporting.PNG)
