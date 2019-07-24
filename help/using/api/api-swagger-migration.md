---
description: Adobe Audience Manager에서 개발자, 개발자, 코드 Ninjas 등을 만나볼 수 있습니다. 또한 신뢰할 수 있고 정확한 API 설명서를 사용하여 작업하고자 합니다. 따라서 Swagger에서 API 콘텐츠를 다시 작성하여 새로운 위치로 이동시켰습니다. 이러한 변경 사항은 Audience Manager API 코드를 사용하여 경험을 개선하는 데 도움이 됩니다.
seo-description: Adobe Audience Manager에서 개발자, 개발자, 코드 Ninjas 등을 만나볼 수 있습니다. 또한 신뢰할 수 있고 정확한 API 설명서를 사용하여 작업하고자 합니다. 따라서 Swagger에서 API 콘텐츠를 다시 작성하여 새로운 위치로 이동시켰습니다. 이러한 변경 사항은 Audience Manager API 코드를 사용하여 경험을 개선하는 데 도움이 됩니다.
seo-title: Audience Manager API 코드 마이그레이션
solution: Audience Manager
title: Audience Manager API 코드 마이그레이션
uuid: 93 CC 28 C 4-4 B 91-4 C 79-93 D 5-ECE 9 BB 4 CC 9 D 5
translation-type: tm+mt
source-git-commit: d368699d0de9a43cb7cf2c1af64da941a811db71

---


# Audience Manager API Code Migration {#audience-manager-api-code-migration}

Adobe Audience Manager에서 개발자, 개발자, 코드 Ninjas 등을 만나볼 수 있습니다. And, like you, we want to work with reliable, accurate [!DNL API] documentation. As a result, we're re-writing our [!DNL API] content in [!DNL Swagger] and moving it to a new location. These changes are designed to help improve your experience with the Audience Manager [!DNL API] code.

## Movin' On Up {#code-migration-details}

<!-- api-swagger-migration.xml -->

[Adobe Audience Manager API Docs](https://bank.demdex.com/portal/swagger/index.html) 사이트는 개정된 [!DNL API] 컨텐츠의 새로운 홈 사이트입니다. We'll try to re-write and move a few sets of [!DNL API] methods with each release. This means you'll have to check in both the new location and the [REST API](../api/rest-api-main/rest-api-main.md) documentation to find all of the available methods. Eventually, all of the public [!DNL API]s will be on the [!DNL Audience Manager] [!DNL API] docs site. The following table lists the revised and migrated [!DNL API]s.

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API 유형 </th> 
   <th colname="col2" class="entry"> API 메서드 </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>알고리즘 모델</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> 알고리즘 모델</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> 데이터 피드</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> 데이터 피드 요청</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> 데이터 피드 파이낸스</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> 데이터 피드 계획</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> 데이터 피드 구독</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>데이터 소스</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> 데이터 소스</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>파생 신호</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> 파생 신호</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>폴더</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> 폴더 분할</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> 특성 폴더</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>보고</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> 보고</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> 세그먼트</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> 세그먼트 테스트 그룹</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> 세그먼트 테스트 그룹 초안 API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>트레이트</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> 트레이트</a> </p> </td> 
  </tr>
 </tbody>
</table>