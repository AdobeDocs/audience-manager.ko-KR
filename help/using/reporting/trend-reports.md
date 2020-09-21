---
description: 트렌드 보고서는 트레이트 및 세그먼트에 대한 트렌드 데이터를 반환합니다.
seo-description: 트렌드 보고서는 트레이트 및 세그먼트에 대한 트렌드 데이터를 반환합니다.
seo-title: 트렌드 보고서
solution: Audience Manager
title: 트렌드 보고서
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: general & trend reports
translation-type: tm+mt
source-git-commit: d1edc392c2017f4625f0494d50463c395248918f
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 1%

---


# 트렌드 보고서{#trend-reports}

트렌드 보고서는 트레이트 및 세그먼트에 대한 트렌드 데이터를 반환합니다.

## 개요 {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] 사용자 [!UICONTROL Role Based Access Control] 그룹 권한을[!UICONTROL RBAC][!UICONTROL Trend] 보고서에 확장합니다. 사용자는 보고 시 볼 권한이 있다는 트레이트 및 세그먼트만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 보고 데이터 내부 팀이 볼 수 있는 기능을 제어할 수 있습니다.

예를 들어 다른 광고주 계정을 관리하는 에이전시는 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다.

필요할 때 [!UICONTROL Trend] 보고서를 실행합니다.

* 트레이트 및 세그먼트별로 트렌드 데이터를 검토합니다.
* 1, 7, 14, 30, 60 및 90일 간격으로 트렌드를 추적합니다.
* 시간에 따른 트레이트 및 세그먼트 트렌드를 비교할 수 있습니다.
* 강력하거나 좋지 않은 성능 특성과 세그먼트를 식별할 수 있습니다.
* 추가적인 분석 및 공유를 위해 데이터(.csv 형식)를 내보냅니다.

다음 그림은 보고서의 주요 요소에 대한 고급 개요를 [!UICONTROL Trend] 제공합니다.

![](assets/trend_reports.png)

1. 다음 옵션을 구성합니다.
   **보고서 유형:** 원하는 보고서 유형(트레이트 또는 세그먼트)을 선택합니다.
   **날짜 범위:** 보고서의 날짜 범위(시작 날짜 및 종료 날짜)를 지정합니다.
   **표시 간격:** 표시 간격(1, 7, 14, 30, 60 및 90일 간격)을 지정합니다.
1. 이름이나 ID로 트레이트 또는 세그먼트를 검색합니다.
1. 폴더 목록에서 보고할 트레이트나 세그먼트를 오른쪽 [!UICONTROL Selections] 패널에 드래그하여 놓습니다.
1. 데이터를 그래픽 형식으로 표시하거나 보고서를 CSV 형식으로 내보냅니다.

## Run a Trend Report {#run-trend-report}

이 절차에서는 [!UICONTROL Trend] 보고서를 실행하는 방법에 대해 설명합니다.

<!-- 

t_working_with_trend_reports.xml

 -->

1. 대시보드에서 를 **[!UICONTROL Analytics]** 클릭합니다 **[!UICONTROL Trend Reports]**.
1. 드롭다운 **[!UICONTROL Report Type]** 목록에서 원하는 유형을 선택합니다. **[!UICONTROL Trait]** 또는 **[!UICONTROL Segment]**.
1. 날짜 상자를 클릭하여 달력을 표시한 다음 보고서의 시작 및 종료 날짜를 선택합니다.
1. 표시 간격을 지정합니다.1, 7, 14, 30, 60 또는 90일
1. 이름이나 ID로 트레이트 또는 세그먼트를 검색합니다.
1. 폴더 목록에서 보고할 트레이트나 세그먼트를 오른쪽 [!UICONTROL Selections] 패널에 드래그하여 놓습니다.
   * 최상의 성능을 위해 한 번에 20개 미만의 트레이트 또는 세그먼트에 대한 보고서를 실행합니다. [!UICONTROL Trend]
1. 보고 **[!UICONTROL Graph Traits]** 있는 보고서 유형(트레이트 또는 세그먼트)에 따라 또는 을 **[!UICONTROL Graph Segments]**&#x200B;클릭합니다. 이러한 옵션은 개별적으로 선택한 트레이트 또는 세그먼트만 모든 폴더 및 그래프를 무시합니다.

   또는

   추가 분석 및 공유를 위해 트레이트 또는 세그먼트 데이터와 모든 폴더를 CSV 형식으로 내보내려면 **[!UICONTROL Export to CSV]** 클릭합니다. 이렇게 하면 모든 일 범위에 대해 [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]및 [!UICONTROL Total Trait Population] 이 내보내집니다.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 에 대해서만 계산됩니다 [!UICONTROL Rule-based Traits] .

1. (선택 사항) 개별 트레이트 또는 세그먼트 위로 마우스를 가져가면 각 데이터 포인트에 대한 방문 수와 날짜가 표시됩니다. 테이블의 열 헤더를 클릭하여 결과를 오름차순 또는 내림차순으로 정렬할 수 있습니다.

## 트레이트에 대한 트렌드 보고서 결과 {#trend-report-results-traits}

아래 필터는 를 실행하고 보고서 유형 [!UICONTROL Trend Report] **[!UICONTROL Trait]** 으로 선택할 때 사용할 수 있습니다.

결과를 필터링하는 방법: [!UICONTROL Device ID]

* [!UICONTROL Unique Trait Realizations] 는 선택한 시간 범위 내에 프로필에 특성을 추가한 익명 장치 방문자 수입니다.
* [!UICONTROL Total Trait Realization] 은 선택한 시간 범위 내의 익명 마우스 트레이트 실현의 총 수입니다.
* [!UICONTROL Total Trait Population] 는 이 특성이 프로필에 있는 익명 장치 방문자 수입니다.

결과를 필터링하는 방법: [!UICONTROL Cross-Device ID]

* [!UICONTROL Unique Trait Realizations] 은 선택한 시간 범위 내에서 프로필에 트레이트를 추가한 인증된 방문자 수입니다.
* [!UICONTROL Total Trait Realization] 은 선택한 시간 범위 내의 인증된 특성 구현의 총 수입니다.
* [!UICONTROL Total Trait Population] 은 이 특성이 프로필에 있는 인증된 방문자의 수입니다.

![trend-report-traits](assets/trend-report-traits.png)

0은 그 날의 데이터를 수집하지 [!DNL Audience Manager] 않았음을 나타냅니다. 빈 항목은 트레이트가 없음을 나타냅니다.

크로스 디바이스 지표가 작동하는 방식을 자세히 살펴보려면 아래 비디오를 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## 세그먼트에 대한 트렌드 보고서 결과 {#segment-report-results-traits}

아래 필터는 를 실행하고 보고서 유형 [!UICONTROL Trend Report] **[!UICONTROL Segments]** 으로 선택할 때 사용할 수 있습니다.

* **[!UICONTROL Real-time Segment Population]**:선택한 시간 범위 내의 세그먼트에 대해 자격이 있는 방문자 수.
* **[!UICONTROL Total Segment Population]**:세그먼트에 자격이 있는 총 방문자 수입니다.

![trend-report-segments](assets/trend-report-segments.png)