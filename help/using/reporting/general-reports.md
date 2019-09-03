---
description: 일반 보고서는 특성, 세그먼트 및 대상에 대한 성과 데이터를 반환합니다.
seo-description: Audience Manager의 일반 보고서는 특성, 세그먼트 및 대상에 대한 성과 데이터를 반환합니다.
seo-title: Audience Manager의 일반 보고서
solution: Audience Manager
title: 일반 보고서
uuid: 0 CEA 75 A 0-969 E -4 EE 3-971 A -60 B 911711 E 52
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# 일반 보고서{#general-reports}

[!UICONTROL General] 보고서는 트레이트, 세그먼트 및 대상에 대한 성과 데이터를 반환합니다.

## 개요 {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager][!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) 를 사용하여 사용자 그룹 권한을 [!UICONTROL General] 보고서로 확장합니다. 사용자는 볼 권한이 있다는 보고에 해당 트레이트 및 세그먼트만 볼 수 있습니다. [!UICONTROL RBAC] 기능을 사용하면 내부 팀이 볼 수 있는 보고 데이터를 제어할 수 있습니다. 예를 들어, 다른 광고주 계정을 관리하는 에이전시는 광고주 A의 계정을 관리하는 팀이 광고주 B의 보고 데이터를 볼 수 없도록 사용자 그룹 권한을 구성할 수 있습니다.

필요할 때 [!UICONTROL General] 보고서를 실행합니다.

* 특성, 세그먼트 또는 대상을 기준으로 성과를 검토할 수 있습니다.
* 1, 7, 14, 30, 60 및 90 일 간격으로 노출 횟수 (합계 및 고유) 를 추적합니다.
* 총 및 고유 로드 카운트를 검토합니다.
* 특성 및 세그먼트 성능을 비교할 수 있습니다.
* 강력하거나 낮은 성능의 특성 및 세그먼트를 식별하고, 수요를 분석하거나, 로드/불 데이터를 타사 보고서와 비교할 수 있습니다.
* 추가 분석 및 공유를 위해 데이터 (. csv 형식) 를 내보낼 수 있습니다.

다음 그림은 [!UICONTROL General] 보고서의 주요 요소에 대한 수준 높은 개요를 제공합니다.

![](assets/general_reports.png)

1. 다음 옵션을 구성합니다.

   * **보고서 유형:** 원하는 보고서 유형 (트레이트, 세그먼트 또는 대상) 를 선택합니다.

   * **날짜의 경우:** 보고서의 날짜 범위를 지정합니다.

2. 특성, 세그먼트 또는 대상을 이름이나 ID 별로 검색합니다.
3. 보고서 목록에서 보고할 트레이트, 세그먼트 또는 대상을 오른쪽의 패널에 [!UICONTROL Selections] 드래그하여 놓습니다.
4. 내보낼 수 있는 표에 표시할 보고서를 생성합니다.

## Run a General Report {#run-general-report}

이 섹션에서는 [!UICONTROL General] 보고서를 실행하고 시간 및 기타 성능 옵션을 설정하는 방법에 대해 설명합니다.

<!-- 

t_run_general_report.xml

 -->

1. **[!UICONTROL Analytics]** 대시보드에서 **[!UICONTROL General Reports]**&#x200B;를 클릭합니다.
1. 드롭다운 **[!UICONTROL Report Type]** 목록에서 원하는 유형을 선택합니다. 특성, 세그먼트 또는 대상.
1. *조건부* 날짜 상자를 클릭하여 달력을 표시한 다음 오늘이 아닌 날짜를 지정하려면 보고서의 종료 날짜를 선택합니다.
1. 특성, 세그먼트 또는 대상을 이름이나 ID 별로 검색합니다.
1. 보고서 목록에서 보고할 트레이트, 세그먼트 또는 대상을 오른쪽의 패널에 [!UICONTROL Selections] 드래그하여 놓습니다.
1. 클릭 **[!UICONTROL Run Report]**.

   내보내기 가능한 표에 결과가 표시됩니다. 열 헤더를 클릭하여 결과를 오름차순이나 내림차순으로 정렬합니다.
2. 보고서 맨 위에 있는 원하는 옵션 단추를 선택하여 성과 ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]또는 [!UICONTROL Total Trait Population]) 또는 시간 (1, 7, 14, 30, 60 또는 90 일 범위) 별로 데이터를 필터링합니다.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] 에 대해서만 [!UICONTROL Rule-based Traits] 계산됩니다.

3. *클릭 (선택 사항***[!UICONTROL Export to CSV]**). 모든 날짜 범위의 [!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Realizations][!UICONTROL Total Trait Population] 내보내기가 내보내집니다.

## 일반 보고서 결과 설명 {#general-reports-explained}

의 숫자는 [!UICONTROL General Reports] 에서 직접 생성됩니다 [!UICONTROL User Profile Store]. 결과는 이러한 보고 번호가 생성된 시간에 백엔드에 [!DNL Audience Manager] 포함된 사용자 수를 반영합니다.

