---
description: 일반적인 데이터 수집 및 통합 질문 및 문제
seo-description: 일반적인 데이터 수집 및 통합 질문 및 문제
seo-title: 데이터 수집 및 제품 통합 FAQ
solution: Audience Manager
title: 데이터 수집 및 제품 통합 FAQ
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
feature: Administration
translation-type: tm+mt
source-git-commit: 1f3b3d7d7ea8eaa0c1b64f147dc60b85f4e2f487
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 83%

---


# 데이터 수집 및 제품 통합 FAQ{#data-collection-and-product-integration-faq}

일반적인 데이터 수집 및 통합 질문 및 문제

<br> 

**[!DNL DCS] 로그 파일 내보내기에서 인바운드 트래픽을 [!DNL DCS] 트래픽과 어떻게 구별할 수 있습니까?**

[!UICONTROL Inbound]를 통해 온보딩된 트레이트는 [!DNL DCS]에 의해 채워지는 것과 같은 방식으로 [!UICONTROL Inbound]에 의해 채워집니다. 트래픽이 [!UICONTROL Inbound]에서 발생했음을 아는 방법은 몇 가지가 있습니다.

* 원격 IP가 68.67.173.18로 설정됩니다.
* 도메인 ID가 5325로 설정됩니다.
* 지역이 0으로 설정됩니다.

<br> 

**dpm.demdex.net의 허용 목록에 추가할 수 있는 IP 주소 목록을 제공할 수 있습니까?**

안타깝지만 불가능합니다. 이러한 IP는 지역에 따라 [!DNL Amazon Web Services]를 통해 동적으로 지정됩니다. 따라서 [!DNL Audience Manager]는 이 주소에 지정할 수 있는 IP 범위를 제어하지 않습니다.

 

**인바운드 및 아웃바운드 SFTP 서버의 허용 목록에 추가할 수 있는 IP 주소를 알려주시겠습니까?**

예, 아래를 참조하십시오.

| 서버 | IP 주소 |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119;3.233.68.222 |
| ftp-out-gtw.demdex.com | 23.22.232.252;18.211.109.184 |

 

아래의 SFTP 서버는 사용되지 않습니다. 이러한 서버를 사용하여 새 계정이 제공되지 않습니다.

| 서버 | IP 주소 |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**새 SFTP 서버를 사용하도록 Audience Manager 인스턴스를 구성하려면 어떻게 합니까?**

[!DNL Audience Manager] 컨설턴트 또는 고객 지원 센터에 연락하면 새 SFTP 계정을 구성합니다.

 

**새 SFTP 서버에 대해 지원되는 인증 방법은 무엇입니까?**

새 SFTP 서버(`ftp-in-gtw` 및 `ftp-out-gtw`)는 [!DNL OpenSSH Key-Based Authentication]를 지원합니다. [!DNL SSH] 키를 생성하거나 사용자가 직접 공개 키를 제공할 수 있습니다.

 

**[!UICONTROL DIL]/[!DNL Analytics] 데이터 통합을 위한 코드 배치 및 페이지 로드 요구 사항은 무엇입니까?**

[!DNL Analytics] 데이터를 [!DNL Audience Manager]에 가져오려면 `s_code` 모듈 뒤에 `s.t()` 함수 *앞에* [!UICONTROL DIL]을 로드하십시오. 예를 들어, 다음 순서대로 코드를 배치하거나 코드가 로드되도록 하십시오.

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] 모듈

3. [!DNL Analytics] `s.t()` 함수 위에 있어야 합니다

우수 사례로서, 다음 두 가지 방법 중 하나를 사용하여 [!DNL Audience Manager]-[!DNL Analytics] 통합을 설정하십시오.

* `s_code`에 바로 [!UICONTROL DIL]을 넣습니다.

* [!DNL Adobe Experience Platform Launch] 또는 [!DNL Adobe DTM]을 통해 [!UICONTROL DIL]과 `s_code`를 제공합니다.

[DIL(데이터 통합 라이브러리) API](../dil/dil-overview.md)를 참조하십시오.

 

**왜 내 [!DNL Analytics] 변수가 [!DNL Audience Manager] 이벤트 호출에서 누락되었습니까?**

