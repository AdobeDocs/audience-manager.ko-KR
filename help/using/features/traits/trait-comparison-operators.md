---
description: 이 문서에서는 특성 빌더에 사용되는 비교 연산자에 대해 설명합니다.
seo-description: 이 문서에서는 특성 빌더에 사용되는 비교 연산자에 대해 설명합니다.
seo-title: 트레이트 빌더에서 비교 연산자 사용
solution: Audience Manager
title: 트레이트 빌더에서 비교 연산자 사용
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# 트레이트 빌더에서 비교 연산자 사용 {#working-with-comparison-operators-in-trait-builder}

이 문서에서는 [!UICONTROL Trait Builder]에 사용되는 비교 연산자에 대해 설명합니다.

## 비교 연산자 목적

<!-- c_tb_comparison_operators.xml -->

비교 연산자(또는 관계형 연산자)는 서로 다른 값 간의 관계를 비교, 테스트 또는 평가하는 데 사용됩니다. [!UICONTROL Trait Builder]에서 신호 규칙을 작성할 때 비교 연산자를 사용하면 다른 키-값 쌍 간의 관계를 테스트할 수 있습니다. 예를 들어 신호 규칙을 만들어 값비싼 카메라 구매자를 위한 대상을 정의할 수 있습니다. 이 경우 카메라/가격 키-값 쌍을 만들고 사용자가 설정한 금액보다 가격이 크거나 같은 카메라를 찾은 경우 자격을 부여할 수 있습니다.

## 비교 연산자의 이점

비교 연산자는 여러 값을 기반으로 트레이트를 평가하고 만들어야 할 때 유용합니다. 상품과 서비스의 가격을 보면 이런 상태를 알 수 있다. 예를 들어, 기업은 고객이 보는 제품의 가격을 기준으로 방문자를 식별할 수 있습니다. 하지만 특정 값을 기반으로 개별 세그먼트를 정의하는 것은 행정적으로 비효율적일 수 있습니다. 비교 연산자는 가격 임계값이나 범위를 기반으로 세분화 트리거를 설정하여 이러한 장애를 극복하는 데 도움이 됩니다.

## 비교 연산자

다음 비교 연산자로 규칙을 작성할 수 있습니다.

| 연산자 | 정의 |
|---|---|
| **==** | 같음 |
| **!=** | 같지 않음 |
| **>** | 보다 큼 |
| **&lt;** |  미만% |
| **=>** | 크거나 같음 |
| **&lt;=** | 작거나 같음 |

## 명명된 연산자

다음과 같은 명명된 연산자로 규칙을 작성할 수 있습니다.

| 연산자 | When[!DNL True] |
|---|---|
| **[!UICONTROL Contains]** | 키-값 쌍 *에 있는 값은 이 연산자가 지정한* 문자를 포함합니다. |
| **[!UICONTROL Matcheswords]** | 키-값 쌍 *의 값은 이 연산자가 지정한 패턴과 일치합니다.* |
| **[!UICONTROL Startswith]** | 키-값 쌍 *의 값은 이 연산자가 지정한 문자*&#x200B;로 시작합니다. |
| **[!UICONTROL Endswith]** | 키-값 쌍 *의 값은 이 연산자가 지정한 문자로 끝납니다.* |
| **[!UICONTROL Matchesregex]** | 키-값 쌍 *의 값은 정규 표현식에 의해 지정된 패턴과 일치합니다.* [정규 표현식 사용에 ](../../features/traits/trait-builder-regex.md) 대한 자세한 내용을  [!UICONTROL Trait Builder]살펴보십시오. |

>[!MORELIKETHIS]
>
>* [트레이트 및 세그먼트 빌더의 부울 표현식](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder의 부울 표현식 이해](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder 표현식의 작업 순서](../../features/traits/trait-operator-precedence.md)
>* [부울 및 비교 연산자가 있는 샘플 표현식](../../features/traits/trait-expression-samples.md)

