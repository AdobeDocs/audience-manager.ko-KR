---
description: 세그먼트 빌더를 사용하여 세그먼트, 구성 부분 및 규칙 만들기에 대해 설명합니다.
seo-description: 세그먼트 빌더를 사용하여 세그먼트, 구성 부분 및 규칙 만들기에 대해 설명합니다.
seo-title: 세그먼트 목적, 구성 및 규칙
solution: Audience Manager
title: 세그먼트 목적, 구성 및 규칙
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 세그먼트
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# 세그먼트: 목적, 구성 및 규칙 {#segments-purpose-composition-and-rules}

[!UICONTROL segments], 구성 부분 및 [!UICONTROL Segment Builder]을 사용하여 규칙 작성을 설명합니다.

## [!UICONTROL Segments] 목적

*`segment`*(또는 *`audience`*)는 일반적인 특성을 공유하는 사용자 집합입니다. Audience Manager에서 서버측 규칙을 사용하여 [!UICONTROL segments]을 만듭니다. 이러한 규칙을 사용하면 다음과 같은 사이트 방문자 속성을 기반으로 대상 그룹을 작성할 수 있습니다.

* 동작;
* 인구 통계(나이, 성별, 소득 등);
* 사용자 인터페이스에서 정의할 수 있는 기타 특성입니다.

## [!UICONTROL Segment] 조성물

Audience Manager [!UICONTROL segment]은 개별 또는 트레이트 그룹으로 구성된 서버측 규칙입니다. 트레이트는 키-값 쌍이라고 하는 데이터 요소로 구성됩니다. [!UICONTROL segment] 수준에서 설정한 규칙과 함께 이러한 키-값 쌍에는 방문자의 트레이트 자격 및 [!UICONTROL segment] 멤버십에 대한 자격이 있는 기준이 포함되어 있습니다.

## [!UICONTROL Adobe Analytics] [!UICONTROL Segment] 매핑에 대한 고려 사항

Adobe Analytics [!UICONTROL segments] 또는 보고서 세트를 Experience Cloud 조직에 매핑하면 Audience Manager이 자동으로 새로운 해당 읽기 전용 [!UICONTROL segments] 및 트레이트를 만듭니다. Audience Manager에서 이러한 [!UICONTROL segments]의 저장 위치를 편집하거나 변경할 수 없습니다. 하지만 매핑된 Adobe Analytics [!UICONTROL segments] 또는 보고서 세트에서 수행한 변경 사항은 Audience Manager에 반영됩니다.

>[!TIP]
>
>Audience Manager [!UICONTROL segments]은 [!DNL Adobe Analytics] [!UICONTROL segments]과 다릅니다. 그 차이점에 대한 심도 있는 설명이 필요하면 [Analytics와 Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)의 세그먼트 이해 를 참조하십시오.

## [!UICONTROL Segment Builder]을 사용하여 규칙 기반 [!UICONTROL Segments] 만들기

단순 예/아니요 조건에 응답하여 실행되는 기존 픽셀과 달리 [!UICONTROL Segment Builder]을 사용하면 복잡한 [!UICONTROL segment] 요구 사항을 만들 수 있습니다. [!UICONTROL traits]과 마찬가지로, [!UICONTROL segments]은 [!DNL Boolean] 표현식([!DNL AND], [!DNL OR]), 비교 연산자(보다 큼, 보다 작음, 같음 등) 및 최신성/빈도 기준을 사용하여 데이터를 평가합니다. [!DNL NOT] 이러한 기능은 비즈니스 요구 사항에 맞는 집중적인 대상 [!UICONTROL segments]을 만드는 데 도움이 됩니다.

## 이점

[!UICONTROL Segments] 다음을 수행할 수 있으므로 표준 픽셀 기반 대상 만들기/세그멘테이션 프로세스를 개선합니다.

* 첫 번째 및 타사 트레이트를 사용하여 연관성 있고 유용한 [!UICONTROL segments] 을 빌드합니다.
* 부울 연산자, 비교 표현식 및 최신성/빈도 기준을 사용하여 정교하고 복잡한 세그먼테이션 규칙을 만듭니다.
* [!UICONTROL segment] 데이터를 대상 파트너에게 보냅니다.
* Audience Manager 보고서를 사용하여 성능 모니터링

>[!MORELIKETHIS]
>
>* [신호, 트레이트 및 세그먼트](../../reference/signal-trait-segment.md)