이런 일은 일반적으로 다음의 경우에 발생합니다.

* 페이지의 다른 코드 요소와 비동기적으로 로드하는 태그 관리 시스템을 통해 [!UICONTROL DIL]을 제공합니다.
* `s.t()` 함수는 [!UICONTROL DIL] 앞에 로드됩니다.

 

**[!UICONTROL DIL]과 호환되는 [!DNL Analytics] 버전은 무엇입니까?**

[!UICONTROL DIL]을 사용하여 작업하려면 [!DNL Analytics] 버전 20.2 이상과 [!DNL Adobe AppMeasurement AS] 라이브러리 버전 3.5.2 이상을 사용해야 합니다. [!DNL Analytics] 또는 [!DNL AppMeasurement] 버전을 모르는 경우에는 페이지에서 수행되는 [!DNL Analytics] 호출을 확인하십시오. 버전 정보는 아래에 나와 있습니다.

이 고객은 [!DNL Analytics] 버전 24.4를 사용합니다.

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

이 고객은 [!DNL AppMeasurement] 버전 3.5.2를 사용합니다.

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**[!DNL Analytics] 고객이 아닌 경우 페이지 데이터를 수집할 수 있습니까?**

예. [!UICONTROL DIL] 모듈은 [!DNL Analytics]를 사용하지 않더라도 페이지 데이터를 수집하는 데 도움이 됩니다. [!UICONTROL DIL]은 올바로 설정되면 다음 항목에서 해당 항목에 대한 데이터를 캡처할 수 있습니다.

* 메타 태그
* URL 및 URL 헤더
* 검색 엔진 유형
* 키워드

또한 고객은 간단한 온사이트 개체를 배포하고 이 개체를 [!UICONTROL DIL]이 데이터를 수집할 키-값 쌍으로 채울 수 있습니다. 이렇게 하면 [!DNL Audience Management] 업데이트 없이 사이트에서 특정 대상 데이터 포인트를 추가 및 제거할 수 있습니다. 파트너 솔루션 담당자와 협력하여 이를 올바로 설정하고 [!DNL DIL] 모듈이 페이지 개체를 올바로 참조하게 하십시오.

<br> 

**[!UICONTROL DIL]이 [!DNL Google Analytics]에서 데이터를 수집할 수 있습니까?**

예. [!UICONTROL DIL]은 일부 [!DNL Google Analytics] (GA) 요소를 수집하고 해당 데이터를 [!DNL Audience Manager]에 전달할 수 있습니다. 다음을 참조하십시오.

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**[!DNL Audience Manager]에서 원시 데이터를 얻을 수 있습니까? 그리고 그 데이터는 얼마나 세분화됩니까?**

예, [!DNL Audience Manager]는 우리가 인벤토리에서 본 사용자에 대해 수집된 데이터를 제공할 수 있습니다. 여기에는 다음 항목이 포함되어 있습니다.

* [!DNL Audience Manager]에 의해 지정된 고유한 사용자 ID(UUID)
* 트레이트 및 세그먼트 ID
* 사용되지 않은 신호
* 타임스탬프
* 페이지 URL

<br> 

**한 사이트에서 데이터를 수집하고 다른 사이트를 통해 사용자 [!DNL Google Ad Manager] 를 타깃팅하고자 합니다. 해당 위치에서 데이터를 수집하지 않으려면 다른 자산에서 코드를 배포해야 합니까?**

아니요. 두 번째 사이트에 대한 데이터 수집이 요구 사항이 아니라면 거기에 DIL을 배포할 필요가 없습니다. [!DNL Google Ad Manager]을 통해 두 번째 사이트의 인벤토리에 액세스할 수 있는 경우, 초기 사이트의 데이터 수집 및 [!DNL Google Ad Manager]를 통해 타깃팅할 수 있습니다.

<br> 

**최고의 타사 데이터 공급자는 어디입니까?**

각 공급자는 테이블에 고유한 사항을 제공하므로 찾고 있는 내용에 따라 답이 달라집니다. 어떤 공급자가 자신에게 가장 적합한지 이해하는 데 중복 보고가 도움이 되도록 할 수 있습니다.

<br> 

