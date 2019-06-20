---
description: 표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.
keywords: 통합 코드
seo-description: 표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.
seo-title: 키-값 쌍을 설명했습니다.
solution: Audience Manager
title: 키-값 쌍을 설명했습니다.
uuid: F 1435742-81 CA -4964-8370-ACCF 2 F 1 C 47 A 5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Key-Value Pairs Explained{#key-value-pairs-explained}

표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.

<!-- 

c_key_value_explained.xml

 -->

키-값 쌍은 두 개의 관련 데이터 요소로 구성됩니다. 데이터 세트를 정의하는 상수 (예: 성별, 색상, 가격) 와 세트에 속하는 변수 (예: 남성/여성, 녹색, 100) 입니다. 완전히 형성된 키-값 쌍은 다음과 비슷합니다.

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. 표준 서식은 데이터를 별도의 키-값 쌍으로 구성합니다. 각 키는 다른 값을 정의하기 위해 다시 사용되더라도 명시적으로 명시되어 있습니다. 이와 반대로 직렬화된 서식은 여러 값을 하나의 키로 정의된 하나의 세트로 응축합니다. 또한 직렬화된 쌍의 경우 키-값 세트 내의 값을 구분하는 특수 표시기가 사용됩니다. 마지막으로, 표준 및 직렬화된 키-값에는 단일 값 또는 여러 개의 값이 포함될 수 있습니다. 다음 표는 표준 및 직렬 키-값 포맷의 예를 제공합니다.

| 서식 지정 | 단일 키 | 키-값 쌍 |
|---|---|---|
| **표준** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **직렬화** | `x=1;2` | `x=1;2&y=3;4` |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. 키-값 쌍의 요소는 다음과 같이 정의됩니다.

* **키:** 키-값 쌍의 고유 식별자.
* **값 구분 기호:** 개별 키-값 쌍을 구분합니다.
* **키-값 구분 기호:** 키 값 쌍 내의 값에서 키를 구분합니다.
* **직렬 구분 문자:** 직렬화된 키-값 쌍 내에서 개별 값을 구분합니다.

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 유형 </th> 
   <th colname="col2" class="entry"> 예 </th> 
   <th colname="col3" class="entry"> 키 </th> 
   <th colname="col4" class="entry"> 키-값 구분 기호 </th> 
   <th colname="col5" class="entry"> 키-값 구분 기호 </th> 
   <th colname="col6" class="entry"> 직렬 구분 문자 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>단일 키</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>키-값 쌍</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>단일 키</b> <p>(일련 번호) </p> </td> 
   <td colname="col2"> <code> x = 1; 2; 3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/a </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>키-값 쌍</b> (일련 번호) </td> 
   <td colname="col2"> <code> x = 1; 2 &amp; y = 3; 4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

