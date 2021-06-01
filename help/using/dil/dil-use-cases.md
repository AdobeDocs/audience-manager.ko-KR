---
description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명.
seo-description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명.
seo-title: DIL 사용 사례 및 코드 샘플
solution: Audience Manager
title: DIL 사용 사례 및 코드 샘플
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL 구현
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 3%

---

# DIL 사용 사례 및 코드 샘플{#dil-use-cases-and-code-samples}

특정 DIL 사용 사례에 대한 코드 샘플 및 설명.

<!-- 

c_dil_use_case.xml

 -->

## DIL {#send-data-elements-dil}을 사용하여 데이터 요소를 Audience Manager에 전송

Audience Manager 요소에 대한 정보를 페이지에 전송하는 개체 변수를 만듭니다. 이 기능은 일반 데이터 수집 또는 Analytics 변수를 사용하여 데이터를 수집하는 데 유용합니다.

<!-- 

c_dil_send_page_objects.xml

 -->

**설명**

다음 코드는 페이지 데이터를 수집하여 [!UICONTROL DIL]을 사용하여 Audience Manager에 전송하는 방법을 보여 줍니다. 이러한 예제에서는 변수를 사용하여 플랫 목록 또는 배열에 데이터 요소를 포함시킵니다. [키-값 쌍](../reference/key-value-pairs-explained.md)으로 변수를 전달하십시오. 또한 키-값 쌍의 키 앞에 `c_` 접두사를 주목하십시오. 이 [필수 접두사](../features/traits/trait-variable-prefixes.md)는 정보를 사용자 정의 데이터로 식별합니다. 첫 번째 예에서는 키에 `c_`을 수동으로 추가해야 합니다. 두 번째 예에서는 [!UICONTROL DIL]이 자동으로 수행합니다.

**값 속성을 일관되게 유지**

데이터를 전달할 때 값 속성을 동일하게 유지해야 합니다. 예를 들어 값이 다른 동일한 키가 두 개 있는 경우 마지막 키-값 쌍의 값이 이전 값 객체보다 우선합니다. 예를 들어 `color:blue` 및 `color:red`을 전달하면 반환된 값이 빨간색으로 설정됩니다(파란색 덮어쓰기).

**예제 1:데이터를 키-값 쌍으로 보내기**

이 기본 예에서는 색상 및 가격 데이터를 키-값 쌍 형태로 Audience Manager에 보냅니다. 코드는 다음과 유사할 수 있습니다.

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**예제 2:개체에 데이터 보내기**

이 고급 예에서는 개체의 데이터를 Audience Manager으로 보내는 방법을 보여 줍니다. 이 메서드를 사용하여 작업할 때 [!UICONTROL DIL] 에서는 개체를 함수 매개 변수로 [!DNL signals()] 메서드에 전달할 수 있습니다. [!UICONTROL DIL] 코드는 다음과 유사할 수 있습니다.

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**예제 3:배열에 페이지 데이터 보내기**

이 경우 변수 `my_object`은(는) 배열을 사용하여 데이터를 보유합니다. 이 예에서는 위의 권장 방법으로 전달된 정보를 기반으로 빌드하지만 제품 유형과 모델을 수용할 추가 레이어를 추가합니다. 코드는 다음과 유사할 수 있습니다.

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## 참조 URL 캡처 {#capture-referring-url}

참조 URL을 캡처하여 Audience Manager에 보냅니다.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>이 방법은 사용자가 유사한 프로토콜(HTTP와 HTTPS)을 사용하는 페이지 간을 이동할 때만 작동합니다. 예를 들어 보안 사이트에서 다른 보안 사이트로 이동할 때 브라우저가 참조 URL을 유지합니다. 보안 사이트와 비보안 사이트 간을 이동할 때 브라우저가 참조 URL을 보존하지 않습니다. 이 동작은 일반적인 브라우저 기능이므로 [!UICONTROL DIL]으로 우회할 수 없습니다.

**코드 샘플**

