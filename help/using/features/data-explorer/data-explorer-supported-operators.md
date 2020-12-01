---
description: 논리 연산자를 사용하여 키-값 쌍 및 채우기 트레이트를 그룹화합니다.
seo-description: 논리 연산자를 사용하여 키-값 쌍 및 채우기 트레이트를 그룹화합니다.
seo-title: 지원되는 논리 연산자
title: 지원되는 논리 연산자
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 9%

---


# 지원되는 논리 연산자 {#supported-logical-operators}

논리 연산자를 사용하여 키-값 쌍 및 채우기 트레이트를 그룹화합니다.

## 신호 검색에 지원되는 연산자 {#supported-operators-search}

지원되는 다음 논리 연산자를 사용하여 키-값 쌍을 검색합니다.

### 비교 연산자

| 연산자 | 정의 |
|---|---|
| **==** | 같음 |
| **>** | 보다 큼 |
| **&lt;** |  미만% |
| **=>** | 크거나 같음 |
| **&lt;=** | 작거나 같음 |

### 명명된 연산자

| 연산자 | When[!DNL True] |
|---|---|
| **[!UICONTROL Contains]** | 키-값 쌍 *에 있는 값은 이 연산자가 지정한* 문자를 포함합니다. |
| **[!UICONTROL Startswith]** | 키-값 쌍 *의 값은 이 연산자가 지정한 문자*&#x200B;로 시작합니다. |
| **[!UICONTROL Endswith]** | 키-값 쌍 *의 값은 이 연산자가 지정한 문자로 끝납니다.* |

## 특성 채우기 및 추정에 지원되는 연산자 {#supported-operators-backfilling}

[!UICONTROL Signal Search]에서 지원하는 연산자를 포함하는 표현식이 포함된 트레이트를 채울 수 있습니다. 이러한 연산자 외에도 트레이트 채우기 및 추정은 백채워진 트레이트 표현식 내에서 키-값 쌍을 결합하는 데 사용되는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL AND NOT] 논리 연산자를 지원합니다.