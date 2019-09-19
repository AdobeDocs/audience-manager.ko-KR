---
description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 타블로가 포함됩니다.
seo-description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 타블로가 포함됩니다.
seo-title: 데이터 처리 구성 요소
solution: Audience Manager
title: 데이터 처리 구성 요소
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 데이터 처리 구성 요소{#data-processing-components}

데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 타블로가 포함됩니다.

<!-- 

c_comproc.xml

 -->

Audience Manager는 다음 구성 요소를 사용하여 데이터를 처리합니다.

## Hadoop {#hadoop}

에서 [!DNL Audience Manager][!DNL Audience Manager] Hadoop은 사용자에 대해 모든 정보가 포함된 마스터 데이터베이스입니다. 예를 들어 프로필 캐시 [서버가](../../reference/system-components/components-data-collection.md) 사용자에 대한 데이터가 포함된 로그 파일을 만들면 해당 데이터를 Hadoop에 보내 보관합니다. 기타 중요한 Hadoop 요소는 다음과 같습니다.

* **** 하이브:Hadoop에 대한 데이터 웨어하우스입니다. Hive는 Hadoop에 저장된 데이터에 대한 임시 쿼리를 관리합니다.

* **** HBase:매우 큰 Hadoop 데이터베이스. 인바운드 및 아웃바운드 데이터, 트레이트 규칙, 알고리즘 모델링 정보를 처리 및 관리하고, 데이터를 저장하고 다른 시스템으로 이동하는 것과 관련된 다른 많은 기능을 수행합니다.

고객은 이러한 시스템에 직접 액세스할 수 없습니다. 그러나 이러한 구성 요소는 사이트 방문자에 대한 중요 데이터를 저장하므로 고객은 간접적으로 함께 작업합니다.

## 눈송이 {#snowflake}

[Snowflake는](https://www.snowflake.net/) 거대한 클라우드 데이터베이스입니다. 그래프의 각 항목에 대한 % 변경 사항을 표시하는 대시보드 그래프 및 관련 텍스트 상자에 데이터를 제공합니다. 대시보드 보고서를 사용하고 [!DNL Audience Manager] 보면 에서 제공하는 데이터와 상호 작용하게 됩니다 [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

이것은 결코 포괄적인 목록이 아니지만, 책임이 [!UICONTROL Snowflake] 있는 몇 가지 일반적인 대시보드 보고서는 다음과 같습니다.

* [일별 특성 변형 보고서](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [배달 및 성과 보고서](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* 모든 중복 보고서(각 중복 [보고서에](/help/using/reporting/dynamic-reports/dynamic-reports.md) 대한 자세한 내용은 대화형 보고서 섹션 참조).
* [미사용 신호 보고서](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR은 Apache의 오픈 소스 데이터베이스 및 서버 시스템입니다. Adobe의 대규모 데이터 세트에 대한 강력하고 빠른 검색 기능을 제공합니다. 고객은 [!DNL Audience Manager] 세그먼트를 작성할 때 SOLR의 기능을 확인할 수 있습니다. 보고서에 데이터를 제공합니다 [!UICONTROL Estimated Historic Segment Size] . SOLR은 속도 때문에 이 역할에 이상적입니다. 예를 들어 SOLR은 규칙을 작성하고 세그먼트에 새 트레이트를 추가할 때 내역 크기 데이터를 업데이트할 수 있습니다.



![](assets/audsize.png)

## 타블로 {#tableau}

[!DNL Audience Manager] 을 [사용하여](https://www.tableausoftware.com/) 대화형 보고서 및 [대상 최적화 보고서에](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 데이터를 [표시합니다](../../reporting/audience-optimization-reports/audience-optimization-reports.md). 대화형 보고서는 트레이트 및 세그먼트에 대한 성과 및 중복 데이터를 표시합니다. 열과 행으로 배열된 숫자를 사용하는 대신 다양한 모양, 색상 및 크기를 사용하여 데이터를 반환합니다. 또한 개별 또는 데이터 포인트 그룹을 선택하고 자세한 내용을 보려면 보고서 결과로 드릴다운할 수 있습니다. 이러한 시각화 기법과 보고서 상호 작용은 대량의 숫자 데이터를 쉽게 이해할 수 있도록 도와줍니다.



![](assets/advertiser_analytics.png)

