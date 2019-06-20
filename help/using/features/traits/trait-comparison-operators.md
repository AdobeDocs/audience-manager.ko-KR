---
description: 이 문서에서는 특성 빌더에 사용되는 비교 연산자를 설명합니다.
seo-description: 이 문서에서는 특성 빌더에 사용되는 비교 연산자를 설명합니다.
seo-title: 특성 빌더에서 비교 연산자를 사용한 작업
solution: Audience Manager
title: 특성 빌더에서 비교 연산자를 사용한 작업
uuid: 41 bec 3 b 3-e 5 df -4 a 6 f-abb 0-80 ce 4 c 75 f 5 e 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## 비교 연산자의 목적

<!-- c_tb_comparison_operators.xml -->

비교 연산자 (또는 관계 연산자) 는 다른 값 간의 관계를 비교, 테스트 또는 평가하는 데 사용됩니다. In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. 예를 들어 값비싼 카메라 쇼핑객을 대상으로 하는 고객을 정의하는 신호 규칙을 만들 수 있습니다. 이 경우 카메라/가격 키-값 쌍을 만들고 설정된 금액이상의 가격이 있는 카메라를 찾은 경우 사용자를 자격을 부여할 수 있습니다.

## 비교 연산자의 이점

비교 연산자는 여러 값을 기반으로 트레이트를 평가하고 만들어야 할 때 유용합니다. 상품 및 서비스의 가격을 보면 이러한 상황을 설명할 수 있습니다. 예를 들어, 기업은 본 제품의 가격을 기준으로 방문자를 식별할 수 있습니다. 그러나 특정 값을 기반으로 개별 세그먼트를 정의하는 것은 관리상의 비효율적일 수 있습니다. 비교 연산자는 가격 임계값 또는 범위를 기반으로 세그멘테이션 트리거를 설정함으로써 이러한 장애를 극복합니다.

## 비교 연산자

다음과 같은 비교 연산자를 사용하여 규칙을 작성할 수 있습니다.

| 연산자 | 정의 |
|---|---|
| **==** | 같음 |
| **!=** | 같지 않음 |
| **&gt;** | 보다 큼 |
| **&lt;** |  미만% |
| **=&gt;** | 크거나 같음 |
| **&lt;=** | 작거나 같음 |

## 지정된 연산자

다음과 같은 명명된 연산자를 사용하여 규칙을 작성할 수 있습니다.

| 연산자 | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [에서 정규 표현식을 사용하는](../../features/traits/trait-builder-regex.md) 방법에 [!UICONTROL Trait Builder]대해 자세히 알아보십시오. |

>[!MORE_ like_ this]
>
>* [트레이트 및 세그먼트 빌더에서 부울 표현식](../../reference/boolean-expressions-tsb.md)
>* [Traitbuilder에서 부울 표현식 이해](../../reference/boolean-expressions-tsb.md)
>* [Traitbuilder 표현식의 작업 순서](../../features/traits/trait-operator-precedence.md)
>* [부울 및 비교 연산자를 사용한 표현식 표현식](../../features/traits/trait-expression-samples.md)

