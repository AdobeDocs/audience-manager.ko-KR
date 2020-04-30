---
description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명입니다.
seo-description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명입니다.
seo-title: DIL 사용 사례 및 코드 샘플
solution: Audience Manager
title: DIL 사용 사례 및 코드 샘플
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# DIL 사용 사례 및 코드 샘플{#dil-use-cases-and-code-samples}

특정 DIL 사용 사례에 대한 코드 샘플 및 설명입니다.

<!-- 

c_dil_use_case.xml

 -->

## DIL을 사용하여 데이터 요소를 Audience Manager로 전송 {#send-data-elements-dil}

페이지 요소에 대한 정보를 Audience Manager에 보내는 개체 변수를 만듭니다. 이 기능은 일반 데이터 수집 또는 Analytics 변수를 사용하여 데이터를 수집하는 대신 유용합니다.

<!-- 

c_dil_send_page_objects.xml

 -->

**설명**

다음 코드는 페이지 데이터를 수집하여 Audience Manager에 보내는 방법을 보여 줍니다 [!UICONTROL DIL]. 이러한 예에서는 변수를 사용하여 데이터 요소를 플랫 목록 또는 배열에 보관합니다. 변수를 [키-값 쌍으로 전달하십시오](../reference/key-value-pairs-explained.md). 또한 키-값 쌍의 키 앞에 있는 `c_` 접두사를 확인하십시오. 이 [필수 접두사는](../features/traits/trait-variable-prefixes.md) 정보를 사용자 정의 데이터로 식별합니다. 첫 번째 예에서는 키에 수동으로 추가해야 `c_` 합니다. 두 번째 예에서는 자동으로 [!UICONTROL DIL] 이 작업을 수행합니다.

**일관된 값 속성 유지**

데이터를 전달할 때 값 속성을 동일하게 유지해야 합니다. 예를 들어 값이 다른 두 개의 동일한 키가 있는 경우 마지막 키-값 쌍의 값이 이전 값 개체보다 우선합니다. 예를 들어, 전달을 `color:blue` 수행하고 반환된 값을 `color:red` red(파란색을 덮어쓰기)로 설정합니다.

**예 1: 데이터를 키-값 쌍으로 보내기**

이 기본 예제는 색상 및 가격 데이터를 키-값 쌍의 형태로 Audience Manager에 보냅니다. 코드는 다음과 비슷합니다.

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**예 2: 개체에서 데이터 보내기**

이 고급 예에서는 개체의 데이터를 Audience Manager로 보내는 방법을 보여 줍니다. 이 메서드로 작업할 때 함수 매개 변수로 객체를 메서드에 전달할 [!UICONTROL DIL] 수 [!DNL signals()] 있습니다. [!UICONTROL DIL] 코드는 다음과 비슷합니다.

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**예 3: 배열에 페이지 데이터 보내기**

이 경우 변수에 데이터 `my_object` 가 있는 배열이 사용됩니다. 이 예에서는 위의 권장 방법으로 전달된 정보를 기반으로 구축되지만 제품 유형과 모델을 수용할 추가 레이어를 추가합니다. 코드는 다음과 비슷합니다.

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

참조 URL을 캡처하여 Audience Manager로 보냅니다.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>이 방법은 사용자가 유사한 프로토콜(HTTP와 HTTPS)을 사용하는 페이지 간을 이동할 때만 작동합니다. 예를 들어 보안 사이트에서 다른 보안 사이트로 이동할 때 브라우저는 참조 URL을 유지합니다. 보안 사이트와 비보안 사이트 간을 이동할 때 브라우저는 참조 URL을 유지하지 않습니다. 이 동작은 일반적인 브라우저 기능이므로 이 동작으로 우회할 수 없습니다 [!UICONTROL DIL].

**코드 샘플**

