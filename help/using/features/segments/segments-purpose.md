---
description: 세그먼트 빌더를 사용하여 세그먼트, 구성 요소 및 규칙 만들기에 대해 설명합니다.
seo-description: 세그먼트 빌더를 사용하여 세그먼트, 구성 요소 및 규칙 만들기에 대해 설명합니다.
seo-title: 세그먼트 목적, 구성 및 규칙
solution: Audience Manager
title: 세그먼트 목적, 구성 및 규칙
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 6%

---


# 세그먼트: 목적, 구성 및 규칙 {#segments-purpose-composition-and-rules}

[!UICONTROL segments], 구성 부분 및 [!UICONTROL Segment Builder]을(를) 사용하여 규칙 생성을 설명합니다.

## [!UICONTROL Segments] 목적

*`segment`*(또는 *`audience`*)은 공통 속성을 공유하는 사용자 집합입니다. Audience Manager에서는 서버측 규칙이 있는 [!UICONTROL segments]을 만듭니다. 이러한 규칙을 사용하여 다음과 같은 사이트 방문자 특성을 기준으로 대상 그룹을 만들 수 있습니다.

* 동작;
* 인구 통계(연령, 성별, 소득 등);
* 사용자 인터페이스에서 정의할 수 있는 기타 특성입니다.

## [!UICONTROL Segment] 컴포지션

Audience Manager [!UICONTROL segment]은 개별 또는 트레이트 그룹으로 구성된 서버측 규칙입니다. 트레이트는 키-값 쌍이라고 하는 데이터 요소로 구성됩니다. [!UICONTROL segment] 수준에서 설정한 규칙과 함께 이러한 키-값 쌍에는 방문자가 트레이트 및 [!UICONTROL segment] 멤버쉽을 평가할 수 있는 기준이 포함되어 있습니다.

## [!UICONTROL Adobe Analytics] [!UICONTROL Segment] 매핑에 대한 고려 사항

Adobe Analytics [!UICONTROL segments] 또는 보고서 세트를 Experience Cloud 조직에 매핑하면 Audience Manager은 자동으로 새로운 해당 읽기 전용 [!UICONTROL segments] 및 트레이트를 만듭니다. Audience Manager에서 이러한 [!UICONTROL segments]의 저장소 위치를 편집하거나 변경할 수 없습니다. 그러나 매핑된 Adobe Analytics [!UICONTROL segments] 또는 보고서 세트에서 수행하는 모든 변경 사항은 Audience Manager에 반영됩니다.

>[!TIP]
>
>Audience Manager [!UICONTROL segments]은 [!DNL Adobe Analytics] [!UICONTROL segments]과(와) 다릅니다. 차이점에 대한 자세한 설명은 [Analytics 및 Audience Manager의 세그먼트 이해](https://docs.adobe.com/content/help/ko-KR/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)를 참조하십시오.

## [!UICONTROL Segment Builder]과 함께 규칙 기반 [!UICONTROL Segments] 만들기

간단한 예/아니요 조건에 응답하여 실행되는 기존 픽셀과 달리 [!UICONTROL Segment Builder]에서는 복잡한 [!UICONTROL segment] 요구 사항을 만들 수 있습니다. [!UICONTROL traits]과 마찬가지로 [!UICONTROL segments]은 [!DNL Boolean] 표현식([!DNL AND], [!DNL OR], [!DNL NOT]), 비교 연산자(보다 큼, 작음, 같음 등) 및 최근/빈도 기준을 사용하여 데이터를 평가합니다. 이러한 기능을 통해 비즈니스 요구 사항과 관련된 집중적인 고객 [!UICONTROL segments]을(를) 만들 수 있습니다.

## 이점

[!UICONTROL Segments] 다음과 같은 기능을 통해 표준 픽셀 기반의 고객 생성/세분화 프로세스를 향상시킬 수 있습니다.

* 자사 트레이트와 타사 트레이트를 사용하여 연관성 있고 유용한 [!UICONTROL segments] 빌드
* 부울 연산자, 비교 표현식 및 최근/빈도 기준을 사용하여 세련되고 복잡한 세그멘테이션 규칙을 만듭니다.
* [!UICONTROL segment] 데이터를 대상 파트너로 보냅니다.
* Audience Manager 보고서를 사용하여 성능 모니터링

>[!MORELIKETHIS]
>
>* [신호, 트레이트 및 세그먼트](../../reference/signal-trait-segment.md)

