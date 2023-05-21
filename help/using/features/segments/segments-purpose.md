---
description: 세그먼트, 세그먼트 구성 부분 및 세그먼트 빌더로 규칙 만들기에 대해 설명합니다.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: 세그먼트 목적, 구성 및 규칙
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 3%

---

# 세그먼트: 목적, 구성 및 규칙 {#segments-purpose-composition-and-rules}

설명 [!UICONTROL segments], 구성 요소 부분 및 [!UICONTROL Segment Builder].

## 목적 [!UICONTROL Segments]

A *`segment`* (또는 *`audience`*)는 공통 속성을 공유하는 사용자 세트입니다. Audience Manager에서 [!UICONTROL segments] 서버측 규칙 사용. 이러한 규칙을 사용하여 다음과 같은 사이트 방문자 속성을 기반으로 대상 그룹을 작성할 수 있습니다.

* 동작;
* 인구 통계(연령, 성별, 소득 등);
* 사용자 인터페이스에서 정의할 수 있는 기타 특성입니다.

## [!UICONTROL Segment] 컴포지션

Audience Manager [!UICONTROL segment] 는 개별 또는 트레이트 그룹으로 구성된 서버측 규칙입니다. 트레이트는 키-값 쌍이라고 하는 데이터 요소로 구성됩니다. 에 설정한 규칙과 함께 [!UICONTROL segment] 수준, 이러한 키-값 쌍에는 방문자를 트레이트에 적합하게 하는 기준이 포함되어 있습니다. [!UICONTROL segment] 멤버십.

## 고려 사항 [!UICONTROL Adobe Analytics] [!UICONTROL Segment] 매핑

Adobe Analytics 매핑 시 [!UICONTROL segments] 또는 보고서 세트를 Experience Cloud 조직에 보내면 Audience Manager에서 자동으로 새로운 읽기 전용 보고서를 만듭니다 [!UICONTROL segments] 및 트레이트. 이러한 파일의 저장소 위치는 편집하거나 변경할 수 없습니다 [!UICONTROL segments] Audience Manager. 그러나 매핑된 Adobe Analytics에서 수행하는 모든 변경 사항 [!UICONTROL segments] 또는 보고서 세트가 Audience Manager에 반영됩니다.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] 다음과다름: [!DNL Adobe Analytics] [!UICONTROL segments]. 읽기 [Analytics 및 Audience Manager의 세그먼트 이해](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) 차이점에 대한 자세한 설명입니다.

## 규칙 기반 만들기 [!UICONTROL Segments] 포함 [!UICONTROL Segment Builder]

일반적인 예/아니요 조건에 따라 실행되는 기존 픽셀과 달리 [!UICONTROL Segment Builder] 복잡성을 만들 수 있습니다. [!UICONTROL segment] 요구 사항. 좋아요 [!UICONTROL traits], [!UICONTROL segments] 를 사용하여 데이터 평가 [!DNL Boolean] 표현식 ([!DNL AND], [!DNL OR], [!DNL NOT]), 비교 연산자(보다 큼, 보다 작음, 같음 등), 최신성/빈도 기준. 이러한 기능은 집중 대상자를 만드는 데 도움이 됩니다 [!UICONTROL segments] 비즈니스 요구 사항과 관련이 있습니다.

## 이점

[!UICONTROL Segments] 표준 픽셀 기반 대상 만들기/세분화 프로세스를 통해 다음과 같은 이점을 얻을 수 있습니다.

* 관련성 있고 유용한 빌드 [!UICONTROL segments] (자사 및 타사 트레이트 포함)
* 부울 연산자, 비교 표현식 및 최신성/빈도 기준을 사용하여 정교하고 복잡한 세그멘테이션 규칙을 만듭니다.
* 보내기 [!UICONTROL segment] 데이터를 대상 파트너에게 보냅니다.
* Audience Manager 보고서로 성능 모니터링

>[!MORELIKETHIS]
>
>* [신호, 트레이트 및 세그먼트](../../reference/signal-trait-segment.md)

