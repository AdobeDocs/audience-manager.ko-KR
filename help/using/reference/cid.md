---
description: d_dpid 및 d_dpuuid 대신 d_cid 또는 d_cid_ic을 사용하도록 코드를 업데이트합니다. DPID 및 DPUUID 변수는 계속 작동하지만 더 이상 사용되지 않습니다. 여기에는 d_ 접두사가 없는 DPID 및 DPUUID 변형이 포함됩니다.
seo-description: d_dpid 및 d_dpuuid 대신 d_cid 또는 d_cid_ic을 사용하도록 코드를 업데이트합니다. DPID 및 DPUUID 변수는 계속 작동하지만 더 이상 사용되지 않습니다. 여기에는 d_ 접두사가 없는 DPID 및 DPUUID 변형이 포함됩니다.
seo-title: CID가 DPID 및 DPUUID 대체
solution: Audience Manager
title: CID가 DPID 및 DPUUID 대체
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

및 대신 `d_cid` 또는 `d_cid_ic` 를 사용하도록 코드를 `d_dpid` 업데이트하십시오 `d_dpuuid`. DPID 및 DPUUID 변수는 계속 작동하지만 더 이상 사용되지 않습니다. 여기에는 DPID 및 DPUUID 변형이 포함되며, `d_ prefix`

## DPID 및 DPUUID:검토 {#dpid-dpuuid-review}

DPID 및 DPUUID는 데이터 공급자 ID와 사용자 ID가 포함된 키-값 쌍입니다. 이 키-값 쌍은 공급자 ID를 사용자 ID에 연결합니다. 이벤트 호출 동안, 인바운드 동기화 이벤트에 대해, ID 호출에 대해 데이터를 전송합니다. ID와 [!DNL Audience Manager]기타 서비스 또는 기능이 없으면 ID를 일치시키거나 동기화할 수 없습니다. 이러한 변수는 아래 표시된 `d_` 접두사와 함께 또는 없이 표현되는 경우가 있습니다. 코드에서 *기울임꼴은* 변수 자리 표시자를 나타냅니다.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 구문 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 ID(DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>데이터 공급자 ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>데이터 공급자 ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 고유 사용자 ID(DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>데이터 공급자 고유 사용자 ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>데이터 공급자 고유 사용자 ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

이러한 키-값 쌍은 여전히 작동하지만 더 이상 사용되지 않습니다. CID 또는 CID_IC를 대신 사용하도록 코드를 업데이트해야 합니다.

## CID 및 CID_IC:정보 {#cid-cidic-about}

CID 및 CID_IC 키-값 쌍은 DPID 및 DPUUID를 대체합니다. DPID 및 DPUUID와 동일한 기능을 제공하지만 단일 키-값 쌍에 데이터 공급자 ID(또는 통합 코드)와 사용자 ID가 포함되어 있으므로 보다 효율적입니다. 각 키-값 쌍에서:

* = 기호는 키와 관련 값을 구분합니다.
* 인쇄되지 않는 ASCII 문자 %01은 값을 구분합니다.

`d_cid` 및 아래 표시된 구문을 `d_cid_ic` 사용하십시오. 코드에서 *기울임꼴은* 변수 자리 표시자를 나타냅니다.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 구문 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>고객 ID(CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>데이터 공급자 ID</i>%01<i>사용자 ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>고객 ID 통합 코드(CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>통합 코드</i>%01<i>사용자 ID</i></code> </p> <p> 통합 코드는 <span class="term"> Audience Manager에서 할당한 데이터 소스 ID 대신 사용할 수 있는 대체 ID입니다</span> <span class="keyword"></span>. 통합 <a href="../features/manage-datasources.md#create-data-source"> 코드를 구성해야 하는</a> 경우 데이터 소스 만들기를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

선언된 [ID에 대한 URL 변수 및 구문을 참조하십시오](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>액세스 권한이 있는 데이터 소스 및 전역 [공유 데이터 소스에](../features/datasources-list-and-settings.md#settings-menu-options)대해 통합 코드를 사용할 수 있습니다. 예를 들어 모바일 식별자 데이터 소스로 작업할 때 통합 코드를 사용할 수 있습니다. 아래에 지정된 대로 다음 통합 코드를 사용하십시오.

* **GAID용 DSID** _20914 - Android 운영 체제를 실행하는 장치를 나타냅니다.
* **iOS 운영** 체제를 실행하는 장치를 나타내는 IDFA용 DSID_20915

**예**

다음 표에서는 이벤트 유형별로 예제를 제공합니다.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이벤트 유형 </th> 
   <th colname="col2" class="entry"> 예 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>이벤트 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">새로운 기능: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">가치 하락: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>인바운드 동기화(IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">새로운 기능: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">가치 하락: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID(ID) 생성 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">새로운 기능: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">가치 하락: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

각 호출에는 다음과 같은 여러 `d_cid` 및 `d_cid_ic` 키 값 쌍을 포함할 수도 있습니다.

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## 개발 팀의 중요 고려 사항 {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>항목 </p> </th> 
   <th colname="col2" class="entry"> <p>설명 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL 인코딩 </p> </td> 
   <td colname="col2"> <p>개발 팀은 CID 키-값 쌍의 다음 변수에 URL 인코딩을 <i>적용해야 합니다</i> . </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> 사용자 ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> 통합 코드</code> </li> 
     </ul> </p> <p> <p>참고:사용자 ID와 통합 코드를 문자열로 <i>연결하기 전에</i> URL을 인코딩해야 합니다. 두 변수를 구분하는 ASCII 문자 %01은 URL 인코딩에서 캡처되지 않아야 하기 때문입니다. </p> </p> <p>URL 인코딩은 예약되었거나 안전하지 않은 문자(예: + 또는 =)가 포함되어 있는 사용자 ID 및 통합 코드가 Adobe 서버로 올바르게 전송되도록 합니다. </p> <p>참조용으로 <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII 인코딩 테이블을</a> 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>전역 공유 데이터 소스에 대한 통합 코드 사용 </p> </td> 
   <td colname="col2"> <p>액세스 권한이 있는 데이터 소스 및 전역 <a href="../features/datasources-list-and-settings.md#settings-menu-options"> 공유 데이터 소스에</a>대해 통합 코드를 사용할 수 있습니다. 예를 들어 모바일 식별자 데이터 소스로 작업할 때 통합 코드를 사용할 수 있습니다. 아래에 지정된 대로 다음 통합 코드를 사용하십시오. </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>GAID용 DSID</b> _20914 - Android 운영 체제를 실행하는 장치를 나타냅니다. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>iOS 운영</b> 체제를 실행하는 장치를 나타내는 IDFA용 DSID_20915 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

