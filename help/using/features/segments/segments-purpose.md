---
description: 세그먼트, 해당 구성 요소, 세그먼트 빌더를 사용한 규칙 생성에 대해 설명합니다.
seo-description: 세그먼트, 해당 구성 요소, 세그먼트 빌더를 사용한 규칙 생성에 대해 설명합니다.
seo-title: 세그먼트 목적, 구성 및 규칙
solution: Audience Manager
title: 세그먼트 목적, 구성 및 규칙
uuid: 886d4abe-b1b6-4983-b4fb-b552d51ba
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 세그먼트:목적, 구성 및 규칙 {#segments-purpose-composition-and-rules}

세그먼트, 해당 구성 요소 및 규칙 만들기에 대해 [!UICONTROL Segment Builder]설명합니다.

## 세그먼트 목적

A *`segment`* (또는 *`audience`* a)는 공통 속성을 공유하는 사용자 세트입니다. Audience Manager에서는 서버측 규칙이 있는 세그먼트를 만듭니다. 이러한 규칙을 사용하여 다음과 같은 사이트 방문자 특성을 기반으로 대상 그룹을 만들 수 있습니다.

* 동작;
* 인구 통계(연령, 성별, 소득 등);
* 사용자 인터페이스에서 정의할 수 있는 기타 특성입니다.

## 세그먼트 구성

Audience Manager 세그먼트는 개별 또는 트레이트 그룹으로 구성된 서버측 규칙입니다. 트레이트는 키-값 쌍이라고 하는 데이터 요소로 구성됩니다. 세그먼트 수준에서 설정한 규칙과 함께 이러한 키-값 쌍에는 방문자가 트레이트 및 세그먼트 멤버십에 대한 자격을 얻을 수 있는 기준이 포함되어 있습니다.

## Adobe Analytics 세그먼트 매핑에 대한 고려 사항

Adobe Analytics 세그먼트 또는 보고서 세트를 Experience Cloud 조직에 매핑하면 Audience Manager는 자동으로 해당 읽기 전용 새 세그먼트 및 트레이트를 만듭니다. Audience Manager에서 이러한 세그먼트의 저장소 위치를 편집하거나 변경할 수 없습니다. 그러나 매핑된 Adobe Analytics 세그먼트 또는 보고서 세트에서 수행한 모든 변경 사항은 Audience Manager에 반영됩니다.

>[!TIP]
>
>Audience Manager 세그먼트는 [!DNL Adobe Analytics] 세그먼트와 다릅니다. Analytics [및 Audience](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) Manager의 세그먼트 이해를 참조하여 차이점에 대한 자세한 설명을 확인하십시오.

## 세그먼트 빌더로 규칙 기반 세그먼트 만들기

간단한 예/아니요 조건에 따라 실행되는 기존 픽셀과 달리, 세그먼트 빌더를 사용하면 복잡한 세그먼트 요구 사항을 만들 수 있습니다. 트레이트와 같이 세그먼트는 [!DNL Boolean] 표현식([!DNL AND], [!DNL OR], [!DNL NOT]), 비교 연산자(보다 큼, 보다 작음, 같음 등) 및 최근/빈도 기준을 사용하여 데이터를 평가합니다. 이러한 기능을 통해 비즈니스 요구 사항에 맞는 고객 세그먼트를 만들 수 있습니다.

## 이점

세그먼트는 다음과 같은 기능을 제공하므로 표준 픽셀 기반 고객 생성/세그멘테이션 프로세스를 통해 개선됩니다.

* 자사 트레이트와 타사 트레이트를 사용하여 연관성 있고 유용한 세그먼트를 만들 수 있습니다.
* 부울 연산자, 비교 표현식 및 최근/빈도 기준을 사용하여 세련되고 복잡한 세그멘테이션 규칙을 만듭니다.
* 세그먼트 데이터를 대상 파트너로 보냅니다.
* Audience Manager 보고서를 사용하여 성능 모니터링

>[!MORELIKETHIS]
>
>* [신호, 트레이트 및 세그먼트](../../reference/signal-trait-segment.md)

