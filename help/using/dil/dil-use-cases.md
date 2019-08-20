---
description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명
seo-description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명
seo-title: DIL 사용 사례 및 코드 샘플
solution: Audience Manager
title: DIL 사용 사례 및 코드 샘플
uuid: 27995 C 2 D -6572-438 E-AF 99-B 5477 F 090 AE 9
translation-type: tm+mt
source-git-commit: 8763bff3960e2033951cf68e65f5ad44377b2917

---


# DIL 사용 사례 및 코드 샘플{#dil-use-cases-and-code-samples}

특정 DIL 사용 사례에 대한 코드 샘플 및 설명

<!-- 

c_dil_use_case.xml

 -->

## DIL를 사용하여 데이터 요소를 Audience Manager로 보내기 {#send-data-elements-dil}

페이지 요소에 대한 정보를 Audience Manager로 보내는 개체 변수를 만듭니다. 이 기능은 일반 데이터 수집이나 Analytics 변수를 사용하여 데이터를 수집하는 대신 유용합니다.

<!-- 

c_dil_send_page_objects.xml

 -->

**설명**

다음 코드는 페이지 데이터를 수집하여 Audience Manager로 보내는 방법을 보여줍니다 [!UICONTROL DIL]. 이러한 예에서는 변수를 사용하여 일반 목록 또는 배열에서 데이터 요소를 보유합니다. 변수를 [키-값 쌍으로 전달하십시오](../reference/key-value-pairs-explained.md). 또한 키-값 쌍의 키 앞에 `c_` 접두사를 둡니다. 이 [필수 접두사는](../features/traits/trait-variable-prefixes.md) 정보를 사용자 정의 데이터로 식별합니다. 첫 번째 예에서는 키에 수동으로 추가해야 `c_` 합니다. 두 번째 예에서는 자동으로 [!UICONTROL DIL] 수행합니다.

**속성 속성 일관성 유지**

데이터를 전달할 때 값 속성을 동일하게 유지해야 합니다. 예를 들어, 값이 다른 두 개의 키가 있는 경우 마지막 키-값 쌍의 값이 이전 값 개체보다 우선합니다. 예를 들어 전달된 값을 `color:blue` 빨간색 (파란색 덮어쓰기) 로 `color:red` 설정합니다.

**예제 1: 데이터를 키-값 쌍으로 보내기**

이 기본 예제는 색상 및 가격 데이터를 키-값 쌍의 형태로 Audience Manager에 보냅니다. 코드는 다음과 비슷합니다.

<pre class="&ldquo;java&rdquo;"><code>var sample_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
sample_ dil. api. signals ({ 
 c_ color: " blue ", 
 c_ price: " 900 "}); 
sample_ dil. api. submit ();</code>
</pre>

**예제 2: 개체에 데이터 보내기**

이 고급 예에서는 개체에서 Audience Manager로 데이터를 보내는 방법을 보여줍니다. 이 메서드로 작업할 때 객체를 함수 매개 변수로 메서드에 전달할 [!UICONTROL DIL] 수 [!DNL signals()] 있습니다. [!UICONTROL DIL] 코드는 다음과 비슷합니다.

<pre class="java"><code>var my_ object = { 
 색상: " blue ", 
 가격: " 900 "}; 
 
var sample_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
//Load 개체를 만들고 키-값 쌍의 모든 키에 "c_" 를 추가하고 데이터를 audiencemanager로 보냅니다. 
sample_ dil. api. signals (my_ object, "c_"). submit ();</code>
</pre>

**예제 3: 배열로 페이지 데이터 보내기**

이 경우, 변수는 배열을 `my_object` 사용하여 데이터를 보유합니다. 이 예는 위의 권장 방법으로 전달된 정보를 기반으로 구축되지만 제품 유형 및 모델을 수용하도록 추가 레이어를 추가합니다. 코드는 다음과 비슷합니다.

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
 sample_ dil. api. signals (my_ objects [i], "c_"); 
} 
sample_ dil. api. submit ();</code>
</pre>

