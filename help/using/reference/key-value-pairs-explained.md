---
description: 표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.
keywords: 통합 코드
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: 키-값 쌍 설명
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 3%

---

# 키-값 쌍 설명{#key-value-pairs-explained}

표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.

<!-- 

c_key_value_explained.xml

 -->

키-값 쌍은 두 개의 관련 데이터 요소, 즉 데이터 세트를 정의하는 상수인 키(예: 성별, 색상, 가격)와 세트에 속하는 변수인 값(예: 남성/여성, 녹색, 100)으로 구성됩니다. 전체 형식의 키-값 쌍은 다음과 같습니다.

* `gender = male`
* `color = green`
* `price > 100`

## 표준 및 직렬화된 키-값 쌍 {#standard-serialized-pairs}

대상은 *`standard`* 또는 *`serialized`* 형식의 키 값 데이터를 허용합니다. 표준 서식은 데이터를 별도의 키-값 쌍으로 구성합니다. 각 키는 다른 값을 정의하기 위해 다시 사용할 때에도 명시적으로 설명됩니다. 반대로 직렬화된 형식은 여러 값을 단일 키로 정의된 하나의 집합으로 압축합니다. 또한 직렬화된 쌍에서는 키-값 집합 내의 값을 구분하는 특수 표시기가 사용됩니다. 마지막으로 표준 및 직렬화된 키-값은 단일 또는 다중 값을 포함할 수 있습니다. 다음 표에서는 표준 및 직렬 키-값 형식의 예를 제공합니다.

| 서식 | 단일 키 | 키-값 쌍 |
|---|---|---|
| **표준** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **직렬화** | `x=1;2` | `x=1;2&y=3;4` |



## 키, 구분 기호 및 구분 기호 {#keys-delimiters-separators}

직렬화된 데이터로 작업할 때 키-값 쌍에서 *within*&#x200B;과(와) *between* 값을 구분하는 문자를 지정해야 합니다. 키-값 쌍의 요소는 다음과 같이 정의됩니다.

* **키:** 키-값 쌍의 고유 식별자입니다.
* **값 구분 기호:** 개별 키-값 쌍을 구분합니다.
* **키-값 구분 기호:** 키-값 쌍 내의 값에서 키를 구분합니다.
* **일련 구분 기호:** 직렬화된 키-값 쌍 내에서 개별 값을 구분합니다.

## 표준 및 일련화된 키-값 요소 {#standard-serialized-key-value-elements}


| 유형 | 예 | 키 | 키-값 구분자 | 키-값 구분 기호 | 직렬 구분자 |
|---------|----------|---------|---------|----------|---------|
| **단일 키**(표준) | `x=1&x=2` | `x` | `=` | `&` | n/a |
| **키-값 쌍**(표준) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/a |
| **단일 키**(일련 번호) | `x=1;2;3` | `x` | `=` | n/a | `;` |
| **키-값 쌍**(직렬) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
