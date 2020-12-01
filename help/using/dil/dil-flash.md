---
description: FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보를 사용하여 작업할 수 있습니다.
seo-description: FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보를 사용하여 작업할 수 있습니다.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---


# Flash DIL{#flash-dil}

FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보를 사용하여 작업할 수 있습니다.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] 는 Audience Manager에서 비디오 재생 데이터를 사용하여 작업할 수 있는  [!DNL ActionScript] 코드 라이브러리입니다. [!DNL Flash DIL] adobe  [!UICONTROL AppMeasurement] 라이브러리가 Analytics에 전달하는 SWF 컨텐츠를 캡처하여 작동합니다. [!DNL Flash DIL] 이 데이터를 별도의  [!UICONTROL DIL] JavaScript 데이터 수집 모듈로 보내 Audience Manager으로 전달합니다. 분석 데이터( [!UICONTROL Props], [!UICONTROL eVars], 이벤트 등) [!DNL FLA] 파일에서 캡처한 이미지는 트레이트 또는 미사용 신호로 Audience Manager에서 사용할 수 있습니다.

## Flash DIL 데이터 수집 요구 사항 {#requirements}

일반적인 구현 및 코드 관련 요구 사항.

<!-- 

c_flash_dil_intro.xml

 -->

**구현 요구 사항**

[!UICONTROL Flash] 데이터 수집에는 다음이 필요합니다.

* [!UICONTROL DIL] 클래스 라이브러리( `dil.swc`). 파트너 솔루션 연락처에서 [!UICONTROL DIL] 클래스 라이브러리를 가져옵니다.