코드는 다음과 비슷합니다.

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 검색 엔진 유형 및 키워드 검색 용어 캡처 {#capture-search-engine-types}

검색 엔진 유형 및 키워드 검색에 대한 정보를 Audience Manager로 전송합니다.

>[!IMPORTANT]
>
>이 섹션에서는 최신 버전의 DIL에서 지원되지 않는 기존 기능에 대해 설명합니다.

**지원되는 검색 엔진**

기본적으로 이러한 검색 엔진에서 검색을 `DIL.getSearchReferrer` 인식합니다(국제 변형 포함).

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**설명**

다음 코드는 지원되는 검색 엔진에 대해 검색 레퍼러를 가져오는 방법을 보여 줍니다. 이 경우 사용자가 [!DNL Google] 캐나다()에서 &quot;homes&quot;라는 용어를 검색했다고 `www.google.ca`가정합니다. 이 코드는 해당 검색어를 캡처하여 Audience Manager로 보내는 데 도움이 됩니다.

**기본 코드**

검색 레퍼러(예: 시작)를 가져오기 위한 기본 코드 `google.com`는 다음과 같습니다.

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**나열된 검색 엔진 코드 샘플**

이 경우 사용자가 [!DNL Google] 캐나다()에서 &quot;homes&quot;라는 용어를 검색했다고 `www.google.ca`가정합니다. 코드가 검색 엔진()과 검색어()에 필요한 `c_` 매개 변수 `c_se`의 접두사를 지정하는 방법을 `c_st`확인하십시오. `c_` 는 Audience Manager에 대한 고객 정의 변수로 식별되는 [필수 접두사입니다](../features/traits/trait-variable-prefixes.md) .

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

이 경우 사용자가 &quot;homes&quot;라는 용어를 검색했다고 가정합니다 `dogpile.com`. 기본적으로 지원되지 [!DNL Dogpile] 않으므로 이 검색 엔진을 인식하고 검색어를 Audience Manager에 반환하도록 DIL을 구성할 수 있습니다. 코드는 다음과 비슷합니다.

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

## 다른 키에 키 값 매핑 {#map-key-values}

키-값 쌍의 값을 다른 키에 연결합니다.

<!-- 

c_dil_map_keys.xml

 -->

**설명**

키-값 쌍에서 키 `c_` 에 추가된 접두사는 신호를 고객 정의 데이터로 식별합니다. 고객 정의 데이터는 이벤트 호출에서 데이터를 전달한 특정 사이트에서 타깃팅하는 데 사용됩니다. 하지만 Audience Manager 계정의 모든 속성에서 이 정보를 사용할 수 있어야 하는 경우가 있습니다. 이렇게 하려면 `c_` 키-값 쌍의 값을 플랫폼 수준 키에 매핑합니다. 플랫폼 수준 키는 접두사로 추가되며 계정의 모든 속성 `d_` 에서 신호를 타깃팅하는 데 사용할 수 있도록 합니다.

예를 들어 특정 사이트에서 ZIP 코드 데이터를 수집하지만 모든 Audience Manager 속성에 타깃팅하려는 경우 플랫폼 수준에서 ZIP 코드를 사용할 수 있도록 하려면 고객이 정의한 ZIP 코드 키(예: `c_zip`) to a platform defined key as shown below.

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

## GTM(Google Tag Manager)의 트래픽 DIL {#traffic-dil-gtm}

GTM 태그를 사용하여 DIL을 설정하고 제공합니다.

<!-- 

t_dil_google_tagmanager.xml

 -->

이 절차에서는 계정, 해당 제품에 대한 일부 작업 지식 및 Audience Manager [!DNL Google Tag Manager] `dil.js` 파일을 가지고 있다고 가정합니다.

GTM에서 `dil.js` 파일에 트래픽을 표시하려면:

1. 새 컨테이너를 만들거나 기존 컨테이너를 엽니다.
1. 컨테이너에 새 태그를 추가합니다.
1. 태그를 열고 다음을 수행합니다.

   * 태그 이름을 지정합니다.
   * Select **[!UICONTROL Custom HTML Tag]** from the **[!UICONTROL Tag Type]** drop-down list.
   * HTML 필드에 스크립트 태그 내에 [!UICONTROL DIL] 코드(라이브러리 + 사용자 지정 코드)를 배치합니다 `<script>DIL code</script>`.
   * 클릭 **[!UICONTROL Save]**.

1. 컨테이너를 게시합니다.
1. 컨테이너 태그 코드를 생성하여 인벤토리에 배치합니다.

>[!MORELIKETHIS]
>
>* [Google 태그 관리자 도움말 센터](https://support.google.com/tagmanager#topic=3441530)
>* [신호](../dil/dil-instance-methods.md#signals)
>* [키 변수의 접두사 요구 사항](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

