---
description: 일반 보고서는 트레이트, 세그먼트 및 대상에 대한 성능 데이터를 반환합니다.
seo-description: Audience Manager의 일반 보고서는 트레이트, 세그먼트 및 대상에 대한 성능 데이터를 반환합니다.
seo-title: Audience Manager의 일반 보고서
solution: Audience Manager
title: 일반 보고서
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: general & trend reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 1%

---


# 일반 보고서{#general-reports}

[!UICONTROL General] 보고서는 트레이트, 세그먼트 및 대상에 대한 성능 데이터를 반환합니다.

## 개요 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] 사용자 그룹  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC])을 사용하여  [!UICONTROL General] 보고서로 권한을 확장합니다. 사용자는 보고 시 볼 권한이 있다는 트레이트 및 세그먼트만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 보고 데이터 내부 팀이 볼 수 있는 기능을 제어할 수 있습니다. 예를 들어 다른 광고주 계정을 관리하는 에이전시는 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다.

필요할 때 [!UICONTROL General] 보고서를 실행합니다.

* 특성, 세그먼트 또는 대상별로 성과를 검토합니다.
* 1, 7, 14, 30, 60 및 90일 간격으로 추적 노출 수(합계 및 고유)입니다.
* 총 및 고유 로드 카운트를 검토합니다.
* 트레이트 및 세그먼트 성과 비교
* 강력하거나 형편없는 성능 특성과 세그먼트를 식별하고 수요를 분석하거나 로드/불 데이터를 타사 보고서와 비교할 수 있습니다.
* 추가적인 분석 및 공유를 위해 데이터(.csv 형식)를 내보냅니다.

다음 그림은 [!UICONTROL General] 보고서의 주요 요소에 대한 고급 개요를 제공합니다.

![](assets/general_reports.png)

1. 다음 옵션을 구성합니다.

   * **보고서 유형:** 원하는 보고서 유형(트레이트, 세그먼트 또는 대상)을 선택합니다.

   * **종료 날짜:** 보고서의 날짜 범위를 지정합니다.

2. 특성, 세그먼트 또는 대상을 이름이나 ID로 검색합니다.
3. 폴더 목록에서 보고할 트레이트, 세그먼트 또는 대상을 오른쪽의 [!UICONTROL Selections] 패널로 드래그하여 놓습니다.
4. 내보내기 가능한 표에 표시할 보고서를 생성합니다.

## 일반 보고서 실행 {#run-general-report}

이 섹션에서는 [!UICONTROL General] 보고서를 실행하고 시간 및 기타 성능 옵션을 설정하는 방법에 대해 설명합니다.

<!-- 

t_run_general_report.xml

 -->

1. **[!UICONTROL Analytics]** 대시보드에서 **[!UICONTROL General Reports]**&#x200B;을 클릭합니다.
1. **[!UICONTROL Report Type]** 드롭다운 목록에서 원하는 유형을 선택합니다.특성, 세그먼트 또는 대상을 참조하십시오.
1. *조건부* 달력을 표시하려면 날짜 상자를 클릭하고 오늘 이외의 날짜를 지정하려면 보고서의 종료 날짜를 선택합니다.
1. 특성, 세그먼트 또는 대상을 이름이나 ID로 검색합니다.
1. 폴더 목록에서 보고할 트레이트, 세그먼트 또는 대상을 오른쪽의 [!UICONTROL Selections] 패널로 드래그하여 놓습니다.
1. 클릭 **[!UICONTROL Run Report]**.

   결과가 내보내기 가능한 표에 표시됩니다. 결과를 오름차순 또는 내림차순으로 정렬하려면 열 헤더를 클릭합니다.
1. 보고서 맨 위에 있는 원하는 옵션 단추를 선택하여 성능( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] 또는 [!UICONTROL Total Trait Population]) 또는 시간(1, 7, 14, 30, 60 또는 90일 범위)별로 데이터를 필터링합니다.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 의 값은  [!UICONTROL Rule-based Traits] 오직

1. *선택* 사항을  **[!UICONTROL Export to CSV]**&#x200B;클릭합니다. 이렇게 하면 모든 일 범위에 대해 [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] 및 [!UICONTROL Total Trait Population]가 내보내집니다.

## 일반 보고서 결과 설명 {#general-reports-explained}

