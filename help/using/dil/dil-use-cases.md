---
description: 특정 DIL 사용 사례에 대한 코드 샘플 및 설명.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL 사용 사례 및 코드 샘플
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 1%

---

# DIL 사용 사례 및 코드 샘플{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>2023년 7월부터 Adobe은 [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장 개발을 중단했습니다.
>
>기존 고객은 [!DNL DIL] 구현을 계속 사용할 수 있습니다. 그러나 Adobe은 이 시점 이후에는 [!DNL DIL]을(를) 개발하지 않습니다. 고객은 장기 데이터 수집 전략에 대해 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)을(를) 평가하는 것이 좋습니다.
>
>2023년 7월 이후에 새로운 데이터 수집 통합을 구현하려는 고객은 대신 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en)을 사용해야 합니다.

특정 DIL 사용 사례에 대한 코드 샘플 및 설명.

<!-- 

c_dil_use_case.xml

 -->

## DIL을 사용하여 Audience Manager에 데이터 요소 보내기 {#send-data-elements-dil}

페이지 요소에 대한 정보를 Audience Manager으로 보내는 개체 변수를 만듭니다. 이 기능은 일반 데이터 수집에 유용하거나 Analytics 변수로 데이터를 수집하는 것에 대한 대안으로 사용됩니다.

<!-- 

c_dil_send_page_objects.xml

 -->

**설명**

다음 코드는 페이지 데이터를 수집하여 [!UICONTROL DIL]을(를) 사용하여 Audience Manager으로 보내는 방법을 보여 줍니다. 이러한 예제에서는 변수를 사용하여 데이터 요소를 플랫 목록 또는 배열에 보관합니다. 변수를 [키-값 쌍](../reference/key-value-pairs-explained.md)(으)로 전달하십시오. 또한 키-값 쌍의 키 앞에 `c_` 접두사를 메모하십시오. 이 [필수 접두사](../features/traits/trait-variable-prefixes.md)은(는) 정보를 사용자 정의 데이터로 식별합니다. 첫 번째 예에서는 `c_`을(를) 키에 수동으로 추가해야 합니다. 두 번째 예제에서는 [!UICONTROL DIL]이(가) 자동으로 수행합니다.

**값 속성을 일관되게 유지**

데이터를 전달할 때 값 속성을 동일하게 유지해야 합니다. 예를 들어, 값이 다른 동일한 키가 두 개 있는 경우 마지막 키-값 쌍의 값이 이전 값 개체보다 우선합니다. 예를 들어 `color:blue` 및 `color:red`을(를) 전달하면 반환된 값이 빨간색으로 설정됩니다(파란색을 덮어씀).

**예제 1: 데이터를 키-값 쌍으로 보내기**

이 기본 예는 색상 및 가격 데이터를 키-값 쌍의 형태로 Audience Manager에 보냅니다. 코드는 다음과 유사할 수 있습니다.

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**예 2: 개체에 데이터 보내기**

이 고급 예에서는 개체의 데이터를 Audience Manager으로 보내는 방법을 보여 줍니다. 이 메서드로 작업할 때 [!UICONTROL DIL]을(를) 사용하면 개체를 함수 매개 변수로 [!DNL signals()] 메서드에 전달할 수 있습니다. [!UICONTROL DIL] 코드가 다음과 유사할 수 있습니다.

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

이 경우 `my_object` 변수는 배열을 사용하여 데이터를 유지합니다. 이 예제는 위의 권장 방법으로 전달된 정보를 기반으로 하지만 제품 유형 및 모델을 수용하기 위해 추가 레이어를 추가합니다. 코드는 다음과 유사할 수 있습니다.

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
>이 방법은 사용자가 유사한 프로토콜(HTTP와 HTTPS)을 사용하는 페이지 간에 이동하는 경우에만 작동합니다. 예를 들어 보안 사이트에서 다른 보안 사이트로 이동할 때 브라우저는 참조 URL을 유지합니다. 보안 사이트와 비보안 사이트 간을 이동할 때 브라우저는 참조 URL을 유지하지 않습니다. 이 동작은 일반적인 브라우저 기능이므로 [!UICONTROL DIL]에서 우회할 수 없습니다.

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

기본적으로 `DIL.getSearchReferrer`은(는) 다음 검색 엔진에서 검색을 인식합니다(국가별 변형 포함).

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**설명**

