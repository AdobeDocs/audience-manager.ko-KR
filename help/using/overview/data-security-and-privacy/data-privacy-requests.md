---
description: 이 문서에서는 Audience Manager의 데이터 개인 정보 보호 규정 준수와 관련된 세부 내용을 다룹니다.
seo-description: 이 문서에서는 Audience Manager의 데이터 개인 정보 보호 규정 준수와 관련된 세부 내용을 다룹니다.
seo-title: 데이터 개인 정보 보호 요청
solution: Audience Manager
keywords: GDPR UI, GDPR API, CPA, 개인 정보
title: 데이터 개인 정보 보호 요청
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 54%

---

# 데이터 개인 정보 보호 요청 {#data-privacy-requests}

## 개요 {#overview}

이 문서에서는 [Privacy Service UI](https://privacyui.cloud.adobe.io/) 및 **[!DNL Privacy Service API]**&#x200B;을 통해 [!DNL Audience Manager]으로 보낼 수 있는 개별 데이터 개인 정보 및 수신 거부 요청 관리에 대한 개요를 제공합니다.

이러한 도구를 사용하여 [!DNL GDPR] 및 [!DNL CCPA]에 따른 소비자 데이터 개인 정보 보호 요청을 보낼 수 있습니다.

이 문서를 읽기 전에 [GDPR 용어집](../data-security-and-privacy/aam-gdpr-glossary.md) 및 [CCPA 용어집](aam-ccpa-glossary.md)을 끝까지 읽어서 여기에 사용된 용어를 더 잘 이해하는 것이 좋습니다.

다음 두 가지 방법으로 [!DNL Audience Manager]의 소비자 데이터에 액세스하고 삭제할 개별 요청을 제출할 수 있습니다.

* [Privacy Service UI](https://privacyui.cloud.adobe.io/) 사용. 설명서는 [여기](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)에서 볼 수 있습니다.
* **[!DNL Privacy Service API]** 사용. 설명서는 [여기](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[!DNL API]에서,  참조는 [여기에서 볼 수 있습니다](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

개별 데이터 개인 정보 보호 요청을 전송할 때 **[Audience Manager 식별자](data-privacy-ids.md)** 섹션에 설명된 대로 해당 네임스페이스 ID(데이터 소스 ID)와 함께 [!DNL Audience Manager] 식별자(ID)를 제출할 수 있습니다.

[Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)는 데이터 액세스 요청과 데이터 삭제 요청, 이렇게 두 가지 유형의 요청을 지원합니다.

## 데이터 액세스 요청 {#access-data}

[Privacy Service UI](https://privacyui.cloud.adobe.io)(문서 [여기](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) 또는 Privacy Service API(설명서 [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 및 [!DNL API] 참조 [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml))를 통해 개별 데이터 액세스 요청을 보낼 수 있습니다.

[Privacy Service UI](https://privacyui.cloud.adobe.io/)를 사용하면 [!UICONTROL Request Builder]를 사용하거나 [!DNL JSON] 파일을 업로드하여 새 작업 요청을 만들 수 있습니다.

유효한 [!DNL JSON] 파일의 모습을 보기 위해 [샘플 JSON을 다운로드](../data-security-and-privacy/assets/access_request.json)할 수 있습니다.

Adobe는 법률에 의해 지정된 기간 내에 데이터 개인 정보 보호 요청을 이행하기 위한 귀하의 노력을 이해합니다.

## 데이터 삭제 요청 {#delete-data}

[Privacy Service UI](https://privacyui.cloud.adobe.io)(문서 [여기](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md))를 통해 또는 Privacy Service API(문서 [here](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 및 [!DNL API] 참조 [여기](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml) 참조)를 통해 데이터 삭제 요청을 보낼 수 있습니다.

[Privacy Service UI](https://privacyui.cloud.adobe.io/)를 사용하면 [!UICONTROL Request Builder]를 사용하거나 [!DNL JSON] 파일을 업로드하여 새 작업 요청을 만들 수 있습니다.

유효한 [!DNL JSON] 파일의 모습을 보기 위해 [샘플 JSON을 다운로드](../data-security-and-privacy/assets/access_request.json)할 수 있습니다.

Adobe는 30일 이내에 데이터 개인 정보 보호 고객 요청을 이행하기 위한 귀하의 노력을 이해합니다. 이러한 이유로 [!DNL Adobe]은(는) 가능한 한 빨리 데이터 삭제 요청을 처리하기 위해 최선을 다하고 있습니다.

소비자 데이터 삭제 요청에 응답하여 [!DNL Audience Manager]은 요청에 포함된 [!DNL Audience Manager] 식별자와 연관된 트레이트 및 세그먼트를 삭제합니다. 또한, [!DNL Audience Manager]에 의해 추가 데이터 수집에서 옵트아웃한 개인의 해당 [!DNL Audience Manager] 식별자 및 해당 ID 매핑이 제거됩니다.

상호 장치 [!DNL CRM] ID 또는 [!DNL cookie] ID와 같이 선언된 ID를 전송하는 경우 데이터 개인 정보 보호 요청에서 [!DNL Audience Manager]는 연결된 모든 장치(선언된 ID당 최대 100개 장치)에서 필요한 삭제를 수행합니다.

[!DNL Audience Manager] 특정 데이터 삭제를 요청하는 데이터 주체의 정보를 분류하지 않고 보내어 삭제 요청을 정품 인증 파트너에게 통보합니다. 그러나 일부 활성화 파트너는

1. [!DNL Audience Manager] 및/또는
2. 주파수가 30일 미만인 [!DNL Audience Manager]에서 업데이트를 받을 수 없습니다. 이러한 경우 [!DNL Audience Manager] 고객은 [!DNL Audience Manager]을(를) 통해 자동화된 방식으로 정품 인증 파트너에게 삭제 요청을 보낼 수 없습니다.

이러한 경우 [!DNL Audience Manager]을(를) 통해 자동화된 방식으로 정품 인증 파트너에게 삭제 요청을 보낼 수 없습니다.

세그먼트 해제를 지원하는 활성화 파트너를 알려면 [Partner Excel 시트](assets/AAM-Partners-October2019.xlsx)를 다운로드하십시오.[!DNL Audience Manager]

## 옵트아웃 요청 {#opt-out-requests}

[!DNL Audience Manager] 옵트아웃 관리와 관련하여 업계 전반의 표준을 지원합니다. [!DNL Audience Manager]에서 지원하는 옵트아웃 유형에 대한 자세한 내용을 참조하십시오.

데이터 액세스 및 삭제 요청은 [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)를 통해 처리되는 반면 옵트아웃 요청은 현재 [!DNL DCS API]를 통해 지원됩니다. 옵트아웃 [!DNL API] 호출이 어떻게 표시되어야 하는지 알아보려면 읽어 보십시오.

### 글로벌 옵트아웃 요청

글로벌 옵트아웃은 [!DNL Audience Manager] 및 모든 브랜드에 대한 기타 [!DNL Adobe Experience Cloud] 솔루션에 대한 옵트아웃을 나타냅니다. 아래 표에는 글로벌 옵트아웃에 사용되는 방법이 나와 있습니다.

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
   <td colname="col2"> <p><a href="https://www.adobe.com/kr/privacy/opt-out.html#customeruse" format="http" scope="external">개인 정보 보호 선택 사항 페이지</a>에서는 최종 사용자가 Adobe Experience Cloud 광고 솔루션(Audience Manager 포함)에 의한 데이터 수집을 제어하고 옵트아웃할 수 있도록 해주는 1번의 클릭 기능을 제공합니다. 특히 개인 정보 보호 선택 사항 페이지의 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">비즈니스 고객 섹션</a>을 참조하십시오. </p> </td> 
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

파트너 수준 옵트아웃을 사용하면 특정 [!DNL Audience Manager] 파트너를 통해 데이터 수집에서 사용자를 옵트아웃할 수 있습니다. [!DNL CRM] ID 및 해시된 이메일 주소를 포함하여 장치 간 ID에 대한 파트너 수준 옵트아웃 요청을 보낼 수 있습니다.

선언된 ID 호출로 파트너 수준 옵트아웃을 수행하면

* [CRM ID](../../reference/ids-in-aam.md)가 데이터 수집에서 옵트아웃됩니다.
* [CRM ID](../../reference/ids-in-aam.md)에 연결된 마지막 장치 ID([Audience Manager 고유 사용자 ID](../../reference/ids-in-aam.md))가 데이터 수집에서 옵트아웃됩니다.
* [!DNL Audience Manager] 는  [!DNL CRM] ID 및  [!DNL CRM] ID에 연결된 마지막 장치 ID에 대한 모든 데이터 수집, 세그먼테이션 또는 활성화를 중단합니다.
* [!DNL Audience Manager] 모든 세그먼트에서 옵트아웃  [!DNL CRM] ID 및 마지막 장치 ID의 세그먼트를 해제합니다.
* [!UICONTROL Destination] 파트너는  [!DNL CRM] ID 및 마지막 장치 ID에 대한 세그먼트 해제 요청을 받습니다. 세그먼테이션 해제는 [실시간](data-privacy-requests.md#aam-partners-with-unsegmentation) 대상과 배치 대상 모두에 대해 작동합니다.
* 이전 데이터는 삭제되지 않습니다.

[!DNL Audience Manager]이(가) 파트너 수준 옵트아웃 요청을 받으면 [!DNL DCS]에 의해 반환되는 [!DNL JSON]에 [!DNL Audience Manager] 사용자 ID 대신 [!UICONTROL "Encountered opt out tag"] 메시지와 함께 [ 오류 코드 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)이(가) 포함됩니다.

`d_cid` 및 `d_cid_ic` 키-값 쌍으로 선언된 ID 옵트아웃 요청을 만들 수 있습니다. `d_dpid` 및 `d_dpuuid`와 같은 기존 매개 변수는 여전히 작동하지만 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../../reference/cid.md)를 참조하십시오. 예에서 *기울임꼴*&#x200B;은 가변 자리 표시자를 나타냅니다.

#### [!DNL CID] 및 [!DNL CID_IC] 포함 옵트아웃

설명 및 구문이 필요하면 [선언된 ID에 대한 URL 변수 및 구문](../../features/declared-ids.md#variables-and-syntax)을 참조하십시오.

| 옵트아웃에 사용하는 값 | 코드 샘플 |
|--- |--- |
| 데이터 공급자 ID 및 사용자 ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 통합 코드 및 사용자 ID. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| `d_cid` 및 `d_cid_ic` 키-값 쌍이 여러 개 있습니다. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 장치 ID 호출을 사용한 파트너 수준 옵트아웃

파트너 수준 옵트아웃을 사용하면 특정 [!DNL Audience Manager] 파트너를 통해 데이터 수집에서 사용자를 옵트아웃할 수 있습니다. [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)를 다음과 같이 호출하여 브랜드의 특정 기기 ID에서 데이터 수집을 옵트아웃할 수 있습니다.

| 옵트아웃에 사용하는 값 | 코드 샘플 |
|--- |--- |
| [!DNL Audience Manager] [!DNL Unique User ID](`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| [!DNL Experience Cloud] ID(`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

[Audience Manager의 ID 색인](/help/using/reference/ids-in-aam.md)에서 `uuid`, `mid` 및 `imsOrgId`에 대해 자세히 알아보십시오.

장치 ID 호출로 파트너 수준 옵트아웃을 수행하면

* 장치 ID가 데이터 수집에서 옵트아웃됩니다.
* [!DNL Audience Manager] 파트너의 모든 데이터 수집, 세그멘테이션 또는 활성화가 종료되며 장치 ID는 계속 진행됩니다.
* [!DNL Audience Manager] 모든 세그먼트에서 장치 ID의 세그먼트를 해제합니다.
* 대상 파트너가 장치 ID에 대한 세그먼트 해제 요청을 받습니다. 세그먼테이션 해제는 [실시간](data-privacy-requests.md#aam-partners-with-unsegmentation) 대상과 배치 대상 모두에 대해 작동합니다.
* 이전 데이터는 삭제되지 않습니다.

## [!DNL Audience Manager] 세분화 기능을 갖춘 파트너  {#aam-partners-with-unsegmentation}

소비자 데이터 개인 정보 보호 요청을 자동화하기 위해 [!DNL Audience Manager]은(는) 활성화 파트너에게 데이터 주체의 삭제 요청을 세그먼트 해제(또는 세그먼트 제거) 정보를 보내 통보하려고 합니다.

그러나 일부 활성화 파트너는

1. [!DNL Audience Manager] 및/또는
2. 30일에 한 번 이상 [!DNL Audience Manager]에서 업데이트를 받을 수 없습니다.

이러한 경우 [!DNL Audience Manager]을(를) 통해 자동화된 방식으로 정품 인증 파트너에게 삭제 요청을 보낼 수 없습니다.

세그먼트 해제를 지원하는 활성화 파트너를 알려면 [장치 기반 대상 목록](/help/using/features/destinations/device-based-destinations-list.md)을 참조하십시오.[!DNL Audience Manager]

## 데이터 수정 요청 {#correction}

[!DNL Audience Manager]이(가) 데이터의 소스가 아닌 경우 [!DNL Audience Manager]에 데이터 교정에 대한 제한된 역할이 있습니다. 정정은 소비자가 잘못된 [!UICONTROL trait]/[!UICONTROL segment] 또는 원하는 [!UICONTROL trait]/[!UICONTROL segment]의 자격이 있음을 의미할 수 있습니다.

[!DNL Audience Manager] 고객은 사용자 프로필에 대해 관련 신호/트레이트/세그먼트를 캡처하고 이 정보를  [오프라인 데이터 ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 인사이트를 통해 다음으로 보낼 수 있습니다 [!DNL Audience Manager]. 사용자가 동작을 반복할 경우 원래 [!UICONTROL trait] 및 [!UICONTROL segments]에 대한 자격이 계속 부여됩니다.
