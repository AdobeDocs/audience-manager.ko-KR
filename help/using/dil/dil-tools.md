---
description: DIL.tools 네임스페이스의 메서드에 대해 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.
seo-description: DIL.tools 네임스페이스의 메서드에 대해 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.
seo-title: DIL 도구
solution: Audience Manager
title: DIL 도구
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# DIL 도구

네임스페이스의 메서드를 `DIL.tools` 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

현재 페이지에 도달하는 데 사용된 검색어를 반환합니다.

<!-- 

r_dil_get_search_referrer.xml

 -->

### 목적 `getSearchReferrer`

DIL에서 `getSearchReferrer` 사이트에 도달하는 데 사용된 검색 결과(이름 및 키워드)를 반환합니다. 특정 검색어를 이 함수에 전달하거나 지원되는 검색 엔진(, [!DNL AOL][!DNL Ask], [!DNL Bing][!DNL Google], [!DNL Yahoo]`document.referrer` 및)을기본적으로 검색하도록 할 수 있습니다.

### 기능 서명

함수 서명: `DIL.tools.getSearchReferrer(uri, initConfig)`

### 함수 매개 변수

`getSearchReferrer` accepts:

* *`{string}`*:( *선택 사항)* 검색 URL이 들어 있는 문자열(정의되지 `document.referrer` 않은 경우 사용).
* *`{object}`*:( *선택 사항)* `hostPattern`, `queryParam`또는 `queryPattern`에 대한 구성을 포함하는 개체입니다.

반환:

* `{object}` 유효한 이름과 키워드가 포함된 개체입니다.

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
   <td> AOL, Ask, Bing, Google 및 Yahoo 검색 엔진에서 사용하는 키워드 검색 용어를 반환합니다. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>사용자 지정 URL 전달</td> 
   <td>사용자 지정 URL을 기반으로 검색 레퍼러를 반환합니다.</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>URL 호스트 이름을 사용자 지정 정규식과 일치</b></td> 
   <td> 참조 URL의 호스트 이름과 일치하도록 사용자 지정 참조를 전달합니다. </td> 
   <td> 
  <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/
    search.aspx?q=adobe+rules",{ 
       hostPattern:/ehow\./, 
         queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>사용자 지정 색인과 검색 패턴 일치</b> </td> 
   <td> 사용자 정의 검색을 수행하려면 사용자 정의 리게를 전달합니다. </td> 
   <td> 
    <code>
      var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
    {
       hostPattern:/ehow\./, 
           search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

단일 리소스 식별자( [!DNL URI])를 해당 구성 요소로 디스어셈블합니다. `hash`, `host`, `href``pathname`, `protocol``search`, `[!DNL uriParams]`및

<!-- 

r_dil_decompose.xml

 -->

함수 서명: `DIL.tools.decomposeURI`

### 함수 매개 변수

`decomposeURI` accepts:

* *`uri {string}`*:( *선택 사항)* URI를 포함하는 문자열입니다. Defaults to `document.location.href` if not specified.

반환:

* *`{object}`*:유효한 이름과 키워드가 포함된 개체입니다.

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

웹 페이지의 메타 태그에 정의된 특정 컨텐츠를 검색하고 해당 데이터를 개체에 반환합니다.

<!-- 

r_dil_get_metatags.xml

 -->

### 기능 서명

함수 서명: `DIL.tools.getMetaTags( 1 or more parameters)`

### 함수 매개 변수

`getMetaTags` 검색할 하나 이상의 이름 매개 변수(문자열 유형)를 허용합니다. 키-값 쌍으로 구성된 객체를 반환합니다.

### 샘플 코드

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ partner:'<i>partnerName'</i>, containerNSID: <i>containerNSID</i> });

dataLib.api.signatures(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
