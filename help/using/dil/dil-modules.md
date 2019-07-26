---
description: DIL. modules 네임스페이스의 메서드를 설명합니다. 이러한 모듈을 사용하여 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체를 사용할 수 있습니다.
seo-description: DIL. modules 네임스페이스의 메서드를 설명합니다. 이러한 모듈을 사용하여 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체를 사용할 수 있습니다.
seo-title: DIL 모듈
solution: Audience Manager
title: DIL 모듈
uuid: d 4 c 0 d 8 dd -79 f 8-448 e-b 17 c-c 935415 dd 449
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# DIL Modules{#dil-modules}

Describes methods in the `DIL.modules` namespace. 이러한 모듈을 사용하여 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체를 사용할 수 있습니다.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Works with [!UICONTROL DIL] to send [!DNL Analytics] tag elements (variables, props, eVars, etc.) Adobe Audience Manager 데이터를 쉼표로 구분된 목록으로 반환합니다. 버전 2.6에서 사용 가능합니다.

**함수 서명:**`DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>You must place this code on the page *before* the `s.t();` function.

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
   <td colname="col3"> <p><span class="keyword"></span><code> Pagename </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>등의 열거되지 않은 Analytics 변수를 포함하는 문자열 배열 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> 반복 이름 </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>An array of objects that contains enumerated <span class="keyword"> Analytics </span> variables like props and evars (e.g. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Maxindex </code> </td> 
   <td colname="col2"> 정수 </td> 
   <td colname="col3"> <p>반환할 반복 이름의 수를 나타냅니다. For example, to return two props or evars, set <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Sitecatalystreportingsuite </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p><span class="keyword"> Analytics </span> 개체를 나타내는 개체. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> Dilinstance </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>An object that represents <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> 옵션 </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>추가 옵션: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> Replacecontextdatnodeodswith </code> </p> <p>다른 항목을 지정하지 않으면 마침표가 기본 밑줄 (_) 로 대체됩니다. </p> <p>For example <code> s.contextData = {abc.def = '123'} </code>would result in <code> c_contextData_abc_def=123 </code> in the event call query string. </p> <p>This option is available only in <span class="wintitle"> DIL </span> version 5.0 or later. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> Filterfromcontextvariables </code> </p> <p>For example, <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> would result in the array of strings being filtered from the data collection of context data. 이 옵션은 PII (개인 식별 정보) 를 제외합니다. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Sitecatalyst. init가 캡처한 데이터**

This function returns details on the following [!DNL Analytics] properties:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**샘플 코드**

This code creates a comma separated list of [!DNL Analytics] events (props, eVars, etc.) 값이 있는 경우

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

To track all the monitored [!DNL Analytics] data points without the additional function shown above, invoke `siteCatalyst.init` by itself like this:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

`GA.submitUniversalAnalytics();` 이 함수는 Google의 데이터를 Audience Manager [!DNL Universal Analytics] 로 보냅니다. This [!UICONTROL DIL] function is designed to work with `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] Google `analytics.js` 코드 라이브러리에 대한 통찰력이나 제어가 없습니다. You should verify that [!UICONTROL DIL] data collection is still working if or when Google releases new versions of `analytics.js`.
   >
   >
* You cannot use `GA.submitUniversalAnalytics();` if you're still working with Google's legacy analytics tracking code (e.g., `ga.js` or `dc.js`). [ga. init를](../dil/dil-modules.md#ga-init) 대신 참조하십시오.
>



**함수 서명:**`DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**속성**

The `GA.submitUniversalAnalytics();` function accepts the following properties.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 속성 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Gaobject </code> </p> </td> 
   <td colname="col2"> <p>The global variable for your instance of <span class="keyword"> Google Analytics </span>. This is usually <code> ga </code> by default, unless you've customized your <span class="keyword"> Google Analytics </span> code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dilinstance </code> </p> </td> 
   <td colname="col2"> <p>The variable that represents your instance of <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Internalpropertyname </code> </p> </td> 
   <td colname="col2"> <p> <i>(선택 사항)</i> <code> analytics. js </code> 라이브러리에서는 내부 속성이 축소된 변수 <code> 'b'입니다 </code>. This variable holds <span class="keyword"> Google Analytics </span> data. </p> <p>Google에서 내부 변수의 이름을 변경하지 않는 한 이 속성은 선택 사항이므로 선택 사항입니다. For example, if this minified variable changed to <code> 'a' </code>, you would call <code> GA.submitUniversalAnalytics(); </code> like this: </p> <p> <code> dil. modules. gasubmituniversalanalytics (ga, dilinstance,' a '); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**예**

Remember to define the [!DNL Google Analytics] `ga` object first, before calling [!UICONTROL DIL] and `GA.submitUniversalAnalytics();`. 코드는 다음과 비슷합니다.

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

>[!MORE_ like_ this]
>
>* [GA 개체 메서드 참조](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)


## GA.init {#ga-init}

`GA.init()` 이 함수는 기존/사용되지 않는 버전의 데이터를 Audience [!DNL Google Analytics] Manager에 보냅니다.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` Google의 이전 분석 추적 코드나 사용에서만 `ga.js` 작동합니다 `dc.js`. You cannot invoke this [!UICONTROL DIL] function if you use `analytics.js`, which is the latest code library for Google [!DNL Universal Analytics]. [!DNL Audience Manager] GA. submituniversalanalytics [!UICONTROL DIL][!DNL Universal Analytics][](../dil/dil-modules.md#ga-submit-universal-analytics)를 사용하는 고객

**함수 서명:**`DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `_gaq` | 배열 | GA 명령이 포함된 배열. |
| `dilInstance` | 개체 | DIL 인스턴스가 포함된 개체. |
| `trackVars` | 개체 | *(선택 사항)* `names` 속성으로 구성된 개체. 이 속성은 추적할 GA 명령 이름의 배열입니다. |

**지원되는 GA 함수 호출**

By default, `GA.init` captures data from the following functions:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL에서 GA 데이터에 대한 키를 만듭니다.**

Audience Manager는 키-값 쌍의 형태로 데이터를 수락하며 GA는 배열의 항목과 함께 작동합니다. To work with GA data, [!UICONTROL DIL] creates a key-value pair automatically and forms a key like this: `c_ <key name>`. GA 배열의 항목도 특정 순서로 표시됩니다. 따라서 데이터가 포함되어 있지 않더라도 모든 매개 변수를 해당 순서대로 제공해야 합니다. [!UICONTROL DIL] 다음 GA 메서드에 대한 키를 매핑합니다.

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

To track all the monitored GA metrics without the additional function shown above, invoke `GA.init` by itself like this:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**샘플 이벤트 호출**

Audience Manager에 대한 URL 이벤트 호출은 다음과 비슷합니다.

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORE_ like_ this]
>
>* [Google Analytics 추적 코드](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [전체 웹 업그레이드: ga.js/dc.js to analytics. js](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [사이트에 analytics. js 추가](https://developers.google.com/analytics/devguides/collection/analyticsjs/)

