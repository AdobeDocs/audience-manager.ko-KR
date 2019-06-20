---
description: 논리 연산자를 사용하여 키-값 쌍 및 특성 채우기를 그룹화합니다.
seo-description: 논리 연산자를 사용하여 키-값 쌍 및 특성 채우기를 그룹화합니다.
seo-title: 지원되는 논리 연산자
title: 지원되는 논리 연산자
uuid: 645 fcb 6 f -50 ac -49 bc -8 df 9-c 699 c 749 cf 8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Supported Logical Operators {#supported-logical-operators}

논리 연산자를 사용하여 키-값 쌍 및 특성 채우기를 그룹화합니다.

## Supported Operators for Signal Search {#supported-operators-search}

다음 지원되는 논리 연산자를 사용하여 키-값 쌍을 검색합니다.

### 비교 연산자

| 연산자 | 정의 |
|---|---|
| **==** | 같음 |
| **&gt;** | 보다 큼 |
| **&lt;** |  미만% |
| **=&gt;** | 크거나 같음 |
| **&lt;=** | 작거나 같음 |

### 지정된 연산자

| 연산자 | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |

## Supported Operators for Trait Backfilling and Estimation {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.