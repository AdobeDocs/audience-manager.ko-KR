---
description: DIL.tools 네임스페이스의 메서드에 대해 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL 도구
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 2%

---

# DIL 도구

>[!WARNING]
>
>2023년 7월부터 Adobe은 [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장 개발을 중단했습니다.
>
>기존 고객은 [!DNL DIL] 구현을 계속 사용할 수 있습니다. 그러나 Adobe은 이 시점 이후에는 [!DNL DIL]을(를) 개발하지 않습니다. 고객은 장기 데이터 수집 전략에 대해 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)을(를) 평가하는 것이 좋습니다.
>
>2023년 7월 이후에 새로운 데이터 수집 통합을 구현하려는 고객은 대신 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)을 사용해야 합니다.

`DIL.tools` 네임스페이스의 메서드를 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

현재 페이지에 도달하기 위해 사용되는 검색어를 반환합니다.

<!-- 

r_dil_get_search_referrer.xml

 -->

### `getSearchReferrer`의 목적

DIL에서 `getSearchReferrer`은(는) 사이트에 도달하기 위해 사용된 검색 결과(이름 및 키워드)를 반환합니다. 기본적으로 특정 검색어를 이 함수에 전달하거나 [!DNL AOL]에 대해 지원되는 검색 엔진([!DNL Ask], [!DNL Bing], [!DNL Google], [!DNL Yahoo] 및 `document.referrer`)을 검색하도록 할 수 있습니다.

### 함수 서명

함수 서명: `DIL.tools.getSearchReferrer(uri, initConfig)`

### 함수 매개 변수

`getSearchReferrer`이(가) 수락:

* *`{string}`*: *(선택 사항)* 검색 URL을 포함하는 문자열입니다(정의되지 않은 경우 `document.referrer` 사용).
* *`{object}`*: *(선택 사항)* `hostPattern`, `queryParam` 또는 `queryPattern`에 대한 구성을 포함하는 개체입니다.

반환:

* `{object}` 올바른 이름과 키워드가 포함된 개체입니다.

### 예

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> 검색 유형 </th> 
   <th> 설명 </th> 
   <th> 코드 샘플 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 기본 검색</td> 
   <td> AOL, Ask, Bing, Google 및 Yahoo 검색 엔진에서 사용되는 키워드 검색어를 반환합니다. </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>사용자 지정 URL로 전달</td> 
   <td>사용자 지정 URL을 기반으로 검색 레퍼러를 반환합니다.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>URL 호스트 이름을 사용자 지정 정규식과 일치</b></td> 
   <td> 참조 URL의 호스트 이름과 일치하도록 사용자 지정 정규 표현식을 전달합니다. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>검색 패턴을 사용자 지정 정규식과 일치</b> </td> 
   <td> 사용자 정의 정규 표현식을 전달하여 사용자 정의 검색을 수행합니다. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## deposeURI

Uniform Resource Identifier( [!DNL URI])를 해당 구성 요소(`hash`, `host`, `href`, `pathname`, `protocol`, `search` 및 `[!DNL uriParams]`)로 디스어셈블합니다.

<!-- 

r_dil_decompose.xml

 -->

함수 서명: `DIL.tools.decomposeURI`

### 함수 매개 변수

`decomposeURI`이(가) 수락:

* *`uri {string}`*: *(선택 사항)* URI를 포함하는 문자열입니다. 지정하지 않은 경우 기본값은 `document.location.href`입니다.

반환:

* *`{object}`*: 올바른 이름과 키워드가 포함된 개체입니다.

### 샘플 코드


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

웹 페이지의 메타 태그에 정의된 특정 콘텐츠를 검색하고 해당 데이터를 개체에 반환합니다.

<!-- 

r_dil_get_metatags.xml

 -->

### 함수 서명

함수 서명: `DIL.tools.getMetaTags( 1 or more parameters)`

### 함수 매개 변수

`getMetaTags`은(는) 검색할 하나 이상의 이름 매개 변수(문자열 유형)를 허용합니다. 키-값 쌍으로 구성된 개체를 반환합니다.

### 샘플 코드

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
