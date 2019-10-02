---
description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드와 함께 전달된 일련의 JSON 개체로서 사용자 데이터를 반환합니다.
seo-description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드와 함께 전달된 일련의 JSON 개체로서 사용자 데이터를 반환합니다.
seo-title: 실시간 아웃바운드 데이터 전송
solution: Audience Manager
title: 실시간 아웃바운드 데이터 전송
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 4e84682dea46f5b6c76464c66199f7a468bec334

---


# 실시간 아웃바운드 데이터 전송 {#real-time-outbound-data-transfers}

아웃바운드 실시간 데이터 전송 프로세스는 사용자 데이터를 일련의 [!DNL JSON] 형식 메시지로 대상 플랫폼에 전달합니다.

<!-- c_outbound_json.xml -->

## 권장 사항

이 방법을 사용하려면 대상 플랫폼이 다음 요구 사항을 충족해야 합니다.

* Audience Manager에서 대량의 메시지를 수신할 수 있도록 확장할 [!DNL URL] 수 있는 끝점을 제공해야 합니다.
* Adobe는 [!DNL JSON] 형식(`Content-type: application/json`);
* 보안 `HTTPS` 데이터 전송을 승인해야 합니다. [!DNL Audience Manager] 은 비보안 `HTTP` 프로토콜을 통해 메시지를 전송하지 않습니다.

## 빈도

이 데이터 전송 방법은 사용자가 세그먼트를 사용할 수 있으므로 거의 실시간으로 데이터를 전송할 수 있습니다. 실시간 메시지는 사용자가 온라인 상태이고 Audience Manager Edge 네트워크에 능동적으로 표시되는 동안에만 제공됩니다. 선택적으로 이 방법은 오프라인 또는 온보드 데이터를 24시간마다 자주 보낼 수도 있습니다.

## 일괄 전송

실시간 전송과 일괄 전송 모두 동일한 종단점으로 전송되며 동일한 메시지 형식을 사용합니다. 일괄 전송을 활성화하면 대상 플랫폼에 일괄 메시지가 전달되는 동안 메시지 볼륨이 급증하게 됩니다. 실시간 메시지를 통해 전송된 세그먼트 자격 조건 중 다수가 배치 메시지에서 반복됩니다. Batch transfers will include only the segment qualifications (or un-qualifications) that have changed since the last batch was delivered.

## 비율 제한

전송 메시지의 처리량에 설정된 속도 제한이 없습니다. 속도 제한을 설정하면 데이터가 손실될 수 있습니다.

## 필수 응답

By default, the recipient server must return the  code to indicate successful receipt. `200 OK` Other codes will be interpreted as failures. This response is expected within 3000 milliseconds. In response to a failure,  will make one retry attempt only.[!DNL Audience Manager]

## 매개 변수

The following table defines the elements in the  data file that you send to the destination.[!DNL JSON]

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 데이터 유형 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>프로세스 시간</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>요청이 실행된 시간입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>메시지 내에 포함된 장치 ID의 유형을 나타내는 ID를 User.DataPartner_UUID 속성에 지정합니다. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID):20914 <code> 년</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA):2015 <code> 년</code> </li>
     <li>Web/Cookie IDs: varies by destination platform</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>Represents the target account in the destination platform. 이 ID는 대상 플랫폼에서 비롯됩니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>The ID of the Audience Manager “destination” object. 이 ID는 Audience Manager에서 유래했습니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>Total number of users in the  POST request.<code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>사용자</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>An array of user objects. By default, each message will contain between 1 and 10 users, to keep the message size optimal. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>Audience <span class="keyword"> Manager</span> UUID입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>대상 플랫폼 UUID 또는 전역 장치 ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 배열 </td> 
   <td colname="col3"> 이 <span class="keyword"> 장치를 본</span> Audience Manager 영역 ID. 예를 들어, 장치가 파리(유럽)에서 일부 활동을 하는 경우 지역 ID는 <code> 6입니다</code>. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>세그먼트</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>세그먼트 개체의 배열입니다. 실시간 메시지의 경우 배열에 사용자가 속한 모든 세그먼트가 포함됩니다. 배치 메시지의 경우 배열에 마지막 배치 이후의 세그먼트 변경 사항만 포함됩니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트의 식별자입니다. 대부분의 경우 Audience Manager에서 생성된 세그먼트 ID(정수)입니다. 경우에 따라 대상 플랫폼에서 허용되는 경우, 고객은 Audience Manager UI(텍스트 필드 열기)에서 세그먼트 식별자를 정의하면 이 속성이 반영됩니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트에 있는 사용자의 상태를 정의합니다. 다음 값을 수락합니다. </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:활성(기본값) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:비활성, 옵트아웃 또는 세그먼트화되지 않음. </li> 
    </ul> <p>사용자는 다음 경우에 세그먼트화되지 않습니다. </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">세그먼트 규칙에 따라 세그먼트에서 제거되었습니다. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">세그먼트의 <a href="../../../features/traits/segment-ttl-explained.md"> 실시간 간격에</a>따라 세그먼트에서 제거되었습니다. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">지난 120일 동안 표시되지 않은 경우 비활성 상태로 이동되었습니다. </li>
     <li>Removed due to a privacy change request (i.e. [!DNL GDPR])</li>
    </ul> <p>All partner IDs that are synced to an  Audience Manager ID will receive the  "Status":"0" flag when a user is unsegmented.<span class="keyword"></span><code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>The time when the user-segment qualification was most recently verified.</p> </td> 
  </tr> 
 </tbody> 
</table>

## 보안

You can secure your real-time outbound data transfer process by signing HTTP requests using private keys or by having  authenticate through the OAuth 2.0 protocol.[](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)[!DNL Audience Manager][](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md)

## 요청

실시간 요청은 다음과 유사할 수 있습니다.

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