코드는 다음과 유사할 수 있습니다.

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 검색 엔진 유형 및 키워드 검색어 {#capture-search-engine-types} 캡처

검색 엔진 유형 및 키워드 검색에 대한 정보를 Audience Manager으로 보냅니다.

>[!IMPORTANT]
>
>이 섹션에서는 최신 버전의 DIL에서 지원되지 않는 기존 기능을 설명합니다.

**지원되는 검색 엔진**

기본적으로 `DIL.getSearchReferrer`은 이러한 검색 엔진에서 검색을 인식합니다(국제 변형 포함).

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**설명**

다음 코드는 지원되는 검색 엔진에 대한 검색 레퍼러를 가져오는 방법을 보여 줍니다. 이 경우 사용자가 [!DNL Google] 캐나다( `www.google.ca`)에서 &quot;home&quot;이라는 용어를 검색했다고 가정해 보겠습니다. 이 코드는 해당 검색어를 캡처하여 Audience Manager으로 전송하는 데 도움이 됩니다.

**기본 코드**

검색 레퍼러를 가져오기 위한 기본 코드(예: `google.com`에서)는 다음과 같습니다.

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**나열된 검색 엔진 코드 샘플**

이 경우 사용자가 [!DNL Google] 캐나다( `www.google.ca`)에서 &quot;home&quot;이라는 용어를 검색했다고 가정해 보겠습니다. 코드가 필요한 `c_` 매개 변수를 검색 엔진( `c_se`)과 검색어( `c_st`)에 접두사로 추가하는 방법을 확인합니다. `c_` 는 Audience Manager [에 고객 ](../features/traits/trait-variable-prefixes.md) 정의 변수로 식별되는 필수 접두사입니다.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**목록에 없는 검색 엔진 코드 샘플**

이 경우 사용자가 `dogpile.com`에서 &quot;home&quot;이라는 용어를 검색했다고 가정해 보겠습니다. 기본적으로 [!DNL Dogpile] 은(는) 지원되지 않으므로 이 검색 엔진을 인식하고 검색어를 Audience Manager으로 반환하도록 DIL을 구성할 수 있습니다. 코드는 다음과 유사할 수 있습니다.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## 키 값을 다른 키 {#map-key-values}에 매핑

키-값 쌍의 값을 다른 키에 연결합니다.

<!-- 

c_dil_map_keys.xml

 -->

**설명**

키-값 쌍에서 키에 추가된 `c_` 접두사는 신호를 고객 정의 데이터로 식별합니다. 고객 정의 데이터는 이벤트 호출 시 데이터를 전달한 특정 사이트에서 타겟팅하는 데 사용됩니다. 그러나 Audience Manager 계정의 모든 속성에서 이 정보를 사용할 수 있는 경우가 있습니다. 이렇게 하려면 `c_` 키-값 쌍의 값을 플랫폼 수준 키에 매핑합니다. 플랫폼 수준 키의 접두사로 `d_`이(가) 있으며, 이 신호를 계정의 모든 속성에서 타겟팅하는 데 사용할 수 있도록 합니다.

예를 들어, 특정 사이트에서 ZIP 코드 데이터를 수집하지만 모든 Audience Manager 속성에 타겟팅하려고 합니다. 플랫폼 수준에서 ZIP 코드를 사용할 수 있도록 하기 위해 고객이 정의한 ZIP 코드 키(예:`c_zip`)를 플랫폼에 추가할 수 있습니다.

**코드 샘플**

코드는 다음과 유사할 수 있습니다.

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

## GTM(Google Tag Manager)의 트래픽 DIL {#traffic-dil-gtm}

GTM 태그를 사용하여 DIL을 설정하고 제공합니다.

<!-- 

t_dil_google_tagmanager.xml

 -->

이 절차에서는 [!DNL Google Tag Manager] 계정, 해당 제품에 대한 일부 작업 지식 및 Audience Manager `dil.js` 파일이 있다고 가정합니다.

GTM에서 `dil.js` 파일에 트래픽을 처리하려면 다음을 수행하십시오.

1. 새 컨테이너를 만들거나 기존 컨테이너를 엽니다.
1. 컨테이너에 새 태그를 추가합니다.
1. 태그를 열어 편집하고 다음을 수행하십시오.

   * 태그 이름을 지정합니다.
   * **[!UICONTROL Tag Type]** 드롭다운 목록에서 **[!UICONTROL Custom HTML Tag]** 을 선택합니다.
   * HTML 필드에 스크립트 태그 `<script>DIL code</script>` 내에 [!UICONTROL DIL] 코드(라이브러리 + 사용자 지정 코드)를 넣습니다.
   * 클릭 **[!UICONTROL Save]**.

1. 컨테이너를 게시합니다.
1. 컨테이너 태그 코드를 생성하여 인벤토리에 배치합니다.

>[!MORELIKETHIS]
>
>* [Google Tag Manager 도움말 센터](https://support.google.com/tagmanager#topic=3441530)
>* [신호](../dil/dil-instance-methods.md#signals)
* [주요 변수의 접두사 요구 사항](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

