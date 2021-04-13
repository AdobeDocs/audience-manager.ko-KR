---
description: 정의 및 추가적으로 읽을 수 있는 링크.
seo-description: 정의 및 추가적으로 읽을 수 있는 링크.
seo-title: 용어 설명
solution: Audience Manager
title: 용어 설명
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: 참조
exl-id: 9e2ee3d3-01b2-4038-abda-fedf0f16f163
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 100%

---

# 용어 설명{#glossary}

정의 및 추가적으로 읽을 수 있는 링크.

## A-B {#a-b}

**알고리즘 모델링**

식별한 핵심 사용자를 넘어 도달 범위를 확장하는 수단으로 [!UICONTROL Algorithmic Modeling]을 사용하십시오. 이 기능을 사용하면 자동화된 데이터 분석을 통해 새롭고 고유한 고객을 발견할 수 있습니다. **[!UICONTROL Audience Data > Models]**&#x200B;에서 [!UICONTROL Algorithmic Models]을 관리하십시오.

[알고리즘 모델 이해](../features/algorithmic-models/algo-models-overview.md)를 참조하십시오.

**BAAAM**

[!UICONTROL Bulk Management Tools]. [!DNL Audience Manager]의 [!UICONTROL Bulk Management Tools]는 한 번의 작업으로 여러 개체를 한 번에 만들거나 수정하거나 삭제할 수 있는 Microsoft Excel 기반 도구 세트입니다. 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트를 사용하여 작업할 수 있습니다. 이 기능에서는 [!DNL Audience Manager] API에 대한 안전하고 인증된 호출을 수행하는 매크로가 포함된 Microsoft Excel 스프레드시트를 사용합니다.

[벌크 관리 도구](../reference/bulk-management-tools/bulk-management-intro.md)를 참조하십시오.

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. [!UICONTROL CDF] 파일은 [!DNL Audience Manager]에 의해 수집된 데이터의 벌크 다운로드를 나타내며 사용자 인터페이스가 부과한 제한을 벗어나는 [!DNL Audience Manager] 데이터로 작업할 수 있도록 해줍니다. [!UICONTROL CDF] 파일에는 [!DNL Audience Manager] 이벤트 호출(`/event`)이 서버에 보내는 것과 동일한 데이터가 포함되어 있습니다. 여기에는 사용자 ID, 트레이트 ID, 세그먼트 ID 및 이벤트 호출로 캡처된 기타 모든 매개 변수 등의 데이터가 포함됩니다.

[고객 데이터 피드](../features/cdf-files.md)를 참조하십시오.

**CRM ID**

CRM ID는 고객이 자신의 CRM 시스템에서 사용자를 식별하는 ID입니다. Audience Manager에서는 CRM ID 대신 DPUUID라는 용어를 사용합니다.

[Audience Manager의 ID 색인](../reference/ids-in-aam.md)에서 DPUUID를 참조하십시오.



**고객 대응 가능 대상**

[대응 가능 대상](/help/using/features/addressable-audiences.md)에서 이 지표는 다음과 같은 장치를 나타냅니다.
* 전환 확인 기간 동안 규칙에 기반하거나 온보딩된 트레이트를 실현했습니다.
   **그리고**
* 동기화 시간과 관계없이 선택한 대상과의 ID 동기화가 있습니다.



**고객 특성**

