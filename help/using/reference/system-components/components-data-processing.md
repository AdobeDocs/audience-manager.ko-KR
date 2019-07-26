---
description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, Solr 및 Tableau가 있습니다.
seo-description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, Solr 및 Tableau가 있습니다.
seo-title: 데이터 처리 구성 요소
solution: Audience Manager
title: 데이터 처리 구성 요소
uuid: D 458 D 869-7 A 23-4016-871 D -0 B 994 CF 4 AF 06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

데이터 처리 구성 요소에는 Hadoop, Snowflake, Solr 및 Tableau가 있습니다.

<!-- 

c_comproc.xml

 -->

Audience Manager 에서는 다음 구성 요소를 사용하여 데이터를 처리합니다.

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. 기타 중요한 Hadoop 요소에는 다음이 포함됩니다.

* **Hive:** Hadoop의 데이터 웨어하우스. Hive는 Hadoop에 저장된 데이터에 대한 애드혹 쿼리를 관리합니다.

* **Hbase:** 매우 큰 Hadoop 데이터베이스. 인바운드 및 아웃바운드 데이터, 특성 규칙, 알고리즘 모델링 정보를 처리하고 관리하며, 데이터를 다른 시스템에 저장하고 이동하는 것과 관련된 다양한 기능을 수행합니다.

고객은 이러한 시스템에 직접 액세스할 수 없습니다. 그러나 이러한 구성 요소가 사이트 방문자에 대한 중요 데이터를 저장하므로 고객이 간접적으로 작업을 수행합니다.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) 는 대규모 클라우드 데이터베이스입니다. 이 콘솔에서는 그래프의 각 항목에 대한 % 변경을 표시하는 많은 대시보드 그래프와 관련 텍스트 상자에 데이터를 제공합니다. If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [일별 특성 변형 보고서](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [전달 및 성과 보고서](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [사용되지 않는 신호 보고서](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

Solr는 Apache의 오픈 소스 데이터베이스 및 서버 시스템입니다. 대용량 데이터 세트에 강력하고 빠른 검색 기능을 제공합니다. [!DNL Audience Manager] 고객은 세그먼트를 빌드할 때 Solr의 작동을 확인할 수 있습니다. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. Solr는 속도가 빠를수록 이 역할에 이상적입니다. 예를 들어 Solr는 규칙을 작성하고 세그먼트에 새로운 트레이트를 추가할 때 내역 크기 데이터를 업데이트할 수 있습니다.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager][은 타블로](https://www.tableausoftware.com/) 기능을 사용하여 [대화형 보고서와](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) [대상 최적화 보고서의 데이터를 표시합니다](../../reporting/audience-optimization-reports/audience-optimization-reports.md). 대화형 보고서는 성능을 표시하고 트레이트 및 세그먼트에 대한 데이터를 겹칩니다. 열과 행으로 정렬된 숫자를 사용하는 대신 다른 모양, 색상 및 크기를 사용하여 데이터를 반환합니다. 또한, 개별 또는 데이터 포인트 그룹을 선택하고 보고서 결과로 드릴다운하여 세부 사항을 볼 수 있습니다. 이러한 시각화 기법과 보고서 상호 작용은 많은 숫자 데이터를 더 쉽게 이해할 수 있도록 도와줍니다.



![](assets/advertiser_analytics.png)

