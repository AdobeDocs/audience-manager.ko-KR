---
description: 논리 연산자를 사용하여 키-값 쌍과 채우기 트레이트를 그룹화합니다.
seo-description: 논리 연산자를 사용하여 키-값 쌍과 채우기 트레이트를 그룹화합니다.
seo-title: 지원되는 논리 연산자
title: 지원되는 논리 연산자
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: 데이터 탐색기
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 10%

---

# 지원되는 논리 연산자 {#supported-logical-operators}

논리 연산자를 사용하여 키-값 쌍과 채우기 트레이트를 그룹화합니다.

## 신호 검색에 지원되는 연산자 {#supported-operators-search}

다음 지원되는 논리 연산자를 사용하여 키-값 쌍을 검색합니다.

### 비교 연산자

| 연산자 | 정의 |
|---|---|
| **==** | 같음 |
| **>** | 보다 큼 |
| **&lt;** |  미만% |
| **=>** | 크거나 같음 |
| **&lt;=** | 작거나 같음 |

### 명명된 연산자

| 연산자 | 다음 경우 [!DNL True]으로 평가됩니다. |
|---|---|
| **[!UICONTROL Contains]** | 키-값 쌍 *의 값에 이 연산자로 지정된* 문자가 포함되어 있습니다. |
| **[!UICONTROL Startswith]** | 키-값 쌍 *의 값은 이 연산자가 지정한* 문자로 시작합니다. |
| **[!UICONTROL Endswith]** | 키-값 쌍 *의 값은* 이 연산자로 지정된 문자로 끝납니다. |

## 트레이트 채우기 및 추정에 대해 지원되는 연산자 {#supported-operators-backfilling}

[!UICONTROL Signal Search]에서 지원하는 연산자를 포함하는 표현식을 포함하는 트레이트를 채우기 수 있습니다. 이러한 연산자 외에도 트레이트 채우기 및 추정은 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL AND NOT] 논리 연산자도 지원합니다. 이 연산자는 백채워진 트레이트 표현식 내에서 키-값 쌍을 결합하는 데 사용됩니다.
