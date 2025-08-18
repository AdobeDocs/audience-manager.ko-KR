---
description: 세그먼트 테스트 그룹에서 함께 수행할 수 없는 테스트 세그먼트를 만들어 서로 다른 대상의 효과를 비교 및 측정합니다. 효율성을 테스트하기 위해 컨트롤 그룹을 제외하고 세그먼트를 전체의 백분율로 나눌 수 있습니다.
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# [!UICONTROL Audience Lab] {#audience-lab}

[!UICONTROL Segment Test Groups]에서 함께 수행할 수 없는 테스트 세그먼트를 만들어 서로 다른 대상의 효과를 비교 및 측정합니다. 효율성을 테스트하기 위해 컨트롤 그룹을 제외하고 세그먼트를 전체의 백분율로 나눌 수 있습니다.

## 개요 {#audience-lab-overview}

[!UICONTROL Audience Lab]은(는) [프로필 링크](../../features/profile-merge-rules/merge-rules-overview.md)를 사용하여 장치 간 테스트를 실행합니다. 이렇게 하면 사용자가 동일한 테스트 세그먼트에 대해 자격을 확보하고 여러 장치에서 동일한 처리를 받을 수 있습니다. 테스트 그룹의 테스트 세그먼트는 기본 세그먼트가 할당한 [프로필 병합 규칙](../../features/profile-merge-rules/merge-rules-dashboard.md)을(를) 상속합니다.

[!UICONTROL Audience Lab] 기본 보기에는 각 테스트 그룹에 대한 카드가 표시됩니다. **[!UICONTROL Test Group]** 보기에 액세스하려면 카드를 클릭하십시오. 이 보기에는 다음 정보가 포함됩니다.

* **[테스트 그룹 정보](../../features/audience-lab/audience-lab-information-view.md)**
* **[테스트 그룹 보고](../../features/audience-lab/audience-lab-reporting-view.md)**

각각 **최대 15개의 테스트 세그먼트**&#x200B;를 가진 **최대 10개의 테스트 그룹**&#x200B;을 만들 수 있습니다.

![](assets/test-groups-view.PNG)

## 테스트 그룹 검색 및 필터링 {#search-and-filter}

여러 테스트 세그먼트가 있는 여러 테스트 그룹을 만들기 시작하면 검색 상자를 사용하여 특정 테스트 그룹을 찾는 것이 더 쉬울 수 있습니다. 다음을 수행하여 테스트 그룹을 검색할 수 있습니다.

* 테스트 그룹의 이름
* 테스트 그룹에 있는 테스트 세그먼트의 이름입니다.
* 테스트 그룹에 대한 설명.

![](assets/search_and_filter_audience_lab.png)

상태별로 테스트 그룹을 필터링할 수도 있습니다. 사용 가능한 모든 상태는 아래의 [상태](../../features/audience-lab/audience-lab.md#status) 섹션에 설명되어 있습니다.

## [!UICONTROL Status] {#status}

테스트 그룹의 상태는 활성, 예약, 일시 중지, 초안 또는 완료일 수 있습니다. 아래 표에서 각 요소에 대한 자세한 내용을 확인하십시오.

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 상태 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 활성 </span></b> </p> </td> 
   <td colname="col2"> <p><i>활성</i> 테스트 그룹은 데이터가 현재 대상으로 전송되고 있음을 의미합니다. 대상으로 데이터 전송을 일시 중단하려면 <b><span class="uicontrol"> 테스트 그룹 </span></b> 카드에서 <b><span class="uicontrol"> 일시 중지 테스트 </span></b>을(를) 누르십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 예약된 </span></b> </p> </td> 
   <td colname="col2"> <p><i>예약된</i> 테스트 그룹이 아직 활성 상태가 아니지만 더 이상 편집할 수 없습니다. <b>테스트 그룹 만들기</b> 마법사에서 선택한 시작 날짜에 활성화됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 일시 중지됨 </span></b> </p> </td> 
   <td colname="col2"> <p><i>일시 중지됨</i> 테스트 그룹이 현재 데이터를 대상으로 전송하지 않습니다. 특성 전송을 다시 시작하려면 <b><span class="uicontrol"> 테스트 그룹 </span></b> 카드에서 <b><span class="uicontrol"> 활성 </span></b> 만들기를 누르십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 초안 </span></b> </p> </td> 
   <td colname="col2"> <p><i>초안</i> 테스트 그룹이 아직 활성 상태가 아니므로 편집할 수 있습니다. 아직 매핑된 대상으로 데이터를 전송하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 완료 </span></b> </p> </td> 
   <td colname="col2"> <p><i>완료됨</i> 테스트 그룹이 <b><span class="uicontrol"> 테스트 그룹 만들기 </span></b> 마법사에서 선택한 종료 날짜에 도달하여 보고 데이터 전송을 중지했습니다. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 액션 </th> 
   <th colname="col2" class="entry"> 설명 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> </span></b> 편집 </p> </td>
   <td colname="col2"> <p>초안 테스트 그룹에 <b>only</b> 사용 가능. <b><span class="uicontrol"> 새 테스트 그룹 만들기 </span></b> 마법사를 다시 시작할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 일시 중지 </span></b> </p> </td>
   <td colname="col2"> <p>활성 테스트 그룹에 사용 가능합니다. 대상으로 테스트 세그먼트 전송을 일시 중지할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> </span></b> 활성화 </p> </td>
   <td colname="col2"> <p>일시 중지된 테스트 그룹에 사용 가능합니다. 대상으로 테스트 세그먼트 전송을 재개할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 보기 </span></b> </p> </td>
   <td colname="col2"> <p>완료된 테스트 그룹에 사용할 수 있습니다. 테스트가 생성한 보고 정보를 볼 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 중복 </span></b> </p> </td>
   <td colname="col2"> <p>복제 중인 테스트 그룹과 동일한 구성으로 새 테스트 그룹을 만들 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> </span></b> 삭제 </p> </td>
   <td colname="col2"> <p>테스트 그룹을 삭제할 수 있습니다. 테스트 세그먼트는 대상에서 매핑 해제되고, 테스트 그룹에 연결된 기준선 세그먼트 및 전환 트레이트는 완전히 편집할 수 있습니다. 원할 경우 보고를 저장할 테스트 그룹을 삭제할 때 CSV 파일을 다운로드하라는 경고가 표시됩니다. </p> </td>
  </tr>
 </tbody>
</table>
