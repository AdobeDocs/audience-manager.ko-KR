---
description: FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보를 사용할 수 있습니다.
seo-description: FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보를 사용할 수 있습니다.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833 CFD -768 E -4 B 16-95 C 5-DEBD 8411 DF 38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보를 사용할 수 있습니다.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 는 Audience Manager에서 비디오 재생 데이터를 사용할 수 있도록 해주는 [!DNL ActionScript] 코드 라이브러리입니다. [!DNL Flash DIL] Adobe [!UICONTROL AppMeasurement] 라이브러리가 Analytics에 전달하는 SWF 컨텐츠를 캡처하여 작동합니다. [!DNL Flash DIL] 이 데이터를 Audience Manager에 전달하는 별도의 [!UICONTROL DIL] JavaScript 데이터 수집 모듈로 보냅니다. Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals.

## Requirements for Flash DIL Data Collection {#requirements}

일반 구현 및 코드 관련 요구 사항.

<!-- 

c_flash_dil_intro.xml

 -->

**구현 요구 사항**

[!UICONTROL Flash] 데이터 수집에는 다음이 필요합니다.

* [!UICONTROL DIL] 클래스 라이브러리 ( `dil.swc`). Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact.

* JavaScript [!UICONTROL DIL] data collection code on the page.
* [DIL ActionScript 라이브러리가](../dil/dil-flash.md#flash-dil-actionscript) 데이터를 수집하려는 Flash 객체에 로드됩니다.
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**Allowscriptaccess로`Always`설정 또는`sameDomain`**

The `AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. [!UICONTROL Flash DIL] 데이터 통합을 구성할 때 Flash `AllowScriptAccess` 매개 변수가 OR로 `always` 설정되어 있는지 `sameDomain`확인합니다. [!UICONTROL Flash DIL] 설정된 경우 `AllowScriptAccess` 데이터 수집이 작동하지 `never`않습니다. See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS[!UICONTROL DIL]코드 배치**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. When the [!DNL FLA] file loads first, before [!UICONTROL DIL] data collection is ready, you can miss the initial data signals that [!UICONTROL Flash DIL] sends to that module. However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL].

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] 페이지 보기, 링크 추적, 미디어 추적 및 기타 미디어 보기 이벤트를 Adobe [!UICONTROL AppMeasurement] 라이브러리에서 캡처합니다.

<!-- 

r_flash_dil_data_collected.xml

 -->

**페이지 보기 이벤트**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**링크 추적 이벤트**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (호출된 추적 링크 유형)
* `pev1` (링크 URL)
* `pev2`(링크 텍스트)

**미디어 추적 이벤트**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**기타 데이터 포인트**

이러한 매개 변수의 데이터는 기본적으로 수집됩니다.

* `mediaName` (미디어/비디오 요소 이름)
* `mediaAdName` (광고 이름)
* `mediaAdParentName` (광고가 중첩되어 있는 기본 미디어 컨텐츠의 이름)
* `mediaAdParentPod` (광고가 재생되는 기본 콘텐트 내의 창 또는 광고 나누기)
* `mediaAdParentPodPos` (광고가 재생되는 창 내의 숫자 위치입니다. 둘 이상의 광고가 창 내에서 재생할 수 있습니다.

>[!MORE_ like_ this]
>
>* [Appmeasurement Flash, Flex 및 OSMF 구현 안내서](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

[!UICONTROL Flash DIL] 모듈은 Adobe appmeasurement 데이터를 Audience Manager 트레이트나 사용하지 않은 신호로 변환합니다.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. 트레이트는 키-값 쌍으로서 세그먼트를 작성하는 데 사용됩니다. For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**Audience Manager 트레이트를 Analytics 변수에 일치**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

예를 보려면 표를 참조하십시오.

| Analytics 데이터 요소 | Analytics 예제 | Adobe Audience Manager 트레이트 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **Evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**DIL/Analytics 데이터를 사용하지 않은 신호로 분석**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library.

>[!MORE_ like_ this]
>
>* [트레이트](../features/traits/trait-details-page.md)
>* [신호, 트레이트 및 세그먼트](../reference/signal-trait-segment.md)
>* [키-값 쌍을 설명했습니다.](../reference/key-value-pairs-explained.md)
>* [주요 변수의 접두사 요구 사항](../features/traits/trait-variable-prefixes.md)


## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code for your [!DNL Flash] object to send Analytics data to Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only.
   >
   >
* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

