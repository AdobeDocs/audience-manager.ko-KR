---
description: 데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 인바운드 서버 간 데이터 전송 및 로그 파일이 포함됩니다.
seo-description: 데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 인바운드 서버 간 데이터 전송 및 로그 파일이 포함됩니다.
seo-title: 데이터 수집 구성 요소
solution: Audience Manager
title: 데이터 수집 구성 요소
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 6%

---


# 데이터 수집 구성 요소{#data-collection-components}

데이터 수집 구성 요소에는 데이터 수집 서버, DIL API, 인바운드 서버 간 데이터 전송 및 로그 파일이 포함됩니다.

<!-- 

c_compcollect.xml

 -->

Audience Manager에는 다음과 같은 데이터 수집 구성 요소가 포함되어 있습니다.

* [데이터 수집 서버(DCS) 및 프로필 캐시 서버(PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [DIL(데이터 통합 라이브러리)](../../reference/system-components/components-data-collection.md#dil)
* [인바운드 서버-서버](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [로그 파일](../../reference/system-components/components-data-collection.md#log-files)

## 데이터 수집 서버(DCS) 및 프로필 캐시 서버(PCS) {#dcs-pcs}

DCS와 PCS는 서로 연동되며 특성 구현, 고객 세분화 및 데이터 스토리지와 관련된 서비스를 별도로 제공합니다.

**[!UICONTROL Data Collection Servers (DCS)]함수로 플러그인 호출**

[!DNL Audience Manager]에서 DCS:

* 이벤트 호출에서 특성 데이터를 수신하고 평가합니다. 여기에는 실시간 세그멘테이션에 사용되는 정보와 서버간 전송으로 예약된 간격으로 전달된 데이터가 포함됩니다.
* 구현된 트레이트 및 [세그먼트 빌더](../../features/segments/segment-builder.md)로 만든 자격 규칙을 기준으로 사용자를 세그먼트화합니다.
* 장치 ID 및 인증된 프로필 ID를 만들고 관리합니다. 여기에는 데이터 공급자 ID, 사용자 ID, 선언된 ID, 통합 코드 등과 같은 식별자가 포함됩니다.
* 실시간 이벤트 호출 전에 사용자가 이미 인식한 추가 트레이트가 있는지 PCS에서 확인합니다. 이를 통해 DCS는 실시간 데이터 및 내역 데이터를 기반으로 사용자를 평가할 수 있습니다.
* 로그 파일을 작성하고 저장 및 처리를 위해 분석 시스템으로 전송합니다.

**[!DNL DCS]수요 관리[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS]은 지리적으로 분산된 부하 균형 조정 시스템입니다. 즉, [!DNL Audience Manager]은 사이트 방문자의 지리적 위치를 기준으로 지역 데이터 센터에 대한 요청을 주고 받을 수 있습니다. 이 전략은 [!DNL DCS] 응답이 해당 방문자에 대한 정보가 포함된 데이터 센터로 바로 이동하므로 응답 시간을 개선하는 데 도움이 됩니다. [!UICONTROL GSLB] 관련된 데이터가 사용자에게 가장 가까운 서버에서 캐시되므로 Adobe의 시스템을 효율적으로 만듭니다.

>[!IMPORTANT]
>
>[!DNL DCS]은 IPv4를 사용하는 장치에서 발생하는 웹 트래픽만 감지합니다.

이벤트 호출에서 지리적 위치는 더 큰 JSON 데이터 본문에 반환되는 키-값 쌍에서 캡처됩니다. 이 키-값 쌍은 `"dcs_region": region ID` 매개 변수입니다.

![](assets/dcs-map.png)

고객은 Adobe의 데이터 수집 코드를 통해 간접적으로 [!DNL DCS]과(와) 교류합니다. API 세트를 통해 [!DNL DCS]과 직접 작업할 수도 있습니다. [DCS(데이터 수집 서버) API 메서드 및 코드](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)를 참조하십시오.

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS]은 큰 데이터베이스(기본적으로 거대한 서버측 쿠키)입니다. 서버 간 전송 및 [!DNL DCS]에서 활성 사용자에 대해 받은 데이터를 저장합니다. [!UICONTROL PCS] 데이터는 장치 ID, 인증된 프로필 ID 및 연결된 트레이트로 구성됩니다. [!DNL DCS]이(가) 실시간 호출을 받으면 사용자가 속해 있거나 자격이 되는 다른 트레이트가 있는지 [!UICONTROL PCS]에서 확인합니다. 또한 트레이트가 나중에 세그먼트에 추가되는 경우 해당 트레이트 ID가 [!UICONTROL PCS]에 추가되고 사용자는 특정 사이트나 앱을 방문하지 않고도 자동으로 해당 세그먼트에 자격을 부여할 수 있습니다. [!UICONTROL PCS]은(는) 새롭고 역사적인 트레이트 데이터를 사용하여 실시간 또는 백그라운드에서 사용자를 일치시키거나 세그먼트화할 수 있으므로 사용자에 대한 [!DNL Audience Manager]의 이해를 더욱 깊게 하는 데 도움이 됩니다. 이러한 행동은 실시간 자격 조건에서보다 사용자의 상황을 더 완전하고 정확하게 파악할 수 있도록 해줍니다.

고객이 [!UICONTROL PCS]에서 직접 작업할 수 있는 UI 컨트롤이 없습니다. [!UICONTROL PCS]에 대한 고객 액세스는 데이터 저장소 및 데이터 전송의 역할을 통해 간접적입니다. [!UICONTROL PCS]은 Apache Cassandra에서 실행됩니다.

**비활성 ID를[!UICONTROL PCS]**

이전에 설명한 바와 같이 [!UICONTROL PCS]은 활성 사용자의 특성 ID를 저장합니다. 활성 사용자는 지난 14일 동안 도메인에서 [edge 데이터 서버](../../reference/system-components/components-edge.md)에 의해 본 모든 사용자입니다. [!UICONTROL PCS]에 대한 이러한 호출은 사용자를 활성 상태로 유지합니다.

* [!DNL /event] 호출
* [!DNL /ibs] 호출(ID 동기화)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

17일 동안 비활성 상태인 경우 [!UICONTROL PCS] 트레이트가 플러시됩니다. 그러나 이러한 특성들은 그대로 유지됩니다. hadoop에 보관되어 있습니다. 사용자가 다른 시간에 다시 표시되는 경우, Hadoop은 모든 특성을 [!UICONTROL PCS]으로 다시 푸시합니다(일반적으로 24시간 이내).

**기타  [!UICONTROL DCS/PCS] 프로세스:개인 정보 옵트아웃**

이러한 서버 시스템은 개인 정보 및 사용자 옵트아웃 요청을 처리합니다. 사용자가 데이터 수집을 옵트아웃한 경우 사용자 쿠키 정보는 로그 파일에 수집되지 않습니다. 개인정보 보호 정책에 대한 자세한 내용은 [Adobe 개인 정보 보호 센터](https://www.adobe.com/kr/privacy/advertising-services.html)를 참조하십시오.

## DIL(데이터 통합 라이브러리) {#dil}

[!UICONTROL DIL] 은 데이터 수집을 위해 페이지에 배치하는 코드입니다. 사용 가능한 서비스 및 방법에 대한 자세한 내용은 [DIL API](../../dil/dil-overview.md)를 참조하십시오.

## 인바운드 서버-서버 {#inbound-outbound-server}

이러한 시스템은 Adobe 고객과의 다양한 서버 간 통합으로 전송된 데이터를 수신하는 시스템입니다. 자세한 내용은 [대상 데이터 전송](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md)에 대한 설명서를 참조하십시오.

## 로그 파일 {#log-files}

[!UICONTROL PCS]은 로그 파일에 데이터를 만들고 기록합니다. 처리, 보고 및 저장을 위해 다른 데이터베이스 시스템으로 전송됩니다.

>[!MORELIKETHIS]
>
>* [Adobe 개인 정보 보호 센터](https://www.adobe.com/kr/privacy.html)

