---
description: 일반 보고서는 트레이트, 세그먼트 및 대상에 대한 성능 데이터를 반환합니다.
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: 일반 보고서
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# 일반 보고서{#general-reports}

A [!UICONTROL General] 보고서는 트레이트, 세그먼트 및 대상에 대한 성능 데이터를 반환합니다.

## 개요 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 사용 [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])을 클릭하여 사용자 그룹 권한을 다음으로 확장 [!UICONTROL General] 보고서. 사용자는 볼 수 있는 권한이 있는 보고에서 이러한 트레이트와 세그먼트만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 내부 팀에서 볼 수 있는 보고 데이터를 제어할 수 있습니다. 예를 들어 다른 광고주 계정을 관리하는 기관은 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다.

실행 [!UICONTROL General] 다음 작업을 수행해야 할 때 보고합니다.

* 트레이트, 세그먼트 또는 대상별로 성능을 검토합니다.
* 1, 7, 14, 30, 60 및 90일 간격으로 노출 횟수(합계 및 고유)를 추적합니다.
* 총 및 고유 로드 수를 검토합니다.
* 트레이트 및 세그먼트 성과 비교.
* 성능 특성 및 세그먼트가 강하거나 불량한 경우 식별하고, 수요를 분석하거나 로드/실행 데이터를 타사 보고서와 비교합니다.
* 추가 분석 및 공유를 위해 데이터(.csv 형식)를 내보냅니다.

다음 그림은 의 주요 요소에 대한 높은 수준의 개요를 제공합니다. [!UICONTROL General] 보고서.

![](assets/general_reports.png)

1. 다음 옵션을 구성합니다.

   * **보고서 유형:** 원하는 보고서 유형(트레이트, 세그먼트 또는 대상)을 선택합니다.

   * **다음 기간 동안:** 보고서의 날짜 범위를 지정합니다.

2. 이름 또는 ID로 트레이트, 세그먼트 또는 대상을 검색합니다.
3. 폴더 목록에서 보고할 트레이트, 세그먼트 또는 대상을 [!UICONTROL Selections] 오른쪽 패널
4. 내보낼 테이블에 표시할 보고서를 생성합니다.

## 일반 보고서 실행 {#run-general-report}

이 섹션에서는 다음을 실행하는 방법을 설명합니다. [!UICONTROL General] 시간 및 기타 성능 옵션을 보고 및 설정합니다.

<!-- 

t_run_general_report.xml

 -->

1. 다음에서 **[!UICONTROL Analytics]** 대시보드, 클릭 **[!UICONTROL General Reports]**.
1. 다음에서 **[!UICONTROL Report Type]** 드롭다운 목록에서 원하는 유형(트레이트, 세그먼트 또는 대상)을 선택합니다.
1. *조건부* 날짜 상자를 클릭하여 달력을 표시한 다음 오늘 이외의 날짜를 지정하려면 보고서의 종료 날짜를 선택합니다.
1. 이름 또는 ID로 트레이트, 세그먼트 또는 대상을 검색합니다.
1. 폴더 목록에서 보고할 트레이트, 세그먼트 또는 대상을 [!UICONTROL Selections] 오른쪽 패널
1. 클릭 **[!UICONTROL Run Report]**.

   내보내기가 가능한 테이블에 결과가 표시됩니다. 열 헤더를 클릭하여 결과를 오름차순 또는 내림차순으로 정렬합니다.
1. 보고서 상단에서 원하는 옵션 버튼을 선택하여 성능별로 데이터를 필터링합니다( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], 또는 [!UICONTROL Total Trait Population]) 또는 시간별(1, 7, 14, 30, 60 또는 90일 범위).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 다음에 대해 계산됨: [!UICONTROL Rule-based Traits] 만 해당.

1. *선택 사항* 클릭 **[!UICONTROL Export to CSV]**. 내보내는 작업 [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], 및 [!UICONTROL Total Trait Population] 모든 요일 범위에 대해.

## 일반 보고서 결과 설명 {#general-reports-explained}

에 있는 숫자 [!UICONTROL General Reports] 에서 바로 생성됩니다. [!UICONTROL User Profile Store]. 결과는 다음과 같은 사용자 수를 반영합니다. [!DNL Audience Manager] 이러한 보고 번호가 생성된 시간에 백엔드에 포함됩니다.

