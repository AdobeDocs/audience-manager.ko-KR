---
description: 일반적인 데이터 수집 및 통합 질문 및 문제
seo-description: 일반적인 데이터 수집 및 통합 질문 및 문제
seo-title: 데이터 수집 및 제품 통합 FAQ
solution: Audience Manager
title: 데이터 수집 및 제품 통합 FAQ
uuid: fa 8 e 79 f 4-99 cb -41 fd -8 a 85-d 4 f 92 d 03 c 7 a 5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

일반적인 데이터 수집 및 통합 질문 및 문제

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**로그 파일의 트래픽에서[!UICONTROL DCS]인바운드 트래픽을 구별할 수 있는[!UICONTROL DCS]방법은 무엇입니까?**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* 원격 IP는 68.67.173.18로 설정됩니다.
* Domainid는 5325로 설정됩니다.
* 영역이 0로 설정됩니다.

<br> 

**dpm. demdex. net에 대한 허용 목록을 만들 수 있는 IP 주소 목록을 제공해 주실 수 있습니까?**

안타깝지만 불가능합니다. These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**인바운드 및 아웃바운드 FTP 서버에 대한 화이트리스트에 사용할 수 있는 IP 주소를 제공할 수 있습니까?**

예. 아래를 참조하십시오.

| 항목 | 주소 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**A[!UICONTROL DIL]/[!DNL Analytics]데이터 통합에 대한 코드 배치 및 페이지 로드 요구 사항은 무엇입니까?**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. 예를 들어, 코드를 배치하거나 이 순서대로 로드하는지 확인합니다.

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] 모듈

3. [!DNL Analytics] `s.t()` 함수 위에 있어야 합니다

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**변수가[!DNL Analytics][!DNL Audience Manager]이벤트 호출에 누락되는 이유는 무엇입니까?**

일반적으로 다음과 같은 경우에 나타납니다.

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* The `s.t()` function loads before [!UICONTROL DIL].

<br> 

**사용 가능한[!DNL Analytics]작업[!UICONTROL DIL]버전**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. [!DNL Analytics] 또는 [!DNL AppMeasurement] 버전을 모르는 경우 페이지에서 만든 [!DNL Analytics] 호출을 확인합니다. 버전 정보는 아래와 같습니다.

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**고객이 아닌 경우 페이지 데이터를 수집할[!DNL Analytics]수 있습니까?**

예. The [!UICONTROL DIL] module helps you collect page data even if you&#39;re not using [!DNL Analytics]. When set up properly, [!UICONTROL DIL] can capture data from and about:

* meta 태그
* URL 및 URL 헤더
* 검색 엔진 유형
* 키워드

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**데이터를[!UICONTROL DIL]수집할[!DNL Google Analytics]수 있습니까?**

예. [!UICONTROL DIL] 일부 [!DNL Google Analytics] (GA) 요소를 수집하고 해당 데이터를 전달할 [!DNL Audience Manager]수 있습니다. 다음을 참조하십시오.

* [ga. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [ga. init](../dil/dil-modules.md#ga-init)

<br> 

**원시 데이터를[!DNL Audience Manager]가져올 수 있습니까?**

Yes, [!DNL Audience Manager] can provide you with data collected for users we&#39;ve seen on your inventory. 여기에는 다음 항목이 포함되어 있습니다.

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* 특성 및 세그먼트 ID
* 사용하지 않은 신호
* 타임스탬프
* 페이지 URL

<br> 

**한 사이트에서 데이터를 수집하고 다른 사이트에서 DFP를 통해 사용자를 타깃팅하려고 합니다. Do I need to deploy code on the other property if I don&#39;t want to collect data from that location?**

아니요. 두 번째 사이트의 데이터 수집이 요구 사항이 아닐 경우, DIL를 거기에 배포하지 않아도 됩니다. DFP를 통해 두 번째 사이트의 인벤토리에 액세스할 수 있는 경우 초기 사이트 및 DFP를 통해 Target의 데이터 수집을 사용할 수 있습니다.

<br> 

**타사 데이터 제공업체란 무엇입니까?**

각 제공업체는 표에 고유한 것을 가져올 수 있으므로 원하는 사항에 따라 답변이 달라집니다. Adobe는 사용자에게 가장 적합한 공급자를 이해하는 데 도움이 되도록 오버랩 보고를 활성화할 수 있습니다.

<br> 

**쿠키를[!DNL Audience Manager]설정하고 DFP에 변수를 전달하는 방법은?**

[!DNL Audience Manager] 2 개의 쿠키 설정: 하나는 DFP 광고 태그에 세그먼트 변수를 보내고 다른 하나는 DFP가 읽는 고유한 사용자 ID (UUID) 를 설정합니다. 광고 태그에 UUID를 추가하면 사용자 수준의 보고 및 고객 검색을 수행할 수 있습니다.

<br> 

**사용자가 도달한 전환 단계의 포인트에 대한 DSP 정보를 보낼 수 있습니까?**

예. 우리는 단계 데이터를 전송할 수 있지만, DSP 에는 이것을 사용할 기술적인 기능이 있어야 한다. DSP는 여러 세그먼트를 처리할 수 있음을 확인해야 합니다. 그렇지 않을 경우, 특정 세그먼트를 만들어 사용자를 다른 세그먼트에서 끌어낼 수 있습니다 (예: 전환 진행 상황 (예: 단계 1와 2 완료, 3 단계 아님). 사용자를 다시 타깃팅하거나 특정 랜딩 페이지로 안내하거나 특정 크리에이티브를 표시할 수 있도록 이 정보를 DSP로 전송할 수 있습니다.

<br> 

**FTP를 통해 전송된 데이터를 어디에서 선택했는지 확인할 수[!DNL Audience Manager]있습니까?**

A file has been picked up when the extension changes from `.sync` to `.processed`. 이 경우 파일이 통합 큐에 있습니다. 또한 계정 관리자가 파일이 업로드되었는지 확인할 수 있습니다.

<br> 

**[DCS API의 기능을](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)테스트하려고 합니다. 아래에 표시된 것과 같은 이벤트 호출을 보냅니다. The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

보고서는 보고서를 생성할 때 백엔드에 표시되는 인증되지 않은 프로필 레코드 (UUID) 를 기반으로 모집단을 계산합니다.

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>생성된 UUID는 쿠키가 설정된 장치가 추가 활동을 트리거할 때 백엔드 데이터 저장소에서만 구체화된 것입니다.

이러한 이유로 보고서는 호출에서 선언된 ID로 트리거된 이벤트를 반영하지 않습니다. We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**사용자 프로필은[여러 지역에 걸쳐 동기화되는 데 얼마나 걸립니까](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

일반적으로 사용자 프로필은 지역 간에 동기화하는 데 최대 24 시간이 걸립니다. 하지만 드문 경우 프로세스는 최대 48 시간이 걸릴 수 있습니다.
