---
description: 이 문서에서는 Audience Manager의 데이터 개인 정보 보호 규정 준수와 관련된 세부 내용을 다룹니다.
seo-description: 이 문서에서는 Audience Manager의 데이터 개인 정보 보호 규정 준수와 관련된 세부 내용을 다룹니다.
seo-title: 데이터 개인 정보 보호 요청
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: 데이터 개인 정보 보호 요청
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '1477'
ht-degree: 54%

---


# 데이터 개인 정보 보호 요청 {#data-privacy-requests}

## 개요 {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

이 문서를 읽기 전에 [GDPR 용어집](../data-security-and-privacy/aam-gdpr-glossary.md) 및 [CCPA 용어집](aam-ccpa-glossary.md)을 끝까지 읽어서 여기에 사용된 용어를 더 잘 이해하는 것이 좋습니다.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* [Privacy Service UI](https://privacyui.cloud.adobe.io/) 사용. 설명서는 [여기](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)에서 볼 수 있습니다.
* **[!DNL Privacy Service API]** 사용. 설명서는 [여기](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[!DNL API]에서,  참조는 [여기에서 볼 수 있습니다](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)** section, along with their respective namespace IDs (data source IDs).

[Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)는 데이터 액세스 요청과 데이터 삭제 요청, 이렇게 두 가지 유형의 요청을 지원합니다.

## 데이터 액세스 요청 {#access-data}

You can send individual data access requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

[Privacy Service UI](https://privacyui.cloud.adobe.io/)를 사용하면 [!UICONTROL Request Builder]를 사용하거나 [!DNL JSON] 파일을 업로드하여 새 작업 요청을 만들 수 있습니다.

유효한 [!DNL JSON] 파일의 모습을 보기 위해 [샘플 JSON을 다운로드](../data-security-and-privacy/assets/access_request.json)할 수 있습니다.

Adobe는 법률에 의해 지정된 기간 내에 데이터 개인 정보 보호 요청을 이행하기 위한 귀하의 노력을 이해합니다.

## 데이터 삭제 요청 {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the Privacy Service API (documentation [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

[Privacy Service UI](https://privacyui.cloud.adobe.io/)를 사용하면 [!UICONTROL Request Builder]를 사용하거나 [!DNL JSON] 파일을 업로드하여 새 작업 요청을 만들 수 있습니다.

유효한 [!DNL JSON] 파일의 모습을 보기 위해 [샘플 JSON을 다운로드](../data-security-and-privacy/assets/access_request.json)할 수 있습니다.

Adobe는 30일 이내에 데이터 개인 정보 보호 고객 요청을 이행하기 위한 귀하의 노력을 이해합니다. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

When you send declared IDs, such as cross device [!DNL CRM] IDs or [!DNL cookie] IDs, in data privacy requests, [!DNL Audience Manager] will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

[!DNL Audience Manager] 는 특정 데이터 삭제를 요청하는 데이터 주체의 정보를 분류하지 않고 보내어 삭제 요청에 대해 정품 인증 파트너에게 통보하려고 합니다. 그러나 일부 활성화 파트너는

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

세그먼트 해제를 지원하는 활성화 파트너를 알려면 [Partner Excel 시트](assets/AAM-Partners-October2019.xlsx)를 다운로드하십시오.[!DNL Audience Manager]

## 옵트아웃 요청 {#opt-out-requests}

[!DNL Audience Manager] 옵트아웃 관리와 관련하여 업계 표준 지원 Read on for complete information on the types of opt-out supported by [!DNL Audience Manager].

데이터 액세스 및 삭제 요청은 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)를 통해 처리되는 반면 옵트아웃 요청은 현재 [!DNL DCS API]를 통해 지원됩니다. Read on to learn what the opt-out [!DNL API] calls should look like.

### 글로벌 옵트아웃 요청

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. 아래 표에는 글로벌 옵트아웃에 사용되는 방법이 나와 있습니다.

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵트아웃 대상 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p><a href="https://www.adobe.com/kr/privacy/opt-out.html#customeruse" format="http" scope="external">개인 정보 보호 선택 사항 페이지</a>에서는 최종 사용자가 Adobe Experience Cloud 광고 솔루션(Audience Manager 포함)에 의한 데이터 수집을 제어하고 옵트아웃할 수 있도록 해주는 1번의 클릭 기능을 제공합니다. 특히 개인 정보 보호 선택 사항 페이지의 <a href="https://www.adobe.com/kr/privacy/opt-out.html#customeruse" format="http" scope="external">비즈니스 고객 섹션</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager에 대한 직접 API 호출 </p> </td> 
   <td colname="col2"> <p>사용자는 아래 DCS API를 호출하여 모든 Audience Manager 브랜드에 의한 데이터 수집에서 옵트아웃하고 <a href="../../reference/ids-in-aam.md">Audience Manager 사용자 ID</a>를 포함할 수 있습니다. </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>그 결과, 제출된 Audience Manager 사용자 ID에 대한 <code>demdex=NOTARGET</code> 및 <code>dextp=NOTARGET</code> 쿠키를 설정하게 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 장치 </p> </td> 
   <td colname="col2"> <p>다음 장치에 대한 옵트아웃 및 개인 정보 보호 설정을 확인하십시오. </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/ko-KR/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android 장치 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/ko-KR/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS 장치 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

최종 사용자는 Adobe의 업계 표준 파트너 웹 사이트를 방문하여 글로벌 데이터 수집을 옵트아웃할 수 있습니다.

* [DAA(Digital Advertising Alliance)](https://optout.aboutads.info/?c=2#!/)
* [NAI(Network Advertising Initiative)](https://optout.networkadvertising.org/?c=1#!/)

위에 설명된 옵트아웃 요청에 따라,

* [!DNL Audience Manager] 사용자가 브라우저 쿠키를 지우지 않는 한 모든 데이터 수집, 세그멘테이션 또는 활성화를 중단합니다.
* 이전 데이터는 120일 후 사용자 프로필에서 제거됩니다.

### 선언된 ID 호출을 사용한 파트너 수준 옵트아웃

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

선언된 ID 호출로 파트너 수준 옵트아웃을 수행하면

* [CRM ID](../../reference/ids-in-aam.md)가 데이터 수집에서 옵트아웃됩니다.
* [CRM ID](../../reference/ids-in-aam.md)에 연결된 마지막 장치 ID([Audience Manager 고유 사용자 ID](../../reference/ids-in-aam.md))가 데이터 수집에서 옵트아웃됩니다.
* [!DNL Audience Manager] 이 ID와 ID에 연결된 마지막 장치 ID에 대해 앞으로 모든 데이터 수집, 세그멘테이션 또는 활성화를 [!DNL CRM] [!DNL CRM] 중단합니다.
* [!DNL Audience Manager] 모든 세그먼트에서 옵트아웃 [!DNL CRM] ID 및 마지막 장치 ID를 세그먼트화할 수 없습니다.
* [!UICONTROL Destination] 파트너는 [!DNL CRM] ID 및 마지막 장치 ID에 대한 세그먼트 해제 요청을 받습니다. 세그먼테이션 해제는 [실시간](data-privacy-requests.md#aam-partners-with-unsegmentation) 대상과 배치 대상 모두에 대해 작동합니다.
* 이전 데이터는 삭제되지 않습니다.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

`d_cid` 및 `d_cid_ic` 키-값 쌍으로 선언된 ID 옵트아웃 요청을 만들 수 있습니다. `d_dpid` 및 `d_dpuuid`와 같은 기존 매개 변수는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../../reference/cid.md)를 참조하십시오. 예에서 *기울임꼴*&#x200B;은 가변 자리 표시자를 나타냅니다.

#### 수신 거부 [!DNL CID] 및 [!DNL CID_IC]

설명 및 구문이 필요하면 [선언된 ID에 대한 URL 변수 및 구문](../../features/declared-ids.md#variables-and-syntax)을 참조하십시오.

| 옵트아웃에 사용하는 값 | 코드 샘플 |
|--- |--- |
| 데이터 공급자 ID 및 사용자 ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 통합 코드 및 사용자 ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 다중 `d_cid` 및 `d_cid_ic` 키-값 쌍. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 장치 ID 호출을 사용한 파트너 수준 옵트아웃

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)를 다음과 같이 호출하여 브랜드의 특정 기기 ID에서 데이터 수집을 옵트아웃할 수 있습니다.

| 옵트아웃에 사용하는 값 | 코드 샘플 |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| ID( [!DNL Experience Cloud]`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

[Audience Manager의 ID 색인](/help/using/reference/ids-in-aam.md)에서 `uuid`, `mid` 및 `imsOrgId`에 대해 자세히 알아보십시오.

장치 ID 호출로 파트너 수준 옵트아웃을 수행하면

* 장치 ID가 데이터 수집에서 옵트아웃됩니다.
* [!DNL Audience Manager] 파트너의 모든 데이터 수집, 세그멘테이션 또는 활성화를 중지하고 장치 ID를 진행합니다.
* [!DNL Audience Manager] 모든 세그먼트에서 장치 ID 세그먼트 해제;
* 대상 파트너가 장치 ID에 대한 세그먼트 해제 요청을 받습니다. 세그먼테이션 해제는 [실시간](data-privacy-requests.md#aam-partners-with-unsegmentation) 대상과 배치 대상 모두에 대해 작동합니다.
* 이전 데이터는 삭제되지 않습니다.

## [!DNL Audience Manager] 세분화 기능을 갖춘 파트너 {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

그러나 일부 활성화 파트너는

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

세그먼트 해제를 지원하는 활성화 파트너를 알려면 [장치 기반 대상 목록](/help/using/features/destinations/device-based-destinations-list.md)을 참조하십시오.[!DNL Audience Manager]

## 데이터 수정 요청 {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] 고객은 사용자 프로필에 대해 관련 신호/특성/세그먼트를 캡처하고 [오프라인 데이터 수집으로 이 정보를 전송할 수](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 있습니다 [!DNL Audience Manager]. Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