**쿠키를  [!DNL Audience Manager] 설정하고 변수를 어떻게 전달합니까 [!DNL Google Ad Manager]?**

[!DNL Audience Manager] 2개 쿠키:하나는 세그먼트 변수를  [!DNL Google Ad Manager] 광고 태그로 보내고 다른 하나는 고유한 사용자 ID(UUID)를 설정하며, 이 ID는 읽은  [!DNL Google Ad Manager]사람입니다. 광고 태그에 UUID를 추가하는 것은 사용자 수준의 보고 및 대상 검색을 수행할 수 있음을 의미합니다.

<br> 

**사용자가 도달한 전환 단계의 포인트에 대한 DSP 정보를 보낼 수 있습니까?**

예. 단계 데이터를 보낼 수 있지만 DSP에 이를 사용할 수 있는 기술적 능력이 있어야 합니다. DSP는 여러 세그먼트를 처리할 수 있음을 확인해야 합니다. 처리할 수 없다면 전환 진행 상태(예: 1단계와 2단계를 완료했지만 3단계는 완료하지 않음)에 따라 다른 세그먼트에서 사용자를 끌어모을 특정 세그먼트를 만들어야 할 수도 있습니다. 이 정보를 DSP로 보내 사용자를 재타겟팅하고 특정 랜딩 페이지로 안내하거나 특정 크리에이티브를 표시할 수 있습니다.

<br> 

**FTP를 통해 전송된 데이터가 [!DNL Audience Manager]에 의해 선택되었음을 어떻게 확인할 수 있습니까?**

확장자가 `.sync`에서 `.processed`로 변경될 때 파일이 선택되었습니다. 이렇게 되면 파일은 섭취 큐에 있게 됩니다. 또한 계정 관리자는 파일이 업로드된 시점을 확인할 수 있습니다.

<br> 

**[DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)의 기능을 테스트하고 싶습니다. 아래 표시된 것과 같은 이벤트 호출을 보내고 있습니다. 호출에는 [선언된 ID](../features/declared-ids.md) 및 신호가 포함되어 있으며, 이렇게 되면 이미 설정한 트레이트 및 세그먼트를 실현해야 합니다. [!UICONTROL General Reports] 및 [!UICONTROL Trend Reports]를 사용하여 트레이트 및 세그먼트 인구가 증가하고 있는지 확인할 수 있습니까?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

아니오. 이 경우 [!UICONTROL General Reports] 및 [!UICONTROL Trend Reports]에 의존하지 마십시오.

보고서는 보고서가 생성될 때 백엔드에 표시되는 인증되지 않은 프로필 레코드(UUID)를 기반으로 인구를 계산합니다.

[!DNL DCS]에 대한 첫 번째 호출에서 선언된 ID는 어떠한 UUID에도 연결되어 있지 *않습니다*(즉, 클라이언트 측에 [demdex 쿠키](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)가 없음). [!DNL DCS]는 무작위로 UUID를 생성하고 [!DNL demdex] 쿠키를 설정하여 응답 호출에서 전달하지만 UUID를 백엔드로 전송하지는 않습니다.

>[!NOTE]
>
>쿠키가 설정된 장치가 추가 활동을 트리거하면 생성된 UUID는 백엔드 데이터 저장소에서만 나타납니다.

이러한 이유로, 보고서에는 호출에서 선언된 ID에 의해 트리거된 이벤트가 반영되지 않습니다. [!DNL DCS]에 대한 이벤트 테스트 호출에서는 UUID, ECID(이전의 MID) 또는 모바일 장치 ID를 사용하는 것이 좋습니다. 그러면 [!UICONTROL General Reports] 및 [!UICONTROL Trend Reports]에서 트레이트와 세그먼트 실현을 확인할 수 있습니다.

[Audience Manager ID 색인](../reference/ids-in-aam.md)을 참조하십시오.

<br> 

**[지역](../api/dcs-intro/dcs-api-reference/dcs-regions.md) 간에 사용자 프로필을 동기화하는 데 시간이 얼마나 걸립니까?**

일반적으로 사용자 프로필이 지역 간에 동기화되려면 최대 24시간이 걸립니다. 그러나 드문 경우 이 프로세스는 최대 48시간이 걸릴 수 있습니다.
