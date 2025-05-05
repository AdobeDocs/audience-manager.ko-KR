---
description: DIL.modules 네임스페이스의 메서드에 대해 설명합니다. 이러한 모듈을 사용하면 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체로 작업할 수 있습니다.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL 모듈
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 3%

---

# DIL 모듈{#dil-modules}

>[!WARNING]
>
>2023년 7월부터 Adobe에서 [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장 개발을 중단했습니다.
>
>기존 고객은 [!DNL DIL] 구현을 계속 사용할 수 있습니다. 그러나 Adobe은 이 시점 이후에는 [!DNL DIL]을(를) 개발하지 않습니다. 고객은 장기 데이터 수집 전략에 대해 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)를 평가하는 것이 좋습니다.
>
>2023년 7월 이후에 새로운 데이터 수집 통합을 구현하려는 고객은 대신 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)를 사용해야 합니다.

`DIL.modules` 네임스페이스의 메서드를 설명합니다. 이러한 모듈을 사용하면 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체로 작업할 수 있습니다.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

[!UICONTROL DIL]을(를) 사용하여 [!DNL Analytics] 태그 요소(변수, Prop, eVar 등)를 보냅니다. Audience Manager. 쉼표로 구분된 목록으로 데이터를 반환합니다. 버전 2.6에서 사용할 수 있습니다.

**함수 서명:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>`s.t();` 함수를 *이전* 페이지에 이 코드를 배치해야 합니다.

<!-- 

r_dil_sc_init.xml

 -->

