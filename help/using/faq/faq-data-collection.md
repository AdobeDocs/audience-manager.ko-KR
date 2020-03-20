---
description: 일반적인 데이터 수집 및 통합 질문 및 문제
seo-description: 일반적인 데이터 수집 및 통합 질문 및 문제
seo-title: 데이터 수집 및 제품 통합 FAQ
solution: Audience Manager
title: 데이터 수집 및 제품 통합 FAQ
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: d221890d2a80cd557a6968d3382ee8842fea9aef

---


# 데이터 수집 및 제품 통합 FAQ{#data-collection-and-product-integration-faq}

일반적인 데이터 수집 및 통합 질문 및 문제

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**인바운드 트래픽과[!UICONTROL DCS]로그 파일 내보내기의[!UICONTROL DCS]트래픽을 구별하려면 어떻게 합니까?**

를 통해 생성된 트레이트는 [!UICONTROL Inbound] 에 의해 채워지는 [!UICONTROL Inbound] 것과 동일한 방식으로 채워집니다 [!UICONTROL DCS]. 트래픽이 [!UICONTROL Inbound]다음에서 비롯되었다고 알려주는 몇 가지 다른 방법이 있습니다.

* 원격 IP는 68.67.173.18로 설정됩니다.
* DomainID는 5325로 설정됩니다.
* 영역은 0으로 설정됩니다.

<br> 

**dpm.demdex.net에 대한 허용 목록을 제공할 수 있는 IP 주소 목록을 제공해 주시겠습니까?**

불행하게도, 우리는 할 수 없습니다. 이러한 IP는 지리적 영역에 따라, 를 통해 동적으로 할당됩니다 [!DNL Amazon Web Services]. 따라서 이 주소에 할당할 수 있는 IP의 범위를 제어하지 [!DNL Audience Manager] 않습니다.

<br> 

**인바운드 및 아웃바운드 sFTP 서버에 대해 허용 목록에 추가할 수 있는 IP 주소를 알려주시겠습니까?**

예, 아래를 참조하십시오.

| 항목 | 주소 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**데이터 통합을 위한 코드 배치 및 페이지 로드 요구 사항은[!UICONTROL DIL][!DNL Analytics]무엇입니까?**

데이터를 가져오려면 [!DNL Analytics] 모듈 [!DNL Audience Manager]뒤에 [!UICONTROL DIL] 함수 `s_code` 앞에 *로드하십시오* `s.t()` . 예를 들어 코드를 배치하거나 다음 순서로 로드해야 합니다.

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] 모듈 [!UICONTROL DIL]

3. [!DNL Analytics] `s.t()` 함수 위에 있어야 합니다

다음 두 가지 방법 중 하나를 사용하여 [!DNL Audience Manager][!DNL Analytics] 통합을 설정하는 것이 좋습니다.

* 직접 [!UICONTROL DIL] 작업 `s_code`진행

* 서비스를 [!UICONTROL DIL] 통해 또는 `s_code` 을 통해 제공할 [!DNL Adobe Experience Platform Launch] 수 [!DNL Adobe DTM]있습니다.

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**이벤트 호출에서 내[!DNL Analytics]변수가 누락된 이유는[!DNL Audience Manager]무엇입니까?**

이 문제는 일반적으로 다음과 같은 경우에 발생합니다.

* 페이지의 다른 코드 요소와 비동기식으로 로드되는 태그 관리 시스템을 [!UICONTROL DIL] 통해 제공됩니다.
* 이 `s.t()` 함수는 먼저 로드됩니다 [!UICONTROL DIL].

<br> 

**어떤 버전의[!DNL Analytics]작업을 사용하고[!UICONTROL DIL]있습니까?**

작업할 때는 [!DNL Analytics] 버전 20.2 이상 및 [!DNL Adobe AppMeasurement AS] 라이브러리 버전 3.5.2 이상을 사용해야 합니다 [!UICONTROL DIL]. 귀하의 [!DNL Analytics] 버전 또는 [!DNL AppMeasurement] 버전을 모르는 경우 페이지에서 [!DNL Analytics] 이루어지는 호출을 확인하십시오. 아래에 표시된 버전 정보:

이 고객은 [!DNL Analytics] 버전 24.4를 사용합니다.

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

이 고객은 [!DNL AppMeasurement] 버전 3.5.2를 사용합니다.

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**고객이 아닌 경우 페이지 데이터를 수집할 수[!DNL Analytics]있습니까?**

예. 이 [!UICONTROL DIL] 모듈은 사용하지 않는 경우에도 페이지 데이터를 수집하는 데 도움이 됩니다 [!DNL Analytics]. 제대로 설정되면, 다음 데이터를 캡처할 [!UICONTROL DIL] 수 있습니다.

* 메타 태그
* URL 및 URL 헤더
* 검색 엔진 유형
* 키워드

또한 클라이언트는 간단한 온사이트 객체를 배포하고 데이터를 수집할 키-값 쌍으로 채울 [!UICONTROL DIL] 수 있습니다. 이를 통해 [!DNL Audience Management] 업데이트 없이 사이트에서 특정 고객 데이터 포인트를 추가하고 제거할 수 있습니다. 파트너 솔루션 담당자와 협력하여 이 설정을 적절하게 설정하고 [!DNL DIL] 모듈이 페이지 개체를 올바르게 참조하는지 확인합니다.

<br> 

**데이터를[!UICONTROL DIL]수집할 수[!DNL Google Analytics]있습니까?**

예. [!UICONTROL DIL] 는 일부 [!DNL Google Analytics] (GA) 요소를 수집하고 해당 데이터를 [!DNL Audience Manager]전달할 수 있습니다. 다음을 참조하십시오.

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**원시 데이터를 가져올 수[!DNL Audience Manager]있으며 얼마나 세분화됩니까?**