* 이러한 숫자는 트래픽이 과도한 방문자 ID를 포함하지 않습니다. 보트의 트래픽은 백엔드 시스템에 도달하기 전에 필터링됩니다. 또한 일부 보트 트래픽은 백엔드에서 주별 정리 작업 중에 무시됩니다.
* 인바운드 처리를 통해 데이터를 타게팅하고 이러한 ID에 [!DNL Audience Manager] 더 이상 시스템에서 활성 상태가 아닌 사용자를 포함하는 경우 이러한 비활성 [!DNL Audience Manager] UUIDS는 절대로에 도달하지 않으며 [!UICONTROL User Profile Store] 보고되지 않습니다.
* [!UICONTROL Total Trait Realizations] 에 대해서만 [!UICONTROL Rule-based Traits] 계산됩니다.

## 일반 보고서에 트레이트가 표시됩니다. {#general-report-results-traits}

일반 보고서를 실행하고 보고서 유형으로 선택하면 **[!UICONTROL Trait]** 아래 지표를 사용할 수 있습니다.

**고유한 특성 실현**

이 지표는 선택한 시간 범위에서 특성에 대해 자격을 부여한 [고유한 Audience Manager 사용자 ID (UUID)](../reference/ids-in-aam.md) 의 고유한 수를 나타냅니다. 예를 들어 사용자가 10/1에서 홈 페이지를 세 번 방문한 경우 고유한 특성 구현을 보게 됩니다.

**총 특성 구현**

이 지표는 선택한 시간 범위에서 트레이트 총 트레이트 수를 나타냅니다. 예를 들어 사용자가 홈 페이지를 방문한 다음 기술 뉴스 및 스포츠 뉴스 섹션으로 이동한 경우 일반 보고서에 총 세 개의 특성 실현과 고유한 특성 구현으로 나타납니다.

**총 특성 수**

이 지표는 현재 트레이트에 대해 자격 조건을 갖춘 Audience Manager UUIDS의 총 금액을 나타냅니다. 이 숫자를 사용하여 세그멘테이션 및 타깃팅에 사용할 수 있는 총 사용자 수를 파악하십시오. 일반적으로 사용자는 [120 일간 트레이트의 일부로 남아](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)있습니다. 예를 들어, 사용자가 오늘 3 회 홈 페이지를 방문하고 나중에 반환하지 않는 사용자는 지금부터 120 일 전까지 이 인구의 사용자로 유지됩니다. 120 일 표시에서는 모집단에서 제거됩니다. 고유한 특성 및 전체 특성 모집단 간의 차이점에 대한 자세한 내용은 [특성 참조 참조](../features/traits/trait-qualification-reference.md) 자료를 참조하십시오.

아래 그림은 트레이트 보고서 유형에 대한 일반 보고서 실행 결과를 보여줍니다.

![](assets/general_reports_metrics.png)

## 세그먼트에 대한 일반 보고서 결과 {#general-report-results-segments}

일반 보고서를 실행하고 보고서 유형으로 선택하면 **[!UICONTROL Segment]** 아래 지표를 사용할 수 있습니다.

**실시간 세그먼트 모집단**

이 지표는 특정 시간 동안 실시간으로 본 고유 방문자 수를 나타내며 Audience Manager가 본 시점에 해당 세그먼트에 대한 자격을 검증받은 고유 방문자 수를 나타냅니다.

**총 세그먼트 모집단 수**

이 지표는 선택한 룩백 기간 내의 세그먼트에 대한 자격 조건을 충족하는 Audience Manager UUIDS의 총 수를 나타냅니다. 1 일 총 세그먼트 인구는 타깃팅에 가장 정확한 사용자 기반을 나타냅니다.

>[!NOTE]
>
>활성화된 **[!UICONTROL Include Destination Mappings]** 대상에 대한 세그먼트 모집단 분류를 보려면 선택합니다.

아래 그림은 세그먼트 보고서 유형에 대한 일반 보고서 실행 결과를 보여줍니다.

![](assets/general_reports_segment_metrics.png)

## 대상에 대한 일반 보고서 결과 {#general-report-results-destinations}

일반 보고서를 실행하고 보고서 유형으로 선택하면 **[!UICONTROL Destination]** 아래 지표를 사용할 수 있습니다.

**실시간 세그먼트 모집단**

이 지표는 특정 시간 동안 실시간으로 본 고유 방문자 수를 나타내며 Audience Manager가 본 시점에 해당 세그먼트에 대한 자격을 검증받은 고유 방문자 수를 나타냅니다.

**총 세그먼트 모집단 수**

이 지표는 룩백 기간 내의 세그먼트에 속하는 대상 관리자 UUIDS의 총 수를 대상으로 나타냅니다.

아래 그림은 대상 보고서 유형에 대한 일반 보고서 실행 결과를 보여줍니다.

![](assets/general_reports_destinations.png)
