---
description: 대상 URL에 추가할 수 있는 매크로를 설명합니다.
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: 정의된 대상 매크로
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---

# 정의된 대상 매크로 {#destination-macros-defined}

대상 [!DNL URL]에 추가할 수 있는 매크로를 설명합니다.

<!-- destination-macros.xml -->

[!DNL URL] 대상을 만들 때 [!DNL URL] 문자열에 다음 매크로를 삽입할 수 있습니다. 대상 [!DNL URL] 내의 적절한 매크로 배치에 대해 데이터/대상 파트너에게 문의하십시오.

>[!NOTE]
>
>매크로는 별도로 명시되지 않는 한 선택 사항입니다. *기울임꼴*&#x200B;은 변수 자리 표시자를 나타냅니다.

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
   <td colname="col2"> <p>필수. </p> <p>대상 URL에서 매핑된 세그먼트 값의 위치를 정의합니다. 일반적으로 <i>세그먼트 ID</i>이지만 통합 코드일 수도 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>사용자의 <span class="keyword"> Audience Manager</span> ID를 대상 URL에 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p><i>데이터 원본 ID</i>은(는) 매크로에 전달된 데이터 원본의 식별자에 해당합니다. </p> <p>이것이 어떻게 작용하는지 간단한 예로 살펴보자. 이 경우 다음 ID 및 조건을 가진 <span class="keyword"> Audience Manager</span> 파트너가 있습니다. </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">데이터 원본 ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">내부 고객 ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">선언된 ID: 파트너가 이러한 값을 선언된 ID <code> 1:CustomerABC</code>(으)로 전달하려고 합니다. </li> 
    </ul> <p><code>%dpid_<i>data source id</i>%</code>을(를) 사용하여 이 작업을 수행하려면 <span class="keyword"> Audience Manager</span> 파트너가 다음과 같이 매크로 형식을 지정합니다. </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>매크로가 <code> 1</code>을(를) <code> CustomerABC</code>(으)로 바꿉니다. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>방문자에게 GDPR 규정이 적용되는지 여부를 나타냅니다. IAB와 통합된 URL 대상으로 전송된 세그먼트에 동의를 포함하려면 이 매크로를 사용하십시오. 자세한 내용은 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그 인</a>을 참조하세요.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>방문자가 사이트에서 동의를 제공하거나 거부할 때 수집된 동의 문자열(IAB 공급업체 ID 포함). 이 매크로를 사용하여 IAB와 통합된 URL 대상으로 전송된 세그먼트에 동의 문자열을 포함할 수 있습니다. <code>XXXX</code>을(를) 대상 파트너 ID로 바꾸십시오. 자세한 내용은 <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">IAB TCF용 Audience Manager 플러그 인</a>을 참조하세요. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>상위 웹 페이지에서 사용된 프로토콜을 검색하여 대상 URL에 삽입합니다. 예:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">웹 페이지가 <b>https</b>://aam_client.com이면 이 매크로는 <b>https</b>://url-destination.com으로 바뀝니다. </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">웹 페이지가 <b>http</b>://aam_client.com이면 이 매크로는 <b>http</b>://url-destination.com으로 바뀝니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>대상 URL에 <span class="keyword"> Experience Cloud</span> ID를 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DCS(데이터 수집 서버)</span> 영역을 대상 URL에 삽입합니다. 지연을 최소화하기 위해 방문자가 <span class="keyword"> Audience Manager</span>에 대해 HTTP 호출을 수행하면 가장 가까운 <span class="wintitle"> DCS</span> 데이터 센터로 리디렉션됩니다. 이 작업은 방문자의 위치를 감지하여 적절한 데이터 센터로 보낼 수 있는 DNS를 통해 수행됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>대상 URL에 난수를 삽입하여 캐시 무효화 기능을 수행합니다. 이렇게 하면 브라우저에서 캐시된 콘텐츠를 제공하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>브라우저에서 캐시된 콘텐츠를 제공하지 않도록 대상 URL에 UNIX 타임스탬프를 삽입합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 대상 매크로로 캐시 무효화 {#destination-cache-busting}

`%rnd%` 및 `%timestamp%` 매크로는 브라우저 캐싱을 방지하기 위해 [!DNL URL] 문자열에 고유한 값을 삽입합니다.

## `%rnd%` 및 `%timestamp%`(으)로 캐시 무효화 {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

브라우저는 자주 요청된 콘텐츠를 메모리에 캐시합니다(저장). 페이지가 로드되면 저장된 콘텐츠는 원격 서버가 아닌 캐시에서 제공됩니다. 이 프로세스는 데이터가 다른 위치가 아닌 로컬에서 제공되므로 효율적인 다운로드 시간을 유지하는 데 도움이 됩니다. 그러나 캐싱은 서버 호출이 필요하지 않으므로 고유한 요청 수를 인위적으로 줄여 보고를 왜곡할 수 있습니다.

캐시 무효화는 브라우저가 콘텐츠를 저장하고 재사용하지 못하도록 합니다. 이 기법은 임의의 숫자나 타임스탬프를 URL 문자열에 삽입하는 코드를 사용하므로 이 코드가 브라우저에만 고유한 것처럼 보입니다. 따라서 각 `HTTP` 호출은 서버에 대한 별도의 요청으로 계산됩니다. 각 요청에 대해 새 서버 호출을 강제하면 보고 정확도를 유지하고 불일치를 줄이는 데 도움이 됩니다. [!DNL Audience Manager]은(는) 캐시 무효화에 대한 두 개의 매크로를 제공합니다.

* `%rnd%`: URL에 난수를 삽입합니다.
* `%timestamp%`: URL에 Unix 날짜/시간을 삽입합니다.

## `%rnd%`과(와) `%timestamp%` 비교 {#compare-rnd-timestamp}

두 매크로 모두 캐싱을 금지하지만 `%rnd%`이(가) 더 효율적일 수 있습니다. 예를 들어 `%timestamp%`의 경우 여러 사용자가 동시에 페이지를 보면 동일한 날짜/시간 값을 받게 됩니다. 따라서 [!DNL URL]은(는) 고유하지 않으며 여러 호출은 한 번만 계산됩니다. 그러나 `%rnd%`은(는) 사용자가 동일한 페이지를 동시에 보는 경우에도 각 호출에 대해 고유한 숫자 값을 생성합니다. 즉, [!DNL URL] 문자열에 다른 값이 포함되어 있으며 고유한 것으로 계산됩니다.

>[!MORELIKETHIS]
>
>* [정의된 대상 매크로](../../features/destinations/destination-macros.md#destination-macros-defined)
