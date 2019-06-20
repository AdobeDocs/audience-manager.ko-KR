---
description: 세그먼트 테스트 그룹에서 상호 배타적인 테스트 세그먼트를 만들어 다른 대상의 효과를 비교하고 측정합니다. 효율성을 테스트하기 위해 컨트롤 그룹을 Aside로 설정하고 세그먼트를 백분율로 나눌 수 있습니다.
seo-description: 세그먼트 테스트 그룹에서 상호 배타적인 테스트 세그먼트를 만들어 다른 대상의 효과를 비교하고 측정합니다. 효율성을 테스트하기 위해 컨트롤 그룹을 Aside로 설정하고 세그먼트를 백분율로 나눌 수 있습니다.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: AAEE 820 C -1 E 78-4 FD 4-BD 8 F -2629085 D 78 E 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. 효율성을 테스트하기 위해 컨트롤 그룹을 Aside로 설정하고 세그먼트를 백분율로 나눌 수 있습니다.

## 개요 {#audience-lab-overview}

[!UICONTROL Audience Lab][프로필 링크를](../../features/profile-merge-rules/merge-rules-overview.md) 사용하여 장치 간 테스트를 강화합니다. 이렇게 하면 사용자가 동일한 테스트 세그먼트에 대한 자격을 받을 수 있고 장치 간에 동일한 처리를 받을 수 있습니다. The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

[!UICONTROL Audience Lab] 기본 보기에는 각 테스트 그룹에 대한 카드가 표시됩니다. Click a card to access the **[!UICONTROL Test Group]** view. 이 보기에는 다음과 같은 정보가 포함됩니다.

* **[테스트 그룹 정보](../../features/audience-lab/audience-lab-information-view.md)**
* **[테스트 그룹 보고](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

여러 테스트 세그먼트를 사용하여 여러 테스트 그룹을 만들기 시작하면 검색 상자를 사용하여 특정 테스트 그룹을 찾는 것이 더 쉽습니다. 다음과 같은 방법으로 테스트 그룹을 검색할 수 있습니다.

* 테스트 그룹의 이름;
* 테스트 그룹의 테스트 세그먼트 이름
* 테스트 그룹에 대한 설명입니다.

![](assets/search_and_filter_audience_lab.png)

상태별로 테스트 그룹을 필터링할 수도 있습니다. All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## 상태 {#status}

테스트 그룹의 상태는 활성, 예약, 일시 중지, 초안 또는 완료일 수 있습니다. 아래 표에 나와 있는 각 제품에 대한 자세한 내용을 살펴보십시오.

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
   <td colname="col2"> <p><i>활성</i> 테스트 그룹은 현재 데이터가 대상으로 전송되고 있음을 의미합니다. Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 예약됨 </span></b> </p> </td> 
   <td colname="col2"> <p><i>예약된</i> 테스트 그룹은 아직 활성화되지 않았지만 더 이상 편집할 수 없습니다. It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 일시 중지됨 </span></b> </p> </td> 
   <td colname="col2"> <p><i>일시 중지된</i> 테스트 그룹은 현재 대상에 데이터를 전송하지 않습니다. Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 초안 </span></b> </p> </td> 
   <td colname="col2"> <p><i>초안</i> 테스트 그룹은 아직 활성화되지 않았으므로 여전히 편집할 수 있습니다. 데이터는 매핑된 대상에 아직 전송되지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> completed </span></b> </p> </td> 
   <td colname="col2"> <p><i>완료된</i> 테스트 그룹이 테스트 그룹 <b><span class="uicontrol"> 만들기 </span></b> 마법사에서 선택한 종료 날짜에 도달했으며 보고 데이터 전송을 중지했습니다. </p> </td>
  </tr>
 </tbody>
</table>

## 작업 {#actions}

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
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 일시 정지 </span></b> </p> </td>
   <td colname="col2"> <p>활성 테스트 그룹에 사용할 수 있습니다. 대상으로 테스트 세그먼트 전송을 일시 중지할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Make Active </span></b> </p> </td>
   <td colname="col2"> <p>일시 중지된 테스트 그룹에 사용할 수 있습니다. 대상으로 테스트 세그먼트 전송을 다시 시작할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 보기 </span></b> </p> </td>
   <td colname="col2"> <p>완료된 테스트 그룹에 사용할 수 있습니다. 테스트를 생성한 보고 정보를 볼 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 복제 </span></b> </p> </td>
   <td colname="col2"> <p>복제할 구성과 동일한 구성으로 새 테스트 그룹을 만들 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 삭제 </span></b> </p> </td>
   <td colname="col2"> <p>테스트 그룹을 삭제할 수 있습니다. 테스트 세그먼트는 대상에서 매핑되지 않고, 테스트 그룹과 연결된 기본 세그먼트 및 전환 트레이트도 편집할 수 있습니다. 원할 경우 보고서를 저장하도록 테스트 그룹을 삭제할 때 CSV 파일을 다운로드하라는 메시지가 표시됩니다. </p> </td>
  </tr>
 </tbody>
</table>