---
description: 추가 읽기를 위한 정의 및 링크.
seo-description: 추가 읽기를 위한 정의 및 링크.
seo-title: 용어 설명
solution: Audience Manager
title: 용어 설명
uuid: 01 FC 26 F 5-DB 9 D -4 E 90-B 4 C 1-27 C 6 A 510 ACCC
translation-type: tm+mt
source-git-commit: d5a8b763d2d0d1ceebe2252ebd283943dcbc1754

---


# 용어 설명{#glossary}

추가 읽기를 위한 정의 및 링크.

## A-B {#a-b}

**알고리즘 모델링**

Use [!UICONTROL Algorithmic Modeling] as a means of extending reach beyond the core of users you&#39;ve identified. 이 기능은 자동화된 데이터 분석을 통해 고유한 신규 고객을 발견하는 데 도움이 됩니다. [!UICONTROL Algorithmic Models]**[!UICONTROL Audience Data > Models]** 관리

See [Understanding Algorithmic Models](../features/algorithmic-models/understanding-models.md#understanding-models).

<br> 

**Baaam**

[!UICONTROL Bulk Management Tools] 구문을 사용하는 키-값 쌍으로 전달됩니다. [!UICONTROL Bulk Management Tools] In는 [!DNL Audience Manager] Microsoft Excel 기반의 도구 모음으로 한 번에 여러 개체를 만들거나 수정하거나 삭제할 수 있습니다. 데이터 소스, 파생된 신호, 대상, 폴더, 세그먼트 및 트레이트를 사용하여 작업할 수 있습니다. The feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs.

[일괄 관리 도구를 참조하십시오](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed] 구문을 사용하는 키-값 쌍으로 전달됩니다. [!UICONTROL CDF] 파일은 수집된 데이터의 벌크 다운로드를 나타내며, 사용자가 [!DNL Audience Manager] Adobe 사용자 인터페이스에서 지정한 제한 밖의 [!DNL Audience Manager] 데이터를 사용하여 작업할 수 있도록 합니다. [!UICONTROL CDF] 파일에는 [!DNL Audience Manager] 이벤트 호출 ( `/event`) 이 Adobe 서버로 보내는 동일한 데이터가 들어 있습니다. 여기에는 사용자 ID, 특성 ID, 세그먼트 ID 및 이벤트 호출에 의해 캡처된 기타 모든 매개 변수와 같은 데이터가 포함됩니다.

[고객 데이터 피드를 참조하십시오](../features/cdf-files.md).

<br> 

**CRM ID**

CRM ID는 고객이 자신의 CRM 시스템에서 사용자를 식별하는 ID 입니다. CRM ID 대신 Adobe Audience Manager에서 DPUUID 용어를 사용합니다.

See DPUUID in the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**고객 지정 가능 대상**

[어드레서블 대상의](/help/using/features/addressable-audiences.md)경우 이 지표는 다음과 같은 장치를 나타냅니다.
* 은 (는) 룩백 창에서 규칙 기반이나 온보드 트레이트를 구현했습니다.
   **and**
* 동기화 시간에 관계없이 ID가 선택한 대상과 동기화되도록 합니다.

<br> 

**고객 속성**

See [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**고객 일치 비율**

고객 지정 가능 대상 ÷ 고객 총 고객 수 (%) [지정 가능한 대상을 참조하십시오](/help/using/features/addressable-audiences.md).

<br> 

**고객 총 고객 수**

[어드레서블 대상의](/help/using/features/addressable-audiences.md)경우 이 지표는 룩백 창 동안 오프라인 파일에서 오프라인 파일에서 규칙 기반 트레이트를 구현한 장치 수를 나타냅니다.

<br> 

**demdex.net**

Demdex.net is a legacy domain controlled by [!DNL Adobe]. It reflects [!DNL Audience Manager]&#39;s original, pre-acquisition name ( [!DNL Demdex]). [!DNL Adobe] 2011 년 인수되었으며 회사 [!DNL Demdex] 브랜드에 [!DNL Audience Manager]다시 브랜드 All HTTP calls to `demdex.net` domains are calls sent in to [!DNL Adobe].

[Demdex 도메인에 대한 호출 이해](../reference/demdex-calls.md)를 참조 하십시오.

<br> 

**Daid**

[!UICONTROL Device Advertising IDs] 모바일 장치를 식별하는 데 사용되는 고유한 장치 식별자입니다. 이러한 ID는 Adobe가 아니라 장치 제조업체가 할당합니다. We support iOS and Android device IDs in [!DNL Audience Manager].

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**대상**

In [!DNL Audience Manager], a destination is any other system (ad server, DSP, ad network, etc.) 로 데이터를 공유할 수 있습니다. The [!UICONTROL Destination Builder] in our UI provides the tools that let you create and manage these data delivery processes. [!DNL Audience Manager] 대상 기능은 **[!UICONTROL Audience Data > Destinations]** 에 있습니다.

<br> 

**DIL**

The [!UICONTROL Data Integration Library] is an API library used by [!DNL Audience Manager] to collect user interaction data. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**DPM**

[!UICONTROL Data Provider Match] 구문을 사용하는 키-값 쌍으로 전달됩니다. It tells internal [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the ID service is passing in customer data for synchronization or requesting an ID. [Demdex 도메인에 대한 호출 이해](../reference/demdex-calls.md)를 참조 하십시오.

## E-F {#e-f}

**ECID(Experience Cloud ID)**

Previously named the [!DNL Marketing Cloud] ID (MID or MCID). [!DNL Experience Cloud] ID는 ID 서비스에 대한 중심입니다. 사이트 방문자의 고유한 영구 식별자입니다. See Cookies and the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html).

<br> 

**폴더 특성**

폴더 분류법에 포함된 트레이트의 자동 그룹화 계층의 각 폴더는 세그먼트를 정의하는 데 사용할 수 있는 트레이트를 자동으로 만듭니다.

[폴더 트레이트를 참조하십시오.](../features/traits/about-folder-traits.md)About.

<br> 

**주파수 표시**

광고주가 지정된 크리에이티브를 최종 사용자에게 표시하려는 횟수입니다. You can configure various frequency capping expressions in [!UICONTROL Segment Builder].

[최근 및 빈도](../features/segments/recency-and-frequency.md)보기

## G-H {#g-h}

**Gaid**

Google 광고 ID: Google 이 Android 운영 체제를 실행하는 하드웨어 장치에 할당하는 고유한 장치 ID 입니다. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

전역 고유 식별자에 대한 약어. We don&#39;t use the term GUID in [!DNL Audience Manager]. In our case, the GUID is the [!DNL Audience Manager] UUID.
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

광고주가 제품에 할당하는 고유한 장치 ID의 식별자입니다. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**인바운드**

The process by which you can send audience data from other sources to [!DNL Audience Manager]. See [Sending Audience Data](/help/using/integration/sending-audience-data/send-audience-data.md).

<br> 

**통합 코드**

[!DNL Audience Manager] UI 또는 API를 사용하여 작업할 때 특성, 세그먼트 또는 데이터 소스를 만들 때 통합 코드를 추가할 수 있습니다. 통합 코드는 다음 경우에 따라 다른 용도로 사용됩니다.

* [!UICONTROL Traits]: 통합 코드는 ID, SKU 또는 내부 비즈니스 프로세스에서 사용하는 기타 값에 대한 필드입니다. 선택 사항입니다.
* [!UICONTROL Segments]: 통합 코드는 사용자 정의 ID 또는 기타 회사별 정보에 대한 필드입니다. 선택 사항입니다.
* [!UICONTROL Data Sources]: 크로스 디바이스 데이터 소스를 만들거나, Experience Cloud ID 서비스를 사용하거나, 작업할 때는 통합 코드가 필요합니다 [!UICONTROL Profile Merge Rules]. See [Create a Data Source](../features/manage-datasources.md#create-data-source) for more information.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

[알고리즘 모델링을 참조하십시오](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

[Experience Cloud ID를 참조하십시오](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server] 구문을 사용하는 키-값 쌍으로 전달됩니다. The [!UICONTROL PCS] is a large database, running on Apache Cassandra. It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] 데이터는 장치 ID, 인증된 프로필 ID 및 관련 트레이트로 구성됩니다.

[데이터 수집 구성 요소를 참조하십시오](../reference/system-components/components-data-collection.md).

<br> 

**프로필 링크**

[프로필 병합 규칙 옵션을 참조하십시오](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**프로필 병합 규칙**

[!UICONTROL Profile Merge Rules] 세그멘테이션에 사용할 데이터 [!DNL Audience Manager] 유형을 제어할 수 있습니다.

[프로필 병합 규칙 옵션을 참조하십시오](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**구현**

사이트 방문자가 트레이트를 평가하는 작업. [방문자 프로필 뷰어](../features/visitor-profile-viewer.md) 도구를 사용하여 특정 사용자의 트레이트 구현에 대한 정보를 얻을 수 있습니다.

## S-T {#s-t}

**세그먼트**

세그먼트 (또는 대상자) 는 공통 속성을 공유하는 사용자 세트입니다.

[세그먼트 참조: 목적, 컴포지션 및 규칙을](../features/segments/segments-purpose.md)참조하십시오.

<br> 

**세그먼트 지정 가능 대상**

[지정 가능 대상의](/help/using/features/addressable-audiences.md)이 지표는 보고서 룩백 기간 동안 세그먼트에 속하고 사이트에서 활성 ID 동기화가 있는 사용자의 수를 나타냅니다. Segments can include your own first-party data and second party and third party data, via traits acquired in the [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**세그먼트 총 모집단 수**

[지정 가능 대상의](/help/using/features/addressable-audiences.md)이 지표는 보고서 룩백 기간 동안 세그먼트의 구성원인 모든 장치의 수를 나타냅니다.

<br> 

**세그먼트 일치 비율**

세그먼트 지정 가능 대상 ÷ 총 세그먼트 모집단을 퍼센트로 나타낸 것입니다. [지정 가능한 대상을 참조하십시오](/help/using/features/addressable-audiences.md).

<br> 

**신호**

Signals are the smallest data units in [!DNL Audience Manager] and are expressed as key-value pairs.

[신호, 특성 및 세그먼트를 참조하십시오](../reference/signal-trait-segment.md).

<br> 

**특성**

트레이트는 하나 이상의 신호를 조합한 것입니다. [신호, 특성 및 세그먼트를 참조하십시오](../reference/signal-trait-segment.md).

<br> 

**트레이트 모집단**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (TTL (Time-to-Live))**

TTL는 자격이 있는 방문자가 트레이트에 머무는 일 수를 정의합니다. TTL는 트레이트가 아닌 트레이트에 설정됩니다. 방문자는 TTL 구간이 끝나기 전에 적절한 트레이트를 보지 못하면 세그먼트에서 폴아웃합니다. [자세한 내용은 세그먼트와 트레이트 시간을 참조하십시오](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] 고유 사용자 ID. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

[!DNL Experience Cloud] ID 서비스 (이전 방문자 ID) 는의 모든 솔루션에서 방문자를 식별하는 범용 영구 ID를 제공합니다 [!DNL Experience Cloud].

[Experience Cloud ID 서비스](https://marketing.adobe.com/resources/help/en_US/reference/marketing-cloud-id-service.html) 설명서를 참조하십시오.

## W-X-Y-Z {#w-z}

