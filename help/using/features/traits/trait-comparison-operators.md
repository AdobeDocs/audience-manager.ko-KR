---
description: 이 문서에서는 트레이트 빌더에 사용되는 비교 연산자에 대해 설명합니다.
seo-description: 이 문서에서는 트레이트 빌더에 사용되는 비교 연산자에 대해 설명합니다.
seo-title: 트레이트 빌더에서 비교 연산자 사용
solution: Audience Manager
title: 트레이트 빌더에서 비교 연산자 사용
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 트레이트
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 12%

---

# 트레이트 빌더에서 비교 연산자 사용 {#working-with-comparison-operators-in-trait-builder}

이 문서에서는 [!UICONTROL Trait Builder]에 사용되는 비교 연산자에 대해 설명합니다.

## 비교 연산자 목적

<!-- c_tb_comparison_operators.xml -->

비교 연산자(또는 관계형 연산자)는 서로 다른 값 간의 관계를 비교, 테스트 또는 평가하는 데 사용됩니다. [!UICONTROL Trait Builder]에서 신호 규칙을 작성할 때 비교 연산자를 사용하여 다른 키-값 쌍 간의 관계를 테스트할 수 있습니다. 예를 들어, 신호 규칙을 만들어 고가의 카메라 구매자를 위한 대상을 정의할 수 있습니다. 이 경우 카메라/가격 키-값 쌍을 만들고, 사용자가 설정된 금액보다 크거나 같은 카메라를 찾은 경우 자격을 부여할 수 있습니다.

## 비교 연산자의 이점

비교 연산자는 여러 값을 기반으로 트레이트를 평가하고 만들어야 할 때 유용합니다. 상품과 서비스의 가격을 보면 이런 상황을 알 수 있다. 예를 들어, 비즈니스는 보고 있는 제품 가격을 기반으로 방문자를 식별할 수 있습니다. 그러나 특정 값을 기반으로 개별 세그먼트를 정의하는 것은 행정적으로 비효율적일 수 있습니다. 비교 연산자는 가격 임계값 또는 범위를 기반으로 세분화 트리거를 설정하여 이러한 장애를 해결하는 데 도움이 됩니다.

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

| 연산자 | 다음 경우 [!DNL True]으로 평가됩니다. |
|---|---|
| **[!UICONTROL Contains]** | 키-값 쌍 *의 값에 이 연산자로 지정된* 문자가 포함되어 있습니다. |
| **[!UICONTROL Matcheswords]** | 키-값 쌍 *의 값은 이 연산자에 의해 지정된 패턴과 일치합니다.* |
| **[!UICONTROL Startswith]** | 키-값 쌍 *의 값은 이 연산자가 지정한* 문자로 시작합니다. |
| **[!UICONTROL Endswith]** | 키-값 쌍 *의 값은* 이 연산자로 지정된 문자로 끝납니다. |
| **[!UICONTROL Matchesregex]** | 키-값 쌍 *의 값은 정규 표현식에서 지정한 패턴과 일치합니다.* [에서 ](../../features/traits/trait-builder-regex.md) 정규 표현식 사용에 대해 자세히  [!UICONTROL Trait Builder]알아보십시오. |

>[!MORELIKETHIS]
>
>* [트레이트 및 세그먼트 빌더의 부울 표현식](../../reference/boolean-expressions-tsb.md)
* [TraitBuilder의 부울 표현식 이해](../../reference/boolean-expressions-tsb.md)
* [TraitBuilder 표현식의 작업 순서](../../features/traits/trait-operator-precedence.md)
* [부울 및 비교 연산자가 있는 샘플 표현식](../../features/traits/trait-expression-samples.md)

