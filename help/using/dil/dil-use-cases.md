---
description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL 사용 사례 및 코드 샘플
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 2%

---

# DIL 사용 사례 및 코드 샘플{#dil-use-cases-and-code-samples}

특정 DIL 사용 사례에 대한 코드 샘플 및 설명.

<!-- 

c_dil_use_case.xml

 -->

## DIL을 사용하여 Audience Manager에 데이터 요소 보내기 {#send-data-elements-dil}

Audience Manager 요소에 대한 정보를 페이지로 전송하는 개체 변수를 만듭니다. 이 기능은 일반 데이터 수집에 유용하거나 Analytics 변수로 데이터를 수집하는 것에 대한 대안으로 사용됩니다.

<!-- 

c_dil_send_page_objects.xml

 -->

**설명**

다음 코드는 페이지 데이터를 수집하여 를 사용하여 Audience Manager으로 전송하는 방법을 보여 줍니다 [!UICONTROL DIL]. 이러한 예제에서는 변수를 사용하여 데이터 요소를 플랫 목록 또는 배열에 보관합니다. 변수를 다음과 같이 전달하십시오. [키-값 쌍](../reference/key-value-pairs-explained.md). 또한 다음을 참고하십시오. `c_` key-value 쌍에서 키 앞에 접두사를 추가합니다. 이 [필수 접두사](../features/traits/trait-variable-prefixes.md) 는 정보를 사용자 정의 데이터로 식별합니다. 첫 번째 예에서는 을 수동으로 추가해야 합니다 `c_` 키를 누릅니다. 두 번째 예에서는 [!UICONTROL DIL] 자동으로 수행합니다.

**값 속성 일관성 유지**

데이터를 전달할 때 값 속성을 동일하게 유지해야 합니다. 예를 들어, 값이 다른 동일한 키가 두 개 있는 경우 마지막 키-값 쌍의 값이 이전 값 개체보다 우선합니다. 예를 들어 를 전달합니다 `color:blue` 및 `color:red` 반환된 값을 빨간색으로 설정합니다(파란색을 덮어씀).

**예제 1: 데이터를 키-값 쌍으로 보내기**

이 기본 예는 색상 및 가격 데이터를 키-값 쌍의 형태로 Audience Manager에 보냅니다. 코드는 다음과 유사할 수 있습니다.

<pre class="&ldquo;java&rdquo;"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**예제 2: 개체에 데이터 보내기**

이 고급 예에서는 개체의 데이터를 Audience Manager으로 보내는 방법을 보여 줍니다. 이 메서드를 사용하여 작업할 때 [!UICONTROL DIL] 함수 매개 변수로 개체를 [!DNL signals()] 메서드를 사용합니다. [!UICONTROL DIL] 코드는 다음과 유사할 수 있습니다.

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**예제 3: 배열에 페이지 데이터 보내기**

이 경우 변수는 `my_object` 배열을 사용하여 데이터를 보유합니다. 이 예제는 위의 권장 방법으로 전달된 정보를 기반으로 하지만 제품 유형 및 모델을 수용하기 위해 추가 레이어를 추가합니다. 코드는 다음과 유사할 수 있습니다.

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

참조 URL을 캡처하여 Audience Manager으로 보냅니다.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>이 방법은 사용자가 유사한 프로토콜(HTTP와 HTTPS)을 사용하는 페이지 간에 이동하는 경우에만 작동합니다. 예를 들어 보안 사이트에서 다른 보안 사이트로 이동할 때 브라우저는 참조 URL을 유지합니다. 보안 사이트와 비보안 사이트 간을 이동할 때 브라우저는 참조 URL을 유지하지 않습니다. 이 동작은 일반적인 브라우저 기능이며 다음을 통해 우회할 수 없습니다. [!UICONTROL DIL].

**코드 샘플**

코드는 다음과 유사할 수 있습니다.

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## 검색 엔진 유형 및 키워드 검색어 캡처 {#capture-search-engine-types}

검색 엔진 유형 및 키워드 검색에 대한 정보를 Audience Manager으로 보냅니다.

>[!IMPORTANT]
>
>이 섹션에서는 최신 버전의 DIL에서 지원되지 않는 기존 기능에 대해 설명합니다.

