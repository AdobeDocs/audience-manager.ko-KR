---
description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명
seo-description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명
seo-title: DIL 사용 사례 및 코드 샘플
solution: Audience Manager
title: DIL 사용 사례 및 코드 샘플
uuid: 27995 C 2 D -6572-438 E-AF 99-B 5477 F 090 AE 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# DIL Use Cases and Code Samples{#dil-use-cases-and-code-samples}

특정 DIL 사용 사례에 대한 코드 샘플 및 설명

<!-- 

c_dil_use_case.xml

 -->

## Send Data Elements to Audience Manager with DIL {#send-data-elements-dil}

페이지 요소에 대한 정보를 Audience Manager로 보내는 개체 변수를 만듭니다. 이 기능은 일반 데이터 수집이나 Analytics 변수를 사용하여 데이터를 수집하는 대신 유용합니다.

<!-- 

c_dil_send_page_objects.xml

 -->

**설명**

The following code demonstrates how to collect page data and send it to Audience Manager with [!UICONTROL DIL]. 이러한 예에서는 변수를 사용하여 일반 목록 또는 배열에서 데이터 요소를 보유합니다. Remember, pass in variables as [key-value pairs](../reference/key-value-pairs-explained.md). Also, note the `c_` prefix before the key in the key-value pair. This [required prefix](../features/traits/trait-variable-prefixes.md) identifies information as user-defined data. In the first example, you need to manually append `c_` to the key. In the second example, [!UICONTROL DIL] does this for you automatically.

**속성 속성 일관성 유지**

데이터를 전달할 때 값 속성을 동일하게 유지해야 합니다. 예를 들어, 값이 다른 두 개의 키가 있는 경우 마지막 키-값 쌍의 값이 이전 값 개체보다 우선합니다. For example, passing in `color:blue` and `color:red` sets the returned value to red (overwrites blue).

**예제 1: 데이터를 키-값 쌍으로 보내기**

이 기본 예제는 색상 및 가격 데이터를 키-값 쌍의 형태로 Audience Manager에 보냅니다. 코드는 다음과 비슷합니다.

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
sample_ dil. api. signals ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**예제 2: 개체에 데이터 보내기**

이 고급 예에서는 개체에서 Audience Manager로 데이터를 보내는 방법을 보여줍니다. When working with this method, [!UICONTROL DIL] lets you pass an object as a function parameter into the [!DNL signals()] method. [!UICONTROL DIL] 코드는 다음과 비슷합니다.

<pre class="java"><code>var my_ object = { 
 색상: " blue ", 
 가격: " 900 "}; 
 
var sample_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
//Load 개체를 만들고 키-값 쌍의 모든 키에 "c_" 를 추가하고 데이터를 audiencemanager로 보냅니다. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**예제 3: 배열로 페이지 데이터 보내기**

In this case, the variable `my_object` uses an array to hold data. 이 예는 위의 권장 방법으로 전달된 정보를 기반으로 구축되지만 제품 유형 및 모델을 수용하도록 추가 레이어를 추가합니다. 코드는 다음과 비슷합니다.

<pre class="java"><code>var my_ objects = [{ 
 색상: " blue ", 
 가격: " 900 "}, 
{ 
 유형: " Acura ", 
 모델: " tl "}]; 
 
var sample_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
 
for (var i = 0; i &lt; my_ objects. length; i + +) 
//Load 개체를 만들고 키-값 쌍의 모든 키에 "c_" 를 추가합니다. 
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

