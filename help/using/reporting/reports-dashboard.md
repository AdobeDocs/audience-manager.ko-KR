---
description: 대시보드를 사용하여 지정된 기간 동안 특성 유형과 세그먼트별로 분류된 파트너의 고유 방문자 수에 대한 정보를 볼 수 있습니다.
seo-description: 대시보드를 사용하여 지정된 기간 동안 특성 유형과 세그먼트별로 분류된 파트너의 고유 방문자 수에 대한 정보를 볼 수 있습니다.
seo-title: 보고서 대시보드
solution: Audience Manager
title: 보고서 대시보드
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: 보고 참조 참조
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 1%

---

# 보고서 대시보드 {#reports-dashboard}

대시보드를 사용하여 지정된 기간 동안 트레이트 유형 및 세그먼트별로 분류된 고유한 방문자 수에 대한 정보를 봅니다.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] 사용자  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])를 사용하여 사용자 그룹 권한을 로  [!UICONTROL Dashboard]확장합니다. 사용자는 대시보드에서 볼 수 있는 권한이 있는 정보만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 내부 팀이 볼 수 있는 보고 데이터 기능을 제어할 수 있습니다.

예를 들어 다른 광고주 계정을 관리하는 에이전시는 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다. 이 대시보드는 데이터 배달 문제를 해결하는 데 사용할 수 있습니다.

예를 들어 고유 사용자 유형(규칙 기반 및 온보드)의 분류를 사용하는 총 고유 사용자의 급감 또는 스파이크가 발견되면 잠재적인 데이터 배달 문제를 추적하기 위한 더 나은 시작점이 있습니다. 총 고유 사용자 및 온보드 고유 사용자의 급감이 발견되면 [!UICONTROL On-boarding Status] 보고서로 이동하여 인바운드 파일에 문제가 있는지 확인할 수 있습니다.

**대시보드에 액세스하려면:**

1. 위쪽 탐색 메뉴에서 **[!UICONTROL Dashboard]**&#x200B;을 클릭합니다.
2. *선택* 사항드롭다운 목록에서 마지막 보고 날짜(7일, 14일(기본값), 30일 또는 60일)에서 원하는 기간을 선택합니다.

   선택한 기간에 따라 [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] 및 [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] 패널의 델타 변경 사항은 오늘 종료되는 기간 동안 동일한 길이의 이전 기간과 비교하여 대상의 고유 방문자 수가 변경된 것을 표시합니다. 예를 들어 7일을 선택하면 델타는 7일 전에 끝나는 7일 동안의 고유 방문자와 7일 전에 끝나는 7일 동안의 고유 방문자를 비교합니다.

   >[!NOTE]
   >
   >[!UICONTROL Trend] 보고서를 실행하여 평범하지 않은 델타 변경을 조사할 수 있습니다. 예를 들어 지난 7일 동안 특별히 큰 델타 변경이 있는 경우, 지난 14일(2 x 7) 동안 [!UICONTROL Trend] 보고서를 실행하여 숫자를 더 잘 이해할 수 있습니다.

   로그인한 사용자의 권한에 따라 다음 패널이 표시됩니다.

   * [파트너 고유 수](../reporting/reports-dashboard.md#partner-uniques)
   * [가장 큰 트레이트/가장 많이 변경된 트레이트](../reporting/reports-dashboard.md#largest-traits)
   * [가장 큰 세그먼트/가장 많이 변경된 세그먼트](../reporting/reports-dashboard.md#most-changed-segments)

3. *선택* 사항 **[!UICONTROL Normalize]** 을 클릭하면 모든 데이터가 동일한 비율로 표시됩니다. 모든 데이터 포인트 위로 마우스를 가져가면 자세한 정보를 볼 수 있습니다.

## 파트너 고유 수 {#partner-uniques}

보기에 필요한 권한:[!UICONTROL View All Traits].

![](assets/partner_uniques.png)

이 패널에는 지정된 기간 동안의 고유 방문자 수가 표시됩니다. 개별 색상으로 구분된 라인은 알고리즘, 규칙 기반 및 온보드 트레이트를 사용하여 캡처된 총 고유 방문자 수와 고유한 방문자 수를 나타냅니다.

>[!NOTE]
>
>총 고유 방문자 수는 규칙 기반 트레이트나 온보드 트레이트를 통해 캡처된 방문자를 나타냅니다. 하지만 고유 방문자 수의 총계는 규칙 기반 트레이트와 온보드 트레이트를 사용하여 캡처된 고유 방문자 수의 합계와 같지 않습니다. 동일한 고유 사용자가 이러한 두 특성 유형 중 하나로 표시될 수 있습니다.

## 가장 큰 트레이트/가장 많이 변경된 트레이트 {#largest-traits}

보기에 필요한 권한:[!UICONTROL View Traits].

![](assets/largest_traits.png)

이 패널에는 다양한 트레이트에서 캡처한 고유 방문자 수가 표시됩니다.

**[!UICONTROL Show]** 드롭다운 목록을 사용하여 다양한 유형의 트레이트에 대한 정보를 표시합니다.[!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] 또는 [!UICONTROL Rule-Based].

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
   <td colname="col2"> <p>고유 방문자 수에 대한 정보를 숫자(가장 높은 방문자에서 가장 낮은 방문자)별로 정렬하고 지정된 기간 동안의 고유 방문자의 델타 변경을 나열합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 많이 변경된 트레이트</span> </p> </td> 
   <td colname="col2"> <p>델타 변경 내용별로 정렬된 고유 방문자 수에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 가장 큰 세그먼트/가장 많이 변경된 세그먼트 {#most-changed-segments}

보기에 필요한 권한:[!UICONTROL View Segments].

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
   <td colname="col2"> <p>지정된 기간 동안의 고유 방문자 수 및 고유 방문자의 델타 변경에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 가장 최근에 변경된 세그먼트</span> </p> </td> 
   <td colname="col2"> <p>델타 변경 내용별로 정렬된 고유 방문자 수에 대한 정보를 표시합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
