---
description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드와 함께 전달된 일련의 JSON 개체로서 사용자 데이터를 반환합니다.
seo-description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드와 함께 전달된 일련의 JSON 개체로서 사용자 데이터를 반환합니다.
seo-title: 실시간 아웃바운드 데이터 전송
solution: Audience Manager
title: 실시간 아웃바운드 데이터 전송
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# 실시간 아웃바운드 데이터 전송 {#real-time-outbound-data-transfers}

아웃바운드 실시간 데이터 전송 프로세스는 사용자 데이터를 메서드와 함께 전달된 일련의 [!DNL JSON] 개체로 `POST` 반환합니다.

<!-- c_outbound_json.xml -->

## 권장 사항

이 방법을 사용하려면 데이터 파트너를 권장합니다.

* 데이터를 [!DNL JSON] 형식으로 수락합니다.
* 데이터를 반환하기 위한 `POST` 호출에서 사용할 수 있는 URL을 제공합니다.
* 안전한 `HTTPS` 데이터 전송을 수용합니다. [!DNL Audience Manager] 이 파일을 비보안 `HTTP` 프로토콜로 전송하지 않습니다.

## 빈도

이 데이터 전송 방법은 사용자가 세그먼트를 사용할 수 있으므로 거의 실시간으로 데이터를 전송할 수 있습니다. 또한 이 방법은 24시간마다 오프라인 또는 온보드 데이터를 일괄적으로 보낼 수 있습니다.

## 필수 응답

기본적으로 수신자 서버는 성공적인 입고를 나타내는 `200 OK` 코드를 반환해야 합니다. 다른 코드는 실패로 해석됩니다. 이 응답은 3000밀리초 이내에 예상됩니다. 실패에 대한 응답으로 1번의 다시 시도만 [!DNL Audience Manager] 수행합니다.

## 매개 변수

다음 표에서는 반환된 [!DNL JSON] 데이터 파일의 요소를 정의합니다.

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
   <td colname="col3"> <p>파일에 Android 또는 iOS ID가 포함되어 있는지 여부를 나타내는 ID입니다. 다음 ID 값을 사용합니다. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID):20914 <code> 년</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA):2015 <code> 년</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>데이터를 보내는 시스템에서 사용하는 클라이언트 ID입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>대상 파트너가 사용자에게 할당한 ID입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>POST 요청의 총 사용자 <code> 수입니다</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>사용자</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>사용자 개체의 배열입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>Audience <span class="keyword"> Manager</span> UUID입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>데이터 파트너 UUID. 데이터 파트너에 UUID가 없으면 비워 둡니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Regions</i></code> </td> 
   <td colname="col2"> 배열 </td> 
   <td colname="col3"> 이 <span class="keyword"> 장치를 본</span> Audience Manager 영역 ID. 예를 들어, 장치가 파리(유럽)에서 일부 활동을 하는 경우 지역 ID는 <code> 6입니다</code>. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>세그먼트</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>세그먼트 개체의 배열입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트 ID 대상 매핑. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>상태</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트에 있는 사용자의 상태를 정의합니다. 다음을 수락합니다. </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:활성(기본값) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:비활성, 옵트아웃 또는 세그먼트화되지 않음. </li> 
    </ul> <p>사용자는 다음 경우에 세그먼트화되지 않습니다. </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">세그먼트 규칙에 따라 세그먼트에서 제거되었습니다. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">세그먼트의 <a href="../../../features/traits/segment-ttl-explained.md"> 실시간 간격에</a>따라 세그먼트에서 제거되었습니다. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">지난 120일 동안 표시되지 않은 경우 비활성 상태로 이동되었습니다. </li> 
    </ul> <p>Audience Manager ID에 동기화된 모든 파트너 <span class="keyword"> ID는</span> 사용자가 세그먼트화되지 않은 경우 <code> "Status":"0"</code> 플래그를 받습니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>가장 최근 세그먼트 자격 검증 시간입니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

## 보안

개인 키를 사용하여 HTTP 요청에 [](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) 서명하거나 OAuth 2.0 프로토콜을 통해 [!DNL Audience Manager] 인증함으로써 실시간 아웃바운드 데이터 전송 프로세스를 보호할 [수](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 있습니다.

## 코드 샘플

실시간 데이터 응답은 다음과 유사할 수 있습니다.

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
