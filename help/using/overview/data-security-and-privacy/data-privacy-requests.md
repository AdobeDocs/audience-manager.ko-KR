---
description: 이 문서에서는 Audience Manager의 데이터 개인 정보 보호 규정 준수와 관련된 기술을 다룹니다.
seo-description: 이 문서에서는 Audience Manager의 데이터 개인 정보 보호 규정 준수와 관련된 기술을 다룹니다.
seo-title: 데이터 개인 정보 요청
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: 데이터 개인 정보 요청
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 1a7f207b593ea783e20a0398bb0d543628253049

---


# 데이터 개인 정보 요청 {#data-privacy-requests}

## 개요 {#overview}

이 문서에서는 개인 정보 보호 서비스 UI 및 [](https://gdprui.cloud.adobe.io/) **[!DNL Privacy Service API]**

이러한 툴을 사용하면 GDPR 및 CPA에서 수행한 소비자 데이터 개인 정보 보호 요청을 전송할 수 있습니다.

이 문서를 읽기 전에 GDPR [용어집](../data-security-and-privacy/aam-gdpr-glossary.md) 및 CPA [용어집을](aam-ccpa-glossary.md)통해 여기에서 사용되는 용어를 보다잘 이해하는 것이 좋습니다.

다음 두 가지 방법으로 Audience Manager에서 소비자 데이터에 액세스하고 삭제할 개별 요청을 제출할 수 있습니다.

* 개인 정보 [서비스 UI를 통해](https://gdprui.cloud.adobe.io/). 설명서를 [참조하십시오](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Through the **[!DNL Privacy Service API]**. 설명서[및 API 참조 설명서를](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)여기에서[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)참조하십시오.

개별 데이터 개인 정보 보호 요청을 전송할 때 Audience Manager 식별자 **[섹션에 설명된 대로 해당](data-privacy-ids.md)**네임스페이스 ID(데이터 소스 ID)와 함께 모든 Audience Manager ID를 제출할 수 있습니다.

개인정보 보호 [서비스는](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 두 가지 유형의 요청을 지원합니다.데이터 액세스 및 데이터 삭제 요청

## 데이터 액세스 요청 {#access-data}

개인 정보 서비스 UI( [여기](https://gdprui.cloud.adobe.io/) 설명서)를 통해 [개별 데이터 액세스 요청을 전송할 수 있습니다](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md). [!DNL Privacy Service API] 이 [경우](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) (설명서 및 참조 [!DNL API] [](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml))를 호출하거나 참조할 수 있습니다.

개인정보 [보호 서비스](https://gdprui.cloud.adobe.io/) UI를 사용하여 [!UICONTROL Request Builder] 또는 [!DNL JSON] 파일을 업로드하여 새 작업 요청을 만들 수 있습니다.

유효한 [!DNL JSON] 파일의 모양을 확인하려면 샘플 JSON을 [다운로드할 수 있습니다](../data-security-and-privacy/assets/access_request.json).

Adobe는 법률에 의해 규정된 기간 내에 귀하의 데이터 개인 정보 보호 요청을 준수하기 위한 귀하의 약속을 이해합니다.

## 데이터 삭제 요청{#delete-data}

개인정보 보호 서비스 UI( [여기](https://gdprui.cloud.adobe.io/) 설명서 [)](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)를 [!DNL Privacy Service API] 통해 [또는 데이터 삭제 요청(설명서](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 및 API [참조](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml))을 여기에서 호출하여 보낼 수 있습니다.

개인정보 [보호 서비스](https://gdprui.cloud.adobe.io/) UI를 사용하여 [!UICONTROL Request Builder] 또는 [!DNL JSON] 파일을 업로드하여 새 작업 요청을 만들 수 있습니다.

유효한 [!DNL JSON] 파일의 모양을 확인하려면 샘플 JSON을 [다운로드할 수 있습니다](../data-security-and-privacy/assets/access_request.json).

Adobe는 30일 이내에 데이터 개인 정보 보호 고객의 요청을 존중해야 한다는 귀하의 약속을 이해합니다. 이러한 이유로 Adobe는 가능한 한 빨리 데이터 삭제 요청을 처리하기 위해 최선을 다하고 있습니다.

소비자 데이터 삭제 요청에 대한 응답으로 Audience Manager는 요청에 포함된 Audience Manager 식별자와 연결된 트레이트 및 세그먼트를 삭제합니다. 또한 Audience Manager에서 추가 데이터 수집을 옵트아웃한 개인의 Audience Manager 식별자 및 해당 ID 매핑이 제거됩니다.

상호 장치 ID 또는 쿠키 ID와 같은 선언된 ID를 데이터 개인 정보 [!DNL CRM] 보호 요청에서 Audience Manager는 연결된 모든 장치(선언된 ID당 최대 100개의 장치)에서 필요한 삭제를 수행합니다.

Audience Manager는 특정 데이터 삭제를 요청하는 데이터 주체의 세그먼트 정보를 제거하여 삭제 요청에 대해 활성화 파트너에게 알리려고 시도합니다. 그러나 일부 정품 인증 파트너는 다음과 같습니다.

1. Audience Manager 및/또는
2. Audience Manager에서 30일 미만의 빈도를 업데이트할 수 없습니다. 이러한 경우 Audience Manager 고객은 Audience Manager를 통해 자동화된 방식으로 활성화 파트너에게 삭제 요청을 보낼 수 없습니다.

이러한 경우 Audience Manager를 통해 자동 방식으로 활성화 파트너에게 삭제 요청을 보낼 수 없습니다.

파트너 Excel [시트를](assets/AAM-Partners-October2019.xlsx) 다운로드하여 Audience Manager 활성화 파트너가 세그먼트 해제를 지원하는 경우를 확인하십시오.

## 옵트아웃 요청 {#opt-out-requests}

Audience Manager는 옵트아웃 관리와 관련하여 업계 표준을 지원합니다. Audience Manager에서 지원하는 옵트아웃 유형에 대한 자세한 내용을 살펴보십시오.

데이터 액세스 및 삭제 요청은 개인정보 보호 서비스를 통해 처리되지만 [현재](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)옵트아웃 요청은 DCS API를 통해 지원됩니다. 옵트아웃 API 호출이 어떻게 표시되어야 하는지 살펴보십시오.

### 전역 옵트아웃 요청

글로벌 옵트아웃은 Audience Manager와 모든 브랜드를 위한 기타 Adobe Experience Cloud 솔루션 간의 옵트아웃을 나타냅니다. 아래 표에는 전역 옵트아웃에 사용되는 방법이 나와 있습니다.

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵트아웃 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>개인 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 정보 보호 선택 페이지에서는 최종 사용자가 Adobe Experience Cloud 광고 솔루션(Audience Manager 포함)을 통해 데이터 수집을 제어하고 옵트아웃할 수 있는 1회 클릭 기능을 </a> 제공합니다. 특히 개인 정보 선택 페이지의 <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> 비즈니스 고객 섹션을 </a> 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager에 대한 직접 API 호출 </p> </td> 
   <td colname="col2"> <p>사용자는 아래 DCS API를 호출하고 Audience Manager 사용자 ID를 포함시켜 모든 Audience Manager 브랜드의 데이터 수집을 거부할 수 <a href="../../reference/ids-in-aam.md"> 있습니다 </a>. </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>따라서 제출된 Audience Manager 사용자 ID에 대한 <code>demdex=NOTARGET</code> 쿠키 및 <code>dextp=NOTARGET</code> 쿠키를 설정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 장치 </p> </td> 
   <td colname="col2"> <p>옵트아웃 및 개인 정보 설정을 참조하십시오. </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android 디바이스 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS 장치 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

또한 최종 사용자는 Adobe의 업계 표준 파트너의 웹 사이트를 방문하여 글로벌 데이터 수집을 거부할 수 있습니다.

* [DAA(Digital Advertising Alliance)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative(NAI)](https://optout.networkadvertising.org/?c=1#!/).

위에 설명된 옵트아웃 요청을 따릅니다.

* 사용자가 브라우저 쿠키를 지우지 않는 한 Audience Manager는 모든 데이터 수집, 세그멘테이션 또는 활성화를 중단합니다.
* 내역 데이터는 120일 후 사용자 프로필에서 제거됩니다.

### 선언된 ID 호출이 있는 파트너 수준 옵트아웃

파트너 수준 옵트아웃을 사용하면 특정 Audience Manager 파트너의 데이터 수집에서 사용자를 옵트아웃할 수 있습니다. CRM ID 및 해시된 이메일 주소를 포함하여 장치 간 ID에 대한 파트너 수준 옵트아웃 요청을 보낼 수 있습니다.

선언된 ID 호출이 있는 파트너 수준 옵트아웃을 팔로우합니다.

* CRM [ID가](../../reference/ids-in-aam.md) 데이터 수집에서 옵트아웃됩니다.
* CRM ID에[연결된 마지막 장치 ID](../../reference/ids-in-aam.md)(Audience Manager [고유 사용자 ID](../../reference/ids-in-aam.md) )는데이터 수집에서 옵트아웃됩니다.
* Audience Manager는 CRM ID 및 CRM ID에 연결된 마지막 장치 ID에 대해 모든 데이터 수집, 세그멘테이션 또는 활성화를 중단합니다.
* Audience Manager는 모든 세그먼트에서 옵트아웃 CRM ID와 마지막 장치 ID의 세그먼트를 해제합니다.
* 대상 파트너는 CRM ID 및 마지막 장치 ID에 대한 세그먼트 해제 요청을 받습니다. 세그먼테이션은 [실시간](data-privacy-requests.md#aam-partners-with-unsegmentation) 및 배치 대상에 모두 작동합니다.
* 내역 데이터는 삭제되지 않습니다.

Audience Manager가 파트너 수준 옵트아웃 요청을 받으면 DCS에서 반환되는 JSON에 Audience Manager 사용자 ID 대신 메시지와 [](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)[!UICONTROL "Encountered opt out tag"]함께 오류 코드 171이 포함됩니다.

선언된 ID 옵트아웃 요청은 `d_cid` 및 `d_cid_ic` 키-값 쌍으로 할 수 있습니다. 및 같은 기존 매개 변수는 `d_dpid` 여전히 작동하지만 `d_dpuuid` 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../../reference/cid.md)를 참조하십시오. In the examples, *italics* indicates a variable placeholder.

#### CID 및 CID_IC가 있는 옵트아웃

설명 및 구문은 선언된 ID [에 대한 URL 변수 및 구문을 참조하십시오](../../features/declared-ids.md#variables-and-syntax).

| 다음을 사용하여 옵트아웃 | 코드 샘플 |
|--- |--- |
| 데이터 공급자 ID 및 사용자 ID입니다. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| 통합 코드 및 사용자 ID입니다. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| 여러 개의 d_cid 및 d_cid_ic 키-값 쌍. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### 파트너 수준 옵트아웃(장치 ID 호출)

파트너 수준 옵트아웃을 사용하면 특정 Audience Manager 파트너의 데이터 수집에서 사용자를 옵트아웃할 수 있습니다. DCS API를 다음과 같이 호출하여 브랜드의 특정 장치 ID에 대한 데이터 수집에서 옵트아웃할 수 [있습니다](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md).

| 다음을 사용하여 옵트아웃 | 코드 샘플 |
|--- |--- |
| Audience Manager 고유 사용자 ID(`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID(`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Audience Manager `uuid`의 ID `mid` 인덱스와 자세한 내용을 참조하십시오 `imsOrgId` [](/help/using/reference/ids-in-aam.md).

장치 ID 호출이 있는 파트너 수준 옵트아웃을 따릅니다.

* 장치 ID 파섹
* Audience Manager는 파트너의 모든 데이터 수집, 세그멘테이션 또는 활성화를 중단하고 장치 ID를 진행합니다.
* Audience Manager는 모든 세그먼트에서 장치 ID의 세그먼트를 해제합니다.
* 대상 파트너는 장치 ID에 대한 세그먼트 해제 요청을 받습니다. 세그먼테이션은 [실시간](data-privacy-requests.md#aam-partners-with-unsegmentation) 및 배치 대상에 모두 작동합니다.
* 내역 데이터는 삭제되지 않습니다.

## Audience Manager 파트너, 세분화 해제 기능 {#aam-partners-with-unsegmentation}

소비자 데이터 개인 정보 보호 요청을 자동화하기 위해 Audience Manager는 활성화 파트너에게 데이터 주체의 삭제 요청을 세그먼트 해제(또는 세그먼트 제거) 정보를 전송하여 통보하려고 시도합니다.

그러나 정품 인증 파트너 중 일부는 다음과 같습니다.

1. Audience Manager 및/또는
2. 30일 동안 Audience Manager에서 업데이트를 한 번 이상 받을 수 없습니다.

이러한 경우 Audience Manager를 통해 자동 방식으로 활성화 파트너에게 삭제 요청을 보낼 수 없습니다.

장치 기반 대상 [목록을](/help/using/features/destinations/device-based-destinations-list.md) 참조하여 Audience Manager 활성화 파트너가 세그먼트 해제를 지원하는지 확인하십시오.

## 데이터 수정 요청 {#correction}

Audience Manager가 데이터의 소스가 아니기 때문에 Audience Manager에는 데이터 교정을 위한 제한된 역할이 있습니다. 정정은 소비자가 잘못된 트레이트/세그먼트에서 실격 처리하거나 원하는 트레이트/세그먼트에 자격이 있음을 의미할 수 있습니다.

Audience Manager 고객은 사용자 프로필에 대해 관련 신호/트레이트/세그먼트를 캡처하고 [오프라인 데이터 인제스트를](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 통해 Audience Manager에 이 정보를 전송할 수 있습니다. 사용자가 동작을 반복할 경우 원래 트레이트 및 세그먼트에 계속 자격을 얻게 됩니다.
