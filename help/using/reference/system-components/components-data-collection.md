---
description: 데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 인바운드 서버 간 데이터 전송 및 로그 파일이 포함됩니다.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: 데이터 수집 구성 요소
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 6%

---

# 데이터 수집 구성 요소{#data-collection-components}

데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 인바운드 서버 간 데이터 전송 및 로그 파일이 포함됩니다.

<!-- 

c_compcollect.xml

 -->

Audience Manager에는 다음 데이터 수집 구성 요소가 포함되어 있습니다.

* [DCS(데이터 수집 서버) 및 PCS(프로필 캐시 서버)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [DIL(데이터 통합 라이브러리)](../../reference/system-components/components-data-collection.md#dil)
* [인바운드 서버 간](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [로그 파일](../../reference/system-components/components-data-collection.md#log-files)

## DCS(데이터 수집 서버) 및 PCS(프로필 캐시 서버) {#dcs-pcs}

DCS와 PCS는 함께 작동하며 트레이트 실현, 대상자 세분화 및 데이터 저장과 관련된 서비스를 별도로 제공합니다.

**[!UICONTROL Data Collection Servers (DCS)]함수로 플러그인 호출**

위치 [!DNL Audience Manager], DCS:

* 이벤트 호출에서 트레이트 데이터를 수신하고 평가합니다. 여기에는 실시간 세분화에 사용되는 정보와 서버 간 전송에 의해 예약된 간격으로 전달되는 데이터가 포함됩니다.
* 실현된 트레이트 및 사용자가 만든 자격 규칙에 따라 사용자를 세그먼트화합니다 [세그먼트 빌더](../../features/segments/segment-builder.md).
* 장치 ID 및 인증된 프로필 ID를 만들고 관리합니다. 여기에는 데이터 공급자 ID, 사용자 ID, 선언된 ID, 통합 코드 등과 같은 식별자가 포함됩니다.
* PCS에서 실시간 이벤트 호출 전에 사용자가 이미 실현한 추가 트레이트를 확인합니다. 이렇게 하면 DCS가 실시간 데이터 및 내역 데이터를 기반으로 사용자를 평가할 수 있습니다.
* 로그 파일을 작성하여 저장 및 처리를 위해 분석 시스템으로 전송합니다.

**[!DNL DCS]다음을 통해 수요 관리[!UICONTROL Global Server Load Balancing (GSLB)]**

다음 [!DNL DCS] 는 지리적으로 분산된 부하 분산 시스템입니다. 이것은 다음을 의미합니다. [!DNL Audience Manager] 은 사이트 방문자의 지리적 위치에 따라 지역 데이터 센터에 대한 요청을 지시할 수 있습니다. 이 전략은 다음과 같은 이유로 응답 시간을 개선하는 데 도움이 됩니다. [!DNL DCS] 응답은 해당 방문자에 대한 정보가 포함된 데이터 센터로 직접 이동합니다. [!UICONTROL GSLB] 관련 데이터가 사용자와 가장 가까운 서버에 캐시되므로 시스템을 효율적으로 사용할 수 있습니다.

>[!IMPORTANT]
>
>다음 [!DNL DCS] 는 IPv4를 사용하는 장치에서 발생하는 웹 트래픽만 감지합니다.

이벤트 호출에서 지리적 위치는 JSON 데이터의 더 큰 본문에 반환된 키-값 쌍으로 캡처됩니다. 이 키-값 쌍은 `"dcs_region": region ID` 매개 변수.

![](assets/dcs-map.png)

고객인 경우 다음과 같은 작업을 수행합니다 [!DNL DCS] 데이터 수집 코드를 통해 간접적으로 을 사용하여 직접 작업할 수도 있습니다. [!DNL DCS] API 세트를 통해 다음을 참조하십시오 [DCS(데이터 수집 서버) API 메서드 및 코드](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

다음 [!UICONTROL PCS] 는 큰 데이터베이스(기본적으로 큰 서버측 쿠키)입니다. 서버 간 전송 및 [!DNL DCS]에서 활성 사용자에 대해 받은 데이터를 저장합니다. [!UICONTROL PCS] 데이터는 장치 ID, 인증된 프로필 ID 및 연결된 트레이트로 구성됩니다. 다음의 경우 [!DNL DCS] 실시간 호출을 받으면 [!UICONTROL PCS] 다른 트레이트의 경우 사용자가 속하거나 자격이 있을 수 있습니다. 그리고 나중에 트레이트가 세그먼트에 추가되면 해당 트레이트 ID가 [!UICONTROL PCS] 또한 사용자는 특정 사이트 또는 앱을 방문하지 않고도 해당 세그먼트를 자동으로 사용할 수 있습니다. 다음 [!UICONTROL PCS] 심화하도록 지원 [!DNL Audience Manager]는 새 트레이트 데이터와 기록 트레이트 데이터를 실시간으로 또는 백그라운드에서 사용자를 일치시키고 세그먼트화할 수 있으므로 사용자를 이해할 수 있습니다. 이 비헤이비어는 실시간 자격으로만 보는 것보다 더 완벽하고 정확한 사용자 사진을 제공합니다.

고객이 로 직접 작업할 수 있도록 하는 UI 컨트롤은 없습니다. [!UICONTROL PCS]. 에 대한 고객 액세스 권한 [!UICONTROL PCS] 는 데이터 저장소 및 데이터 전송으로서의 역할을 통해 간접적으로 수행됩니다. 다음 [!UICONTROL PCS] 는 Apache Cassandra에서 실행됩니다.

**에서 비활성 ID 삭제[!UICONTROL PCS]**

앞에서 설명한 대로 [!UICONTROL PCS] 활성 사용자의 트레이트 ID를 저장합니다. 활성 사용자는에서 본 모든 사용자입니다. [에지 데이터 서버](../../reference/system-components/components-edge.md) 지난 14일 동안 모든 도메인에서 다음 호출은 [!UICONTROL PCS] 사용자를 활성 상태로 유지합니다.

* [!DNL /event] 호출
* [!DNL /ibs] 호출(ID 동기화)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

다음 [!UICONTROL PCS] 17일 동안 비활성 상태인 경우 트레이트를 플러시합니다. 그러나 이러한 트레이트는 손실되지 않습니다. hadoop에 저장되어 있습니다. 사용자가 다른 시간에 다시 표시되면 Hadoop은 모든 트레이트를 로 다시 푸시합니다 [!UICONTROL PCS], 일반적으로 24시간 이내.

**기타 [!UICONTROL DCS/PCS] 프로세스: 개인 정보 옵트아웃**

이러한 서버 시스템은 개인 정보 및 사용자 옵트아웃 요청을 처리합니다. 사용자가 데이터 수집을 옵트아웃한 경우 사용자 쿠키 정보가 로그 파일에 수집되지 않습니다. 개인정보 처리방침에 대한 자세한 내용은 [Adobe 개인 정보 보호 센터](https://www.adobe.com/kr/privacy/advertising-services.html).

## DIL(데이터 통합 라이브러리) {#dil}

[!UICONTROL DIL] 는 데이터 수집을 위해 페이지에 배치하는 코드입니다. 다음을 참조하십시오. [DIL API](../../dil/dil-overview.md) 사용 가능한 서비스 및 방법에 대한 자세한 내용을 참조하십시오.

## 인바운드 서버 간 {#inbound-outbound-server}

이러한 시스템은 클라이언트와 다양한 서버 간 통합으로 전송되는 데이터를 수신합니다. 다음에서 설명서를 참조하십시오. [대상 데이터 보내기](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) 추가 정보.

## 로그 파일 {#log-files}

다음 [!UICONTROL PCS] 로그 파일에 데이터를 작성 및 기록합니다. 이러한 파일은 처리, 보고 및 저장을 위해 다른 데이터베이스 시스템으로 전송됩니다.

>[!MORELIKETHIS]
>
>* [Adobe 개인 정보 보호 센터](https://www.adobe.com/kr/privacy.html)

