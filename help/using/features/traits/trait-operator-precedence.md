---
description: 특성 빌더는 아래 나열된 작업 순서에 따라 표현식에서 낮은 우선순위로 표현식을 평가합니다. 특성 높은 우선순위 연산자로 정의된 요소는 다른 우선순위 연산자보다 먼저 평가됩니다. 이 섹션은 높은 수준부터 낮음까지 우선순위에 따라 각 연산자의 등급을 지정합니다.
seo-description: 특성 빌더는 아래 나열된 작업 순서에 따라 표현식에서 낮은 우선순위로 표현식을 평가합니다. 특성 높은 우선순위 연산자로 정의된 요소는 다른 우선순위 연산자보다 먼저 평가됩니다. 이 섹션은 높은 수준부터 낮음까지 우선순위에 따라 각 연산자의 등급을 지정합니다.
seo-title: 트레이트 빌더에서의 작업 순서
solution: Audience Manager
title: 트레이트 빌더에서의 작업 순서
uuid: DF 325047-AF 62-45 AD -9 CA 1-046 BFCBE 5341
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Order of Operations in Trait Builder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 아래 나열된 작업 순서에 따라 표현식에서 낮은 우선순위로 표현식을 평가합니다. 특성 높은 우선순위 연산자로 정의된 요소는 다른 우선순위 연산자보다 먼저 평가됩니다. 이 섹션은 높은 수준부터 낮음까지 우선순위에 따라 각 연산자의 등급을 지정합니다.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 연산자 우선 순위 </th> 
   <th colname="col2" class="entry"> 기호 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 괄호 </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> 괄호 안의 표현식은 항상 먼저 평가되며 우선 순위 순서를 따릅니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 비교 연산자 </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> 보다 작음, 큼, 보다 작음/같음, 다음보다 큼/같게 평가됩니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 같음 연산자 </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> 같지 않음 - 같지 않은 연산자는 이전 연산자 다음에 평가됩니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> and</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> 또는</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
 </tbody>
</table>

>[!MORE_ like_ this]
>
>* [Traitbuilder에서 Boolean 표현식 (and, or, not) 를 사용한 작업](../../reference/boolean-expressions-tsb.md)
>* [Traitbuilder에서 비교 연산자를 사용한 작업](../../features/traits/trait-comparison-operators.md)