[!UICONTROL General Reports]의 숫자는 Adobe [!UICONTROL User Profile Store]에서 직접 생성됩니다. 결과는 이 보고 번호가 생성된 시점에 백엔드에 [!DNL Audience Manager]이 포함된 사용자 수를 반영합니다.

* 이 숫자들은 트래픽이 너무 많은 방문자 ID를 포함하지 않습니다. 보트 트래픽은 백엔드 시스템에 도달하기 전에 필터링됩니다. 또한 일부 보트 트래픽은 백 엔드에서 주별 정리 작업 실행 중에 무시됩니다.
* [!DNL Audience Manager] UUID에서 인바운드 처리를 통해 데이터를 온보드 중이고 이러한 ID에 시스템에서 더 이상 활성 상태가 아닌 사용자가 포함된 경우, 이러한 비활성 [!DNL Audience Manager] UUID는 [!UICONTROL User Profile Store]에 도달하지 않고 보고되지 않습니다.
* [!UICONTROL Total Trait Realizations] 의 값은  [!UICONTROL Rule-based Traits] 오직

## 일반 보고서 트레이트 결과{#general-report-results-traits}

아래 필터는 일반 보고서를 실행하고 보고서 유형으로 **[!UICONTROL Trait]**&#x200B;을 선택하면 사용할 수 있습니다.

결과를 [!UICONTROL Device ID]별로 필터링할 때:

* [!UICONTROL Unique Trait Realizations] 는 선택한 시간 범위 내에 프로필에 특성을 추가한 익명 장치 방문자 수입니다.
* [!UICONTROL Total Trait Realization] 은 선택한 시간 범위 내의 총 익명 특성 실현의 수입니다.
* [!UICONTROL Total Trait Population] 는 이 특성이 프로필에 있는 익명 장치 방문자 수입니다.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

결과를 [!UICONTROL Cross-Device ID]별로 필터링할 때:

* [!UICONTROL Unique Trait Realizations] 은 선택한 시간 범위 내에서 프로필에 트레이트를 추가한 인증된 방문자 수입니다.
* [!UICONTROL Total Trait Realization] 은 선택한 시간 범위 내의 인증된 특성 구현의 총 수입니다.
* [!UICONTROL Total Trait Population] 은 이 특성이 프로필에 있는 인증된 방문자의 수입니다.

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


## 일반 보고서 세그먼트 결과{#general-report-results-segments}

아래 지표는 일반 보고서를 실행하고 보고서 유형으로 **[!UICONTROL Segment]**&#x200B;을 선택하면 사용할 수 있습니다.

### 실시간 세그먼트 모집단

이 지표는 지정된 시간 범위 동안 실시간으로 보고 Audience Manager에서 본 시간에 세그먼트에 대해 자격이 부여된 고유 방문자 수를 나타냅니다.

### 총 세그먼트 모집단

이 지표는 선택한 뒤로 조회 기간 내에 세그먼트에 자격이 있는 총 Audience Manager UUID 수를 나타냅니다. 1일 총 세그먼트 인구는 타깃팅을 위한 가장 정확한 사용자 기반을 나타냅니다.

>[!NOTE]
>
>활성화된 대상에 대한 세그먼트 모집단 분류를 보려면 **[!UICONTROL Include Destination Mappings]**&#x200B;을 선택합니다.

아래 그림에서는 세그먼트 보고서 유형에 대한 일반 보고서를 실행한 결과를 보여줍니다.

![](assets/general_reports_segment_metrics.png)

## 대상에 대한 일반 보고서 결과{#general-report-results-destinations}

아래 지표는 일반 보고서를 실행하고 보고서 유형으로 **[!UICONTROL Destination]**&#x200B;을 선택하면 사용할 수 있습니다.

**실시간 세그먼트 모집단**

이 지표는 지정된 시간 범위 동안 실시간으로 보고 Audience Manager에서 본 시간에 세그먼트에 대해 자격이 부여된 고유 방문자 수를 나타냅니다.

**총 세그먼트 모집단**

이 지표는 룩백 기간 내에 세그먼트에 속하는 Audience Manager UUID가 대상으로 전송된 총 수를 나타냅니다.

아래 그림에서는 대상 보고서 유형에 대한 일반 보고서를 실행한 결과를 보여줍니다.

![](assets/general_reports_destinations.png)
