---
description: 표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.
keywords: 통합 코드
seo-description: 표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.
seo-title: 키-값 쌍 설명
solution: Audience Manager
title: 키-값 쌍 설명
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# 키-값 쌍 설명{#key-value-pairs-explained}

표준 및 직렬화된 키-값 쌍을 정의하고 설명합니다.

<!-- 

c_key_value_explained.xml

 -->

키-값 쌍은 두 개의 관련 데이터 요소로 구성됩니다.키(예: 성별, 색상, 가격)와 집합에 속하는 변수(예: 남성/여성, 녹색, 100)를 정의하는 상수입니다. 전체 형식의 키-값 쌍은 다음과 같습니다.

* `gender = male`
* `color = green`
* `price > 100`

## 표준 및 직렬화된 키-값 쌍 {#standard-serialized-pairs}

대상은 키 값 데이터를 *`standard`* 또는 *`serialized`* 형식으로 허용합니다. 표준 서식은 데이터를 개별 키-값 쌍으로 구성합니다. 각 키는 다른 값을 정의하는 데 다시 사용되더라도 명시적으로 지정됩니다. 반대로, 직렬화된 서식은 여러 값을 단일 키로 정의된 하나의 세트로 압축합니다. 또한 직렬화된 쌍에서 특수 표시기는 키 값 집합 내에서 값을 구분하는 데 사용됩니다. 마지막으로, 표준 및 직렬화된 키 값에는 단일 또는 여러 값이 포함될 수 있습니다. 다음 표에서는 표준 및 직렬 키 값 형식의 예를 제공합니다.

| 서식 지정 | 단일 키 | 키-값 쌍 |
|---|---|---|
| **표준** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **일련 번호** | `x=1;2` | `x=1;2&y=3;4` |



## 키, 구분 기호 및 구분 기호 {#keys-delimiters-separators}

직렬화된 데이터를 사용할 때는 키-값 쌍 *내부와* 값 *사이의* 값을 구분하는 문자를 지정해야 합니다. 키-값 쌍의 요소는 다음과 같이 정의됩니다.

* **** 키:키-값 쌍의 고유 식별자입니다.
* **** 값 구분 기호:개별 키-값 쌍을 구분합니다.
* **** 키 값 구분 기호:키-값 쌍 내의 값과 키를 구분합니다.
* **** 직렬 구분 문자:직렬화된 키-값 쌍 내에서 개별 값을 구분합니다.

## 표준 및 직렬화된 키-값 요소 {#standard-serialized-key-value-elements}

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
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>키-값 쌍</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>단일 키</b> <p>(시리얼) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/a </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>키-값 쌍</b> (시리얼) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

