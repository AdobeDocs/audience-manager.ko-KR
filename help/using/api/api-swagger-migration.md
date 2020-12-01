---
description: 여기 Audience Manager에서 엔지니어들, 개발자들 그리고 코드 닌자 같은 분들이죠 Adobe는 귀사와 같이 안정적이고 정확한 API 설명서를 사용하고 싶습니다. 따라서 Swagger에서 API 컨텐츠를 다시 작성하고 새로운 위치로 이동시킵니다. 이러한 변경 사항은 Audience Manager API 코드를 통해 경험을 향상시키는 데 도움이 됩니다.
seo-description: 여기 Audience Manager에서 엔지니어들, 개발자들 그리고 코드 닌자 같은 분들이죠 Adobe는 귀사와 같이 안정적이고 정확한 API 설명서를 사용하고 싶습니다. 따라서 Swagger에서 API 컨텐츠를 다시 작성하고 새로운 위치로 이동시킵니다. 이러한 변경 사항은 Audience Manager API 코드를 통해 경험을 향상시키는 데 도움이 됩니다.
seo-title: Audience Manager API 코드 마이그레이션
solution: Audience Manager
title: Audience Manager API 코드 마이그레이션
uuid: 93cc28c4-4b91-4c79-93d5-ece9bb4cc9d5
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 6%

---


# Audience Manager API 코드 마이그레이션 {#audience-manager-api-code-migration}

여기 Audience Manager에서 엔지니어들, 개발자들 그리고 코드 닌자 같은 분들이죠 Adobe는 귀사처럼 신뢰할 수 있고 정확한 [!DNL API] 설명서를 사용하여 작업하고자 합니다. 따라서 [!DNL Swagger]에 [!DNL API] 콘텐츠를 다시 쓰고 새 위치로 이동하는 중입니다. 이러한 변경 사항은 Audience Manager [!DNL API] 코드를 통해 사용자 경험을 향상시키는 데 도움이 됩니다.

## 위로 이동 {#code-migration-details}

<!-- api-swagger-migration.xml -->

[Adobe Audience Manager API 문서](https://bank.demdex.com/portal/swagger/index.html) 사이트는 수정된 [!DNL API] 컨텐츠의 새 홈입니다. 각 릴리스에 대해 몇 가지 [!DNL API] 메서드 세트를 다시 작성하고 이동하려고 합니다. 즉, 모든 사용 가능한 방법을 찾으려면 새 위치와 [REST API](../api/rest-api-main/rest-api-main.md) 설명서를 모두 체크 인해야 합니다. 결국 모든 공용 [!DNL API]은 [!DNL Audience Manager] [!DNL API] 문서 사이트에 있게 됩니다. 다음 표에는 수정된 및 마이그레이션된 [!DNL API]이 나열되어 있습니다.

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
---------|----------
| **[!UICONTROL Algorithmic Models**] | [알고리즘 모델](https://bank.demdex.com/portal/swagger/index.html#/Algorithmic_Models_API) |
| **[!UICONTROL Audience Marketplace]** | <ul><li>[데이터 피드](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/get_available_data_feeds_)</li><li>[데이터 피드 요청](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Buyer%20API/post_available_data_feeds__dataSourceId__requests)</li><li>[데이터 피드 재무](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Finance%20API/get_data_feeds_billing_report)</li><li>[데이터 피드 계획](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__plans_)</li><li>[데이터 피드 구독](https://bank.demdex.com/portal/swagger/index.html#/Audience%20Marketplace%20Seller%20API/get_data_feeds__dataSourceId__subscriptions)</li></ul> |
| **[!UICONTROL Data Sources]** | [데이터 소스 ](https://bank.demdex.com/portal/swagger/index.html#/Data_Source_API) |
| **[!UICONTROL Folders]** | <ul><li>[폴더 분할](https://bank.demdex.com/portal/swagger/index.html#/Segment_Folder_API)</li><li>[특성 폴더](https://bank.demdex.com/portal/swagger/index.html#/Trait%20Folder%20API)</li></ul> |
| **[!UICONTROL Reporting]** | [보고](https://bank.demdex.com/portal/swagger/index.html#/Reporting%20API) |
| **[!UICONTROL Segments]** | <ul><li>[세그먼트](https://bank.demdex.com/portal/swagger/index.html#/Segments%20API)</li><li>[세그먼트 테스트 그룹](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API)</li><li>[세그먼트 테스트 그룹 초안 API](https://bank.demdex.com/portal/swagger/index.html#/Segment%20Test%20Group%20API/post_segment_test_groups_drafts)</li></ul> |
| **[!UICONTROL Traits]** | [트레이트](https://bank.demdex.com/portal/swagger/index.html#/Traits%20API) |