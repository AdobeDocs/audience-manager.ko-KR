---
description: Adobe는 옵트아웃 관리와 관련하여 모든 업계 표준을 준수합니다. Audience Manager에서 지원하는 옵트아웃 유형에 대한 자세한 내용을 살펴보십시오.
seo-description: Adobe는 옵트아웃 관리와 관련하여 모든 업계 표준을 준수합니다. Audience Manager에서 지원하는 옵트아웃 유형에 대한 자세한 내용을 살펴보십시오.
seo-title: 옵트아웃 관리
solution: Audience Manager
title: 옵트아웃 관리
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# 옵트아웃 관리{#opt-out-management}

Adobe는 옵트아웃 관리와 관련하여 모든 업계 표준을 준수합니다. Audience Manager에서 지원하는 옵트아웃 유형에 대한 자세한 내용을 살펴보십시오.

## 전역 옵트아웃 {#global-opt-out}

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
   <td colname="col2"> <p>아래의 DCS API를 호출하고 Audience Manager 사용자 ID를 포함시켜 모든 Audience Manager 브랜드의 데이터 수집을 옵트아웃할 <a href="../../reference/ids-in-aam.md"> 수 있습니다 </a> </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=1234567890123456789012345689012345678;dextp=12;HUNDP=12 12형 </code> </p> <p>따라서 제출된 Audience Manager 사용자 ID에 대해 <code>demdex=NOTARGET</code> 및 <code>dextp=NOTARGET</code> 쿠키를 설정합니다. </p> </td> 
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

* Audience Manager는 앞으로 모든 데이터 수집, 세분화 또는 활성화를 중단합니다.
* 내역 데이터는 120일 후 사용자 프로필에서 제거됩니다.

## 파트너 수준 옵트아웃 {#partner-opt-out}

파트너 수준 옵트아웃은 특정 Audience Manager 파트너의 데이터 수집을 거부할 수 있도록 허용합니다. 파트너 수준 옵트아웃은 아래 섹션에 설명된 [대로](../../features/declared-ids.md) 선언된 ID 호출 및 장치 ID 호출을 사용하여 작동합니다.

### 선언된 ID 호출이 있는 파트너 수준 옵트아웃

선언된 ID 호출이 있는 파트너 수준 옵트아웃을 팔로우합니다.

* CRM ID에[연결된 마지막 장치 ID](../../reference/ids-in-aam.md)(Audience Manager [고유 사용자 ID](../../reference/ids-in-aam.md) )는데이터 수집에서 옵트아웃됩니다.
* Audience Manager는 CRM ID에 연결된 마지막 장치 ID에 대해 모든 데이터 수집, 세그멘테이션 또는 활성화를 중단합니다.
* 내역 데이터는 삭제되지 않습니다.

<br/>

**옵트아웃 호출**

Audience Manager가 파트너 수준 옵트아웃 요청을 받으면 DCS에서 반환되는 JSON에 Audience Manager 사용자 ID 대신 메시지와 [](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes)[!UICONTROL "Encountered opt out tag"]함께 오류 코드 171이 포함됩니다.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**예**

선언된 ID 옵트아웃 요청은 `d_cid` 및 `d_cid_ic` 키-값 쌍으로 할 수 있습니다. 및 같은 기존 매개 변수는 `d_dpid` 여전히 작동하지만 `d_dpuuid` 더 이상 사용되지 않는 것으로 간주됩니다. [CID가 DPID 및 DPUUID 대체](../../reference/cid.md)를 참조하십시오. In the examples, *italics* indicates a variable placeholder.

**CID 및 CID_IC가 있는 옵트아웃**

설명 및 구문은 선언된 ID [에 대한 URL 변수 및 구문을 참조하십시오](../../features/declared-ids.md#variables-and-syntax).

| 다음을 사용하여 옵트아웃 | 코드 샘플 |
|--- |--- |
| 데이터 공급자 ID 및 사용자 ID입니다. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| 통합 코드 및 사용자 ID입니다. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| 여러 개의 d_cid 및 d_cid_ic 키-값 쌍. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### 파트너 수준 옵트아웃(장치 ID 호출)

DCS API를 다음과 같이 호출하여 브랜드의 특정 장치 ID에 대한 데이터 수집에서 옵트아웃할 수 [있습니다](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md).

| 다음을 사용하여 옵트아웃 | 코드 샘플 |
|--- |--- |
| Audience Manager 고유 사용자 ID(`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Experience Cloud ID(`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Audience Manager `uuid`의 ID `mid` 인덱스와 자세한 내용을 참조하십시오 `imsOrgId` [](/help/using/reference/ids-in-aam.md).

장치 ID 호출이 있는 파트너 수준 옵트아웃을 따릅니다.

* 장치 ID 파섹
* Audience Manager는 파트너의 모든 데이터 수집, 세그멘테이션 또는 활성화를 중단하고 장치 ID를 진행합니다.
* 내역 데이터는 삭제되지 않습니다.
