---
description: 세그먼트 빌더, 세그먼트 구성 요소 및 세그먼트 빌더를 사용하여 규칙을 만듭니다.
seo-description: 세그먼트 빌더, 세그먼트 구성 요소 및 세그먼트 빌더를 사용하여 규칙을 만듭니다.
seo-title: 세그먼트 목적, 컴포지션 및 규칙
solution: Audience Manager
title: 세그먼트 목적, 컴포지션 및 규칙
uuid: 886 d 4 abe-b 1 b 6-4983-b 4 fb-b 552 d 54 d 51 ba
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segments: Purpose, Composition, and Rules {#segments-purpose-composition-and-rules}

Describes segments, their constituent parts, and rule creation with [!UICONTROL Segment Builder].

## 세그먼트의 목적

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. Audience Manager 에서는 서버측 규칙이 있는 세그먼트를 만듭니다. 이러한 규칙을 사용하여 다음과 같은 사이트 방문자 특성을 기반으로 대상 그룹을 만들 수 있습니다.

* 동작;
* 인구 통계 (연령, 성별, 수입 등);
* 사용자 인터페이스에서 정의할 수 있는 기타 특성입니다.

## 세그먼트 컴포지션

Audience Manager 세그먼트는 개별 또는 트레이트로 구성된 서버측 규칙입니다. 트레이트는 키-값 쌍이라는 데이터 요소로 구성됩니다. 세그먼트 수준에서 설정한 규칙과 함께, 이러한 키-값 쌍은 트레이트 및 세그먼트 멤버쉽에 대한 방문자를 자격을 부여하는 기준을 포함합니다.

>[!TIP]
>
>Audience Manager segments are different from [!DNL Adobe Analytics] segments. Read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.

## 세그먼트 빌더를 사용하여 규칙 기반 세그먼트 만들기

세그먼트 빌더는 예/아니요 조건에 대한 응답으로 실행되는 기존 픽셀과 달리 복잡한 세그먼트 요구 사항을 만들 수 있습니다. Like traits, segments evaluate data using [!DNL Boolean] expressions ([!DNL AND], [!DNL OR], [!DNL NOT]), comparison operators (greater than, less than, equal to, etc.), and recency/frequency criteria. 이러한 기능을 통해 비즈니스 요구 사항과 관련된 고객 세그먼트를 만들 수 있습니다.

## 이점

세그먼트는 다음과 같은 이유로 표준 픽셀 기반 대상 생성/세그멘테이션 프로세스를 향상시켜 줍니다.

* 자사 트레이트와 서드파티 트레이트를 사용하여 연관성 있고 유용한 세그먼트를 제작할 수 있습니다.
* 부울 연산자, 비교 표현식 및 최근/빈도 기준을 사용하여 세련되고 복잡한 세그멘테이션 규칙을 만듭니다.
* 세그먼트 데이터를 대상 파트너로 전송합니다.
* Adobe Audience Manager 보고서에서 성과 모니터링

>[!MORE_ like_ this]
>
>* [신호, 트레이트 및 세그먼트](../../reference/signal-trait-segment.md)

