---
description: 표현식 빌더 코드 편집기에서 표현식을 만드는 데 참조할 수 있는 예입니다.
seo-description: 표현식 빌더 코드 편집기에서 표현식을 만드는 데 참조할 수 있는 예입니다.
seo-title: 부울 및 비교 연산자가 있는 샘플 표현식
solution: Audience Manager
title: 부울 및 비교 연산자가 있는 샘플 표현식
uuid: ee74c376-2099-4816-8694-43f58845a0ac
feature: 트레이트
exl-id: 68041d61-7942-4c2f-9e78-f2b2f803ef59
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 13%

---

# 부울 및 비교 연산자가 있는 샘플 표현식 {#sample-expressions-with-boolean-and-comparison-operators}

[!UICONTROL Expression Builder] 코드 편집기에서 표현식을 만드는 데 참조할 수 있는 예입니다.

## 코드 샘플 개요 {#code-samples-overview}

<!-- r_tb_expression_samples.xml -->

[!UICONTROL Expression Builder] 코드 편집기를 사용하여 나만의 트레이트 규칙을 만듭니다. 다음 예제를 통해 시작할 수 있습니다. 몇 가지 예제 서문은 `c_` 가 있는 *`key`* 변수 서문을 사용하여 이 변수를 사용자 정의 변수로 식별합니다. 이벤트 호출이 해당 구문을 사용하여 [!DNL Audience Manager]에 데이터를 전송하는 경우 *`key`* 변수에 대한 `c_` 접두사(또는 다른 이름 지정 규칙)을 포함합니다.

## 부울 표현식 {#boolean-expressions}

### 및 예

이 규칙은 부울 [!UICONTROL AND] 연산자를 사용하여 트레이트 자격 요구 사항을 설정합니다.

<table id="table_7C5E23EC9E0F43B182EA9771D7BB6E87"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 샘플 코드 </th> 
   <th colname="col2" class="entry"> 자격을 부여하려면 방문자가 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(c_make=="A") AND (c_model=="B") AND (c_search=="1")</code> </td> 
   <td colname="col2"> 
    <ul id="ul_F1BB5084FB794BE7A3569F9C106FC481"> 
     <li id="li_56E8C3BACF1C4B33A46CF92C51FF2286">특정 메이크와 모델을 찾습니다. </li> 
     <li id="li_DD55F053BFCF4B0888B6994013000DB2">검색 결과 페이지에서 제품을 찾습니다(검색 = "1" 또는 "true"). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### 또는 예

이 규칙은 [!DNL Boolean] [!UICONTROL OR] 및 [!UICONTROL AND] 연산자를 사용하여 트레이트 자격 요구 사항을 설정합니다.

<table id="table_6E8BA5EE1D7F4DCC9A92074D0C2C050E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 샘플 코드 </th> 
   <th colname="col2" class="entry"> 자격을 부여하려면 방문자가 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(a== "1" OR b=="1") AND (c=="new")</code> </td> 
   <td colname="col2"> 변수 <code><i>a </i></code> 또는 <code><i>b </i></code> 및 <code><i>c </i></code>에 의해 설정된 조건을 충족합니다. </td> 
  </tr> 
 </tbody> 
</table>

## 보다 큼, 보다 작음, 같음 범위 예

이 규칙은 범위를 사용하여 트레이트 자격 요구 사항을 설정합니다.

<table id="table_988DE28E35D94348ADD334FB4C9F68D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 샘플 코드 </th> 
   <th colname="col2" class="entry"> 자격을 부여하려면 방문자가 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code>(price &gt;= 1.00 AND price &lt;= 100.00)</code> </td> 
   <td colname="col2"> 1.00에서 100.00 사이의 모든 가격 조건을 충족합니다. </td> 
  </tr> 
 </tbody> 
</table>
