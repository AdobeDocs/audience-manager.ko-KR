---
description: 표현식 빌더 코드 편집기에서 표현식 작성을 참조하는 예입니다.
seo-description: 표현식 빌더 코드 편집기에서 표현식 작성을 참조하는 예입니다.
seo-title: 부울 및 비교 연산자를 사용한 표현식 표현식
solution: Audience Manager
title: 부울 및 비교 연산자를 사용한 표현식 표현식
uuid: EE 74 C 376-2099-4816-8694-43 F 58845 A 0 AC
translation-type: tm+mt
source-git-commit: 92b75773d2bbe2f635d84bd5bffe625d2023b6cf

---


# Sample Expressions With Boolean and Comparison Operators {#sample-expressions-with-boolean-and-comparison-operators}

Examples you can refer to for creating expressions in the [!UICONTROL Expression Builder] code editor.

## Code Samples Overview {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

Create your own trait rules with the [!UICONTROL Expression Builder] code editor. 다음 예는 시작하는 데 도움이 될 수 있습니다. Some of the examples preface the *`key`* variable with `c_` to identify it as a user-defined variable. Include the `c_` prefix (or any other naming convention) for *`key`* variable if your event calls send data to [!DNL Audience Manager] using that syntax.

## Boolean Expressions {#boolean-expressions}

### AND example

The rule establishes trait qualification requirements using Boolean [!UICONTROL AND] operators.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 샘플 코드 </th> 
   <th colname="col2" class="entry"> 자격을 갖추려면 방문자가 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_ make = = "a") and (c_ model = = "b") and (c_ search = = "1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">특정 제조사 및 모델을 찾습니다. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">검색 결과 페이지에서 제품을 찾습니다 (검색 = "1" 또는 "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 또는 예

This rule establishes trait qualification requirements using [!DNL Boolean] [!UICONTROL OR] and [!UICONTROL AND] operators.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 샘플 코드 </th> 
   <th colname="col2" class="entry"> 자격을 갖추려면 방문자가 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a = = "1" 또는 b = = "1") and (c = = "new")</code> </td> 
   <td colname="col2"> Meet the conditions set by variables <code><i>a </i></code> or <code><i>b </i></code> and <code><i>c </i></code>. </td> 
  </tr> 
 </tbody> 
</table>

## 보다 큼, 작음, 같음 등이 있는 범위 예

이 규칙은 범위를 사용하여 트레이트 자격 조건을 설정합니다.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 샘플 코드 </th> 
   <th colname="col2" class="entry"> 자격을 갖추려면 방문자가 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(가격 &gt; = 1.00 및 가격 &lt; = 100.00)</code> </td> 
   <td colname="col2"> 1.00 ~ 100.00의 가격 조건 충족 </td> 
  </tr> 
 </tbody> 
</table>