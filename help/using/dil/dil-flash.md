---
description: FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보로 작업합니다.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>2023년 7월부터 Adobe은 [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장 개발을 중단했습니다.
>
>기존 고객은 [!DNL DIL] 구현을 계속 사용할 수 있습니다. 그러나 Adobe은 이 시점 이후에는 [!DNL DIL]을(를) 개발하지 않습니다. 고객은 장기 데이터 수집 전략에 대해 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)을(를) 평가하는 것이 좋습니다.
>
>2023년 7월 이후에 새로운 데이터 수집 통합을 구현하려는 고객은 대신 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)을 사용해야 합니다.

FLA 파일에서 Analytics로 전송된 데이터를 수집하고 Audience Manager에서 해당 정보로 작업합니다.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL]은(는) Audience Manager에서 비디오 재생 데이터를 사용할 수 있는 [!DNL ActionScript] 코드 라이브러리입니다. [!DNL Flash DIL]은(는) Adobe [!UICONTROL AppMeasurement] 라이브러리가 Analytics에 전달하는 SWF 콘텐츠를 캡처하여 작동합니다. [!DNL Flash DIL]에서 해당 데이터를 별도의 [!UICONTROL DIL] JavaScript 데이터 수집 모듈로 전송하여 해당 정보를 Audience Manager에 전달합니다. [!UICONTROL Props] 파일에서 캡처된 분석 데이터([!UICONTROL eVars], [!DNL FLA], 이벤트 등)는 트레이트 또는 사용되지 않은 신호로 Audience Manager에서 사용할 수 있습니다.

## Flash DIL 데이터 수집 요구 사항 {#requirements}

일반 구현 및 코드 관련 요구 사항.

<!-- 

c_flash_dil_intro.xml

 -->

**구현 요구 사항**

[!UICONTROL Flash] 데이터 수집에는 다음이 필요합니다.

* [!UICONTROL DIL] 클래스 라이브러리(`dil.swc`)입니다. 파트너 솔루션 연락처에서 [!UICONTROL DIL] 클래스 라이브러리를 가져옵니다.

