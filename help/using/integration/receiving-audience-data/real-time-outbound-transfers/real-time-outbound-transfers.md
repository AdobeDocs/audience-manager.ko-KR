---
description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드와 함께 전달된 일련의 JSON 개체로서 사용자 데이터를 반환합니다.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: 실시간 아웃바운드 데이터 전송
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 5%

---

# 실시간 아웃바운드 데이터 전송 {#real-time-outbound-data-transfers}

아웃바운드 실시간 데이터 전송 프로세스는 사용자 데이터를 일련의 [!DNL JSON] 대상 플랫폼에 형식이 지정된 메시지.

<!-- c_outbound_json.xml -->

## 권장 사항

이 메서드를 사용하려면 대상 플랫폼이 다음 요구 사항을 충족해야 합니다.

* 끝점을 제공해야 합니다 [!DNL URL] Audience Manager에서 많은 양의 메시지를 받을 수 있도록 확장할 수 있습니다.
* 데이터를에서 수락해야 합니다. [!DNL JSON] 포맷`Content-type: application/json`);
* 보안 조치를 취해야 합니다 `HTTPS` 데이터 전송. [!DNL Audience Manager] 안전하지 않은 메시지를 통해 보내지 않습니다. `HTTP` 프로토콜.

## 빈도

이 데이터 전송 방법은 사용자가 세그먼트에 대한 자격이 있으므로 거의 실시간으로 데이터를 전송할 수 있습니다. 실시간 메시지는 사용자가 온라인 상태이고 Audience Manager 에지 네트워크에 능동적으로 표시되는 동안에만 전달됩니다. 선택적으로 이 메서드는 24시간마다 오프라인 데이터나 온보딩된 데이터 배치를 자주 전송할 수도 있습니다.

## 배치 이전

실시간 및 배치 전송이 모두 동일한 종단점으로 전송되며 동일한 메시지 형식을 사용합니다. 배치 전송이 활성화되면 배치 메시지가 전달되는 동안 대상 플랫폼에 메시지 볼륨이 증가합니다. 실시간 메시지를 통해 전송되는 많은 세그먼트 자격은 배치 메시지에서 반복됩니다. 배치 이전에는 마지막 배치가 전달된 후 변경된 세그먼트 자격(또는 자격 미적용)만 포함됩니다.

## 비율 제한

전달된 메시지의 처리량에 설정된 비율 제한은 없습니다. 비율 제한을 설정하면 데이터가 손실될 수 있습니다.

## 필수 응답

기본적으로 수신자 서버는 `200 OK` 성공적인 입고를 나타내는 코드입니다. 다른 코드는 실패로 해석됩니다. 이 응답은 3000밀리초 이내에 예상됩니다. 실패에 대한 응답으로, [!DNL Audience Manager] 다시 시도 한 번만 시도합니다.

## 매개 변수

다음 표에서는 [!DNL JSON] 대상에 보내는 데이터 파일입니다.

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
   <td colname="col3"> <p>메시지에 포함된 장치 ID 유형을 나타내는 ID로서 User.DataPartner_UUID 속성에 있습니다. </p> 
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
   <td colname="col3"> <p>의 총 사용자 수 <code> POST</code> 요청. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>사용자 객체의 배열입니다. 기본적으로 메시지 크기를 최적 상태로 유지하기 위해 각 메시지에는 1명에서 10명의 사용자가 포함됩니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>다음 <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>대상 플랫폼 UUID 또는 글로벌 장치 ID </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 배열 </td> 
   <td colname="col3"> 다음 <span class="keyword"> Audience Manager</span> 이 장치를 본 지역 ID. 예를 들어, 장치가 파리(유럽)에서 일부 활동을 했다면 지역 ID는 <code> 6</code>. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>세그먼트 개체의 배열입니다. 실시간 메시지의 경우 배열에 사용자가 속한 모든 세그먼트가 포함됩니다. 배치 메시지의 경우 배열에 마지막 배치 이후 세그먼트 변경 사항만 포함됩니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트의 식별자입니다. 대부분의 경우 Audience Manager(정수)에서 생성된 세그먼트 ID입니다. 경우에 따라 대상 플랫폼에서 을 허용하는 경우 고객이 Audience Manager 사용자 인터페이스(텍스트 필드 열기)에서 세그먼트 식별자를 정의하여 이 속성에 반영될 수 있습니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트에서 사용자의 상태를 정의합니다. 다음 값을 허용합니다. </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: 활성(기본값) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: 비활성, 옵트아웃 또는 세그먼트화되지 않습니다. </li> 
    </ul> <p>사용자는 다음과 같은 경우 세그먼트화되지 않습니다. </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">세그먼트 규칙에 따라 세그먼트에서 제거되었습니다. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">세그먼트의 <a href="../../../features/traits/segment-ttl-explained.md"> 실시간 간격</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">지난 120일 동안 표시되지 않은 경우 비활성 상태로 이동되었습니다. </li>
     <li>개인 정보 변경 요청으로 인해 제거됨(예: <span class="keyword"> GDPR</span>)</li>
    </ul> <p>에 동기화된 모든 파트너 ID <span class="keyword"> Audience Manager</span> ID가 <code> "Status":"0"</code> 사용자가 세그먼트화되지 않은 경우 플래그를 지정합니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>사용자 세그먼트 자격이 가장 최근에 확인된 시간입니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

## 보안

다음 방법으로 실시간 아웃바운드 데이터 전송 프로세스를 보호할 수 있습니다. [HTTP 요청 서명](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) 개인 키 사용 또는 [!DNL Audience Manager] 인증 [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 프로토콜.

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
