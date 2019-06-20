---
description: d_ dpid 및 d_ dpuuid 대신 d_ cid 또는 d_ cid_ ic를 사용하도록 코드를 업데이트합니다. dpid 및 dpuuid 변수는 계속 작동하지만 더 이상 사용되지 않는 것으로 간주해야 합니다. 여기에는 d_ prefix 없이 dpid 및 dpuuid 변형이 포함됩니다.
seo-description: d_ dpid 및 d_ dpuuid 대신 d_ cid 또는 d_ cid_ ic를 사용하도록 코드를 업데이트합니다. dpid 및 dpuuid 변수는 계속 작동하지만 더 이상 사용되지 않는 것으로 간주해야 합니다. 여기에는 d_ prefix 없이 dpid 및 dpuuid 변형이 포함됩니다.
seo-title: CID가 DPID 및 DPUUID를 대신함
solution: Audience Manager
title: CID가 DPID 및 DPUUID를 대신함
uuid: 3641 EAC 5-B 19 E -45 D 5-BC 1 C -35 A 23 B 4 BAB 8 C
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Update your code to use `d_cid` or `d_cid_ic` instead of `d_dpid` and `d_dpuuid`. dpid 및 dpuuid 변수는 계속 작동하지만 더 이상 사용되지 않는 것으로 간주해야 합니다. This includes DPID and DPUUID variants without the `d_ prefix`.

## DPID and DPUUID: A Review {#dpid-dpuuid-review}

dpid 및 dpuuid는 데이터 공급자 ID와 사용자 ID가 포함된 키-값 쌍입니다. 이러한 키-값은 사용자 ID에 공급자 ID를 연결합니다. 이들은 이벤트 호출 중에, 인바운드 동기화 이벤트 및 ID 호출에 대해 데이터를 전송합니다. Without them, [!DNL Audience Manager], and other services or features, would not have a way to match and synchronize IDs. These variables are sometimes expressed with or without the `d_` prefix as shown below. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 구문 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPID (데이터 공급자 ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_ dpid =<i>데이터 공급자 ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>DPID =<i>데이터 공급자 ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>데이터 공급자 고유 사용자 ID (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_ dpuuid =<i>데이터 공급자 고유한 사용자 ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>DPUUID =<i>데이터 공급자 고유한 사용자 ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

이러한 키-값 쌍은 여전히 작동하지만 더 이상 사용되지 않습니다. 대신 CID 또는 CID_ IC를 사용하도록 코드를 업데이트해야 합니다.

## CID and CID_IC: About {#cid-cidic-about}

cid 및 cid_ ic 키-값 쌍은 dpid 및 dpuuid를 대체합니다. DPID 및 DPUUID와 동일한 기능을 제공하지만 데이터 공급자 ID (또는 통합 코드) 와 단일 키-값 쌍에 사용자 ID를 포함하므로 보다 효율적입니다. 각 키-값 쌍:

* = 기호는 키와 관련 값을 구분합니다.
* 인쇄되지 않는 ASCII 문자 % 01는 값을 구분합니다.

`d_cid` 아래 표시된 구문을 `d_cid_ic` 사용하십시오. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 구문 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>고객 ID (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid =<i>데이터 공급자 ID</i>% 01<i>사용자 ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>고객 ID 통합 코드 (CID_ IC) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid_ ic =<i>통합 코드</i>% 01<i>사용자 ID</i></code> </p> <p> <span class="term"> 통합 코드는</span> <span class="keyword"> Audience Manager</span>에서 할당한 데이터 소스 ID 대신 사용할 수 있는 대체 ID 입니다. See <a href="../features/manage-datasources.md#create-data-source"> Create a Data Source</a> if you need to configure an integration code. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also, [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>You can use integration codes for your own data sources and for global [shared data sources](../features/datasources-list-and-settings.md#settings-menu-options), which you have access to. 예를 들어, 모바일 식별자 데이터 소스로 작업할 때 통합 코드를 사용할 수 있습니다. 아래 지정된 통합 코드를 정확하게 사용하십시오.

* **dsid_ 20914** - Android 운영 체제를 실행하는 장치를 나타내는 도마뱀붙이
* **IDFA** 용 DSID_ 20915 - iOS 운영 체제를 실행하는 장치를 나타냅니다.

**예**

다음 표에서는 이벤트 유형별 예를 제공합니다.

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
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">New: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Deprecated: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>인바운드 동기화 (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">New: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Deprecated: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID (ID) 생성 </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">New: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Deprecated: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Each call can also include multiple `d_cid` and `d_cid_ic` key value pairs like this:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Important Considerations for Development Teams {#dev-considerations}

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
   <td colname="col2"> <p>Your development teams <i>must</i> apply URL encoding to the following variables in the CID key-value pair: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> 사용자 ID</code> <code> (DPUUID)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> 통합 코드</code> </li> 
     </ul> </p> <p> <p>Note: You must URL encode the user ID and integration code <i>before</i> concatenating them into a string. 이것은 두 변수를 구분하는 ASCII 문자 % 01 이 URL 인코딩에서 캡처되면 안 되기 때문입니다. </p> </p> <p>URL 인코딩은 + 또는 =와 같은 예약되거나 안전하지 않은 문자가 포함된 사용자 ID 및 통합 코드가 Adobe 서버로 올바르게 전송되도록 보장합니다. </p> <p>Use the <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII encoding table</a> for reference. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>전역 공유 Data Sources에 대한 통합 코드 사용 </p> </td> 
   <td colname="col2"> <p>You can use integration codes for your own data sources and for global <a href="../features/datasources-list-and-settings.md#settings-menu-options"> shared data sources</a>, which you have access to. 예를 들어, 모바일 식별자 데이터 소스로 작업할 때 통합 코드를 사용할 수 있습니다. 아래 지정된 통합 코드를 정확하게 사용하십시오. </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>dsid_ 20914</b> - Android 운영 체제를 실행하는 장치를 나타내는 도마뱀붙이 </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>IDFA</b> 용 DSID_ 20915 - iOS 운영 체제를 실행하는 장치를 나타냅니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

