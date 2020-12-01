---
description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드와 함께 전달되는 일련의 JSON 개체로서 사용자 데이터를 반환합니다.
seo-description: 아웃바운드 실시간 데이터 전송 프로세스는 POST 메서드와 함께 전달되는 일련의 JSON 개체로서 사용자 데이터를 반환합니다.
seo-title: 실시간 아웃바운드 데이터 전송
solution: Audience Manager
title: 실시간 아웃바운드 데이터 전송
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 5%

---


# 실시간 아웃바운드 데이터 전송 {#real-time-outbound-data-transfers}

아웃바운드 실시간 데이터 전송 프로세스는 사용자 데이터를 일련의 [!DNL JSON] 형식의 메시지로 대상 플랫폼에 전달합니다.

<!-- c_outbound_json.xml -->

## 권장 사항

이 메서드를 사용하려면 대상 플랫폼이 다음 요구 사항을 충족해야 합니다.

* Audience Manager에서 대량의 메시지를 수신하도록 확장할 수 있는 끝점 [!DNL URL]을(를) 제공해야 합니다.
* [!DNL JSON] 형식(`Content-type: application/json`);
* 보안 `HTTPS` 데이터 전송을 승인해야 합니다. [!DNL Audience Manager] 안전하지 않은  `HTTP` 프로토콜을 통해 메시지를 전송하지 않습니다.

## 빈도

이 데이터 전송 방법은 사용자가 세그먼트를 사용할 수 있으므로 거의 실시간으로 데이터를 전송할 수 있습니다. 실시간 메시지는 사용자가 온라인 상태이고 Audience Manager Edge 네트워크에 능동적으로 표시되는 동안에만 전달됩니다. 선택적으로 이 방법을 사용하면 24시간마다 오프라인 또는 온보드 데이터의 일괄 처리를 보낼 수도 있습니다.

## 일괄 전송

실시간 및 일괄 전송 모두 동일한 종단점으로 전송되며 동일한 메시지 형식을 사용합니다. 일괄 전송 기능이 활성화되면 배치 메시지가 전달되는 동안 대상 플랫폼에 메시지 볼륨이 급등하게 됩니다. 실시간 메시지를 통해 전송되는 많은 세그먼트 자격 조건은 배치 메시지에서 반복됩니다. 배치 이전에는 마지막 배치를 전달한 이후 변경된 세그먼트 자격(또는 비자격)만 포함됩니다.

## 비율 제한

There are no rate limits set on the throughput of delivered messages. 속도 제한을 설정하면 데이터가 손실될 수 있습니다.

## 필수 응답

받는 사람 서버는 기본적으로 `200 OK` 코드를 반환하여 성공적인 입고를 나타내야 합니다. 다른 코드는 실패로 해석됩니다. 이 응답은 3000밀리초 이내에 필요합니다. 오류에 대한 응답으로 [!DNL Audience Manager]은(는) 한 번만 다시 시도합니다.

## 매개 변수

다음 표에서는 대상으로 보내는 [!DNL JSON] 데이터 파일의 요소를 정의합니다.

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
   <td colname="col3"> <p>메시지 내에 포함된 장치 ID의 유형을 나타내는 ID를 User.DataPartner_UUID 속성에서 지정합니다. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID(GAID):<code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS ID(IDFA):<code> 20915</code> </li>
     <li>웹/쿠키 ID:대상 플랫폼별로 다름</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>대상 플랫폼의 대상 계정을 나타냅니다. 이 ID는 대상 플랫폼에서 만들어졌습니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>Audience Manager "대상" 개체의 ID입니다. 이 ID는 Audience Manager에서 유래했습니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p><code> POST</code> 요청의 총 사용자 수입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>사용자 개체의 배열입니다. 메시지 크기를 최적으로 유지하기 위해 기본적으로 각 메시지에는 1명에서 10명의 사용자가 포함됩니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> UUID입니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>대상 플랫폼 UUID 또는 전역 장치 ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> 배열 </td> 
   <td colname="col3"> 이 장치를 본 <span class="keyword"> Audience Manager</span> 영역 ID. 예를 들어, 장치가 파리(유럽)에서 일부 활동을 하는 경우 지역 ID는 <code> 6</code>입니다. <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">DCS 영역 ID, 위치 및 호스트 이름</a>을 참조하십시오. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>배열 </p> </td> 
   <td colname="col3"> <p>세그먼트 개체의 배열입니다. 실시간 메시지의 경우 배열에 사용자가 속한 모든 세그먼트가 포함됩니다. 배치 메시지의 경우 배열에 마지막 배치 이후의 세그먼트 변경 사항만 포함됩니다.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트의 식별자입니다. 대부분의 경우 Audience Manager에 의해 생성된 세그먼트 ID입니다(정수). 경우에 따라, 대상 플랫폼이 허용하는 경우 고객은 Audience Manager 사용자 인터페이스(텍스트 필드 열기)에서 세그먼트 식별자를 정의하면 이 속성이 반영됩니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>세그먼트에 있는 사용자의 상태를 정의합니다. 다음 값을 수락합니다. </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>:활성(기본값) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>:비활성, 옵트아웃 또는 세그먼트화되지 않은 </li> 
    </ul> <p>사용자는 다음 경우에 세그먼트화되지 않습니다. </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">세그먼트 규칙에 따라 세그먼트에서 제거되었습니다. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">세그먼트의 <a href="../../../features/traits/segment-ttl-explained.md"> time-to-live interval</a>을 기준으로 세그먼트에서 제거했습니다. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">지난 120일 동안 표시되지 않은 경우 비활성 상태로 이동되었습니다. </li>
     <li>개인 정보 변경 요청(예:<span class="keyword"> GDPR</span>)</li>
    </ul> <p><span class="keyword"> Audience Manager</span> ID에 동기화된 모든 파트너 ID는 사용자가 세그먼트화되지 않은 경우 <code> "Status":"0"</code> 플래그를 수신합니다. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>사용자 세그먼트 자격이 가장 최근에 확인된 시간입니다.</p> </td> 
  </tr> 
 </tbody> 
</table>

## 보안

개인 키를 사용하여 [HTTP 요청](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)에 서명하거나 [!DNL Audience Manager]가 [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) 프로토콜을 통해 인증하도록 하여 실시간 아웃바운드 데이터 전송 프로세스를 보호할 수 있습니다.

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
