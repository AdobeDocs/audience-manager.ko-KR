---
description: 동일한 트레이트와 기간에 대한 보고서 간 고유한 사용자 합계의 변형을 설명합니다.
seo-description: Adobe Audience Manager에서 동일한 트레이트와 기간에 대한 보고서 간 고유한 사용자 합계의 변형을 설명합니다
seo-title: AAM에서 Overlap Reports 및 일반 보고서의 고유 사용자 수 계산
solution: Audience Manager
title: Overlap Reports 및 일반 보고서의 고유 사용자 수 계산
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: 보고 참조
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Overlap Reports 및 일반 보고서의 고유 사용자 수 계산{#counting-unique-users-in-overlap-and-general-reports}

이 페이지에서는 동일한 트레이트와 기간에 대한 보고서 간 고유한 사용자 합계 변화를 설명합니다.

<!-- 

c_unique_user_counts.xml

 -->

## 겹치기 보고서:고유 사용자 수

Overlap Reports는 트레이트에 대한 자격이 있는 사용자를 다음과 같이 계산합니다.

* 보고서에 대해 선택한 시간 간격 동안.
* 여기에는 [time-to-live](../features/traits/segment-ttl-explained.md) 값이 보고서에 대해 선택한 시간 간격보다 더 깁니다.
* 시스템에서 활성 상태로 보이는 경우(즉, 다른 트레이트에 대한 자격이 있는 경우 ID 동기화 등) 지난 60일 이내에

## 일반 보고서:고유 사용자 수

일반 보고서는 사이트 방문자가 선택한 기간 동안 트레이트에 대한 자격이 있는 경우 고유 방문자로 계산합니다.

>[!MORELIKETHIS]
>
>* [대화형 보고서](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
* [일반 보고서](../reporting/general-reports.md#general-reports-overview)

