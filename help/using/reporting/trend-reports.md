---
description: 트렌드 보고서는 트레이트 및 세그먼트에 대한 트렌드 데이터를 반환합니다.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: 트렌드 보고서
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 1%

---

# 트렌드 보고서{#trend-reports}

트렌드 보고서는 트레이트 및 세그먼트에 대한 트렌드 데이터를 반환합니다.

## 개요 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 사용 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])을 클릭하여 사용자 그룹 권한을 다음으로 확장 [!UICONTROL Trend] 보고서. 사용자는 볼 수 있는 권한이 있는 보고에서 이러한 트레이트와 세그먼트만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 내부 팀에서 볼 수 있는 보고 데이터를 제어할 수 있습니다.

예를 들어 다른 광고주 계정을 관리하는 기관은 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다.

실행 [!UICONTROL Trend] 다음 작업을 수행해야 할 때 보고합니다.

* 트레이트 및 세그먼트별로 트렌드 데이터를 검토합니다.
* 1, 7, 14, 30, 60 및 90일 간격으로 트렌드를 추적합니다.
* 시간 경과에 따른 트레이트 및 세그먼트 트렌드를 비교합니다.
* 성능 특성 및 세그먼트가 강하거나 불량한 경우 식별합니다.
* 추가 분석 및 공유를 위해 데이터(.csv 형식)를 내보냅니다.

다음 그림은 의 주요 요소에 대한 높은 수준의 개요를 제공합니다. [!UICONTROL Trend] 보고서.

![](assets/trend_reports.png)

1. 다음 옵션을 구성합니다.
   **보고서 유형:** 원하는 보고서 유형(트레이트 또는 세그먼트)을 선택합니다.
   **날짜 범위:** 보고서의 날짜 범위(시작 날짜 및 종료 날짜)를 지정합니다.
   **표시 간격:** 표시 간격(1, 7, 14, 30, 60 및 90일 간격)을 지정합니다.
1. 이름 또는 ID로 트레이트 또는 세그먼트를 검색합니다.
1. 폴더 목록에서 보고할 트레이트나 세그먼트를 [!UICONTROL Selections] 오른쪽 패널
1. 그래픽 형식으로 데이터에 표시할 보고서를 생성하거나 보고서를 CSV 형식으로 내보냅니다.

## 트렌드 보고서 실행 {#run-trend-report}

이 절차에서는 [!UICONTROL Trend] 보고서.

<!-- 

t_working_with_trend_reports.xml

 -->

1. 다음에서 **[!UICONTROL Analytics]** 대시보드, 클릭 **[!UICONTROL Trend Reports]**.
1. 다음에서 **[!UICONTROL Report Type]** 드롭다운 목록에서 원하는 유형을 선택합니다. **[!UICONTROL Trait]** 또는 **[!UICONTROL Segment]**.
1. 날짜 상자를 클릭하여 달력을 표시한 다음 보고서의 시작 날짜와 종료 날짜를 선택합니다.
1. 표시 간격(1, 7, 14, 30, 60 또는 90일)을 지정합니다.
1. 이름 또는 ID로 트레이트 또는 세그먼트를 검색합니다.
1. 폴더 목록에서 보고할 트레이트나 세그먼트를 [!UICONTROL Selections] 오른쪽 패널
   * 최상의 성능을 위해 [!UICONTROL Trend] 한 번에 20개 이하의 트레이트 또는 세그먼트에 대해 보고합니다.
1. 클릭 **[!UICONTROL Graph Traits]** 또는 **[!UICONTROL Graph Segments]**, 보고 있는 보고서 유형(트레이트 또는 세그먼트)에 따라 다릅니다. 이러한 옵션은 개별적으로 선택한 트레이트나 세그먼트만 모든 폴더와 그래프를 무시합니다.

   또는

   클릭 **[!UICONTROL Export to CSV]** 추가 분석 및 공유를 위해 트레이트 또는 세그먼트 데이터와 모든 폴더를 CSV 형식으로 내보냅니다. 내보내는 작업 [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], 및 [!UICONTROL Total Trait Population] 모든 요일 범위에 대해.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 다음에 대해 계산됨: [!UICONTROL Rule-based Traits] 만 해당.

1. (선택 사항) 개별 트레이트 또는 세그먼트 위에 마우스를 놓아 각 데이터 포인트에 대한 방문 횟수와 날짜를 표시합니다. 표에서 열 헤더를 클릭하여 결과를 오름차순이나 내림차순으로 정렬할 수 있습니다.

## 트레이트에 대한 트렌드 보고서 결과 {#trend-report-results-traits}

아래 필터는 를 실행할 때 사용할 수 있습니다. [!UICONTROL Trend Report] 및 선택 **[!UICONTROL Trait]** 를 보고서 유형으로 사용하십시오.

다음을 기준으로 결과 필터링 시 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 은 선택한 시간 범위 내에서 프로필에 트레이트를 추가한 익명 장치 방문자의 수입니다.
* [!UICONTROL Total Trait Realization] 은 선택한 시간 범위 내에 있는 총 익명 마우스 트레이트 실현 수입니다.
* [!UICONTROL Total Trait Population] 은 프로필에 이 트레이트를 가진 익명 장치 방문자의 수입니다.

다음을 기준으로 결과 필터링 시 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 은 선택한 시간 범위 내에서 프로필에 트레이트를 추가한 인증된 방문자의 수입니다.
* [!UICONTROL Total Trait Realization] 은 선택한 시간 범위 내 인증된 총 트레이트 실현 수입니다.
* [!UICONTROL Total Trait Population] 은 프로필에 이 트레이트가 있는 인증된 방문자의 수입니다.

![트렌드 보고서 트레이트](assets/trend-report-traits.png)

0은 다음을 나타냅니다 [!DNL Audience Manager] 해당 날짜의 데이터를 수집하지 않았습니다. 빈 항목은 트레이트가 존재하지 않았음을 나타냅니다.

크로스 디바이스 지표가 작동하는 방식에 대한 자세한 내용은 아래 비디오를 시청하십시오.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## 세그먼트에 대한 트렌드 보고서 결과 {#segment-report-results-traits}

아래 필터는 를 실행할 때 사용할 수 있습니다. [!UICONTROL Trend Report] 및 선택 **[!UICONTROL Segments]** 를 보고서 유형으로 사용하십시오.

* **[!UICONTROL Real-time Segment Population]**: 선택한 시간 범위 내에서 세그먼트에 적합한 방문자의 수입니다.
* **[!UICONTROL Total Segment Population]**: 세그먼트에 대한 적격 방문자의 총 수입니다.

![트렌드 보고서 세그먼트](assets/trend-report-segments.png)
