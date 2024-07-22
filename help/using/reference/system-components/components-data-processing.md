---
description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 Tableau가 포함됩니다.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: 데이터 처리 구성 요소
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---

# 데이터 처리 구성 요소{#data-processing-components}

데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 Tableau가 포함됩니다.

<!-- 

c_comproc.xml

 -->

Audience Manager은 다음 구성 요소를 사용하여 데이터를 처리합니다.

## Hadoop {#hadoop}

[!DNL Audience Manager]에서 Hadoop은 [!DNL Audience Manager]이(가) 사용자에 대해 알고 있는 모든 것을 포함하는 기본 데이터베이스입니다. 예를 들어 [프로필 캐시 서버](../../reference/system-components/components-data-collection.md)에서 사용자에 대한 데이터가 포함된 로그 파일을 만들면 해당 데이터를 Hadoop에 전송하여 저장합니다. 기타 중요한 Hadoop 요소는 다음과 같습니다.

* **하이브:** Hadoop을 위한 데이터 웨어하우스입니다. Hive는 Hadoop에 저장된 데이터에 대한 임시 쿼리를 관리합니다.

* **HBase:** 매우 큰 Hadoop 데이터베이스입니다. 인바운드 및 아웃바운드 데이터, 트레이트 규칙, 알고리즘 모델링 정보를 처리 및 관리하며 데이터 저장 및 다른 시스템으로의 이동과 관련된 다양한 기능을 수행합니다.

고객은 이러한 시스템에 직접 액세스할 수 없습니다. 그러나 이러한 구성 요소가 사이트 방문자에 대한 중요한 데이터를 저장하기 때문에 고객은 간접적으로 이러한 구성 요소와 함께 작업합니다.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/)은(는) 대규모 클라우드 데이터베이스입니다. 이 보고서는 그래프의 각 항목에 대한 % 변경 사항을 표시하는 많은 대시보드 그래프 및 관련 텍스트 상자에 데이터를 제공합니다. [!DNL Audience Manager]을(를) 사용하고 대시보드 보고서를 보면 [!UICONTROL Snowflake]에서 제공한 데이터와 상호 작용하고 있습니다.



![](assets/dashboardreport.png)

이는 결코 포괄적인 목록이 아니지만 [!UICONTROL Snowflake]이(가) 담당하는 몇 가지 일반적인 대시보드 보고서에는 다음이 포함됩니다.

* [일별 트레이트 변형 보고서](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 모든 중복 보고서(각 중복 보고서에 대한 자세한 내용은 [대화형 보고서](/help/using/reporting/dynamic-reports/dynamic-reports.md) 섹션 참조).
* [사용되지 않은 신호 보고서](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR은 Apache의 오픈 소스 데이터베이스 및 서버 시스템입니다. 대용량 데이터 세트에 비해 강력하고 빠른 검색 기능을 제공합니다. [!DNL Audience Manager] 고객은 세그먼트를 작성할 때 SOLR이 작동하는 것을 볼 수 있습니다. [!UICONTROL Estimated Historic Segment Size] 보고서에 데이터를 제공합니다. SOLR은 속도가 빠르기 때문에 이 역할에 이상적입니다. 예를 들어 SOLR은 규칙을 작성하고 새 트레이트를 세그먼트에 추가할 때 기록 크기 데이터를 업데이트할 수 있습니다.



![](assets/audsize.png)

## 타블로 {#tableau}

[!DNL Audience Manager]은(는) [Tableau](https://www.tableausoftware.com/)을(를) 사용하여 [대화형 보고서](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 및 [Audience Optimization 보고서](../../reporting/audience-optimization-reports/audience-optimization-reports.md)에 데이터를 표시합니다. 대화형 보고서는 성능을 표시하며 트레이트 및 세그먼트에 대한 데이터와 겹칩니다. 열과 행에 정렬된 숫자를 사용하는 대신 서로 다른 모양, 색상 및 크기를 사용하여 데이터를 반환합니다. 또한 개별 또는 데이터 포인트 그룹을 선택하고 보고서 결과를 드릴다운하여 자세한 내용을 확인할 수 있습니다. 이러한 시각화 기술과 보고서 상호 작용성은 대량의 숫자 데이터를 더 쉽게 이해할 수 있도록 해줍니다.



![](assets/advertiser_analytics.png)
