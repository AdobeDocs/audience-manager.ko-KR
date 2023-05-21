---
description: Audience Manager에서 사용할 수 있는 알고리즘 모델에 대해 설명합니다.
keywords: 알고리즘 모델이 예측 대상이 작동하는 방식
seo-description: Describes the algorithmic models available in Audience Manager.
seo-title: Algorithmic Models Overview
solution: Audience Manager
title: 알고리즘 모델 개요
feature: Algorithmic Models
exl-id: ee5c3392-2756-45c5-b325-41a51d3c494f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 15%

---

# 알고리즘 모델 개요

## 알고리즘 모델링이란?{#what-algo-modeling}

Audience Manager의 알고리즘 모델링은 데이터 과학을 사용하여 기존 대상을 확장하거나 개인으로 분류하는 것을 의미합니다.

이 작업은 두 가지 유형의 알고리즘을 통해 수행됩니다. [!UICONTROL Look-Alike Modeling] 및 [!UICONTROL Predictive Audiences].

## 유사 잠재고객 모델링{#lam}

[!UICONTROL Look-Alike Modeling] 는 자동화된 데이터 분석을 통해 새롭고 고유한 대상을 발견할 수 있도록 지원합니다. 이 프로세스는 트레이트 또는 세그먼트, 시간 간격, 퍼스트 파티 데이터 소스 및 타사 데이터 소스를 선택하면 시작됩니다. 선택 항목은 알고리즘 모델에 대한 입력을 제공합니다. Analytics 프로세스가 실행되면 선택한 모집단의 공유 특성을 기반으로 적합한 사용자를 찾습니다.

완료 시 이 데이터는에서 사용할 수 있습니다. [트레이트 빌더](../../features/traits/about-trait-builder.md) 를 사용하여 를 기반으로 트레이트를 만들 수 있는 위치 [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md). 또한 알고리즘 트레이트와 규칙 기반 트레이트를 결합하는 세그먼트를 작성하고 부울 표현식 및 비교 연산자를 사용하여 다른 자격 요구 사항을 추가할 수 있습니다.

[!UICONTROL Look-Alike Modeling] 는 사용 가능한 모든 트레이트 데이터에서 값을 추출하는 동적 방법을 제공합니다.

에 대해 자세히 알아보기 [!UICONTROL Look-Alike Modeling], 참조 [유사 모델링 이해](understanding-models.md).

## Predictive Audiences{#predictive-audiences}

[!UICONTROL Predictive Audiences] 을 사용하면 알 수 없는 대상을 고급 데이터 과학 기술을 사용하여 실시간으로 개별 성향으로 분류할 수 있습니다.

마케팅 컨텍스트에서 성향은 인구 통계, 탐색 습관, 쇼핑 이력 등과 같은 특정 트레이트 집합을 공유하는 방문자, 사용자 또는 잠재적 구매자로 정의되는 대상 세그먼트로입니다.

[!UICONTROL Predictive Audiences] 모델은 Audience Manager의 머신 러닝 기능을 사용하여 알 수 없는 대상을 개별 성향으로 자동으로 분류함으로써 이러한 개념을 한 단계 더 발전시킵니다. Audience Manager은 알려진 대상 세트에 대해 알 수 없는 대상의 성향을 계산하여 이를 달성합니다.

에 대해 자세히 알아보기 [!UICONTROL Predictive Audiences], 참조 [Predictive Audiences 개요](predictive-audiences.md).
