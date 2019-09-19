---
description: 대시보드를 사용하여 지정된 기간 동안 특성 유형 및 세그먼트별로 분류된 파트너의 고유 방문자 수에 대한 정보를 봅니다.
seo-description: 대시보드를 사용하여 지정된 기간 동안 특성 유형 및 세그먼트별로 분류된 파트너의 고유 방문자 수에 대한 정보를 봅니다.
seo-title: 보고서 대시보드
solution: Audience Manager
title: 보고서 대시보드
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# 보고서 대시보드 {#reports-dashboard}

대시보드를 사용하여 지정된 기간 동안 특성 유형 및 세그먼트별로 분류된 고유 방문자 수에 대한 정보를 봅니다.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 은 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])를 사용하여 사용자 그룹 권한을 로 [!UICONTROL Dashboard]확장합니다. 사용자는 대시보드에서 볼 권한이 있는 정보만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 보고 데이터 내부 팀이 볼 수 있는 기능을 제어할 수 있습니다.

예를 들어 다른 광고주 계정을 관리하는 에이전시는 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다. 이 대시보드는 데이터 배달 문제를 해결하는 데 사용할 수 있습니다.

예를 들어 고유 사용자 유형(규칙 기반 및 온보드)의 분류가 있는 전체 고유 사용자의 하락 또는 스파이크를 발견하면 잠재적인 데이터 전달 문제를 추적하기 위한 더 나은 시작점이 있습니다. 총 고유 사용자 및 온보드 고유 사용자에 대한 감소가 있는 경우 이 [!UICONTROL On-boarding Status] 보고서로 이동하여 인바운드 파일에 문제가 있는지 확인할 수 있습니다.

**대시보드에 액세스하려면**

1. 위쪽 탐색 메뉴에서 을 클릭합니다 **[!UICONTROL Dashboard]**.
2. *선택* 사항 드롭다운 목록에서 마지막 보고 날짜(7일, 14일(기본값), 30일 또는 60일)에서 원하는 기간을 선택합니다.

   선택한 기간에 따라 [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] 및 [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] 패널의 델타 변경 사항은 오늘 끝나는 기간과 동일한 길이의 이전 기간에 대한 대상의 고유 방문자 수를 표시합니다. 예를 들어 7일을 선택하면 델타는 오늘 종료되는 이전 7일 동안의 고유 방문자와 7일 전에 끝나는 7일 동안의 고유 방문자를 비교합니다.

   >[!NOTE]
   >
   >당신은 [!UICONTROL Trend] 보고서를 실행함으로써 평범하지 않은 것으로 보이는 델타 변화를 조사할 수 있습니다. 예를 들어 지난 7일 동안 비정상적으로 큰 델타 변경이 나타나는 경우, 지난 14일(2 x 7) 동안 [!UICONTROL Trend] 보고서를 실행하여 숫자를 보다 잘 파악할 수 있습니다.

   로그인한 사용자의 권한에 따라 다음 패널이 표시됩니다.

   * [파트너 고유](../reporting/reports-dashboard.md#partner-uniques)
   * [가장 큰 트레이트/가장 많이 변경된 트레이트](../reporting/reports-dashboard.md#largest-traits)
   * [가장 큰 세그먼트/가장 많이 변경된 세그먼트](../reporting/reports-dashboard.md#most-changed-segments)

3. *선택* 사항 그래프 **[!UICONTROL Normalize]** 위에 있는 모든 데이터를 동일한 비율로 표시하려면 클릭합니다. 모든 데이터 포인트 위로 마우스를 가져가면 자세한 내용을 볼 수 있습니다.

## 파트너 고유 {#partner-uniques}

보기에 필요한 권한: [!UICONTROL View All Traits]Adobe

![](assets/partner_uniques.png)

이 패널에는 지정된 기간 동안의 고유 방문자 수가 표시됩니다. 개별 색으로 구분된 선은 전체 고유 방문자 수와 알고리즘, 규칙 기반 및 온보드 트레이트를 사용하여 캡처된 고유 방문자 수를 나타냅니다.

>[!NOTE]
>
>총 고유 방문자 수는 규칙 기반 또는 온보드 트레이트를 통해 캡처된 방문자를 나타냅니다. 하지만 고유 방문자 수의 총계는 규칙 기반 트레이트와 온보드 트레이트를 사용하여 캡처된 고유 방문자 수의 합계와 일치하지 않습니다. 동일한 고유 사용자가 이러한 두 가지 특성 유형 중 하나로 표시될 수 있습니다.

## 가장 큰 트레이트/가장 많이 변경된 트레이트 {#largest-traits}

보기에 필요한 권한: [!UICONTROL View Traits]Adobe

![](assets/largest_traits.png)

이 패널에는 다양한 트레이트에서 캡처한 고유 방문자 수가 표시됩니다.

다양한 유형의 트레이트에 대한 정보를 표시하려면 **[!UICONTROL Show]** 드롭다운 목록을 사용합니다. [!UICONTROL All Traits][!UICONTROL Algorithmic], [!UICONTROL Onboarded]또는 [!UICONTROL Rule-Based]기타

이 패널에는 다음 탭이 있습니다.

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 탭 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 큰 트레이트</span> </p> </td> 
   <td colname="col2"> <p>고유 방문자 수에 대한 정보를 숫자(가장 높음 - 가장 낮음)별로 정렬하고 지정된 기간 동안 고유 방문자의 델타 변경을 나열합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 많이 변경된 트레이트</span> </p> </td> 
   <td colname="col2"> <p>델타 변경을 기준으로 정렬된 고유 방문자 수에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 가장 큰 세그먼트/가장 많이 변경된 세그먼트 {#most-changed-segments}

보기에 필요한 권한: [!UICONTROL View Segments]Adobe

![](assets/largest_segments.png)

이 패널에는 다양한 세그먼트가 캡처한 고유 방문자 수가 실시간으로 표시됩니다.

이 패널에는 다음 탭이 있습니다.

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 탭 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 큰 세그먼트</span> </p> </td> 
   <td colname="col2"> <p>지정된 기간 동안 고유 방문자 수와 고유 방문자 수의 델타 변경에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 많이 변경된 세그먼트</span> </p> </td> 
   <td colname="col2"> <p>델타 변경을 기준으로 정렬된 고유 방문자 수에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