>[!MORE_ like_ this]
>
>* [신호](../dil/dil-instance-methods.md#signals)


## 참조 URL 캡처 {#capture-referring-url}

참조 URL를 캡처하여 Audience Manager로 보냅니다.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>이 메서드는 사용자가 비슷한 프로토콜 (http와 https) 이 있는 페이지 간을 이동할 때에만 작동합니다. 예를 들어 보안 사이트에서 다른 보안 사이트로 이동하면 브라우저가 참조 URL를 유지합니다. 브라우저에서는 보안 사이트와 비보안 사이트 사이를 이동할 때 참조 URL 이 유지되지 않습니다. 이 동작은 정상적인 브라우저 기능이며, 이 기능은 [!UICONTROL DIL]우회할 수 없습니다.

**코드 샘플**

코드는 다음과 비슷합니다.

<pre class="java"><code>var adobe_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
adobe_ dil. api. signals ({d_ referer: document. referrer}). submit ();</code>
</pre>

## 검색 엔진 유형 및 키워드 검색어 캡처 {#capture-search-engine-types}

검색 엔진 유형 및 키워드 검색에 대한 정보를 Audience Manager로 전송합니다.

>[!IMPORTANT]
>
>이 섹션에서는 이전 버전의 DIL에서 지원되지 않는 레거시 기능에 대해 설명합니다.

**지원되는 검색 엔진**

기본적으로, 이러한 검색 엔진에서 검색을 `DIL.getSearchReferrer` 인식합니다 (국제 변형 포함).

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**설명**

다음 코드는 지원되는 검색 엔진에 대한 검색 레퍼러를 가져오는 방법을 보여줍니다. 이 경우 사용자가 Canada () 에서 [!DNL Google] "Home" 이라는 용어를 검색했다고 `www.google.ca`가정합니다. 이 코드는 해당 검색어를 캡처하여 Audience Manager로 전송하는 데 도움이 됩니다.

**기본 코드**

검색 참조를 가져오는 기본 코드는 다음과 같습니다 (예 `google.com`:).

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**나열된 검색 엔진 코드 샘플**

이 경우 사용자가 Canada () 에서 [!DNL Google] "Home" 이라는 용어를 검색했다고 `www.google.ca`가정합니다. 코드가 필요한 `c_` 매개 변수를 검색 엔진 ( `c_se`) 와 검색어 ( `c_st`) 에 접두사로 추가하는 방법을 확인하십시오. `c_` 는 고객 지정 변수로서 Audience Manager에 이를 식별하는 [필수 접두사입니다](../features/traits/trait-variable-prefixes.md) .

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

이 경우 사용자가 "홈" 이라는 단어를 검색했다고 `dogpile.com`가정해봅시다. 기본적으로 지원되지 [!DNL Dogpile] 않으므로, DIL를 구성하여 이 검색 엔진을 인식하고 검색어를 Audience Manager로 반환하도록 할 수 있습니다. 코드는 다음과 비슷합니다.

<pre class="java"><code>var adobe_ dil = dil. create ({partner: "<i>Partner Name</i>"}); 
var search_ referrer = dil. tools. getsearchreferrer (document. referrer, { 
 Hostpattern: /dogpile\./, 
 Queryparam: " q "}); 
 
if (search_ referrer &amp; &amp; search_ referrer. valid) { 
 adobe_ dil. api. signals ({ 
 c_ SE: se. name, 
 c_ st: se. keywords 
 }). submit (); 
}</code>
</pre>

## 키 값을 다른 키에 매핑 {#map-key-values}

값을 키-값 쌍의 다른 키에 연결합니다.

<!-- 

c_dil_map_keys.xml

 -->

**설명**

키-값 쌍의 키에 추가되는 `c_` 접두사는 이 신호를 고객 정의 데이터로 식별합니다. 고객 정의 데이터는 이벤트 호출에서 데이터를 전달한 특정 사이트를 타깃팅하는 데 사용됩니다. 그러나 경우에 따라 Audience Manager 계정의 모든 속성에서 이 정보를 사용할 수 있게 되기를 원할 수 있습니다. 이렇게 하려면 `c_` 키-값 쌍의 값을 플랫폼 수준 키에 매핑하십시오. 플랫폼 수준 키에 접두사가 추가되어 `d_` 계정의 모든 속성에서 타깃팅에 대한 신호가 제공됩니다.

예를 들어, 특정 사이트에서 우편번호 데이터를 수집하고 모든 Audience Manager 자산으로 타깃팅하려고 합니다. 플랫폼 수준에서 우편번호를 사용할 수 있도록 하려면, 고객이 정의한 우편번호 키 (예: `c_zip`) 를 플랫폼 정의된 키에 아래 표시된 것처럼 매핑할 수 있습니다.

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


## Google Tag Manager (GTM) 의 트래픽 DIL {#traffic-dil-gtm}

GTM 태그로 DIL를 설정하고 제공합니다.

<!-- 

t_dil_google_tagmanager.xml

 -->

이 절차에서는 계정이 있는 [!DNL Google Tag Manager] 경우, 해당 제품에 대한 작업 지식과 Audience Manager `dil.js` 파일이 있다고 가정합니다.

GTM에서 `dil.js` 파일을 트래픽하려면:

1. 새 컨테이너를 만들거나 기존 컨테이너를 엽니다.
1. 컨테이너에 새 태그를 추가합니다.
1. 태그를 열어 편집하고 다음을 수행합니다.

   * 태그의 이름을 지정합니다.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * HTML 필드에서 코드 (라이브러리 [!UICONTROL DIL] + 사용자 지정 코드) 를 스크립트 태그 `<script>DIL code</script>`내에 삽입합니다.
   * 클릭 **[!UICONTROL Save]**.

1. 컨테이너를 게시합니다.
1. 컨테이너 태그 코드를 생성하여 인벤토리에 배치합니다.

>[!MORE_ like_ this]
>
>* [Google Tag Manager 도움말 센터](https://support.google.com/tagmanager#topic=3441530)