* 페이지의 JavaScript [!UICONTROL DIL] 데이터 수집 코드.
* [데이터를 수집할 Flash 개체에 DIL ActionScript ](../dil/dil-flash.md#flash-dil-actionscript) 라이브러리가 로드되었습니다.
* Adobe [!DNL AppMeasurement] [!DNL AS] 라이브러리(버전 3.5.2 이상)가 데이터를 수집할 [!DNL Flash] 개체를 로드했습니다.

**AllowScriptAccess를  `Always` 또는`sameDomain`**

SWF 파일을 로드하는 HTML 코드의 `AllowScriptAccess`은 SWF 파일 내에서 아웃바운드 URL 액세스를 수행하는 기능을 제어합니다. [!UICONTROL Flash DIL] 데이터 통합을 구성할 때 Flash `AllowScriptAccess` 매개 변수가 `always` 또는 `sameDomain`으로 설정되어 있는지 확인하십시오. [!UICONTROL Flash DIL] 데이터 수집은 로 설정된 경우  `AllowScriptAccess` 작동하지 않습니다 `never`. [스크립트 또는 호스트 웹 페이지에 대한 액세스 제어](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)를 참조하십시오.

**JS  [!UICONTROL DIL] 코드 배치**

JS [!UICONTROL DIL] 데이터 수집 모듈을 페이지에 배치하여 [!DNL FLA] 파일 전에 로드하도록 합니다. [!DNL FLA] 파일이 먼저 로드되면 [!UICONTROL DIL] 데이터 수집이 준비되기 전에 [!UICONTROL Flash DIL]가 해당 모듈로 보내는 초기 데이터 신호를 놓칠 수 있습니다. 그러나 일단 인스턴스화되면 [!UICONTROL DIL] 데이터 수집 모듈은 [!UICONTROL Flash DIL]에 의해 전달된 모든 후속 SWF 파일 데이터를 캡처합니다.

## Flash DIL {#data-collected}에 의해 수집된 데이터

[!UICONTROL Flash DIL] adobe  [!UICONTROL AppMeasurement] 라이브러리에서 페이지 보기, 링크 추적, 미디어 추적 및 기타 미디어 보기 이벤트를 캡처합니다.

<!-- 

r_flash_dil_data_collected.xml

 -->

**페이지 보기 이벤트**

`s.trackVars`에서 별도로 지정하지 않는 한, [!UICONTROL Flash DIL]은 Adobe AppMeasurement에서 다음 데이터를 수집합니다.

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**링크 추적 이벤트**

`s.linkTrackVars`에서 별도로 지정하지 않는 한 [!UICONTROL Flash DIL]은 Adobe [!UICONTROL AppMeasurement]에서 다음 데이터를 수집합니다.

* `pe` (추적 링크 유형 호출)
* `pev1` (링크 URL)
* `pev2`(링크 텍스트)

**미디어 추적 이벤트**

`s.Media.trackVars`에서 달리 지정하지 않는 한 [!UICONTROL Flash DIL]은 페이지 보기 이벤트 섹션에 열거된 모든 데이터를 수집합니다.

**기타 데이터 포인트**

이러한 매개 변수의 데이터는 기본적으로 수집됩니다.

* `mediaName` (미디어/비디오 요소 이름)
* `mediaAdName` (광고 이름)
* `mediaAdParentName` (광고가 중첩된 기본 미디어 컨텐츠의 이름)
* `mediaAdParentPod` (광고가 재생되는 기본 컨텐츠 내의 창 또는 광고 중단)
* `mediaAdParentPodPos` (광고가 재생되는 창 내의 숫자 위치입니다. 둘 이상의 광고가 창 내에서 재생할 수 있습니다.

## Audience Manager {#flash-dil-data}의 Flash DIL 데이터

[!UICONTROL Flash DIL] 모듈은 Adobe AppMeasurement 데이터를 Audience Manager 트레이트 및 사용되지 않은 신호로 바꿉니다.

<!-- 

c_flash_dil_in_aam.xml

 -->

분석 [!UICONTROL Props], [!UICONTROL eVars] 및 이벤트는 Audience Manager의 트레이트처럼 작동합니다. 트레이트는 키-값 쌍이며 세그먼트를 만드는 데 사용됩니다. 예를 들어 `c30=foo` 같은 Analytics prop에서 `c30`은 키(상수)이고 `foo`은 값(변수)입니다.

**Audience Manager 트레이트를 분석 변수에 일치**

[!UICONTROL Flash DIL]에서 전달된 Analytics 데이터를 사용하려면 `c_`에 키 값이 접두사로 추가된 Audience Manager 트레이트를 만들어야 합니다.

예는 다음 표를 참조하십시오.

| 분석 데이터 요소 | 분석 예 | Audience Manager 특성 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**사용되지 않는 신호로 DIL/분석 데이터**

Audience Manager은 해당 특성 없이도 Analytics [!UICONTROL Props], [!UICONTROL eVars] 및 이벤트를 허용합니다. 이 경우 데이터는 트레이트 생성에 사용할 수 없으며 대신 [사용되지 않은 신호 보고서](../reporting/dynamic-reports/unused-signals.md)에 나타납니다. 이 정보를 최대한 활용하려면 [!UICONTROL Flash DIL] 라이브러리에서 전달한 Analytics 데이터와 일치하는 Audience Manager 트레이트를 만드십시오.

## Flash DIL 라이브러리 {#flash-dil-actionscript}

Analytics 데이터를 Audience Manager으로 보내는 [!DNL Flash] 개체의 코드입니다.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 각 [!DNL Flash] 개체에 대해 코드는 파트너 인스턴스 하나( `d.partner`)만 지원합니다.
   >
   >
* Adobe [!UICONTROL AppMeasurement] [!DNL AS] 라이브러리 버전 3.5.2 이상이 필요합니다.


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [트레이트](../features/traits/trait-details-page.md)
>* [신호, 트레이트 및 세그먼트](../reference/signal-trait-segment.md)
>* [키-값 쌍 설명](../reference/key-value-pairs-explained.md)
>* [주요 변수의 접두사 요구 사항](../features/traits/trait-variable-prefixes.md)

