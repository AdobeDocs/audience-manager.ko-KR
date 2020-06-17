---
description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 Tableau가 포함됩니다.
seo-description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 Tableau가 포함됩니다.
seo-title: 데이터 처리 구성 요소
solution: Audience Manager
title: 데이터 처리 구성 요소
uuid: d458d869-7a23-4016-871d-0b994cf4af06
translation-type: tm+mt
source-git-commit: 9a92420b1f0116c0fd71db56895720e0ee894f30
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# 데이터 처리 구성 요소{#data-processing-components}

데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 Tableau가 포함됩니다.

<!-- 

c_comproc.xml

 -->

Audience Manager은 다음 구성 요소를 사용하여 데이터를 처리합니다.

## Hadoop {#hadoop}

Hadoop [!DNL Audience Manager]은 사용자에 대해 모든 정보가 포함된 기본 [!DNL Audience Manager] 데이터베이스입니다. 예를 들어 [프로필 캐시 서버가](../../reference/system-components/components-data-collection.md) 사용자에 대한 데이터가 포함된 로그 파일을 만들면 해당 데이터를 Hadoop에 보내 보관합니다. 기타 중요한 Hadoop 요소는 다음과 같습니다.

* **하이브:** Hadoop에 대한 data warehouse Hive는 Hadoop에 저장된 데이터에 대한 임시 쿼리를 관리합니다.

* **HBase:** 매우 큰 Hadoop 데이터베이스입니다. 인바운드 및 아웃바운드 데이터, 특성 규칙, 알고리즘 모델링 정보를 처리 및 관리하고 데이터를 저장하고 다른 시스템으로 이동하는 것과 관련된 다양한 기능을 수행합니다.

고객은 이러한 시스템에 직접 액세스할 수 없습니다. 그러나 이러한 구성 요소는 사이트 방문자에 대한 중요 데이터를 저장하므로 고객은 간접적으로 작업합니다.

## 눈꽃 {#snowflake}

[눈송이는](https://www.snowflake.net/) 거대한 클라우드 데이터베이스이다. 그래프의 각 항목에 대한 % 변경 사항을 표시하는 많은 대시보드 그래프와 관련 텍스트 상자에 데이터를 제공합니다. 대시보드 보고서 [!DNL Audience Manager] 를 사용하고 보면 에서 제공하는 데이터와 상호 작용하게 됩니다 [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

이것은 종합적인 목록이 아니라 책임이 있는 일부 일반적인 대시보드 보고서 [!UICONTROL Snowflake] 가 포함됩니다.

* [일별 특성 변형 보고서](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 모든 중복 보고서(각 중복 보고서에 대한 자세한 내용은 [대화형 보고서](/help/using/reporting/dynamic-reports/dynamic-reports.md) 섹션 참조).
* [사용하지 않은 신호 보고서](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR은 Apache의 오픈 소스 데이터베이스 및 서버 시스템입니다. Adobe의 대용량 데이터 세트에 대한 강력하고 빠른 검색 기능을 제공합니다. 고객으로서 세그먼트를 작성할 때 SOLR이 작동하는 것을 확인할 수 있습니다. [!DNL Audience Manager] 데이터를 [!UICONTROL Estimated Historic Segment Size] 보고서에 제공합니다. SOLR은 속도 때문에 이 역할에 이상적입니다. 예를 들어 SOLR은 규칙을 작성하고 세그먼트에 새 트레이트를 추가할 때 내역 크기 데이터를 업데이트할 수 있습니다.



![](assets/audsize.png)

## 타블로 {#tableau}

[!DNL Audience Manager] 타블로 [를](https://www.tableausoftware.com/) 사용하여 [대화형 보고서](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 및 [대상 최적화 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md)에 데이터를표시합니다. 대화형 보고서에는 성과 표시 및 트레이트 및 세그먼트에 대한 중복 데이터가 표시됩니다. 열과 행으로 정렬된 숫자를 사용하는 대신 다양한 모양, 색상 및 크기를 사용하여 데이터를 반환합니다. 또한 개별 또는 데이터 포인트 그룹을 선택하고 자세한 내용은 보고서 결과로 드릴다운할 수 있습니다. 이러한 시각화 기법과 보고서 상호 작용은 대량의 숫자 데이터를 쉽게 이해할 수 있도록 도와줍니다.



![](assets/advertiser_analytics.png)

