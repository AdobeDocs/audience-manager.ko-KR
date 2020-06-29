---
description: DIL.modules 네임스페이스의 메서드를 설명합니다. 이러한 모듈을 사용하면 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체를 사용하여 작업할 수 있습니다.
seo-description: DIL.modules 네임스페이스의 메서드를 설명합니다. 이러한 모듈을 사용하면 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체를 사용하여 작업할 수 있습니다.
seo-title: DIL 모듈
solution: Audience Manager
title: DIL 모듈
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 4%

---


# DIL 모듈{#dil-modules}

네임스페이스의 메서드를 `DIL.modules` 설명합니다. 이러한 모듈을 사용하면 프로그래밍 방식으로 데이터를 수집하고 Audience Manager 개체를 사용하여 작업할 수 있습니다.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

태그 요소 [!UICONTROL DIL] [!DNL Analytics] (변수, prop, eVar 등)를 전송하는 데 사용됩니다. 를 Audience Manager에 추가합니다. 데이터를 쉼표로 구분된 목록으로 반환합니다. 버전 2.6에서 사용 가능합니다.

**함수 서명:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>이 코드를 함수 *앞에* 삽입해야 `s.t();` 합니다.

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
   <td colname="col3"> <p>열거되지 않은 Analytics 변수 <span class="keyword"> , </span> , <code> pageName </code>등 <code> channel </code>을 포함하는 문자열 <code> campaign </code><code> product </code>배열 </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>prop 및 evar(예: <span class="keyword"> </span> <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> 정수 </td> 
   <td colname="col3"> <p>반환할 반복 이름의 수를 나타냅니다. 예를 들어 두 개의 prop 또는 evar를 반환하려면 을 설정합니다 <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>Analytics 개체를 나타내는 <span class="keyword"></span> 개체입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>DIL을 나타내는 <span class="wintitle"> 개체 </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> 개체 </td> 
   <td colname="col3"> <p>추가 옵션: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>다른 항목을 지정하지 않으면 점이 기본 밑줄( _ )로 대체됩니다. </p> <p>예를 <code> s.contextData = {abc.def = '123'} </code>들어 이벤트 호출 쿼리 문자열 <code> c_contextData_abc_def=123 </code> 이 발생합니다. </p> <p>이 옵션은 DIL <span class="wintitle"></span> 버전 5.0 이상에서만 사용할 수 있습니다. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>예를 들어 컨텍스트 데이터의 데이터 수집에서 문자열 배열을 필터링하게 <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> 됩니다. 이 옵션은 PII(개인 식별 정보)를 제외합니다. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**siteCatalyst.init에서 캡처한 데이터**

이 함수는 다음 속성에 대한 세부 사항을 [!DNL Analytics] 반환합니다.

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

이 코드는 쉼표로 구분된 이벤트(prop, eVar 등) [!DNL Analytics] 목록을 만듭니다. if values for them exist.

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

위에 표시된 추가 기능 없이 모니터링되는 모든 [!DNL Analytics] 데이터 포인트를 추적하려면 다음과 같이 자체 `siteCatalyst.init` 로 호출합니다.

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

이 `GA.submitUniversalAnalytics();` 함수는 Google의 데이터를 Audience Manager [!DNL Universal Analytics] 로 전송합니다. 이 [!UICONTROL DIL] 함수는 Google용 최신 코드 라이브러리인 Google과 함께 작동하도록 디자인되었습니다 `analytics.js`[!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] 은 Google 코드 라이브러리에 대한 통찰력이나 제어를 가지고 있지 않습니다 `analytics.js` . Google에서 새 버전의 [!UICONTROL DIL] 데이터 수집을 출시하더라도 데이터 수집이 여전히 작동하는지 확인해야 합니다 `analytics.js`.
   >
   >
* 여전히 Google의 기존 분석 추적 코드(예: `GA.submitUniversalAnalytics();` 또는 `ga.js` `dc.js`)로 작업하는 경우에는 사용할 수 없습니다. 대신 [GA.init를](../dil/dil-modules.md#ga-init) 참조하십시오.
>



**함수 서명:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**속성**

이 `GA.submitUniversalAnalytics();` 함수에는 다음 속성이 사용됩니다.

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
   <td colname="col2"> <p>Google Analytics 인스턴스에 대한 전역 변수 <span class="keyword"> </span>. Google Analytics <code> ga </code> <span class="keyword"> </span> 코드를 사용자 지정하지 않은 경우 기본적으로 사용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>DIL의 인스턴스를 나타내는 <span class="wintitle"> 변수입니다 </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(선택 사항)</i> 라이브러리에서 <code> analytics.js </code> 내부 속성은 축소 변수입니다 <code> 'b' </code>. 이 변수는 <span class="keyword"> Google Analytics </span> 데이터를 보관합니다. </p> <p>이 속성은 Google이 내부 변수의 이름을 변경하지 않는 한 설정할 필요가 없으므로 선택 사항입니다. 예를 들어, 이 축소 변수가 (으)로 변경된 경우 <code> 'a' </code>다음과 <code> GA.submitUniversalAnalytics(); </code> 같이 호출합니다. </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**예**

and를 호출하기 전에 먼저 [!DNL Google Analytics] 개체를 정의해야 `ga` 합니다 [!UICONTROL DIL] `GA.submitUniversalAnalytics();`. 코드는 다음과 비슷합니다.

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

이 `GA.init()` 함수는 이전/사용되지 않는 버전의 데이터를 Audience Manager [!DNL Google Analytics] 로 전송합니다.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` Google의 기존 분석 추적 코드 `ga.js` 와 함께 사용할 수 `dc.js`있습니다. Google의 최신 코드 라이브러리인 이 [!UICONTROL DIL] 함수를 사용하면 이 함수를 호출할 수 `analytics.js`없습니다 [!DNL Universal Analytics]. [!DNL Audience Manager] GA.submitUniversalAnalytics를 사용하고 [!UICONTROL DIL] 있어야 [!DNL Universal Analytics] 하는 고객 [](../dil/dil-modules.md#ga-submit-universal-analytics).

**함수 서명:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `_gaq` | 배열 | GA 명령이 포함된 배열. |
| `dilInstance` | 개체 | DIL 인스턴스가 포함된 객체입니다. |
| `trackVars` | 개체 | *(선택 사항)* 속성으로 구성된 `names` 개체입니다. 이 속성은 추적할 GA 명령 이름의 배열입니다. |

**지원되는 GA 함수 호출**

기본적으로 다음 함수의 데이터를 `GA.init` 캡처합니다.

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL에서 GA 데이터에 대한 키를 만듭니다.**

Audience Manager은 키-값 쌍의 형태로 데이터를 받아들이는 반면 GA는 배열의 항목들과 함께 작동합니다. GA 데이터를 사용하여 작업하려면 [!UICONTROL DIL] 키-값 쌍을 자동으로 만들고 다음과 같은 키를 만듭니다. `c_ <key name>`. 또한 GA 배열의 항목은 특정 순서로 표시됩니다. 따라서 데이터가 없는 경우에도 모든 매개 변수를 해당 순서로 제공해야 합니다. [!UICONTROL DIL] maps keys for following GA methods:

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

위에 표시된 추가 기능 없이 모니터링되는 모든 GA 지표를 추적하려면 다음과 같이 스스로 `GA.init` 호출합니다.

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**샘플 이벤트 호출**

Audience Manager에 대한 URL 이벤트 호출은 다음과 비슷합니다.

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics 추적 코드](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [전체 웹 업그레이드: ga.js/dc.js에 문의](https://developers.google.com/analytics/devguides/collection/upgrade/reference/gajs-analyticsjs)
>* [사이트에 analytics.js 추가](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga 객체 메서드 참조](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

