---
description: 대상 URL에 추가할 수 있는 매크로를 설명합니다.
seo-description: 대상 URL에 추가할 수 있는 매크로를 설명합니다.
seo-title: 정의된 대상 매크로
solution: Audience Manager
title: 정의된 대상 매크로
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 3%

---


# 정의된 대상 매크로 {#destination-macros-defined}

대상 [!DNL URL]에 추가할 수 있는 매크로를 설명합니다.

<!-- destination-macros.xml -->

[!DNL URL] 대상을 만들 때 다음 매크로를 [!DNL URL] 문자열에 삽입할 수 있습니다. 대상 [!DNL URL] 내에서 적절한 매크로 배달에 대해 데이터/대상 파트너에게 문의하십시오.

>[!NOTE]
>
>매크로는 달리 명시하지 않는 한 선택 사항입니다. *기울임꼴*&#x200B;은 변수 자리 표시자를 나타냅니다.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매크로 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>필수 여부. </p> <p>대상 URL에서 매핑된 세그먼트 값의 위치를 정의합니다. 일반적으로 이것은 <i>세그먼트 ID</i>이지만 통합 코드일 수도 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>사용자의 <span class="keyword"> Audience Manager</span> ID를 대상 URL에 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>데이터 소스 id</i>는 매크로에 전달된 데이터 소스의 식별자에 해당합니다. </p> <p>간단한 예로 이것이 어떻게 작동하는지 살펴보겠습니다. 이 경우 다음 ID와 조건이 있는 <span class="keyword"> Audience Manager</span> 파트너가 있습니다. </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">데이터 소스 ID:<code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">내부 고객 ID:<code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">선언된 ID:파트너가 이 값을 선언된 ID <code> 1:CustomerABC</code>으로 전달하려고 합니다. </li> 
    </ul> <p>이 작업을 수행하려면 <code>%dpid_<i>data source id</i>%</code> Audience Manager</span> 파트너가 다음과 같이 매크로를 포맷합니다.<span class="keyword"> </span></p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>매크로가 <code> 1</code>을(를) <code> CustomerABC</code>(으)로 대체합니다. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>방문자에게 GDPR 규정이 적용되는지 여부를 나타냅니다. IAB와 통합된 URL 대상으로 전송된 세그먼트에 동의를 포함하려면 이 매크로를 사용하십시오. 자세한 내용은 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF</a>용 Audience Manager 플러그인을 참조하십시오.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>방문자가 사이트에서 동의를 제공하거나 거부할 때 수집된 동의 문자열(IAB 공급업체 ID 포함). IAB와 통합된 URL 대상으로 전송된 세그먼트에 동의 문자열을 포함하려면 이 매크로를 사용하십시오. <code>XXXX</code>을(를) 대상 파트너 ID로 바꿉니다. 자세한 내용은 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF</a>용 Audience Manager 플러그인을 참조하십시오. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>상위 웹 페이지에서 사용되는 프로토콜을 감지하여 대상 URL에 삽입합니다. 예:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">웹 페이지가 <b>https</b>://aam_client.com인 경우 이 매크로는 <b>https</b>://url-destination.com으로 대체됩니다. </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">웹 페이지가 <b>http</b>://aam_client.com인 경우 이 매크로는 <b>http</b>://url-destination.com으로 대체됩니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Experience Cloud</span> ID를 대상 URL에 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 데이터 수집 서버(DCS)</span> 영역을 대상 URL에 삽입합니다. 지연을 최소화하기 위해 방문자가 <span class="keyword"> Audience Manager</span>에 HTTP 호출을 하면 가장 가까운 <span class="wintitle"> DCS</span> 데이터 센터로 리디렉션됩니다. 이 방법은 방문자의 위치를 감지하고 적절한 데이터 센터로 안내하는 DNS를 통해 수행됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>대상 URL에 무작위 숫자를 삽입하여 캐시 저작 기능을 수행합니다. 이렇게 하면 브라우저가 캐시된 컨텐츠를 제공할 수 없습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>브라우저가 캐시된 컨텐츠를 제공하지 못하도록 대상 URL에 UNIX 타임스탬프를 삽입합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 대상 매크로가 있는 캐시 빌드 {#destination-cache-busting}

`%rnd%` 및 `%timestamp%` 매크로는 브라우저 캐싱을 방지하기 위해 고유한 값을 [!DNL URL] 문자열에 삽입합니다.

## `%rnd%` 및 `%timestamp%` {#dest-cache-busting}로 캐시 버스트

<!-- c_dest_cache_busting.xml -->

브라우저 캐시(저장)는 자주 요청되는 컨텐츠를 메모리에 저장합니다. 페이지가 로드되면 저장된 컨텐츠는 원격 서버가 아니라 캐시에서 제공됩니다. 데이터가 다른 위치가 아니라 로컬에서 제공되므로 이 프로세스를 통해 다운로드 시간을 효율적으로 유지할 수 있습니다. 그러나 캐싱에는 서버 호출이 필요하지 않으므로 고유한 요청 수를 인위적으로 낮춰 보고 결과를 왜곡할 수 있습니다.

캐쉬 버팅을 사용하면 브라우저가 컨텐츠를 저장하고 재사용할 수 없습니다. 이 기술은 URL 문자열에 무작위 숫자나 타임스탬프를 삽입하는 코드를 사용하므로 브라우저에서만 볼 수 있습니다. 따라서 각 `HTTP` 호출은 서버에 대한 별도의 요청으로 카운트됩니다. 각 요청에 대해 새로운 서버 호출을 적용하면 보고 정확도를 유지하고 불일치를 줄이는 데 도움이 됩니다. [!DNL Audience Manager] 캐시 빌드에 대한 두 가지 매크로를 제공합니다.

* `%rnd%`:URL에 무작위 숫자를 삽입합니다.
* `%timestamp%`:Unix 날짜/시간을 URL에 삽입합니다.

## `%rnd%`과 `%timestamp%` {#compare-rnd-timestamp} 비교

두 매크로 모두 캐싱을 차단하지만 `%rnd%`이(가) 더 효율적일 수 있습니다. 예를 들어 `%timestamp%`을 사용하면 여러 사용자가 동시에 페이지를 보는 경우 동일한 날짜/시간 값을 받게 됩니다. 따라서 [!DNL URL]은 고유하지 않으며 여러 개의 호출은 한 번만 카운트됩니다. 하지만, `%rnd%`은 각 호출에 대해 고유한 숫자 값을 생성합니다(사용자가 동일한 페이지를 동시에 볼 때에도). 즉, [!DNL URL] 문자열에는 다른 값이 포함되어 있으며 고유하도록 계산됩니다.

>[!MORELIKETHIS]
>
>* [정의된 대상 매크로](../../features/destinations/destination-macros.md#destination-macros-defined)