**지원되는 검색 엔진**

기본적으로, `DIL.getSearchReferrer` 은 다음 검색 엔진에서 검색을 인식합니다(국제 변형 포함).

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**설명**

다음 코드는 지원되는 검색 엔진에 대한 검색 레퍼러를 가져오는 방법을 보여 줍니다. 이 경우 사용자가에서 &quot;홈&quot;이라는 용어를 검색했다고 가정해 보겠습니다 [!DNL Google] 캐나다 ( `www.google.ca`). 이 코드는 이러한 검색어를 캡처하여 Audience Manager으로 전송하는 데 도움이 됩니다.

**기본 코드**

검색 레퍼러 가져오기에 대한 기본 코드(에서) `google.com`, 예를 들어 )는 다음과 같습니다.

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**나열된 검색 엔진 코드 샘플**

이 경우 사용자가 &quot;홈&quot;이라는 용어를 검색했다고 가정해 보겠습니다 [!DNL Google] 캐나다 ( `www.google.ca`). 코드 접두사가 필요한 방법을 참고하십시오 `c_` 검색 엔진에 대한 매개 변수( `c_se`) 및 검색어( `c_st`). `c_` 다음 값: [필수 접두사](../features/traits/trait-variable-prefixes.md) 이를 Audience Manager 대상으로 고객 정의 변수로 식별합니다.

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

이 경우 사용자가 &quot;홈&quot;이라는 용어를 검색했다고 가정해 보겠습니다 `dogpile.com`. 이유 [!DNL Dogpile] 은(는) 기본적으로 지원되지 않습니다. 이 검색 엔진을 인식하고 검색어를 Audience Manager으로 반환하도록 DIL을 구성할 수 있습니다. 코드는 다음과 유사할 수 있습니다.

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

키-값 쌍에서 `c_` 키에 추가된 접두사는 신호를 고객 정의 데이터로 식별합니다. 고객 정의 데이터는 이벤트 호출 시 데이터를 전달한 특정 사이트에서의 타겟팅에 사용됩니다. 그러나 경우에 따라 Audience Manager 계정의 모든 속성에서 이 정보를 사용할 수 있게 해야 합니다. 이렇게 하려면 의 값을 매핑합니다. `c_` 플랫폼 수준 키에 대한 키-값 쌍입니다. 플랫폼 수준 키 접두사가 붙습니다. `d_` 및 을 사용하면 계정의 모든 속성에서 타깃팅에 신호를 사용할 수 있습니다.

예를 들어 특정 사이트에서 우편 번호 데이터를 수집하지만 모든 Audience Manager 속성에 타겟팅하려고 합니다. 플랫폼 수준에서 우편번호를 사용할 수 있도록 하기 위해 고객 정의 우편번호 키(예: )를 매핑할 수 있습니다. `c_zip`)을 클릭하여 아래 표시된 대로 플랫폼 정의 키로 변경할 수 있습니다.

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

이 절차에서는 다음 항목이 있다고 가정합니다. [!DNL Google Tag Manager] 계정, 해당 제품에 대한 작업 지식 및 Audience Manager `dil.js` 파일.

트래픽을 분산하려면 `dil.js` gtm의 파일:

1. 새 컨테이너를 만들거나 기존 컨테이너를 엽니다.
1. 컨테이너에 새 태그를 추가합니다.
1. 태그를 열어 편집하고:

   * 태그 이름을 지정합니다.
   * 선택 **[!UICONTROL Custom HTML Tag]** 다음에서 **[!UICONTROL Tag Type]** 드롭다운 목록입니다.
   * HTML 필드에 [!UICONTROL DIL] 스크립트 태그 내의 코드(라이브러리 + 사용자 지정 코드) `<script>DIL code</script>`.
   * 클릭 **[!UICONTROL Save]**.

1. 컨테이너를 게시합니다.
1. 컨테이너 태그 코드를 생성하여 인벤토리에 넣습니다.

>[!MORELIKETHIS]
>
>* [Google Tag Manager 도움말 센터](https://support.google.com/tagmanager#topic=3441530)
>* [신호](../dil/dil-instance-methods.md#signals)
>* [주요 변수의 접두사 요구 사항](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)

