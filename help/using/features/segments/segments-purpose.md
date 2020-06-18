---
description: 세그먼트 빌더를 사용하여 세그먼트, 구성 요소 및 규칙 만들기에 대해 설명합니다.
seo-description: 세그먼트 빌더를 사용하여 세그먼트, 구성 요소 및 규칙 만들기에 대해 설명합니다.
seo-title: 세그먼트 목적, 구성 및 규칙
solution: Audience Manager
title: 세그먼트 목적, 구성 및 규칙
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# 세그먼트: 목적, 구성 및 규칙 {#segments-purpose-composition-and-rules}

구성 요소 [!UICONTROL segments]및 규칙 만들기에 대해 설명합니다 [!UICONTROL Segment Builder].

## 목적 [!UICONTROL Segments]

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. Audience Manager에서 서버측 규칙 [!UICONTROL segments] 으로 만듭니다. 이러한 규칙을 사용하여 다음과 같은 사이트 방문자 특성을 기준으로 대상 그룹을 만들 수 있습니다.

* 동작;
* 인구 통계(연령, 성별, 소득 등);
* 사용자 인터페이스에서 정의할 수 있는 기타 특성입니다.

## [!UICONTROL Segment] 컴포지션

Audience Manager [!UICONTROL segment] 는 개별 또는 트레이트 그룹으로 구성된 서버측 규칙입니다. 트레이트는 키-값 쌍이라고 하는 데이터 요소로 구성됩니다. 이러한 키-값 쌍에는 [!UICONTROL segment] 수준에서 설정한 규칙과 함께 방문자가 트레이트 및 [!UICONTROL segment] 멤버십에 대한 자격을 얻을 수 있는 기준이 포함됩니다.

## 매핑 시 고려 사항 [!UICONTROL Adobe Analytics] [!UICONTROL Segment]

Experience Cloud 조직에 Adobe Analytics [!UICONTROL segments] 또는 보고서 세트를 매핑하면 Audience Manager은 자동으로 해당 읽기 전용 및 새 트레이트를 만듭니다 [!UICONTROL segments] . Audience Manager에서 이러한 저장소 위치를 편집하거나 변경할 수 [!UICONTROL segments] 없습니다. 그러나 매핑된 Adobe Analytics 또는 보고서 세트에서 수행한 모든 변경 사항은 Audience Manager에 반영됩니다 [!UICONTROL segments] .

>[!TIP]
>
>Audience Manager [!UICONTROL segments] 는 [!DNL Adobe Analytics] 다르다 [!UICONTROL segments]. Read [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/ko-KR/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.

## 규칙 기반 만들기 [!UICONTROL Segments] 는 [!UICONTROL Segment Builder]

간단한 예/아니요 조건에 응답하여 실행되는 기존 픽셀과 달리 복잡한 요구 사항 [!UICONTROL Segment Builder] 을 만들 수 [!UICONTROL segment] 있습니다. 예 [!UICONTROL traits]를 들어, 표현식( [!UICONTROL segments] , [!DNL Boolean][!DNL AND]), 비교 연산자(보다 큼, 보다 작음, 같음 등) 및 최근/빈도 기준을 사용하여 데이터를 [!DNL OR][!DNL NOT]평가합니다. 이러한 기능을 통해 비즈니스 요구 사항에 [!UICONTROL segments] 맞는 집중적인 고객을 만들 수 있습니다.

## 이점

[!UICONTROL Segments] 다음과 같은 기능을 통해 표준 픽셀 기반의 고객 생성/세분화 프로세스를 향상시킬 수 있습니다.

* 자사 트레이트와 타사 트레이트를 [!UICONTROL segments] 사용하여 연관성 있고 유용한 콘텐츠를 제작할 수 있습니다.
* 부울 연산자, 비교 표현식 및 최근/빈도 기준을 사용하여 세련되고 복잡한 세그멘테이션 규칙을 만듭니다.
* 대상 파트너에게 [!UICONTROL segment] 데이터 전송
* Audience Manager 보고서를 사용하여 성능 모니터링

>[!MORELIKETHIS]
>
>* [신호, 트레이트 및 세그먼트](../../reference/signal-trait-segment.md)

