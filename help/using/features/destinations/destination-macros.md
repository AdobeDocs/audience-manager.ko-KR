---
description: 대상 URL에 추가할 수 있는 매크로를 설명합니다.
seo-description: 대상 URL에 추가할 수 있는 매크로를 설명합니다.
seo-title: 대상 매크로가 정의됨
solution: Audience Manager
title: 대상 매크로가 정의됨
uuid: 982 CAB 05-8 A 3 F -4 F 96-B 4 D 0-291709712 AD 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Destination Macros Defined {#destination-macros-defined}

Describes the macros you can add to a destination [!DNL URL].

<!-- destination-macros.xml -->

[!DNL URL] 대상을 만들 때 다음 매크로를 [!DNL URL] 문자열에 삽입할 수 있습니다. Check with your data/destination partner about proper macro placement within the destination [!DNL URL].

>[!NOTE]
>
>다른 언급이 없는 한 매크로는 선택 사항입니다. *기울임꼴*&#x200B;은 변수 자리 표시자를 나타냅니다.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> macro </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>필수 여부. </p> <p>대상 URL에서 매핑된 세그먼트 값의 위치를 정의합니다. Usually this is the <i>Segment ID</i>, but could also be the integration code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Inserts the user's <span class="keyword"> Audience Manager</span> ID into the destination URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>% DPID_<i>DATA 소스 ID</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>데이터 소스 ID</i> 는 매크로에 전달된 데이터 소스의 식별자에 해당합니다. </p> <p>간단한 예를 살펴보겠습니다. In this case, we have an <span class="keyword"> Audience Manager</span> partner with the following IDs and conditions: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Data source ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">An internal customer ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: The partner wants to pass in these values as the declared ID <code> 1:CustomerABC</code>. </li> 
    </ul> <p><code>% DPID_<i>DATA 소스 ID</i>%</code>를 사용하여 이렇게 하려면 <span class="keyword"> Audience Manager</span> 파트너가 다음과 같이 매크로의 형식을 지정합니다. </p> 
    <ul class="simplelist"> 
     <li> <code> % DPID_ 1%</code> </li> 
    </ul> <p>The macro will replace <code> 1</code> with <code> CustomerABC</code>. </p> <p> 
     <draft-comment>
       AAM -22193에 대한 자세한 내용 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % HTTP_ PROTO %</code> </p> </td> 
   <td colname="col2"> <p>상위 웹 페이지에 사용된 프로토콜을 감지하고 대상 URL에 삽입합니다. 예: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">if the webpage is <b>https</b>://aam_client.com, this macro will be replaced with <b>https</b>://url-destination.com </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">if the webpage is <b>http</b>://aam_client.com, this macro will be replaced with <b>http</b>://url-destination.com </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % MCID %</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Experience Cloud</span> ID를 대상 URL에 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % REGION %</code> </p> </td> 
   <td colname="col2"> <p>Inserts the <span class="wintitle"> Data Collection Server (DCS)</span> region into the destination URL. In order to minimize latency, when the visitor makes an HTTP call to <span class="keyword"> Audience Manager</span>, they are being redirected to the closest <span class="wintitle"> DCS</span> datacenter. 이는 방문자의 위치를 감지하고 적절한 데이터 센터로 연결할 수 있는 DNS를 통해 이루어집니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> % RND %</code> </p> </td> 
   <td colname="col2"> <p>대상 URL에 무작위 숫자를 삽입하여 캐시 제거 기능을 수행합니다. 이렇게 하면 브라우저에서 캐시된 컨텐츠를 제공하는 것을 방지할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>UNIX 타임스탬프를 대상 URL에 삽입하여 브라우저가 캐시된 컨텐츠를 제공하지 않도록 합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache Busting with Destination Macros {#destination-cache-busting}

`%rnd%` And `%timestamp%` 매크로는 브라우저 캐싱을 방지하기 위해 [!DNL URL] 문자열에 고유한 값을 삽입합니다.

## Cache Busting with `%rnd%` and `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

브라우저는 자주 요청된 컨텐츠를 메모리에 캐시 (저장) 합니다. 페이지가 로드되면 저장된 콘텐트는 원격 서버가 아닌 캐시에서 제공됩니다. 이 프로세스는 데이터가 다른 위치가 아니라 로컬에 제공되므로 효율적인 다운로드 시간을 유지하는 데 도움이 됩니다. 하지만 캐싱은 서버 호출을 요구하지 않기 때문에 고유한 요청의 수를 인위적으로 낮춰 보고를 기울일 수 있습니다.

캐시 제거는 브라우저가 컨텐츠를 저장 및 재사용하지 못하도록 합니다. 이 기술은 임의의 숫자 또는 타임스탬프를 URL 문자열에 삽입하는 코드를 사용하여 브라우저에 고유한 모양을 만듭니다. `HTTP` 따라서 각 호출은 서버에 대한 별도의 요청으로 계산됩니다. 각 요청에 대해 새 서버 호출을 적용하면 보고 정확도를 유지하고 불일치 수를 줄일 수 있습니다. [!DNL Audience Manager] 캐시 분할을 위한 두 개의 매크로를 제공합니다.

* `%rnd%`: URL에 무작위 숫자를 삽입합니다.
* `%timestamp%`: UNIX 날짜/시간을 URL에 삽입합니다.

## `%rnd%` 비교 및 `%timestamp%`{#compare-rnd-timestamp}

Both macros prevent caching, but `%rnd%` may be more efficient. For example, with `%timestamp%`, if several users view a page simultaneously they'll get the same date/time value. As a result, the [!DNL URL] is not unique and multiple calls are counted only once. However, `%rnd%` generates a unique numeric value for each call (even when users see the same page simultaneously). This means the [!DNL URL] string contains different values and is counted as unique.

>[!MORE_ like_ this]
>
>* [대상 매크로가 정의됨](../../features/destinations/destination-macros.md#destination-macros-defined)