다음 코드는 지원되는 검색 엔진에 대한 검색 레퍼러를 가져오는 방법을 보여 줍니다. 이 경우 사용자가 [!DNL Google] 캐나다(`www.google.ca`)에서 &quot;홈&quot;이라는 용어로 검색했다고 가정해 보겠습니다. 이 코드는 이러한 검색어를 캡처하여 Audience Manager으로 전송하는 데 도움이 됩니다.

**기본 코드**

검색 레퍼러를 가져오기 위한 기본 코드(예: `google.com`에서)는 다음과 같습니다.

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**나열된 검색 엔진 코드 샘플**

이 경우 사용자가 [!DNL Google] 캐나다(`www.google.ca`)에서 &quot;홈&quot;이라는 용어를 검색했다고 가정해 보겠습니다. 코드 접두사가 필요한 `c_` 매개 변수를 검색 엔진(`c_se`) 및 검색어(`c_st`)에 어떻게 추가하는지 확인하십시오. `c_`은(는) Audience Manager에 대한 고객 정의 변수로 식별하는 [필수 접두사](../features/traits/trait-variable-prefixes.md)입니다.

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

이 경우 사용자가 `dogpile.com`에서 &quot;홈&quot;이라는 용어를 검색했다고 가정해 보겠습니다. [!DNL Dogpile]은(는) 기본적으로 지원되지 않으므로 이 검색 엔진을 인식하고 검색어를 Audience Manager으로 반환하도록 DIL을 구성할 수 있습니다. 코드는 다음과 유사할 수 있습니다.

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

키-값 쌍에서 키에 추가된 `c_` 접두사는 신호를 고객 정의 데이터로 식별합니다. 고객 정의 데이터는 이벤트 호출 시 데이터를 전달한 특정 사이트에서의 타겟팅에 사용됩니다. 그러나 경우에 따라 Audience Manager 계정의 모든 속성에서 이 정보를 사용할 수 있게 해야 합니다. 이렇게 하려면 `c_` 키-값 쌍의 값을 플랫폼 수준 키에 매핑합니다. 플랫폼 수준 키의 접두사로 `d_`이(가) 사용되고 계정의 모든 속성에서 신호를 타깃팅할 수 있게 됩니다.

예를 들어 특정 사이트에서 우편 번호 데이터를 수집하지만 모든 Audience Manager 속성에 타겟팅하려고 합니다. 플랫폼 수준에서 우편 번호를 사용할 수 있도록 하기 위해 아래와 같이 고객이 정의한 우편 번호 키(예: `c_zip`)를 플랫폼 정의 키에 매핑할 수 있습니다.

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

## Google Tag Manager(GTM)의 트래픽 DIL {#traffic-dil-gtm}

GTM 태그를 사용하여 DIL을 설정하고 제공합니다.

<!-- 

t_dil_google_tagmanager.xml

 -->

이 절차에서는 사용자가 [!DNL Google Tag Manager] 계정, 해당 제품에 대한 일부 작업 지식 및 Audience Manager `dil.js` 파일을 가지고 있다고 가정합니다.

GTM에서 `dil.js` 파일을 트래픽하려면 다음을 수행하십시오.

1. 새 컨테이너를 만들거나 기존 컨테이너를 엽니다.
1. 컨테이너에 새 태그를 추가합니다.
1. 태그를 열어 편집하고:

   * 태그 이름을 지정합니다.
   * **[!UICONTROL Custom HTML Tag]** 드롭다운 목록에서 **[!UICONTROL Tag Type]** 선택.
   * HTML 필드에서 [!UICONTROL DIL] 코드(라이브러리 + 사용자 지정 코드)를 스크립트 태그 `<script>DIL code</script>` 내에 배치합니다.
   * **[!UICONTROL Save]** 아이콘을 클릭합니다.

1. 컨테이너를 게시합니다.
1. 컨테이너 태그 코드를 생성하여 인벤토리에 넣습니다.

>[!MORELIKETHIS]
>
>* [Google 태그 관리자 도움말 센터](https://support.google.com/tagmanager#topic=3441530)
>* [신호](../dil/dil-instance-methods.md#signals)
>* [주요 변수의 접두사 요구 사항](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)
