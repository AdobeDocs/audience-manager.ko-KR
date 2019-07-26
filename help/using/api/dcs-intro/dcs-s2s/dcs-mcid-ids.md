---
description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대해 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대해 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-title: Experience Cloud ID 서비스를 통해 사용자 ID 및 지역 가져오기
solution: Audience Manager
title: Experience Cloud ID 서비스를 통해 사용자 ID 및 지역 가져오기
uuid: 80 de 6 cf 2-5 d 9 e -4 ef 8-a 0 f 2-d 53 b 5 d 574 c 89
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions Through the Experience Cloud ID Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make [!UICONTROL DCS] API calls.

## Get the User ID from the ID Service Cookie {#get-user-ids-from-service-cookie}

[Experience Cloud ID 서비스는](https://marketing.adobe.com/resources/help/en_US/mcvid/) 웹 사이트로 들어오는 사용자에게 방문자 및 지역 ID를 할당합니다. These IDs identify users across all the solutions in the [!DNL Experience Cloud] and they are required if you want to make [!UICONTROL DCS] calls.

* The [!UICONTROL user ID] is required to identify and associate data with a particular visitor.
* The [!UICONTROL region ID] is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

ID 서비스 고객은 ID 서비스 쿠키에서 또는 함수를 호출하여 이 정보를 추출할 수 있습니다. 아래 표는 작업을 시작하기 위해 완료해야 하는 작업에 대해 설명합니다.

*기울임꼴로* 된 코드는 변수 자리 표시자를 나타냅니다.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. <span class="keyword"> Experience Cloud</span> 상태 확인</b> </p> </td> 
   <td colname="col2"> <p>You need a <span class="keyword"> Experience Cloud</span> account to use the ID service. <span class="keyword"> Experience Cloud</span> 계정이 있는 경우, 탁월한! </p> <p> <span class="keyword"> Experience Cloud</span>에 속하지 않은 경우 등록하십시오. Adobe를 통해 더 많은 정보를 얻을 수 있습니다. For instructions on how to set up an account, see <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> Core Services - Enabling Your Solutions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. <span class="keyword"> ID 서비스 설정</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID 서비스는</span> 데이터 수집에 사용할 각 페이지에 삽입되는 JavaScript 코드로 구성됩니다. See the ID service <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> implementation guides</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. <span class="keyword"> ID 서비스</span> 쿠키 읽기</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID 서비스는</span> 사용자와 지역 ID를 AMCV 쿠키에 저장합니다. The full cookie name is <code>AMCV_<i>###</i>@AdobeOrg</code>. <code><i># # #</i></code> 요소는 조직 ID의 자리 표시자입니다. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>다음 키-값 쌍에 대한 AMCV 쿠키를 분석합니다. </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>MID =<i>사용자 ID</i></code>: 이 키-값 쌍은 <span class="keyword"> Experience Cloud</span> 사용자 ID를 보유합니다. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>AAMLH =<i>region ID</i></code>: 이 키-값 쌍은 지역 서버 이름과 연관된 영역 ID (때로 <span class="term"> 위치 힌트라고도</span>함) 를 유지합니다. </li> 
     </ul> </p> <p>You can make calls to the <span class="wintitle"> DCS</span> once you have the user and region IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Retrieve the <span class="keyword"> Experience Cloud ID</span> with getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(선택 사항)</i> 이 함수는 <span class="keyword"> Experience Cloud</span> 방문자 ID를 반환합니다. 사용자 정의 솔루션 및 특정 사용 사례에 맞게 설계되었습니다. See <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Working With getMarketingCloudVisitorID</a> below and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> related ID service documentation</a>. </p> <p>ID 서비스 쿠키에서 사용자 및 위치 ID를 받는 경우 이 매개 변수를 사용할 필요가 없습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Working With `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Another way to get the visitor ID is with the `getMarketingCloudVisitorID` function. When invoked, this function queries the [!DNL ID service] and returns an ID. `getMarketingCloudVisitorID` 다음과 같이 선택적 `callback` 인수를 수락합니다.

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback Usage and Purpose {#callback-usage}

`callback` 선택 사항입니다. This function works without it, but returns an ID only when a visitor has a [!DNL Experience Cloud] cookie in their browser. If the visitor cookie is missing, or a visitor doesn't have an ID, the function returns an empty `()` object. 페이지가 로드되고 방문자가 새 ID를 받은 후에도 이러한 상황이 발생할 수 있습니다. To avoid this, `callback` forces this function to check for a visitor ID after the page loads. Without `callback`, the visitor ID function won't return an ID even if it's written to the visitor's browser later.

## 다음 단계 {#next-steps}

Once you have the user and region ID, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).