>[!MORE_ like_ this]
>
>* [신호](../dil/dil-instance-methods.md#signals)


## Capture Referring URL {#capture-referring-url}

참조 URL를 캡처하여 Audience Manager로 보냅니다.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>이 메서드는 사용자가 비슷한 프로토콜 (http와 https) 이 있는 페이지 간을 이동할 때에만 작동합니다. 예를 들어 보안 사이트에서 다른 보안 사이트로 이동하면 브라우저가 참조 URL를 유지합니다. 브라우저에서는 보안 사이트와 비보안 사이트 사이를 이동할 때 참조 URL 이 유지되지 않습니다. This behavior is normal browser functionality and cannot be circumvented by [!UICONTROL DIL].

**코드 샘플**

코드는 다음과 비슷합니다.

<pre class="java"><code>var adobe_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
adobe_ dil. api. signals ({d_ referer: document. referrer}). submit ();</code>
</pre>

## Capture Search Engine Types and Keyword Search Terms {#capture-search-engine-types}

검색 엔진 유형 및 키워드 검색에 대한 정보를 Audience Manager로 전송합니다.

<!-- 

c_dil_search_engine_valid.xml

 -->

**지원되는 검색 엔진**

By default, `DIL.getSearchReferrer` recognizes searches from these search engines (including international variations):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**설명**

다음 코드는 지원되는 검색 엔진에 대한 검색 레퍼러를 가져오는 방법을 보여줍니다. In this case, let's assume a user searched on the term "homes" from [!DNL Google] Canada ( `www.google.ca`). 이 코드는 해당 검색어를 캡처하여 Audience Manager로 전송하는 데 도움이 됩니다.

**기본 코드**

Basic code for getting the search referrer (from `google.com`, for example) looks like this:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**나열된 검색 엔진 코드 샘플**

In this case, let's assume that a user searched for the term "homes" from [!DNL Google] Canada ( `www.google.ca`). Note how the code prefixes the required `c_` parameter to search engine ( `c_se`) and search term ( `c_st`). `c_` 는 고객 지정 변수로서 Audience Manager에 이를 식별하는 [필수 접두사입니다](../features/traits/trait-variable-prefixes.md) .

<pre class="java"><code>var adobe_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
var search_ referrer = dil. tools. getsearchreferrer (); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ SE: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

**목록에 없는 검색 엔진 코드 샘플**

In this case, let's assume that a user searched for the term "homes" from `dogpile.com`. Because [!DNL Dogpile] is not supported by default, you can configure DIL to recognize this search engine and return the search terms to Audience Manager. 코드는 다음과 비슷합니다.

<pre class="java"><code>var adobe_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
var search_ referrer = dil. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer &amp;&amp; search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Map Key Values to Other Keys {#map-key-values}

값을 키-값 쌍의 다른 키에 연결합니다.

<!-- 

c_dil_map_keys.xml

 -->

**설명**

In a key-value pair, the `c_` prefix appended to the key identifies the signal as customer-defined data. 고객 정의 데이터는 이벤트 호출에서 데이터를 전달한 특정 사이트를 타깃팅하는 데 사용됩니다. 그러나 경우에 따라 Audience Manager 계정의 모든 속성에서 이 정보를 사용할 수 있게 되기를 원할 수 있습니다. To do this, map the value in a `c_` key-value pair to a platform level key. A platform level key is prefixed with `d_` and makes the signal available for targeting across all properties in your account.

예를 들어, 특정 사이트에서 우편번호 데이터를 수집하고 모든 Audience Manager 자산으로 타깃팅하려고 합니다. To make the ZIP code available at the platform level, you could map your customer-defined ZIP code key (e.g. `c_zip`) to a platform defined key as shown below.

**코드 샘플**

코드는 다음과 비슷합니다.

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

>[!MORE_ like_ this]
>
>* [주요 변수의 접두사 요구 사항](https://marketing.adobe.com/resources/help/en_US/aam/r_tb_variable_prefixes.html)


## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

GTM 태그로 DIL를 설정하고 제공합니다.

<!-- 

t_dil_google_tagmanager.xml

 -->

This procedure assumes you have a [!DNL Google Tag Manager] account, some working knowledge of that product, and your Audience Manager `dil.js` file.

To traffic the `dil.js` file in GTM:

1. 새 컨테이너를 만들거나 기존 컨테이너를 엽니다.
1. 컨테이너에 새 태그를 추가합니다.
1. 태그를 열어 편집하고 다음을 수행합니다.

   * 태그의 이름을 지정합니다.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * In the HTML field, place the [!UICONTROL DIL] code (library + the custom code) within script tags `<script>DIL code</script>`.
   * 클릭 **[!UICONTROL Save]**.

1. 컨테이너를 게시합니다.
1. 컨테이너 태그 코드를 생성하여 인벤토리에 배치합니다.

>[!MORE_ like_ this]
>
>* [Google Tag Manager 도움말 센터](https://support.google.com/tagmanager#topic=3441530)

