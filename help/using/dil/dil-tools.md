---
description: DIL.도구 네임스페이스의 메서드에 대해 설명합니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL 도구
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 3%

---

# DIL 도구

>[!WARNING]
>
>2023년 7월부터 Adobe은 의 개발을 중단했습니다. [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장명.
><br>
>기존 고객은 [!DNL DIL] 구현. 그러나 Adobe은 개발되지 않습니다 [!DNL DIL] 이 점을 넘어서는 것입니다. 고객은 다음을 평가하는 것이 좋습니다. [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 을 참조하십시오.
><br>
>2023년 7월 이후 새로운 데이터 수집 통합을 구현하려는 고객은 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 대신,

의 메서드에 대해 설명합니다. `DIL.tools` 네임스페이스입니다. 이러한 유틸리티 기능은 특정 작업을 수행하는 데 도움이 됩니다.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

현재 페이지에 도달하기 위해 사용되는 검색어를 반환합니다.

<!-- 

r_dil_get_search_referrer.xml

 -->

### 목적 `getSearchReferrer`

DIL, `getSearchReferrer` 사이트에 도달하기 위해 사용된 검색 결과(이름 및 키워드)를 반환합니다. 특정 검색어를 이 함수에 전달하거나 지원되는 검색 엔진( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], 및 [!DNL Yahoo]에 대해 ) `document.referrer` 기본적으로.

### 함수 서명

함수 서명: `DIL.tools.getSearchReferrer(uri, initConfig)`

### 함수 매개 변수

`getSearchReferrer` 수락:

* *`{string}`*: *(선택 사항)* 검색 URL을 포함하는 문자열(사용) `document.referrer` 정의되지 않은 경우)입니다.
* *`{object}`*: *(선택 사항)* 다음에 대한 구성이 포함된 개체 `hostPattern`, `queryParam`, 또는 `queryPattern`.

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
   <td> AOL, Ask, Bing, Google 및 Yahoo 검색 엔진에서 사용되는 키워드 검색어를 반환합니다. </td> 
   <td>
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
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
   <td> <b>URL 호스트 이름을 사용자 정의 정규 표현식과 일치</b></td> 
   <td> 참조 URL의 호스트 이름과 일치하도록 사용자 지정 정규 표현식을 전달합니다. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>사용자 정의 정규 표현식과 검색 패턴 일치</b> </td> 
   <td> 사용자 정의 정규 표현식을 전달하여 사용자 정의 검색을 수행합니다. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## deposeURI

Uniform Resource Identifier( 디스어셈블링 [!DNL URI])을 구성 요소에 넣을 수 있습니다. `hash`, `host`, `href`, `pathname`, `protocol`, `search`, 및 `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

함수 서명: `DIL.tools.decomposeURI`

### 함수 매개 변수

`decomposeURI` 수락:

* *`uri {string}`*: *(선택 사항)* URI를 포함하는 문자열입니다. 기본값은 입니다. `document.location.href` 지정하지 않은 경우

반환:

* *`{object}`*: 유효한 이름과 키워드가 포함된 객체입니다.

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

`getMetaTags` 검색할 하나 이상의 이름 매개 변수(문자열 유형)를 허용합니다. 키-값 쌍으로 구성된 개체를 반환합니다.

### 샘플 코드

<pre class="javascript"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
