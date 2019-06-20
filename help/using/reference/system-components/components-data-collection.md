---
description: 데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 서버 간 데이터 전송 및 로그 파일이 포함됩니다.
seo-description: 데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 서버 간 데이터 전송 및 로그 파일이 포함됩니다.
seo-title: 데이터 수집 구성 요소
solution: Audience Manager
title: 데이터 수집 구성 요소
uuid: 51 BB 1719-5 FF 2-4 BC 7-8 EB 1-98795 E 05 D 08 F
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

---


# Data Collection Components{#data-collection-components}

데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 서버 간 데이터 전송 및 로그 파일이 포함됩니다.

<!-- 

c_compcollect.xml

 -->

Audience Manager 에는 다음과 같은 데이터 수집 구성 요소가 포함되어 있습니다.

* [DCS (데이터 수집 서버) 및 PCS (프로파일 캐시 서버)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [DIL(데이터 통합 라이브러리)](../../reference/system-components/components-data-collection.md#dil)
* [인바운드 서버-서버](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [로그 파일](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

DCS와 PC는 함께 작동하여 특성 구현, 고객 세분화 및 데이터 스토리지와 관련된 서비스를 별도로 제공합니다.

**[!UICONTROL Data Collection Servers (DCS)]함수**

In [!DNL Audience Manager], the DCS:

* 이벤트 호출에서 트레이트 데이터를 받고 평가합니다. 여기에는 서버간 전송을 통해 예약된 간격으로 전달된 실시간 세그먼테이션 및 데이터에 사용되는 정보가 포함됩니다.
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* 장치 ID 및 인증된 프로필 ID를 만들고 관리합니다. 여기에는 데이터 공급자 ID, 사용자 ID, 선언된 ID, 통합 코드 등과 같은 식별자가 포함됩니다.
* PC에서 실시간 이벤트 호출 전에 이미 구현한 추가 트레이트가 있는지 확인합니다. 따라서 DCS는 실시간 데이터 및 내역 데이터를 기반으로 사용자를 정규화할 수 있습니다.
* 로그 파일을 작성하고 저장 및 처리를 위해 Analytics 시스템에 전송합니다.

**[!UICONTROL DCS]수요를[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!UICONTROL DCS] is a geographically distributed and load-balanced system. This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!UICONTROL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] 관련 데이터가 사용자에게 가장 가까운 서버에 캐시되므로 시스템 효율성이 높아집니다.

>[!IMPORTANT]
>
>The [!UICONTROL DCS] only detects web traffic originating from devices that use IPv4.

이벤트 호출에서 지리적 위치는 더 큰 JSON 데이터 본문에 반환되는 키-값 쌍에 캡처됩니다. This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!UICONTROL DCS] indirectly through our data collection code. You can also work directly with the [!UICONTROL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] 데이터는 장치 ID, 인증된 프로필 ID 및 관련 트레이트로 구성됩니다. When the [!UICONTROL DCS] receives a real time call, it checks the [!UICONTROL PCS] for other traits a user may belong to or qualify for. And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. The [!UICONTROL PCS] helps deepen [!DNL Audience Manager]&#39;s understanding of your users because it can match and segment users in real time or behind the scenes with new and historic trait data. 이러한 행동은 실시간 자격 조건에 비해 사용자를 보다 완전하고 정확하게 파악할 수 있습니다.

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. The [!UICONTROL PCS] runs on Apache Cassandra.

**비활성 ID 제거[!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] 호출
* [!DNL /ibs] 호출 (ID 동기화)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

The [!UICONTROL PCS] flushes traits if they&#39;re inactive for 17-days. 그러나 이러한 특징은 손실되지 않습니다. Hadoop에 저장됩니다. If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**기타[!UICONTROL DCS/PCS]프로세스: 개인 정보 옵트아웃**

이러한 서버 시스템은 개인 정보 및 사용자 옵트아웃 요청을 처리합니다. 사용자가 데이터 수집을 그만둔 경우 사용자 쿠키 정보가 로그 파일에서 수집되지 않습니다. For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## DIL(데이터 통합 라이브러리) {#dil}

[!UICONTROL DIL] 는 데이터 수집을 위해 페이지에 배치하는 코드입니다. See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

클라이언트와 서버 간 다양한 통합을 통해 전송된 데이터를 수신하는 시스템입니다. See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## Log Files {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. 이러한 파일은 처리, 보고 및 저장을 위해 다른 데이터베이스 시스템으로 전송됩니다.

>[!MORE_ like_ this]
>
>* [Adobe 개인 정보 보호 센터](https://www.adobe.com/privacy.html)