**매개 변수**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이름 </th> 
   <th colname="col2" class="entry"> 유형 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> 문자열 </td> 
   <td colname="col3"> <p><code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code> 등과 같은 열거되지 않은 <span class="keyword"> Analytics </span> 변수가 포함된 문자열 배열입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>prop 및 evar와 같은 열거된 <span class="keyword"> Analytics </span> 변수가 포함된 개체 배열(예: <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 정수 </td> 
   <td colname="col3"> <p>반환할 반복된 이름의 수를 나타냅니다. 예를 들어 두 개의 prop 또는 evar를 반환하려면 <code> maxIndex:2 </code>을(를) 설정합니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p><span class="keyword"> Analytics </span> 개체를 나타내는 개체입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p><span class="wintitle"> DIL </span>을(를) 나타내는 개체입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>추가 옵션: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>다른 항목을 지정하지 않으면 마침표가 기본 밑줄( _ )로 바뀝니다. </p> <p>예를 들어 <code> s.contextData = {abc.def = '123'} </code>은(는) 이벤트 호출 쿼리 문자열에 <code> c_contextData_abc_def=123 </code>을(를) 생성합니다. </p> <p>이 옵션은 <span class="wintitle"> DIL </span> 버전 5.0 이상에서만 사용할 수 있습니다. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>예를 들어 <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code>을(를) 사용하면 컨텍스트 데이터의 데이터 컬렉션에서 문자열 배열이 필터링됩니다. 이 옵션은 PII(개인 식별 정보)를 제외합니다. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**siteCatalyst.init에 의해 캡처된 데이터**

이 함수는 다음 [!DNL Analytics] 속성에 대한 세부 정보를 반환합니다.

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar`(1 - 250)
* `prop`(1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**샘플 코드**

이 코드는 [!DNL Analytics]개의 이벤트(Prop, eVar 등)를 쉼표로 구분한 목록을 만듭니다. 해당 값에 대한 값이 있는 경우

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

위에 표시된 추가 함수 없이 모니터링되는 모든 [!DNL Analytics] 데이터 포인트를 추적하려면 다음과 같이 `siteCatalyst.init`을(를) 호출하십시오.

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

`GA.submitUniversalAnalytics();` 함수는 Google의 [!DNL Universal Analytics]에서 Audience Manager으로 데이터를 보냅니다. 이 [!UICONTROL DIL] 함수는 Google [!DNL Universal Analytics]의 최신 코드 라이브러리인 `analytics.js`에서 작동하도록 디자인되었습니다.

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager]에 Google `analytics.js` 코드 라이브러리에 대한 통찰력이나 제어권이 없습니다. Google에서 `analytics.js`의 새 버전을 릴리스할 경우 또는 릴리스할 때 [!UICONTROL DIL] 데이터 수집이 계속 작동하는지 확인해야 합니다.
>
>* Google의 기존 분석 추적 코드(예: `ga.js` 또는 `dc.js`)를 사용하여 작업하는 경우에는 `GA.submitUniversalAnalytics();`을(를) 사용할 수 없습니다. 대신 [GA.init](../dil/dil-modules.md#ga-init)을(를) 참조하십시오.
>

**함수 서명:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**속성**

`GA.submitUniversalAnalytics();` 함수는 다음 속성을 허용합니다.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 속성 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Google Analytics </span>의 인스턴스에 대한 전역 변수입니다. <span class="keyword"> Google Analytics </span> 코드를 사용자 지정하지 않은 경우 기본적으로 <code> ga </code>입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DIL </span>의 인스턴스를 나타내는 변수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(선택 사항)</i> <code> analytics.js </code> 라이브러리에서 내부 속성은 축소된 변수 <code> 'b' </code>입니다. 이 변수에는 <span class="keyword">개의 Google Analytics </span> 데이터가 있습니다. </p> <p>Google에서 내부 변수의 이름을 변경하지 않는 한 이 속성을 설정할 필요가 없으므로 이 속성은 선택 사항입니다. 예를 들어 축소된 이 변수가 <code> 'a' </code>(으)로 변경되면 다음과 같이 <code> GA.submitUniversalAnalytics(); </code>을(를) 호출합니다. </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**예**

[!UICONTROL DIL] 및 `GA.submitUniversalAnalytics();`을(를) 호출하기 전에 먼저 [!DNL Google Analytics] `ga` 개체를 정의해야 합니다. 코드는 다음과 유사할 수 있습니다.

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

`GA.init()` 함수는 [!DNL Google Analytics]의 이전/더 이상 사용되지 않는 버전에서 Audience Manager으로 데이터를 보냅니다.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()`은(는) Google의 이전 analytics 추적 코드인 `ga.js` 또는 `dc.js`에서만 작동합니다. Google [!DNL Universal Analytics]의 최신 코드 라이브러리인 `analytics.js`을(를) 사용하는 경우 이 [!UICONTROL DIL] 함수를 호출할 수 없습니다. [!UICONTROL DIL] 및 [!DNL Universal Analytics]을(를) 사용하는 [!DNL Audience Manager] 고객은 [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)를 볼 수 있습니다.

**함수 서명:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `_gaq` | 배열 | GA 명령이 포함된 배열입니다. |
| `dilInstance` | 개체 | DIL 인스턴스를 포함하는 객체입니다. |
| `trackVars` | 개체 | *(선택 사항)* `names` 속성으로 구성된 개체입니다. 이 속성은 추적하려는 GA 명령 이름의 배열입니다. |

**지원되는 GA 함수 호출**

기본적으로 `GA.init`은(는) 다음 함수에서 데이터를 캡처합니다.

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL이 GA 데이터에 대한 키를 만듭니다**

Audience Manager은 GA가 배열의 항목에 대해 작동하는 동안 데이터를 키-값 쌍 형태로 수락합니다. GA 데이터를 사용하려면 [!UICONTROL DIL]에서 키-값 쌍을 자동으로 만들고 `c_ <key name>`과(와) 같은 키를 만듭니다. 또한 GA 배열의 항목은 특정 순서로 나타납니다. 따라서 데이터가 포함되지 않은 경우에도 모든 매개 변수를 해당 순서로 제공해야 합니다. [!UICONTROL DIL]은(는) 다음 GA 메서드에 대한 키를 매핑합니다.

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**샘플 코드**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

위에 표시된 추가 함수 없이 모니터된 모든 GA 지표를 추적하려면 다음과 같이 `GA.init`을(를) 자체적으로 호출하십시오.

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**샘플 이벤트 호출**

Audience Manager에 대한 URL 이벤트 호출은 다음과 유사할 수 있습니다.

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics 추적 코드](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [웹 업그레이드 완료: ga.js/dc.js to analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [사이트에 analytics.js 추가](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga 개체 메서드 참조](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)
