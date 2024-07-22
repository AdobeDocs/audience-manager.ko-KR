---
description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드를 사용하여 전달된 일련의 JSON 개체로 사용자 데이터를 반환합니다.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: 실시간 아웃바운드 데이터 전송
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 2%

---

# 실시간 아웃바운드 데이터 전송 {#real-time-outbound-data-transfers}

아웃바운드 실시간 데이터 전송 프로세스는 일련의 [!DNL JSON] 형식의 메시지로 사용자 데이터를 대상 플랫폼에 전달합니다.

<!-- c_outbound_json.xml -->

## 권장 사항

이 방법을 사용하려면 대상 플랫폼이 다음 요구 사항을 충족해야 합니다.

* Audience Manager에서 많은 양의 메시지를 받도록 확장할 수 있는 끝점 [!DNL URL]을(를) 제공해야 합니다.
* [!DNL JSON] 형식(`Content-type: application/json`)의 데이터를 허용해야 합니다.
* 보안 `HTTPS` 데이터 전송을 허용해야 합니다. [!DNL Audience Manager]이(가) 비보안 `HTTP` 프로토콜을 통해 메시지를 보내지 않습니다.

## 빈도

이 데이터 전송 방법은 사용자가 세그먼트에 대한 자격을 얻을 때 거의 실시간으로 데이터를 전송할 수 있습니다. 실시간 메시지는 사용자가 온라인 상태이고 Audience Manager Edge 네트워크에 적극적으로 표시되는 동안에만 전달됩니다. 선택적으로, 이 방법은 오프라인 또는 온보딩된 데이터의 배치를 24시간마다 전송할 수도 있습니다.

## 배치 전송

실시간 전송과 배치 전송 모두 동일한 끝점으로 전송되며 동일한 메시지 형식을 사용합니다. 일괄 전송 기능을 활성화하면 일괄 처리 메시지가 배달되는 동안 대상 플랫폼에서 메시지 볼륨이 급증합니다. 실시간 메시지를 통해 전송되는 많은 세그먼트 자격이 배치 메시지에서 반복됩니다. 배치 이전에는 마지막 배치가 전달된 이후 변경된 세그먼트 자격(또는 비자격)만 포함됩니다.

## 비율 제한

게재된 메시지의 처리량에 설정된 속도 제한은 없습니다. 요율 제한을 설정하면 데이터가 손실될 수 있습니다.

## 필수 응답

기본적으로 받는 사람 서버는 `200 OK` 코드를 반환하여 성공적으로 받았음을 나타내야 합니다. 다른 코드는 실패로 해석될 것입니다. 이 응답은 3000밀리초 내에 예상됩니다. 실패에 대한 응답으로 [!DNL Audience Manager]이(가) 한 번만 다시 시도합니다.

## 매개 변수

다음 표는 대상으로 보내는 [!DNL JSON] 데이터 파일의 요소를 정의합니다.

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
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>요청이 실행된 시간입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>User.DataPartner_UUID 속성에서 메시지 내에 포함된 장치 ID 유형을 나타내는 ID입니다. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA): <code> 20915</code> </li>
     <li>웹/쿠키 ID: 대상 플랫폼에 따라 다름</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>대상 플랫폼의 대상 계정을 나타냅니다. 이 ID는 대상 플랫폼에서 가져옵니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>Audience Manager "대상" 개체의 ID입니다. 이 ID는 Audience Manager에서 가져옵니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p><code> POST</code> 요청의 총 사용자 수입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>사용자 개체의 배열입니다. 기본적으로 각 메시지에는 메시지 크기를 최적으로 유지하기 위해 1명에서 10명 사이의 사용자가 포함됩니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>대상 플랫폼 UUID 또는 글로벌 장치 ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 배열 </td> 
   <td colname="col3"> 이 장치를 본 <span class="keyword"> Audience Manager</span> 지역 ID입니다. 예를 들어 장치에 파리(유럽)에서 활동이 있는 경우 지역 ID는 <code> 6</code>입니다. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">개의 DCS 지역 ID, 위치 및 호스트 이름을 참조하십시오</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>세그먼트 객체의 배열입니다. 실시간 메시지의 경우 배열에 사용자가 속한 모든 세그먼트가 포함됩니다. 배치 메시지의 경우, 배열에는 마지막 배치 이후의 세그먼트 변경 사항만 포함됩니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트의 식별자입니다. 대부분의 경우 Audience Manager(정수)에서 생성한 세그먼트 ID입니다. 경우에 따라 대상 플랫폼에서 허용하는 경우 고객은 Audience Manager 사용자 인터페이스(열린 텍스트 필드)에서 세그먼트 식별자를 정의할 수 있으며 이는 이 속성에 반영됩니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트에서 사용자의 상태를 정의합니다. 다음 값을 허용합니다. </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: 활성(기본값) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: 비활성, 옵트아웃 또는 세그먼테이션되지 않음. </li> 
    </ul> <p>사용자는 다음과 같은 경우 세분화되지 않습니다. </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">세그먼트 규칙에 따라 세그먼트에서 제거되었습니다. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">세그먼트의 <a href="../../../features/traits/segment-ttl-explained.md"> TTL(Time-to-Live) 간격</a>을(를) 기반으로 세그먼트에서 제거되었습니다. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">지난 120일 동안 표시되지 않은 경우 비활성 상태로 이동되었습니다. </li>
     <li>개인 정보 변경 요청(예: <span class="keyword"> GDPR</span>)으로 인해 제거되었습니다.</li>
    </ul> <p><span class="keyword"> Audience Manager</span> ID에 동기화되는 모든 파트너 ID는 사용자가 세분화되지 않은 경우 <code> "Status":"0"</code> 플래그를 받습니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>사용자 세그먼트 자격이 가장 최근에 확인된 시간입니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

## 보안

개인 키를 사용하여 [HTTP 요청에 서명](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)하거나 [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 프로토콜을 통해 [!DNL Audience Manager]을(를) 인증하면 실시간 아웃바운드 데이터 전송 프로세스를 보호할 수 있습니다.

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
