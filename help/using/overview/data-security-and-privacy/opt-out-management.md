---
description: Adobe는 옵트아웃 관리와 관련하여 모든 업계 표준을 준수합니다. Audience Manager에서 지원하는 옵트아웃 유형에 대한 자세한 정보는에서 확인하십시오.
seo-description: Adobe는 옵트아웃 관리와 관련하여 모든 업계 표준을 준수합니다. Audience Manager에서 지원하는 옵트아웃 유형에 대한 자세한 정보는에서 확인하십시오.
seo-title: 옵트아웃 관리
solution: Audience Manager
title: 옵트아웃 관리
uuid: 61 b 43 e 0 e-bfe 3-497 e-ade 2-6 a 942 a 98407 e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Opt-out Management{#opt-out-management}

Adobe는 옵트아웃 관리와 관련하여 모든 업계 표준을 준수합니다. Audience Manager에서 지원하는 옵트아웃 유형에 대한 자세한 정보는에서 확인하십시오.

## Global Opt-Out {#global-opt-out}

글로벌 옵트아웃은 모든 브랜드를 위한 Audience Manager와 다른 Adobe Experience Cloud 솔루션의 옵트아웃을 나타냅니다. 아래 표에는 전역 옵트아웃에 사용된 방법이 나와 있습니다.

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
   <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page </a> provides 1-click features that let your end users control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section </a> of the Privacy Choices page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager로 직접 API 호출 </p> </td> 
   <td colname="col2"> <p>You can opt-out from data collection by all Audience Manager brands by making a call to the DCS API below and include the <a href="../../reference/ids-in-aam.md"> Audience Manager User ID </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex = 12345678901234567890123456789012345678; dextp = 12; dst = 12 " </code> </p> <p>As a result, we will set <code>demdex=NOTARGET</code> and <code>dextp=NOTARGET</code> cookies for the submitted Audience Manager User ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 장치 </p> </td> 
   <td colname="col2"> <p>다음을 위한 옵트아웃 및 개인 정보 설정을 참조하십시오. </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android 디바이스 </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS 장치 </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

최종 사용자는 업계 표준 파트너의 웹 사이트를 방문하여 글로벌 데이터 수집을 거부할 수도 있습니다.

* [Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [NAI (Network Advertising Initiative](https://optout.networkadvertising.org/?c=1#!/)).

위에 설명된 옵트아웃 요청을 따르십시오.

* Audience Manager는 모든 데이터 수집, 세분화 또는 활성화를 중단합니다.
* 120 일 후 사용자 프로필에서 내역 데이터가 제거됩니다.

## Partner Level Opt-Out {#partner-opt-out}

파트너 수준의 옵트아웃 허용은 특정 Audience Manager 파트너의 데이터 수집에서 옵트아웃합니다. The partner-level opt-out works with [Declared ID](../../features/declared-ids.md) calls and Device ID calls, as described in the sections below.

### 선언된 ID 호출을 사용하는 파트너 수준 옵트아웃

선언된 ID 호출이 있는 파트너 수준 옵트아웃은 다음과 같습니다.

* The last device ID ([Audience Manager Unique User ID](../../reference/ids-in-aam.md)) linked to the [CRM ID](../../reference/ids-in-aam.md) is opted out of data collection.
* Audience Manager는 CRM ID에 연결된 마지막 장치 ID에 대한 모든 데이터 수집, 세그멘테이션 또는 활성화를 중지합니다.
* 내역 데이터는 삭제되지 않습니다.

<br/>

**옵트아웃 호출**

When Audience Manager receives a partner-level opt-out request, the JSON returned by the DCS contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the Audience Manager user ID.

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

`d_cid` 키와 `d_cid_ic` 키-값 쌍으로 선언된 ID 옵트아웃 요청을 만들 수 있습니다. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. [CID가 DPID 및 DPUUID 대체](../../reference/cid.md)를 참조하십시오. In the examples, *italics* indicates a variable placeholder.

**CID 및 CID_ IC 사용 옵트아웃**

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../../features/declared-ids.md#variables-and-syntax).

| 옵트아웃 | 코드 샘플 |
|--- |--- |
| 데이터 공급자 ID 및 사용자 ID 입니다. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| 통합 코드 및 사용자 ID. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| 여러 d_ cid 및 d_ cid_ ic 키-값 쌍. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### 장치 ID 호출을 통한 파트너 수준 옵트아웃

You can opt-out from data collection on a given device ID for a brand by making the following calls to the [DCS API](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| 옵트아웃 | 코드 샘플 |
|--- |--- |
| An Audience Manager Unique User ID (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An Experience Cloud ID (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Read more about `uuid`, `mid` and `imsOrgId` in the [Index of IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

장치 ID 호출이 있는 파트너 수준 옵트아웃은 다음과 같습니다.

* 장치 ID는 데이터 수집을 옵트아웃합니다.
* Audience Manager는 파트너에 대해 모든 데이터 수집, 세분화 또는 활성화를 중단하고 장치 ID를 진행합니다.
* 내역 데이터는 삭제되지 않습니다.
