---
description: 대시보드를 사용하여 지정된 기간 동안 특성 유형과 세그먼트별로 분류된 파트너의 고유 방문자 수에 대한 정보를 봅니다.
seo-description: 대시보드를 사용하여 지정된 기간 동안 특성 유형과 세그먼트별로 분류된 파트너의 고유 방문자 수에 대한 정보를 봅니다.
seo-title: 보고서 대시보드
solution: Audience Manager
title: 보고서 대시보드
uuid: 350 EEE 2 D -72 F 7-42 A 7-916 B -60 F 9 A 362 C 5 CF
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

대시보드를 사용하여 지정된 기간 동안 특성 유형과 세그먼트별로 분류된 고유 방문자 수에 대한 정보를 봅니다.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] ( [!UICONTROL Role Based Access Control][!UICONTROL RBAC]) 를 사용하여 사용자 그룹 권한을로 [!UICONTROL Dashboard]확장합니다. 사용자는 대시보드에 대한 정보를 볼 수 있는 정보만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 내부 팀이 볼 수 있는 보고 데이터를 제어할 수 있습니다.

예를 들어, 다른 광고주 계정을 관리하는 에이전시는 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다. 이 대시보드는 데이터 배달 문제를 해결하는 데 사용할 수 있습니다.

예를 들어 고유 사용자 유형 (규칙 기반 대 온보딩) 의 분류를 사용하는 총 고유 사용자 수의 DIP 또는 스파이크가 발견되면 잠재적인 데이터 배달 문제를 추적할 수 있는 더 좋은 시작점이 있습니다. If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**대시보드에 액세스하려면:**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *선택 사항* 드롭다운 목록에서 마지막 보고 날짜 (7 일, 14 일 (기본값), 30 일 또는 60 일) 의 원하는 시간대를 선택합니다.

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. 예를 들어 7 일을 선택하면 델타는 7 일 전 7 일에 대한 고유 방문자에 대해 오늘 종료 7 일 동안의 고유 방문자를 비교합니다.

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   로그인한 사용자의 권한에 따라 다음 패널이 표시됩니다.

   * [파트너 고유 방문자](../reporting/reports-dashboard.md#partner-uniques)
   * [가장 큰 특성/가장 변경된 특성](../reporting/reports-dashboard.md#largest-traits)
   * [가장 큰 세그먼트/가장 많이 변경된 세그먼트](../reporting/reports-dashboard.md#most-changed-segments)

3. *옵션* **[!UICONTROL Normalize]** 그래프 위를 클릭하여 동일한 비율에 있는 모든 데이터를 표시합니다. 데이터 포인트 위로 마우스를 가져가면 더 자세한 정보를 볼 수 있습니다.

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

이 패널에는 지정된 기간 동안의 고유 방문자 수가 표시됩니다. 개별 색상 코드 라인은 알고리즘, 규칙 기반 및 온보딩 트레이트를 사용하여 캡처한 고유 방문자 수와 고유 방문자 수를 나타냅니다.

>[!NOTE]
>
>총 고유 방문자 수는 규칙 기반 트레이트나 온보드 트레이트를 통해 캡처한 방문자를 나타냅니다. 그러나 총 고유 방문자 수는 규칙 기반 트레이트와 온보딩 트레이트를 사용하여 캡처한 고유 방문자의 합계와 같지 않습니다. 이 두 특성 중 하나에 동일한 고유 사용자가 표시될 수 있습니다.

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

이 패널에는 다양한 트레이트가 캡처한 고유 방문자 수가 표시됩니다.

**[!UICONTROL Show]** 드롭다운 목록을 사용하여 다양한 유형의 트레이트에 대한 정보를 표시할 수 있습니다. [!UICONTROL All Traits][!UICONTROL Algorithmic], [!UICONTROL Onboarded]또는 [!UICONTROL Rule-Based].

이 패널에는 다음 탭이 포함되어 있습니다.

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 탭 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 큰 특징</span> </p> </td> 
   <td colname="col2"> <p>고유 방문자 수 (가장 높은 것부터 가장 낮음) 로 정렬된 고유 방문자 수에 대한 정보를 표시하며 지정된 기간 동안 고유 방문자의 델타 변경 사항도 나열합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 변경된 특성</span> </p> </td> 
   <td colname="col2"> <p>델타 변경에 따라 정렬된 고유 방문자 수에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

이 패널에는 실시간으로 다양한 세그먼트에서 캡처한 고유 방문자 수가 표시됩니다.

이 패널에는 다음 탭이 포함되어 있습니다.

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 탭 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 최대 세그먼트 수</span> </p> </td> 
   <td colname="col2"> <p>지정된 기간 동안의 고유 방문자 수 및 고유 방문자의 델타 변경 수에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 변경된 세그먼트</span> </p> </td> 
   <td colname="col2"> <p>델타 변경에 따라 정렬된 고유 방문자 수에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

