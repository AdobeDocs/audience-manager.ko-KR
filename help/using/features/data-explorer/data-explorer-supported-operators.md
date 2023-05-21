---
description: 논리 연산자를 사용하여 키-값 쌍을 그룹화하고 트레이트를 채우십시오.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: 지원되는 논리 연산자
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 8%

---

# 지원되는 논리 연산자 {#supported-logical-operators}

논리 연산자를 사용하여 키-값 쌍을 그룹화하고 트레이트를 채우십시오.

## 신호 검색에 지원되는 연산자 {#supported-operators-search}

지원되는 다음 논리 연산자를 사용하여 키-값 쌍을 검색합니다.

### 비교 연산자

| 연산자 | 정의 |
|---|---|
| **==** | 다음과 같음 |
| **>** | 보다 큼 |
| **&lt;** |  미만% |
| **=>** | 크거나 같음 |
| **&lt;=** | 보다 작음/같음 |

### 명명된 연산자

| 연산자 | 다음으로 평가: [!DNL True] 날짜 |
|---|---|
| **[!UICONTROL Contains]** | 키-값 쌍의 값 *다음 포함* 이 연산자로 지정된 문자입니다. |
| **[!UICONTROL Startswith]** | 키-값 쌍의 값 *다음으로 시작* 이 연산자로 지정된 문자입니다. |
| **[!UICONTROL Endswith]** | 키-값 쌍의 값 *다음으로 끝남* 이 연산자로 지정된 문자입니다. |

## 트레이트 다시 채우기 및 추정에 대해 지원되는 연산자 {#supported-operators-backfilling}

에서 지원하는 연산자를 포함하는 표현식을 포함하는 트레이트를 채울 수 있습니다. [!UICONTROL Signal Search]. 이러한 연산자 외에도 트레이트 채우기 및 추정은 다음을 지원합니다. [!UICONTROL AND], [!UICONTROL OR], 및 [!UICONTROL AND NOT] 논리 연산자: 키-값 쌍을 채워진 트레이트 표현식 내에서 결합하는 데 사용됩니다.
