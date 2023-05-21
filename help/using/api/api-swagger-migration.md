---
description: 여기 Audience Manager에서 우리는 여러분과 마찬가지로 엔지니어, 개발자, 그리고 코드 닌자입니다. 그리고 귀하와 마찬가지로 신뢰할 수 있고 정확한 API 설명서를 사용하려고 합니다. 따라서 Swagger에서 API 콘텐츠를 다시 작성하여 새 위치로 이동하고 있습니다. 이러한 변경 사항은 Audience Manager API 코드에 대한 경험을 개선하는 데 도움이 되도록 설계되었습니다.
seo-description: Here at Audience Manager, we're engineers, developers, and code ninjas just like you. And, like you, we want to work with reliable, accurate API documentation. As a result, we're re-writing our API content in Swagger and moving it to a new location. These changes are designed to help improve your experience with the Audience Manager API code.
seo-title: Audience Manager API Code Migration
solution: Audience Manager
title: Audience Manager API 코드 마이그레이션
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
feature: API
exl-id: 081be8a7-5029-45b1-8fb1-0531d5090fe0
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 5%

---

# Audience Manager API 코드 마이그레이션 {#audience-manager-api-code-migration}

여기 Audience Manager에서 우리는 여러분과 마찬가지로 엔지니어, 개발자, 그리고 코드 닌자입니다. 그리고 여러분과 마찬가지로, 우리는 신뢰할 수 있고 정확하게 작업하기를 원합니다 [!DNL API] 설명서를 참조하십시오. 그 결과, 우리는 우리의 [!DNL API] 콘텐츠 [!DNL Swagger] 새 위치로 이동합니다. 이러한 변경 사항은 Audience Manager 경험을 개선하는 데 도움이 되도록 설계되었습니다 [!DNL API] 코드.

## 위로 이동 {#code-migration-details}

<!-- api-swagger-migration.xml -->

다음 [Adobe Audience Manager API 문서](https://bank.demdex.com/portal/swagger/index.html) 사이트는 우리의 수정된 새로운 집입니다 [!DNL API] 콘텐츠. 다시 작성하여 몇 세트 이동 [!DNL API] 각 릴리스에 포함된 메서드. 즉, 새 위치와 을(를) 모두 체크 인해야 합니다. [나머지 API](../api/rest-api-main/rest-api-main.md) 사용 가능한 모든 메서드를 찾을 수 있는 설명서입니다. 결국, 모든 대중들은 [!DNL API]s은(는) 다음에 있습니다. [!DNL Audience Manager] [!DNL API] 문서 사이트. 다음 표에는 수정된 내용과 마이그레이션된 내용이 나와 있습니다 [!DNL API]s.

<!--

<table id="table_CD3C244CB02C48C898745FB982EC828C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API Type </th> 
   <th colname="col2" class="entry"> API Methods </th> 
  </tr> 
 </thead>
 <tbody>
 <tr> 
   <td colname="col1"> <p> <b>Algorithmic Models</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API" format="https" scope="external"> Algorithmic Models</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Audience Marketplace</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4CFB3FAAC0B04E5AADD80E7D7FAF2722"> 
      <li id="li_50EE5F6B2278480E9FEA04AD51664F9D"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_API" format="https" scope="external"> Data Feeds</a> </li> 
      <li id="li_5D372E3819014AB78C12048A9A2DC89F"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Request_API/" format="https" scope="external"> Data Feed Request</a> </li> 
      <li id="li_0582688D08C346C68B81D86A5C46E053"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Finance_API" format="https" scope="external"> Data Feed Finance</a> </li> 
      <li id="li_C1C1CB42D6A74803B4672F6EE2D2D08C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/?f=Data_Feed_Plans_API" format="https" scope="external"> Data Feed Plans</a> </li> 
      <li id="li_D8F9D791D0824287B9D0B0585E3106AB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Feed_Subscription_API" format="https" scope="external"> Data Feed Subscriptions</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Data Source</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Data_Source_API" format="https" scope="external"> Data Sources</a> </p> </td> 
  </tr> 
   <td colname="col1"> <p> <b>Derived Signals</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#/Derived_Signals_API" format="https" scope="external"> Derived Signals</a> </p> </td> 
  </tr>   
  <tr> 
   <td colname="col1"> <p> <b>Folders</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FD05673B372141F3B0EF2C79A338F744"> 
      <li id="li_5D16FCAF6F0E411694A1CFBE9571BDAC"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Folder_API" format="https" scope="external"> Segment Folders</a> </li> 
      <li id="li_5DC088C0F8CA4FC193248366C8400030"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Trait_Folder_API" scope="external" format="https"> Trait Folders</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Reporting</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Reporting_API" format="https" scope="external"> Reporting</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segments</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_098B0655653D4846B70349A35A055C19"> 
      <li id="li_41A3003BF41147969BC88D4F12A5C1BB"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segments_API" format="https" scope="external"> Segments</a> </li> 
      <li id="li_22A858D377634D88AE58BE2CE924169C"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_API/" format="https" scope="external"> Segment Test Groups</a> </li> 
      <li id="li_2B505A1B43CF4B29A0336106C321E7FD"> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Segment_Test_Group_Draft_API/" format="https" scope="external"> Segment Test Group Draft API</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Traits</b> </p> </td> 
   <td colname="col2"> <p> <a href="https://bank.demdex.com/portal/swagger/index.html#!/Traits_API" format="https" scope="external"> Traits</a> </p> </td> 
  </tr>
 </tbody>
</table>

-->


| API 유형 | API 메서드 |
|---------|----------|
| **[!UICONTROL Algorithmic Models**] | [알고리즘 모델](https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API) |
| **[!UICONTROL Audience Marketplace]** | <ul><li>[데이터 피드](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/get_available_data_feeds_)</li><li>[데이터 피드 요청](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/post_available_data_feeds__dataSourceId__requests)</li><li>[데이터 피드 재무](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Finance%20API/get_data_feeds_billing_report)</li><li>[데이터 피드 계획](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__plans_)</li><li>[데이터 피드 구독](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__subscriptions)</li></ul> |
| **[!UICONTROL Data Sources]** | [데이터 소스 ](https://bank.demdex.com/portal/swagger/index.html#/Data_Source_API) |
| **[!UICONTROL Folders]** | <ul><li>[폴더 분할](https://bank.demdex.com/portal/swagger/index.html#/Segment_Folder_API)</li><li>[트레이트 폴더](https://bank.demdex.com/portal/swagger/index.html#/Trait%20Folder%20API)</li></ul> |
| **[!UICONTROL Reporting]** | [보고](https://bank.demdex.com/portal/swagger/index.html#/Reporting%20API) |
| **[!UICONTROL Segments]** | <ul><li>[세그먼트](https://bank.demdex.com/portal/swagger/index.html#/Segments%20API)</li><li>[세그먼트 테스트 그룹](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API)</li><li>[세그먼트 테스트 그룹 초안 API](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API/post_segment_test_groups_drafts)</li></ul> |
| **[!UICONTROL Traits]** | [트레이트](https://bank.demdex.com/portal/swagger/index.html#/Traits%20API) |
