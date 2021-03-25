---
description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-title: Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기
solution: Audience Manager
title: Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e40233ace5cb74743db7d0f9f90707fa596a7e79
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 9%

---


# Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID 서비스 고객은 [!DNL DCS] API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 자세한 내용은 이 섹션을 참조하십시오.

## ID 서비스 쿠키 {#get-user-ids-from-service-cookie}에서 사용자 ID 가져오기

[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html)는 웹 사이트를 방문하는 사용자에게 방문자 및 지역 ID를 할당합니다. 이러한 ID는 [!DNL Experience Cloud]에 있는 모든 솔루션에서 사용자를 식별하며 [!DNL DCS] 호출을 수행하려면 이러한 ID가 필요합니다.

* 데이터를 식별하고 특정 방문자와 연결하는 데 [!UICONTROL user ID]이 필요합니다.
* [!UICONTROL region ID]은(는) 데이터를 [!DNL DCS]에 보내야 하는 지역 서버 이름에 연결되어 있으므로 필요합니다. [!DNL DCS]은 사이트 방문자와 지리적으로 가장 가까운 데이터 센터에 정보를 저장합니다. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

ID 서비스 고객은 ID 서비스 쿠키나 함수를 호출하여 이 정보를 추출할 수 있습니다. 아래 표는 시작하는 데 필요한 작업 또는 단계에 대해 설명합니다.

*기울임체*&#x200B;의 코드는 변수 자리 표시자를 나타냅니다.

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
   <td colname="col2"> <p>ID 서비스를 사용하려면 <span class="keyword"> Experience Cloud</span> 계정이 필요합니다. <span class="keyword"> Experience Cloud</span> 계정이 있는 경우 좋습니다! </p> <p> <span class="keyword"> Experience Cloud</span>에 속하지 않은 경우 등록합니다. 우리는 너를 갖고 싶어. 그리고 항상 더 많은 것을 할 수 있는 공간이 있다. 계정 설정 방법에 대한 지침은 <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> 핵심 서비스용 솔루션 활성화</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. <span class="keyword"> ID 서비스</span></b> 설정 </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID 서비스</span>는 데이터 수집에 사용할 각 페이지에 삽입되는 JavaScript 코드로 구성됩니다. 자세한 내용은 ID 서비스 <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> 구현 안내서</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. <span class="keyword"> ID 서비스</span> 쿠키 읽기</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> ID 서비스</span>는 사용자 및 지역 ID를 AMCV 쿠키에 저장합니다. 전체 쿠키 이름은 <code>AMCV_<i>###</i>@AdobeOrg</code>입니다. <code><i>###</i></code> 요소는 조직 ID의 자리 표시자입니다. 자세한 내용은 <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Experience Cloud ID</a>를 참조하십시오. </p> <p>AMCV 쿠키에 이러한 키-값 쌍을 구문 분석합니다. </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>:이 키-값 쌍은  <span class="keyword"> Experience </span> Cloud 사용자 ID를 보유합니다. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>:이 키-값 쌍은 지역 서버 이름과 연결된 영역 ID( <span class="term"> 위치 힌트라고도 함</span>)를 보유합니다. </li> 
     </ul> </p> <p>사용자 및 지역 ID가 있으면 <span class="wintitle"> DCS</span>를 호출할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. getMarketingCloudVisitorID</b>로 <span class="keyword"> Experience Cloud ID</span> 검색 </p> </td> 
   <td colname="col2"> <p><i>(선택 사항)</i> 이 함수는  <span class="keyword"> Experience Cloud 방문자 </span> ID를 반환합니다. 맞춤형 솔루션 및 특정 활용 사례를 위해 설계되었습니다. <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> 아래의 getMarketingCloudVisitorID</a> 작업 및 <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> 관련 ID 서비스 설명서</a>을 참조하십시오. </p> <p>ID 서비스 쿠키에서 사용자 및 위치 ID를 가져오는 경우 이 옵션을 사용할 필요가 없습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid} 작업

방문자 ID를 얻는 또 다른 방법은 `getMarketingCloudVisitorID` 함수를 사용하는 것입니다. 이 함수를 호출하면 이 함수는 [!DNL ID service]을 쿼리하고 ID를 반환합니다. `getMarketingCloudVisitorID` 다음과 같이 선택적  `callback` 인수를 수락합니다.

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 콜백 사용 및 목적 {#callback-usage}

`callback` 은 선택 사항입니다. 이 함수는 그 없이 작동하지만 방문자의 브라우저에 [!DNL Experience Cloud] 쿠키가 있을 때만 ID를 반환합니다. 방문자 쿠키가 없거나 방문자에게 ID가 없는 경우 이 함수는 빈 `()` 개체를 반환합니다. 이 문제는 페이지가 로드되고 방문자가 새 ID를 받은 후에도 발생할 수 있습니다. 이를 방지하기 위해 `callback`은 페이지가 로드된 후 이 함수를 방문자 ID를 확인하도록 합니다. `callback` 없이 방문자 ID 함수는 나중에 방문자의 브라우저에 기록되더라도 ID를 반환하지 않습니다.

## 다음 단계 {#next-steps}

사용자 및 지역 ID가 있으면 [!DNL DCS] 데이터를 보내고 받을 수 있습니다. [DCS API 호출 만들기](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)를 참조하십시오.