[!DNL Experience Cloud Core Services] 제품 설명서에서 [고객 특성](https://docs.adobe.com/content/help/ko-KR/core-services/interface/customer-attributes/attributes.html)을 참조하십시오.



**고객 일치율**

%로 표현되는 고객 대응 가능 대상 ÷ 고객 총 대상. [대응 가능 대상](/help/using/features/addressable-audiences.md)을 참조하십시오.



**고객 총 대상**

[대응 가능 대상](/help/using/features/addressable-audiences.md)에서 이 지표는 전환 확인 기간 동안 자산에 대한 규칙 기반 트레이트 또는 오프라인 파일에서 온보딩된 트레이트를 실현한 장치 수를 나타냅니다.



**demdex.net**

Demdex.net은 [!DNL Adobe]에 의해 제어되는 기존 도메인으로서, [!DNL Audience Manager]의 원래의, 인수 이전 이름([!DNL Demdex])을 반영합니다. [!DNL Adobe]는 2011년에 [!DNL Demdex]를 인수하고 회사 브랜드를 [!DNL Audience Manager]로 변경했습니다. `demdex.net` 도메인에 대한 모든 HTTP 호출은 [!DNL Adobe]에 전송되는 호출입니다.

[Demdex 도메인에 대한 호출 이해](../reference/demdex-calls.md)를 참조하십시오.



**DAID**

[!UICONTROL Device Advertising IDs]는 모바일 장치를 식별하는 데 사용되는 고유한 장치 식별자입니다. 이 ID는 Adobe가 아니라 장치 제조업체가 지정합니다. [!DNL Audience Manager]에서는 iOS 및 Android 장치 ID가 지원됩니다.

[Audience Manager의 ID 색인](../reference/ids-in-aam.md)을 참조하십시오.



**대상**

[!DNL Audience Manager]에서 대상은 데이터를 공유하려는 다른 시스템(광고 서버, DSP, 광고 네트워크 등) 입니다. UI의 [!UICONTROL Destination Builder]는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. [!DNL Audience Manager] 대상 기능은 **[!UICONTROL Audience Data > Destinations]**&#x200B;에 있습니다.



**DIL**

[!UICONTROL Data Integration Library]는 사용자 상호 작용 데이터를 수집하기 위해 [!DNL Audience Manager]에서 사용하는 API 라이브러리입니다. [DIL(데이터 통합 라이브러리) API](../dil/dil-overview.md)를 참조하십시오.



**dpm**

[!UICONTROL Data Provider Match]. 내부 [!DNL Adobe] 시스템에게 [!DNL Audience Manager] 또는 ID 서비스로부터의 호출이 ID 동기화 또는 요청을 위해 고객 데이터를 전달하고 있음을 알려줍니다. [Demdex 도메인에 대한 호출 이해](../reference/demdex-calls.md)를 참조하십시오.

## E-F {#e-f}

**ECID(Experience Cloud ID)**

이전 이름은 [!DNL Marketing Cloud] ID(MID 또는 MCID)였습니다. [!DNL Experience Cloud] ID는 ID 서비스의 중심입니다. 사이트 방문자에 대한 고유하고 지속적인 식별자입니다. 쿠키 및 [Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html)를 참조하십시오.



**폴더 트레이트**

폴더 분류법 내의 트레이트 자동 그룹화. 계층 구조의 각 폴더는 세그먼트를 정의하는 데 사용할 수 있는 트레이트를 자동으로 만듭니다.

[폴더 트레이트: 설명](../features/traits/about-folder-traits.md)을 참조하십시오.



**빈도 제한**

광고주가 주어진 크리에이티브를 최종 사용자에게 표시하려는 횟수 제한입니다. [!UICONTROL Segment Builder]에서 다양한 빈도 제한 표현 식을 구성할 수 있습니다.

[최신성 및 빈도](../features/segments/recency-and-frequency.md)를 참조하십시오.

## G-H {#g-h}

**GAID**

Google 광고 ID. Google이 Android 운영 체제를 실행하는 하드웨어 장치에 지정하는 고유 장치 ID입니다. [Audience Manager의 ID 색인](../reference/ids-in-aam.md)을 참조하십시오.



**GUID**

Globally Unique Identifier(전 세계적 단일 식별자)의 약어입니다. [!DNL Audience Manager]에서는 GUID라는 용어를 사용하지 않습니다. 여기에서 GUID는 [!DNL Audience Manager] UUID입니다.
[Audience Manager의 ID 색인](../reference/ids-in-aam.md)을 참조하십시오.

## I-J {#i-j}

**IDFA**

광고주용 식별자. Apple이 제품에 할당하는 고유 장치 ID입니다.  [Audience Manager의 ID 색인](../reference/ids-in-aam.md)을 참조하십시오.



**인바운드**

다른 소스의 대상 데이터를 [!DNL Audience Manager]에 보낼 수 있는 프로세스입니다. [대상 데이터 보내기](/help/using/integration/sending-audience-data/send-audience-data.md)를 참조하십시오.



**통합 코드**

[!DNL Audience Manager] UI 또는 API를 사용하여 작업하는 경우 트레이트, 세그먼트 또는 데이터 소스를 만들 때 통합 코드를 추가할 수 있습니다. 이런 경우 통합 코드는 다음과 같이 서로 다른 용도로 사용됩니다.

* [!UICONTROL Traits]: 통합 코드가 내부 비즈니스 프로세스에서 사용하는 ID, SKU 또는 기타값을 위한 필드입니다. 선택 사항입니다.
* [!UICONTROL Segments]: 통합 코드가 사용자 정의 ID 또는 기타 특정 회사에 대한 정보를 위한 필드입니다. 선택 사항입니다.
* [!UICONTROL Data Sources]: 교차 장치 데이터 소스를 만들거나 Adobe Experience Platform ID 서비스를 사용하거나 [!UICONTROL Profile Merge Rules]을 사용하는 작업을 하려면 통합 코드가 필요합니다. 자세한 내용은 [데이터 소스 만들기](../features/manage-datasources.md#create-data-source)를 참조하십시오.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

[알고리즘 모델링](../reference/aam-glossary.md#a-b)을 참조하십시오.

## M-N {#m-n}

**MCID**, **MID**

[Experience Cloud ID](../reference/aam-glossary.md#e-f)를 참조하십시오.

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. [!UICONTROL PCS]는 Apache Cassandra에서 실행되는 대형 데이터베이스로서, 서버 간 전송 및 [!DNL DCS]에서 활성 사용자에 대해 받은 데이터를 저장합니다. [!UICONTROL PCS] 데이터는 장치 ID, 인증된 프로필 ID 및 연결된 트레이트로 구성됩니다.

[데이터 수집 구성 요소](../reference/system-components/components-data-collection.md)를 참조하십시오.



**프로필 링크**

[정의된 프로필 병합 규칙 옵션](../features/profile-merge-rules/merge-rule-definitions.md)을 참조하십시오.



**프로필 병합 규칙**

[!UICONTROL Profile Merge Rules]을 사용하면 [!DNL Audience Manager]가 세그먼테이션에 사용하는 데이터 유형을 제어할 수 있습니다.

[정의된 프로필 병합 규칙 옵션](../features/profile-merge-rules/merge-rule-definitions.md)을 참조하십시오.

## Q-R {#q-r}

**실현**

사이트 방문자가 트레이트에 대한 자격을 받는 작업입니다. [방문자 프로필 뷰어](../features/visitor-profile-viewer.md) 도구를 사용하여 특정 사용자의 트레이트 실현에 대한 정보를 얻을 수 있습니다.

## S-T {#s-t}

**세그먼트**

세그먼트(또는 대상)는 일반적인 특성을 공유하는 사용자 집합입니다.

[세그먼트: 목적, 구성 및 규칙](../features/segments/segments-purpose.md)을 참조하십시오.



**세그먼트 대응 가능 대상**

[대응 가능 대상](/help/using/features/addressable-audiences.md)에서 이 지표는 보고서 전환 확인 기간 동안 세그먼트에 속하고 해당 사이트에 대한 활성 ID 동기화를 보유한 사용자 수를 나타냅니다. 세그먼트는 [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)에서 획득한 트레이트를 통해 자신의 자사 데이터와 제2자 데이터, 타사 데이터를 포함할 수 있습니다.



**세그먼트 총 인구**

[대응 가능 대상](/help/using/features/addressable-audiences.md)에서 이 지표는 보고서 전환 확인 기간 동안 세그먼트의 구성원이었던 모든 장치의 수를 나타냅니다.



**세그먼트 일치율**

%로 표현되는 세그먼트 대응 가능 대상 ÷ 총 세그먼트 인구. [대응 가능 대상](/help/using/features/addressable-audiences.md)을 참조하십시오.



**신호**

신호는 [!DNL Audience Manager]에서 가장 작은 데이터 단위이며 키-값 쌍으로 표현됩니다.

[신호, 트레이트 및 세그먼트](../reference/signal-trait-segment.md)를 참조하십시오.



**트레이트**

트레이트는 하나 이상의 신호가 결합된 것입니다. [신호, 트레이트 및 세그먼트](../reference/signal-trait-segment.md)를 참조하십시오.



**트레이트 인구**

[세그먼트 빌더의 트레이트 및 세그먼트 인구 데이터](../features/segments/segment-builder-data.md)를 참조하십시오.

**TTL(Time-to-Live)**

TTL은 자격이 있는 방문자가 트레이트에 남아 있는 일수를 정의합니다. TTL은 세그먼트가 아니라 트레이트에 대해 설정됩니다. 방문자가 TTL 간격 종료 전에 자격 트레이트를 보지 못할 경우 세그먼트에서 이탈됩니다. [세그먼트 및 트레이트 유지 시간 설명](/help/using/features/traits/segment-ttl-explained.md)에서 더 확인하십시오.



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] 고유 사용자 ID. [Audience Manager의 ID 색인](../reference/ids-in-aam.md)을 참조하십시오.



**Visitor ID**

[!DNL Experience Cloud] ID 서비스(이전 방문자 ID)는 [!DNL Experience Cloud]의 모든 솔루션에서 방문자를 식별하는 범용 영구 ID를 제공합니다.

[Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html) 설명서를 참조하십시오.

## W-X-Y-Z {#w-z}