* 이러한 수치는 트래픽이 많은 방문자 ID를 포함하지 않습니다. 봇의 트래픽은 백엔드 시스템에 도달하기 전에 필터링됩니다. 또한 백엔드에서 매주 정리 작업을 실행하는 동안 일부 보트 트래픽이 무시됩니다.
* 인바운드 처리를 통해 데이터를 온보딩하는 경우 [!DNL Audience Manager] UUID 및 이러한 ID에는 시스템에서 더 이상 활성화되지 않고 비활성 상태인 사용자가 포함됩니다 [!DNL Audience Manager] UUID가 다음에 도달하지 않음 [!UICONTROL User Profile Store] 및 은 보고되지 않습니다.
* [!UICONTROL Total Trait Realizations] 다음에 대해 계산됨: [!UICONTROL Rule-based Traits] 만 해당.

## 트레이트에 대한 일반 보고서 결과 {#general-report-results-traits}

아래 필터는 일반 보고서를 실행하고 를 선택할 때 사용할 수 있습니다. **[!UICONTROL Trait]** 를 보고서 유형으로 사용하십시오.

다음을 기준으로 결과 필터링 시 [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] 은 선택한 시간 범위 내에서 프로필에 트레이트를 추가한 익명 장치 방문자의 수입니다.
* [!UICONTROL Total Trait Realization] 선택한 시간 범위 내 익명의 트레이트 실현의 총 수입니다.
* [!UICONTROL Total Trait Population] 은 프로필에 이 트레이트를 가진 익명 장치 방문자의 수입니다.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

다음을 기준으로 결과 필터링 시 [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] 은 선택한 시간 범위 내에서 프로필에 트레이트를 추가한 인증된 방문자의 수입니다.
* [!UICONTROL Total Trait Realization] 은 선택한 시간 범위 내 인증된 총 트레이트 실현 수입니다.
* [!UICONTROL Total Trait Population] 은 프로필에 이 트레이트가 있는 인증된 방문자의 수입니다.

![general-report-traits-cross-device](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## 세그먼트에 대한 일반 보고서 결과 {#general-report-results-segments}

아래 지표는 일반 보고서를 실행하고 을 선택할 때 사용할 수 있습니다 **[!UICONTROL Segment]** 보고서 유형으로:

### 실시간 세그먼트 채우기

이 지표는 지정된 시간 범위 동안 실시간으로 확인되며 Audience Manager에 의해 확인되는 순간 세그먼트에 대해 자격이 되는 실제 고유 방문자 수를 나타냅니다.

### 총 세그먼트 채우기

이 지표는 선택한 전환 확인 기간 내에 세그먼트에 적합한 총 Audience Manager UUID 수를 나타냅니다. 1일 총 세그먼트 모집단은 타깃팅에 대한 가장 정확한 사용자 기반을 나타냅니다.

>[!NOTE]
>
>선택 **[!UICONTROL Include Destination Mappings]** 활성화된 대상에 대한 세그먼트 모집단 분류를 봅니다.

아래 그림은 세그먼트 보고서 유형에 대한 일반 보고서를 실행한 결과를 보여 줍니다.

![](assets/general_reports_segment_metrics.png)

## 대상에 대한 일반 보고서 결과 {#general-report-results-destinations}

아래 지표는 일반 보고서를 실행하고 을 선택할 때 사용할 수 있습니다 **[!UICONTROL Destination]** 보고서 유형으로:

**실시간 세그먼트 채우기**

이 지표는 지정된 시간 범위 동안 실시간으로 확인되며 Audience Manager에 의해 확인되는 순간 세그먼트에 대해 자격이 되는 실제 고유 방문자 수를 나타냅니다.

**총 세그먼트 채우기**

이 지표는 전환 확인 기간 내의 세그먼트에 속하는 대상으로 전송된 총 Audience Manager UUID 수를 나타냅니다.

아래 그림은 대상 보고서 유형에 대한 일반 보고서를 실행한 결과를 보여 줍니다.

![](assets/general_reports_destinations.png)