예. Adobe [!DNL Audience Manager] 가 귀하의 인벤토리에서 본 사용자를 위해 수집한 데이터를 제공할 수 있습니다. 여기에는 다음 항목이 포함되어 있습니다.

* 에서 할당한 고유 사용자 ID(UUID) [!DNL Audience Manager]
* 트레이트 및 세그먼트 ID
* 사용하지 않은 신호
* 타임스탬프
* 페이지 URL

<br> 

**한 사이트에서 데이터를 수집하고 다른 사이트의 DFP를 통해 사용자를 타깃팅하고자 합니다. 해당 위치에서 데이터를 수집하지 않으려면 다른 속성에 코드를 배포해야 합니까?**

아니요. 두 번째 사이트의 데이터 수집이 요구 사항이 아닌 경우 DIL을 배포할 필요가 없습니다. DFP를 통해 두 번째 사이트의 인벤토리에 액세스할 수 있는 경우, 초기 사이트의 데이터 수집 및 DFP를 통해 타겟을 사용할 수 있습니다.

<br> 

**최고의 타사 데이터 제공업체는 무엇입니까?**

각 공급업체는 테이블에 고유한 요소를 가져오므로 원하는 내용에 따라 결과가 달라집니다. Adobe는 추가 비용 없이 중복 보고를 활성화하여 귀하에게 가장 적합한 공급자를 파악할 수 있도록 지원합니다.

<br> 

**쿠키를[!DNL Audience Manager]설정하고 변수를 DFP로 전달하는 방법은?**

[!DNL Audience Manager] 세트 2 쿠키:하나는 세그먼트 변수를 DFP 광고 태그로 전송하고 다른 하나는 DFP에서 읽는 고유한 사용자 ID(UUID)를 설정합니다. 광고 태그에 UUID를 추가하면 사용자 수준 보고 및 고객 검색을 수행할 수 있습니다.

<br> 

**사용자가 도달한 전환 단계의 포인트에 대한 DSP 정보를 전송할 수 있습니까?**

예. 깔때기 데이터를 전송할 수 있지만 DSP는 이 데이터를 사용할 수 있는 기술적 기능을 가지고 있어야 합니다. DSP는 여러 세그먼트를 처리할 수 있는지 확인해야 합니다. 이러한 세그먼트를 만들 수 없는 경우, 사용자를 전환 진행 상태(예: 3단계가 아닌 1단계 및 2단계)를 기준으로 다른 세그먼트에서 제외하기 위해 특정 세그먼트를 만들어야 할 수 있습니다. 사용자를 리타겟팅하거나 특정 랜딩 페이지로 안내하거나 특정 크리에이티브를 표시할 수 있도록 이 정보를 DSP로 보낼 수 있습니다.

<br> 

**FTP를 통해 전송된 데이터가 에 의해 선택되었는지 어떻게 확인할 수[!DNL Audience Manager]있습니까?**

확장자가 에서 로 변경되면 파일이 `.sync` 선택됩니다 `.processed`. 이 경우 파일이 통합 대기열에 있습니다. 또한 계정 관리자는 파일이 업로드된 시기를 확인할 수 있습니다.

<br> 

**DCS API의 기능을 테스트하고[싶습니다](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). 아래에 표시된 것과 같은 이벤트 호출을 보냅니다. 호출에는 선언된[ID와](../features/declared-ids.md)신호가 포함되며, 이 ID는 이미 설정한 트레이트와 세그먼트를 실현해야 합니다. 및 를 사용하여 트레이트 및 세그먼트 모집단이 증가하고 있는지[!UICONTROL General Reports]확인할[!UICONTROL Trend Reports]수 있습니까?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

아니오, 이 경우에는 [!UICONTROL General Reports] 그리고 [!UICONTROL Trend Reports] 이 경우에 의존하지 마십시오.

보고서는 보고서가 생성될 때 백엔드에서 볼 수 있는 인증되지 않은 프로필 레코드(UUID)를 기반으로 모집단을 계산합니다.

에 대한 첫 번째 호출에서 선언된 ID는 어떤 UUID에도 연결되어 있지 [!UICONTROL DCS]않습니다 *(즉,* demdex 쿠키가 [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) 클라이언트측에 없음). UUID를 [!UICONTROL DCS] 임의로 생성하여 [!DNL demdex] 쿠키를 설정하고 응답 호출에서 이를 전달하지만 UUID를 백엔드로 전송하지 않습니다.

>[!NOTE]
>
>생성된 UUID는 쿠키가 설정된 장치가 추가 활동을 트리거하는 경우에만 백엔드 데이터 스토리지에 구체화됩니다.

이러한 이유로 보고서는 선언된 ID로 트리거된 이벤트를 호출에서 반영하지 않습니다. 이벤트 테스트 호출에서 UUID, ECID(이전 MID) 또는 모바일 장치 ID를 사용하는 것이 좋습니다 [!UICONTROL DCS]. 그런 다음, 및 에서 트레이트 및 세그먼트 관계를 확인할 [!UICONTROL General Reports] 수 [!UICONTROL Trend Reports]있습니다.

Audience Manager [ID의 인덱스도 참조하십시오](../reference/ids-in-aam.md).

<br> 

**사용자 프로필을[지역](../api/dcs-intro/dcs-api-reference/dcs-regions.md)간에 동기화하는 데 얼마나 걸립니까?**

사용자 프로필이 여러 지역에서 동기화되려면 보통 24시간이 걸립니다. 그러나 드문 경우이지만 이 과정은 48시간까지 걸릴 수 있습니다.
