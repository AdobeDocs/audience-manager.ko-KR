---
description: 동일한 트레이트와 기간에 대한 보고서 간 고유 사용자 합계의 차이에 대해 설명합니다.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Overlap Reports 및 일반 보고서의 고유 사용자 수 계산
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 12%

---

# Overlap Reports 및 일반 보고서의 고유 사용자 수 계산{#counting-unique-users-in-overlap-and-general-reports}

이 페이지에서는 동일한 트레이트 및 기간에 대한 보고서 간의 고유 사용자 합계 변동에 대해 설명합니다.

<!-- 

c_unique_user_counts.xml

 -->

## Overlap Report: 고유 사용자 수

중복 보고서는 사용자가 트레이트에 적합할 때 고유한 것으로 카운트합니다.

* 보고서에 대해 선택한 시간 간격 동안.
* 이(가) [TTL(Time-to-Live)](../features/traits/segment-ttl-explained.md) 값이 보고서에 대해 선택한 시간 간격보다 깁니다.
* 시스템에서 활성 상태로 표시되는 경우(즉, 다른 트레이트에 대한 자격이 있고, ID 동기화가 있는 경우 등) 지난 60일 이내

## 일반 보고서: 고유 사용자 수

일반 보고서는 선택한 기간 동안 사이트 방문자가 트레이트에 적합한 경우 사이트 방문자를 고유한 것으로 계산합니다.

>[!MORELIKETHIS]
>
>* [대화형 보고서](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [일반 보고서](../reporting/general-reports.md#general-reports-overview)

