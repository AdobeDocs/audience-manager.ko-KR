---
description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 타블로가 포함됩니다.
seo-description: 데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 타블로가 포함됩니다.
seo-title: 데이터 처리 구성 요소
solution: Audience Manager
title: 데이터 처리 구성 요소
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 시스템 구성 요소
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# 데이터 처리 구성 요소{#data-processing-components}

데이터 처리 구성 요소에는 Hadoop, Snowflake, SOLR 및 타블로가 포함됩니다.

<!-- 

c_comproc.xml

 -->

Audience Manager은 다음 구성 요소를 사용하여 데이터를 처리합니다.

## Hadoop {#hadoop}

[!DNL Audience Manager]에서 Hadoop은 사용자에 대해 알고 있는 모든 [!DNL Audience Manager]을 포함하는 기본 데이터베이스입니다. 예를 들어 [프로필 캐시 서버](../../reference/system-components/components-data-collection.md)가 사용자의 데이터가 포함된 로그 파일을 만들면 해당 데이터를 Hadoop으로 전송하여 저장소에 저장합니다. 기타 중요한 Hadoop 요소는 다음과 같습니다.

* **하이브:** Hadoop을 위한 데이터 웨어하우스. 하이브는 Hadoop에 저장된 데이터에 대한 임시 쿼리를 관리합니다.

* **HBase:** 매우 큰 Hadoop 데이터베이스입니다. 인바운드 및 아웃바운드 데이터, 트레이트 규칙, 알고리즘 모델링 정보를 처리 및 관리하고 데이터를 다른 시스템으로 저장 및 이동하는 것과 관련된 다양한 기타 기능을 수행합니다.

고객은 이러한 시스템에 직접 액세스할 수 없습니다. 그러나 이러한 구성 요소는 사이트 방문자에 대한 중요한 데이터를 저장하므로 고객이 간접적으로 고객과 협력합니다.

## Snowflake {#snowflake}

[](https://www.snowflake.net/) 스노플라케는 거대한 클라우드 데이터베이스이다. 그래프의 각 항목에 대한 % 변경 사항을 표시하는 많은 대시보드 그래프 및 관련 텍스트 상자에 데이터를 제공합니다. [!DNL Audience Manager] 을 사용하고 대시보드 보고서를 보면 [!UICONTROL Snowflake]에서 제공하는 데이터와 상호 작용합니다.



![](assets/dashboardreport.png)

이것은 결코 포괄적인 목록이 아니지만, 일부 일반적인 대시보드 보고서로서 [!UICONTROL Snowflake]이(가) 포함할 책임이 있습니다.

* [일별 트레이트 변형 보고서](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* 모든 중복 보고서(각 중복 보고서에 대한 정보는 [대화형 보고서](/help/using/reporting/dynamic-reports/dynamic-reports.md) 섹션 참조)를 참조하십시오.
* [사용되지 않은 신호 보고서](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR은 Apache의 오픈 소스 데이터베이스 및 서버 시스템입니다. 대규모 데이터 세트에 강력한 빠른 검색 기능을 제공합니다. [!DNL Audience Manager] 고객으로서 세그먼트를 작성할 때 SOLR 실행 상태가 표시됩니다. [!UICONTROL Estimated Historic Segment Size] 보고서에 데이터를 제공합니다. SOLR은 속도 때문에 이 역할에 이상적입니다. 예를 들어 SOLR은 규칙을 작성하고 세그먼트에 새 트레이트를 추가할 때 내역 크기 데이터를 업데이트할 수 있습니다.



![](assets/audsize.png)

## 타블로 {#tableau}

[!DNL Audience Manager] 는  [](https://www.tableausoftware.com/) 대화형 보고서와  [Audience Optimization 보고서](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) 에 데이터를  [ ](../../reporting/audience-optimization-reports/audience-optimization-reports.md)자동으로 표시합니다. 대화형 보고서에는 트레이트 및 세그먼트에 대한 성능 및 겹치기 데이터가 표시됩니다. 열 및 행으로 배치된 숫자를 사용하는 대신 다양한 모양, 색상 및 크기를 사용하여 데이터를 반환합니다. 또한 개별 또는 데이터 포인트 그룹을 선택하고 자세한 내용을 보려면 보고서 결과로 드릴다운할 수 있습니다. 이러한 시각화 기법과 보고서 상호 작용을 통해 많은 숫자 데이터를 쉽게 이해할 수 있습니다.



![](assets/advertiser_analytics.png)
