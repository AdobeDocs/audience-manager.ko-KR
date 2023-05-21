---
description: ID 서비스 고객은 DCS API 호출을 수행하는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대한 정보를 보려면 이 섹션 을 참조하십시오.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 6%

---

# Adobe Experience Platform ID 서비스를 통해 사용자 ID 및 지역 가져오기 {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID 서비스 고객은 이 섹션을 참조하여 만드는 데 필요한 ID에 대한 방문자 쿠키를 읽는 방법에 대해 알아보십시오 [!DNL DCS] API 호출.

## ID 서비스 쿠키에서 사용자 ID 가져오기 {#get-user-ids-from-service-cookie}

다음 [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html) 웹 사이트를 방문하는 사용자에게 방문자 및 지역 ID를 할당합니다. 이러한 ID는 의 모든 솔루션에서 사용자를 식별합니다 [!DNL Experience Cloud] 만들고 싶다면 필수입니다. [!DNL DCS] 호출.

* 다음 [!UICONTROL user ID] 데이터를 식별하고 특정 방문자와 연결하는 데 필요합니다.
* 다음 [!UICONTROL region ID] 지역 서버 이름에 연결되어 있기 때문에 필요합니다. 데이터를 로 보내야 합니다. [!DNL DCS]. 다음 [!DNL DCS] 사이트 방문자에게 지리적으로 가장 가까운 데이터 센터에 정보를 저장합니다. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

ID 서비스 고객은 ID 서비스 쿠키나 함수를 호출하여 이 정보를 추출할 수 있습니다. 아래 표는 시작하기 위해 완료해야 하는 작업 또는 단계에 대해 설명합니다.

의 코드 *기울임체* 변수 자리 표시자를 나타냅니다.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 작업 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. 다음을 확인: <span class="keyword"> Experience Cloud</span> 상태</b> </p> </td> 
   <td colname="col2"> <p>다음이 필요합니다. <span class="keyword"> Experience Cloud</span> ID 서비스를 사용할 계정입니다. 다음 항목이 있는 경우: <span class="keyword"> Experience Cloud</span> 계정, 훌륭합니다! </p> <p> If you're not part of the <span class="keyword"> Experience Cloud</span>을 클릭한 다음 등록하십시오. 우리는 당신을 만나고 싶고, 항상 더 많은 것을 위한 여지가 있습니다. 계정을 설정하는 방법에 대한 지침은 <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> 핵심 서비스를 위한 솔루션 활성화</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. 다음을 설정합니다. <span class="keyword"> ID 서비스</span></b> </p> </td> 
   <td colname="col2"> <p>다음 <span class="keyword"> ID 서비스</span> 는 데이터 수집에 사용할 각 페이지에 배치되는 JavaScript 코드로 구성됩니다. ID 서비스 보기 <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> 구현 안내서</a> 추가 정보. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. 읽기 <span class="keyword"> ID 서비스</span> 쿠키</b> </p> </td> 
   <td colname="col2"> <p>다음 <span class="keyword"> ID 서비스</span> 사용자 및 지역 ID를 AMCV 쿠키에 저장합니다. 전체 쿠키 이름은 입니다. <code>AMCV_<i>###</i>@AdobeOrg</code>. 다음 <code><i>###</i></code> 요소는 조직 ID에 대한 자리 표시자입니다. 다음을 참조하십시오 <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Experience Cloud ID</a> 을 참조하십시오. </p> <p>다음 키-값 쌍에 대해 AMCV 쿠키를 구문 분석합니다. </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: 이 키-값 쌍은 <span class="keyword"> Experience Cloud</span> 사용자 ID. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: 이 키-값 쌍은 지역 ID(때로는이라고 함)를 보유합니다. <span class="term"> 위치 힌트</span>) 지역 서버 이름과 연결되어 있습니다. </li> 
     </ul> </p> <p>을(를) 호출하여 <span class="wintitle"> DCS</span> 사용자 및 지역 ID가 있는 경우 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. 검색 <span class="keyword"> EXPERIENCE CLOUD ID</span> (getMarketingCloudVisitorID 사용)</b> </p> </td> 
   <td colname="col2"> <p><i>(선택 사항)</i> 이 함수는 <span class="keyword"> Experience Cloud</span> 방문자 ID. 사용자 정의 솔루션 및 특정 사용 사례를 위해 설계되었습니다. 다음을 참조하십시오 <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> getMarketingCloudVisitorID를 사용하여 작업</a> 및 아래 <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> 관련 ID 서비스 설명서</a>. </p> <p>ID 서비스 쿠키에서 사용자 및 위치 ID를 가져오는 경우에는 이를 사용할 필요가 없습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 작업 `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

방문자 ID를 가져오는 다른 방법은 를 사용하는 것입니다. `getMarketingCloudVisitorID` 함수. 이 함수를 호출하면 [!DNL ID service] ID를 반환합니다. `getMarketingCloudVisitorID` 은(는) 선택 사항을 허용합니다. `callback` 표시된 인수:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### 콜백 사용 및 목적 {#callback-usage}

`callback` 는 선택 사항입니다. 이 함수는 이 없이 작동하지만 방문자에게 다음이 있는 경우에만 ID를 반환합니다. [!DNL Experience Cloud] 쿠키를 브라우저에 넣습니다. 방문자 쿠키가 없거나 방문자에게 ID가 없는 경우 이 함수는 빈 을 반환합니다 `()` 개체. 이 문제는 페이지가 로드되고 방문자가 새 ID를 받은 후에도 발생할 수 있습니다. 이 문제를 방지하려면 `callback` 는 페이지가 로드된 후 이 함수가 방문자 ID를 확인하도록 강제합니다. 없이 `callback`, 방문자 ID 함수는 나중에 방문자의 브라우저에 작성되더라도 ID를 반환하지 않습니다.

## 다음 단계 {#next-steps}

사용자 및 지역 ID가 있으면 송수신을 시작할 수 있습니다 [!DNL DCS] 데이터. 다음을 참조하십시오 [DCS API 호출 만들기](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
