---
description: DIL. tools 네임스페이스의 메서드를 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.
seo-description: DIL. tools 네임스페이스의 메서드를 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.
seo-title: DIL 도구
solution: Audience Manager
title: DIL 도구
uuid: 2 bc 62 ce 2-16 bd -4 e 80-b 493-c 816 ba 643 b 59
translation-type: tm+mt
source-git-commit: ac9e4f24a896ecae2ebf36dcf34a4ac8fab00cd8

---


# DIL 도구

Describes methods in the `DIL.tools` namespace. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.

<!-- 

c_dil_functions.xml

 -->

## Getsearchreferrer

현재 페이지에 도달하는 데 사용된 검색어를 반환합니다.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Purpose of `getSearchReferrer`

In DIL, `getSearchReferrer` returns search results (names and key words) used to reach your site. You can pass in specific search terms to this function or let it search the supported search engines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], and [!DNL Yahoo]) against `document.referrer` by default.

### 함수 서명

Function signature: `DIL.tools.getSearchReferrer(uri, initConfig)`

### 함수 매개 변수

`getSearchReferrer` 수락:

* *`{string}`*: *(선택 사항)* 검색 URL 이 포함된 문자열입니다 (정의되지 않은 `document.referrer` 경우 사용).
* *`{object}`*: *(선택 사항)*`hostPattern`, `queryParam`또는에 대한 구성을 포함하는 개체 `queryPattern`.

and 반환:

* `{object}` 유효한 이름 및 키워드가 포함된 개체.

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
   <td> AOL, ASK, Bing, Google 및 Yahoo 검색 엔진에서 사용하는 키워드 검색어를 반환합니다. </td> 
   <td>
      <code>var &amp; amp; nbsp; 결과 및 AMP; nbsp; = &amp; amp; nbsp; dil. tools. getsearchreferrer ();</code> 
  </td>
  </tr> 
  <tr> 
   <td>사용자 정의 URL에 전달</td> 
   <td>사용자 지정 URL를 기반으로 하는 검색 레퍼러를 반환합니다.</td> 
   <td> 
  <code>
        var results = 
    DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b>URL 호스트 이름과 사용자 정의 regex 일치</b></td> 
   <td> 참조 URL의 호스트 이름과 일치하도록 사용자 지정 regex를 전달합니다. </td> 
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
   <td> <b>사용자 지정 regex와 검색 패턴 일치</b> </td> 
   <td> 사용자 지정 검색을 수행하려면 사용자 지정 regex를 전달합니다. </td> 
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

## Decomposeuri

Disassembles a Uniform Resource Identifier ( [!DNL URI]) into its constituent components: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, and `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Function signature: `DIL.tools.decomposeURI`

### 함수 매개 변수

`decomposeURI` 수락:

* *`uri {string}`*: *(선택 사항)* URI가 포함된 문자열입니다. Defaults to `document.location.href` if not specified.

and 반환:

* *`{object}`*: 유효한 이름 및 키워드가 포함된 개체.

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

## getmetatags

웹 페이지의 메타 태그에 정의된 특정 컨텐츠를 검색하고 해당 데이터를 개체에 반환합니다.

<!-- 

r_dil_get_metatags.xml

 -->

### 함수 서명

Function signature: `DIL.tools.getMetaTags( 1 or more parameters)`

### 함수 매개 변수

`getMetaTags` 검색할 하나 이상의 이름 매개 변수 (문자열 유형) 를 수락합니다. 키-값 쌍으로 구성된 개체를 반환합니다.

### 샘플 코드

<pre class="&ldquo;javascript&rdquo;"><code>var datalib = dil. create ({ 
 파트너: '<i>Partnername '</i>, 
 Containernsid: <i>containernsid</i> }); 
datalib. api. signals (dil. tools. getmetatags ('<i>application</i>','<i>keywords</i>','<i>description</i>'),' c_'). submit ();</code>
</pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 
dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
