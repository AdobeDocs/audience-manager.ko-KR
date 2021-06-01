---
description: 트레이트 빌더는 높은 우선순위에서 낮은 우선 순위에 따라 아래에 나열된 작업 순서에 따라 표현식을 평가합니다. 우선 순위가 높은 연산자로 정의된 트레이트 요소는 다른 우선 순위 연산자 앞에 먼저 평가됩니다. 이 섹션에서는 높음에서 낮음순으로 각 연산자에 대해 순위를 매깁니다.
seo-description: 트레이트 빌더는 높은 우선순위에서 낮은 우선 순위에 따라 아래에 나열된 작업 순서에 따라 표현식을 평가합니다. 우선 순위가 높은 연산자로 정의된 트레이트 요소는 다른 우선 순위 연산자 앞에 먼저 평가됩니다. 이 섹션에서는 높음에서 낮음순으로 각 연산자에 대해 순위를 매깁니다.
seo-title: 트레이트 빌더의 작업 순서
solution: Audience Manager
title: 트레이트 빌더의 작업 순서
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: 트레이트
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 13%

---

# 트레이트 빌더의 작업 순서 {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] 우선 순위는 높은 우선 순위에서 낮은 우선 순위에 따라 아래 나열된 작업 순서에 따라 표현식을 평가합니다. 우선 순위가 높은 연산자로 정의된 트레이트 요소는 다른 우선 순위 연산자 앞에 먼저 평가됩니다. 이 섹션에서는 높음에서 낮음순으로 각 연산자에 대해 순위를 매깁니다.

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
   <td colname="col3"> 괄호의 표현식은 항상 먼저 평가되고 우선 순위 순서를 따릅니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 비교 연산자 </td> 
   <td colname="col2"> &lt;&gt; &lt;&gt;= </td> 
   <td colname="col3"> 보다 작음, 보다 큼, 보다 작음/같음, 보다 크거나 같음 다음 평가됩니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 평등 연산자 </td> 
   <td colname="col2"> ==!= </td> 
   <td colname="col3"> 같음, 이전 연산자 다음으로 평가되지 않음. </td> 
  </tr> 
  <tr> 
   <td colname="col1">부울 <span class="wintitle"> AND</span> </td> 
   <td colname="col2"><span class="wintitle"> 그리고</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
  <tr> 
   <td colname="col1">부울 <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> 또는</span> </td> 
   <td colname="col3" morerows="1"> n/a </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [TraitBuilder에서 부울 표현식(AND 또는 NOT)을 사용한 작업](../../reference/boolean-expressions-tsb.md)
* [TraitBuilder에서 비교 연산자 사용](../../features/traits/trait-comparison-operators.md)

