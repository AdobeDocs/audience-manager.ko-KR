---
description: 세그먼트 테스트 그룹에서 상호 배타적인 테스트 세그먼트를 만들어 서로 다른 대상의 효과를 비교하고 측정합니다. 유효성 검사를 위해 제어 그룹을 따로 두고 세그먼트를 전체 백분율로 나눌 수 있습니다.
seo-description: 세그먼트 테스트 그룹에서 상호 배타적인 테스트 세그먼트를 만들어 서로 다른 대상의 효과를 비교하고 측정합니다. 유효성 검사를 위해 제어 그룹을 따로 두고 세그먼트를 전체 백분율로 나눌 수 있습니다.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---


# [!UICONTROL Audience Lab] {#audience-lab}

서로 다른 대상의 효과를 비교하고 측정하려면 [!UICONTROL Segment Test Groups]에서 상호 배타적인 테스트 세그먼트를 만듭니다. 유효성 검사를 위해 제어 그룹을 따로 두고 세그먼트를 전체 백분율로 나눌 수 있습니다.

## 개요 {#audience-lab-overview}

[!UICONTROL Audience Lab] 프로필  [링크를 사용하여 ](../../features/profile-merge-rules/merge-rules-overview.md) 장치 간 테스트를 수행합니다. 따라서 사용자가 동일한 테스트 세그먼트에 합격할 수 있고 장치 간에 동일한 대우를 받을 수 있습니다. 테스트 그룹의 테스트 세그먼트는 기본 세그먼트가 할당된 [프로필 병합 규칙](../../features/profile-merge-rules/merge-rules-dashboard.md)을 상속합니다.

[!UICONTROL Audience Lab] 기본 보기에는 각 테스트 그룹의 카드가 표시됩니다. 카드를 클릭하여 **[!UICONTROL Test Group]** 보기에 액세스합니다. 이 보기에는 다음 정보가 포함됩니다.

* **[테스트 그룹 정보](../../features/audience-lab/audience-lab-information-view.md)**
* **[테스트 그룹 보고](../../features/audience-lab/audience-lab-reporting-view.md)**

각각 **최대 15개의 테스트 세그먼트**&#x200B;를 포함하는 최대 10개의 테스트 그룹&#x200B;**을 만들 수 있습니다.**

![](assets/test-groups-view.PNG)

## 테스트 그룹 검색 및 필터링 {#search-and-filter}

여러 테스트 세그먼트로 여러 테스트 그룹을 만들기 시작하면 검색 상자를 사용하여 특정 테스트 그룹을 쉽게 찾을 수 있습니다. 테스트 그룹을 다음 기준으로 검색할 수 있습니다.

* 테스트 그룹 이름
* 테스트 그룹의 테스트 세그먼트 이름
* 테스트 그룹에 대한 설명입니다.

![](assets/search_and_filter_audience_lab.png)

상태별로 테스트 그룹을 필터링할 수도 있습니다. 사용 가능한 모든 상태는 아래의 [상태](../../features/audience-lab/audience-lab.md#status) 섹션에 설명되어 있습니다.

## [!UICONTROL Status] {#status}

테스트 그룹의 상태는 활성, 예약, 일시 중지, 초안 또는 완료일 수 있습니다. 아래 표에 있는 각 항목에 대한 자세한 내용:

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
   <td colname="col2"> <p><i>active</i> 테스트 그룹은 데이터가 현재 대상으로 전송되고 있음을 의미합니다. 대상으로 데이터 전송을 일시 중단하려면 </span></b> 테스트 그룹 <b><span class="uicontrol"> 카드의 <b><span class="uicontrol"> 테스트 일시 중지 &lt;a1/&gt;를 누릅니다.</span></b> </span></b></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 예약됨 </span></b> </p> </td> 
   <td colname="col2"> <p><i>예약된</i> 테스트 그룹이 아직 활성 상태가 아니지만 더 이상 편집할 수 없습니다. <b>테스트 그룹 만들기</b> 마법사에서 선택한 시작 날짜에 활성 상태가 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 일시 정지됨 </span></b> </p> </td> 
   <td colname="col2"> <p>현재 <i>일시 중지된 테스트 그룹이 대상으로 데이터를 전송하지 않습니다. </i> 트레이트 전송을 재개하려면 </span></b> 테스트 그룹 <b><span class="uicontrol"> 카드에서 <b><span class="uicontrol"> 활성 상태로 만들기 를 누릅니다.</span></b> </span></b></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 초안 </span></b> </p> </td> 
   <td colname="col2"> <p><i>draft</i> 테스트 그룹이 아직 활성 상태가 아니므로 편집할 수 있습니다. 데이터가 매핑된 대상으로 아직 전송되지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 완료 </span></b> </p> </td> 
   <td colname="col2"> <p><i>completed</i> 테스트 그룹이 <b><span class="uicontrol"> 테스트 그룹 만들기 </span></b> 마법사에서 선택한 종료 날짜에 도달했으며 보고 데이터 전송을 중지했습니다. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 편집 </span></b> </p> </td>
   <td colname="col2"> <p>초안 테스트 그룹에 대해 <b>만 사용할 수 있습니다. </b> <b><span class="uicontrol"> 새 테스트 그룹 만들기 </span></b> 마법사를 다시 시작할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 일시 정지 </span></b> </p> </td>
   <td colname="col2"> <p>활성 테스트 그룹에 사용할 수 있습니다. 대상으로 테스트 세그먼트 전송을 일시 중지할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 활성화  </span></b> </p> </td>
   <td colname="col2"> <p>일시 중지된 테스트 그룹에 사용할 수 있습니다. 대상으로 테스트 세그먼트 전송을 재개할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 보기 </span></b> </p> </td>
   <td colname="col2"> <p>완료된 테스트 그룹에 사용할 수 있습니다. 테스트가 생성한 보고 정보를 볼 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 복제 </span></b> </p> </td>
   <td colname="col2"> <p>복제하려는 테스트 그룹과 동일한 구성으로 새 테스트 그룹을 만들 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 삭제 </span></b> </p> </td>
   <td colname="col2"> <p>테스트 그룹을 삭제할 수 있습니다. 테스트 세그먼트는 대상에서 매핑되지 않고, 테스트 그룹과 연관된 기준 세그먼트 및 전환 트레이트는 완전히 편집 가능합니다. 원할 경우 테스트 그룹을 삭제할 때 CSV 파일을 다운로드하라는 메시지가 표시됩니다. </p> </td>
  </tr>
 </tbody>
</table>