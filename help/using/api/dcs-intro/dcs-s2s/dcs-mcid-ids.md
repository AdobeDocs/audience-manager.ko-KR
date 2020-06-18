---
description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용을 이 섹션을 참조하십시오.
seo-description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용을 이 섹션을 참조하십시오.
seo-title: Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기
solution: Audience Manager
title: Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 9%

---


# Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID 서비스 고객은 [!DNL DCS] API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용을 이 섹션을 참조하십시오.

## ID 서비스 쿠키에서 사용자 ID 가져오기 {#get-user-ids-from-service-cookie}

Adobe Experience Platform [ID 서비스는](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html) 웹 사이트를 방문하는 사용자에게 방문자 및 지역 ID를 할당합니다. 이러한 ID는 의 모든 솔루션에서 사용자를 식별하며 전화를 걸려면 [!DNL Experience Cloud] 이 [!DNL DCS] 필요합니다.

* 이 [!UICONTROL user ID] 는 데이터를 식별하고 특정 방문자와 연결하는 데 필요합니다.
* 이 [!UICONTROL region ID] 는 지역 서버 이름에 연결되어 있으므로 이 서버에 데이터를 보내야 합니다 [!DNL DCS]. 사이트 방문자에게 지리적으로 가장 가까운 데이터 센터에 정보를 [!DNL DCS] 저장합니다. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

ID 서비스 고객은 ID 서비스 쿠키나 함수를 호출하여 이 정보를 추출할 수 있습니다. 아래 표에서는 시작하기 위해 완료해야 하는 작업 또는 단계에 대해 설명합니다.

기울임꼴의 *코드는* 변수 자리 표시자를 나타냅니다.

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
   <td colname="col2"> <p>ID 서비스를 사용하려면 <span class="keyword"> Experience Cloud</span> 계정이 필요합니다. 만약 <span class="keyword"> Experience Cloud</span> 계정이 있다면, 좋습니다! </p> <p> 사용자가 <span class="keyword"> Experience Cloud</span>에 속하지 않으면 등록하십시오. 우리는 당신을 갖고 싶고, 더 많은 것을 위한 여지도 항상 있습니다. 계정 설정 방법에 대한 지침은 핵심 서비스용 솔루션 <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> 활성화를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>ID 서비스 <span class="keyword"> 는</span> 데이터 수집에 사용할 각 페이지에 삽입되는 JavaScript 코드로 구성됩니다. 자세한 내용은 ID 서비스 <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> 구현 안내서를</a> 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. ID <span class="keyword"> 서비스</span> 쿠키 읽기</b> </p> </td> 
   <td colname="col2"> <p>ID 서비스는 <span class="keyword"></span> 사용자 및 지역 ID를 AMCV 쿠키에 저장합니다. 전체 쿠키 이름은 입니다 <code>AMCV_<i>###</i>@AdobeOrg</code>. 이 <code><i>###</i></code> 요소는 조직 ID의 자리 표시자입니다. See <a href="https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>AMCV 쿠키에 대해 다음 키-값 쌍을 분석합니다. </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: 이 키-값 쌍은 <span class="keyword"> Experience Cloud</span> 사용자 ID를 보유합니다. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: 이 키-값 쌍은 지역 서버 이름과 연결된 영역 ID(위치 힌트라고도 함 <span class="term"></span>)를 보유합니다. </li> 
     </ul> </p> <p>사용자 및 지역 ID가 있는 경우 <span class="wintitle"> DCS를</span> 호출할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. getMarketingCloudVisitorID로 <span class="keyword"> Experience Cloud ID</span> 검색</b> </p> </td> 
   <td colname="col2"> <p><i>(선택 사항)</i> 이 함수는 <span class="keyword"> Experience Cloud 방문자 ID를</span> 반환합니다. 맞춤형 솔루션 및 특정 활용 사례에 맞게 설계되었습니다. 아래의 getMarketingCloudVisitorID <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> 작업 및</a> 관련 ID 서비스 설명서를 참조하십시오 <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"></a>. </p> <p>ID 서비스 쿠키에서 사용자 및 위치 ID를 가져오는 경우 이 옵션을 사용할 필요가 없습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 작업 `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

방문자 ID를 얻는 또 다른 방법은 이 `getMarketingCloudVisitorID` 함수와 함께 사용하는 것입니다. 이 함수를 호출하면 이 함수는 [!DNL ID service] 를 쿼리하고 ID를 반환합니다. `getMarketingCloudVisitorID` 에 표시된 대로 선택적 `callback` 인수를 수락합니다.

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 콜백 사용 및 목적 {#callback-usage}

`callback` 은 선택 사항입니다. 이 함수는 ID 없이 작동하지만 방문자의 브라우저에 [!DNL Experience Cloud] 쿠키가 있는 경우에만 ID를 반환합니다. 방문자 쿠키가 없거나 방문자에게 ID가 없는 경우 이 함수는 빈 `()` 개체를 반환합니다. 페이지가 로드되고 방문자가 새 ID를 받은 후에도 이러한 문제가 발생할 수 있습니다. 이를 방지하려면 페이지가 로드된 후 이 기능이 방문자 ID를 확인하도록 `callback` 합니다. 그렇지 `callback`않으면 방문자 ID 함수는 나중에 방문자의 브라우저에 기록되더라도 ID를 반환하지 않습니다.

## 다음 단계 {#next-steps}

사용자 및 지역 ID가 있으면 데이터 전송 및 수신을 시작할 수 [!DNL DCS] 있습니다. DCS [API 호출 만들기를 참조하십시오](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).