* JavaScript의 [!UICONTROL DIL] 데이터 수집 코드.
* 데이터를 수집하려는 Flash 개체에 [DIL ActionScript 라이브러리](../dil/dil-flash.md#flash-dil-actionscript)가 로드되었습니다.
* Adobe [!DNL AppMeasurement] [!DNL AS] 라이브러리(버전 3.5.2 이상)에서 데이터를 수집하려는 [!DNL Flash] 개체를 로드했습니다.

**AllowScriptAccess를 `Always` 또는`sameDomain`**(으)로 설정

SWF 파일을 로드하는 HTML 코드의 `AllowScriptAccess`은(는) SWF 파일 내에서 아웃바운드 URL 액세스를 수행하는 기능을 제어합니다. [!UICONTROL Flash DIL] 데이터 통합을 구성할 때 Flash `AllowScriptAccess` 매개 변수가 `always` 또는 `sameDomain`(으)로 설정되어 있는지 확인하십시오. [!UICONTROL Flash DIL]이(가) `AllowScriptAccess`(으)로 설정되어 있으면 `never` 데이터 수집이 작동하지 않습니다. [스크립트 또는 호스트 웹 페이지에 대한 액세스 제어](https://helpx.adobe.com/kr/flash/kb/control-access-scripts-host-web.html)를 참조하십시오.

**JS [!UICONTROL DIL] 코드 배치**

[!UICONTROL DIL] 파일 앞에 로드되도록 JS [!DNL FLA] 데이터 수집 모듈을 페이지에 배치해 보십시오. [!DNL FLA] 파일이 처음 로드되면 [!UICONTROL DIL] 데이터 수집이 준비되기 전에 [!UICONTROL Flash DIL]에서 해당 모듈로 보내는 초기 데이터 신호를 놓칠 수 있습니다. 그러나 인스턴스화되면 [!UICONTROL DIL] 데이터 수집 모듈은 [!UICONTROL Flash DIL]에 의해 전달된 모든 후속 SWF 파일 데이터를 캡처합니다.

## Flash DIL에서 수집한 데이터 {#data-collected}

[!UICONTROL Flash DIL]은(는) Adobe [!UICONTROL AppMeasurement] 라이브러리에서 페이지 보기, 링크 추적, 미디어 추적 및 기타 미디어 보기 이벤트를 캡처합니다.

<!-- 

r_flash_dil_data_collected.xml

 -->

**이벤트 보기**

`s.trackVars`에서 별도로 지정하지 않는 한 [!UICONTROL Flash DIL]은(는) Adobe AppMeasurement에서 다음 데이터를 수집합니다.

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**링크 추적 이벤트**

`s.linkTrackVars`에서 별도로 지정하지 않는 한 [!UICONTROL Flash DIL]은(는) Adobe [!UICONTROL AppMeasurement]에서 다음 데이터를 수집합니다.

* `pe`(호출된 추적 링크 유형)
* `pev1`(링크 URL)
* `pev2`(링크 텍스트)

**미디어 추적 이벤트**

`s.Media.trackVars`에서 별도로 지정하지 않는 한 [!UICONTROL Flash DIL]은(는) 페이지 보기 이벤트 섹션에 열거된 모든 데이터를 수집합니다.

**기타 데이터 포인트**

기본적으로 다음 매개 변수의 데이터가 수집됩니다.

* `mediaName`(미디어/비디오 요소 이름)
* `mediaAdName`(광고 이름)
* `mediaAdParentName`(광고가 중첩된 기본 미디어 콘텐츠의 이름)
* `mediaAdParentPod`(광고가 재생되는 기본 콘텐츠 내의 pod 또는 광고 브레이크)
* `mediaAdParentPodPos`(Pod 내에서 광고가 재생되는 숫자 위치입니다. Pod 내에서 두 개 이상의 광고를 재생할 수 있습니다.

## Audience Manager의 Flash DIL 데이터 {#flash-dil-data}

[!UICONTROL Flash DIL] 모듈은 Adobe AppMeasurement 데이터를 Audience Manager 트레이트 및 사용되지 않는 신호로 바꿉니다.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] 및 이벤트는 Audience Manager의 트레이트처럼 작동합니다. 트레이트는 키-값 쌍으로, 세그먼트를 만드는 데 사용됩니다. 예를 들어 `c30=foo`과(와) 같은 Analytics prop에서 `c30`은(는) 키(상수)이고 `foo`은(는) 값(변수)입니다.

**Analytics 변수에 Audience Manager 트레이트 일치**

[!UICONTROL Flash DIL]에서 전달한 Analytics 데이터를 사용하려면 키 값에 `c_`이(가) 접두사로 추가된 Audience Manager 특성을 만들어야 합니다.

예제는 표를 참조하십시오.

| Analytics 데이터 요소 | Analytics 예 | As Audience Manager 트레이트 |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**사용되지 않는 신호로 DIL/Analytics 데이터**

Audience Manager은 해당 트레이트가 없어도 Analytics [!UICONTROL Props], [!UICONTROL eVars] 및 이벤트를 허용합니다. 이 경우 데이터는 트레이트 만들기에 사용할 수 없으며 대신 [사용되지 않은 신호 보고서](../reporting/dynamic-reports/unused-signals.md)에 표시됩니다. 이 정보를 최대한 활용하려면 [!UICONTROL Flash DIL] 라이브러리에서 전달된 Analytics 데이터와 일치하는 Audience Manager 특성을 만드십시오.

## Flash DIL ActionScript 라이브러리 {#flash-dil-actionscript}

Analytics 데이터를 Audience Manager으로 보내기 위한 [!DNL Flash] 개체의 코드입니다.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* 각 [!DNL Flash] 개체에 대해 이 코드는 하나의 파트너 인스턴스(`d.partner`)만 지원합니다.
>
>* Adobe [!UICONTROL AppMeasurement] [!DNL AS] 라이브러리 버전 3.5.2 이상이 필요합니다.

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
