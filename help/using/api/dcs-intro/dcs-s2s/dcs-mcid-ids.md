---
description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-title: Adobe Experience Platform Identity Service를 통해 사용자 ID 및 지역 가져오기
solution: Audience Manager
title: Adobe Experience Platform Identity Service를 통해 사용자 ID 및 지역 가져오기
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Adobe Experience Platform Identity Service를 통해 사용자 ID 및 지역 가져오기 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID 서비스 고객은 API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 [!UICONTROL DCS] 참조하십시오.

## ID 서비스 쿠키에서 사용자 ID 가져오기 {#get-user-ids-from-service-cookie}

Adobe [Experience Platform Identity Service는](https://marketing.adobe.com/resources/help/en_US/mcvid/) 웹 사이트를 방문하는 사용자에게 방문자 및 지역 ID를 할당합니다. 이러한 ID는 의 모든 솔루션에서 사용자를 식별하며, [!DNL Experience Cloud] 전화를 [!UICONTROL DCS] 하려는 경우 필요합니다.

* 데이터는 [!UICONTROL user ID] 특정 방문자를 식별하고 연결하는 데 필요합니다.
* 이 [!UICONTROL region ID] 값은 지역 서버 이름과 연결되어 있으므로 이 서버에 데이터를 보내야 합니다 [!UICONTROL DCS]. 사이트 방문자에게 지리적으로 가장 가까운 데이터 센터에 정보를 [!UICONTROL DCS] 저장합니다. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

ID 서비스 고객은 ID 서비스 쿠키나 함수를 호출하여 이 정보를 추출할 수 있습니다. 아래 표에서는 시작하기 위해 완료해야 하는 작업 또는 단계에 대해 설명합니다.

기울임꼴로 표시된 *코드는* 변수 자리 표시자를 나타냅니다.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Experience Cloud <span class="keyword"> 상태</span> 확인</b> </p> </td> 
   <td colname="col2"> <p>ID 서비스를 <span class="keyword"> 사용하려면</span> Experience Cloud 계정이 필요합니다. Experience Cloud <span class="keyword"> 계정이 있는</span> 경우, 감사합니다! </p> <p> Experience Cloud에 속하지 않는 <span class="keyword"> 경우</span>등록하십시오. 우리는 너를 만나고 싶고, 항상 더 많은 것을 위한 공간이 있다. 계정 설정 방법에 대한 지침은 핵심 서비스 - 솔루션 <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> 활성화를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>ID <span class="keyword"> 서비스는</span> 데이터 수집에 사용할 각 페이지에 삽입되는 JavaScript 코드로 구성됩니다. 자세한 내용은 ID 서비스 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> 구현 안내서를</a> 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. ID <span class="keyword"> 서비스</span> 쿠키 읽기</b> </p> </td> 
   <td colname="col2"> <p>ID <span class="keyword"> 서비스는</span> AMCV 쿠키에 사용자 및 지역 ID를 저장합니다. 전체 쿠키 이름은 <code>AMCV_<i>###</i>@AdobeOrg</code>입니다. 요소는 조직 ID의 자리 표시자입니다. <code><i>###</i></code> See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>AMCV 쿠키를 분석합니다. </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>:이 키-값 쌍은 Experience Cloud <span class="keyword"> 사용자 ID를</span> 보유합니다. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>:이 키-값 쌍은 지역 서버 이름과 연결된 영역 ID( <span class="term"> 위치 힌트라고도</span>함)를 보유합니다. </li> 
     </ul> </p> <p>사용자 및 지역 ID가 <span class="wintitle"> 있는</span> 경우 DCS를 호출할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. getMarketingCloud <span class="keyword"> VisitorID를</span> 사용하여 Experience Cloud ID 검색</b> </p> </td> 
   <td colname="col2"> <p><i>(선택 사항)</i> 이 함수는 Experience Cloud <span class="keyword"> 방문자 ID를</span> 반환합니다. 맞춤형 솔루션 및 특정 활용 사례를 위해 설계되었습니다. 아래의 getMarketingCloudVisitorID <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> 작업 및</a> 관련 ID 서비스 설명서를 <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"></a>참조하십시오. </p> <p>ID 서비스 쿠키에서 사용자 및 위치 ID를 가져오는 경우 이 옵션을 사용할 필요가 없습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 작업 `getMarketingCloudVisitorID`{#working-with-getmarketingcloudvisitorid}

방문자 ID를 얻는 또 다른 방법은 `getMarketingCloudVisitorID` 함수입니다. 이 함수는 호출될 때 를 쿼리하고 ID를 [!DNL ID service] 반환합니다. `getMarketingCloudVisitorID` 표시된 대로 선택적 `callback` 인수를 수락합니다.

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 콜백 사용 및 목적 {#callback-usage}

`callback` 은 선택 사항입니다. 이 함수는 ID 없이 작동하지만 방문자가 브라우저에 [!DNL Experience Cloud] 쿠키를 보유하고 있는 경우에만 ID를 반환합니다. 방문자 쿠키가 없거나 방문자에게 ID가 없는 경우 이 함수는 빈 `()` 개체를 반환합니다. 이 문제는 페이지가 로드되고 방문자가 새 ID를 받은 후에도 발생할 수 있습니다. 이 문제를 방지하려면 `callback` 페이지가 로드된 후 이 함수가 방문자 ID를 확인하도록 합니다. 방문자 `callback`ID가 없으면 방문자의 브라우저에 나중에 기록되더라도 방문자 ID가 반환되지 않습니다.

## 다음 단계 {#next-steps}

사용자 및 지역 ID가 있으면 [!UICONTROL DCS] 데이터 전송 및 수신을 시작할 수 있습니다. DCS [API 호출](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)만들기를 참조하십시오.