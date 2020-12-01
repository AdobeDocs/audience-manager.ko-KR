---
description: 지정된 destinationId의 대상을 반환하는 GET 메서드입니다.
seo-description: 지정된 destinationId의 대상을 반환하는 GET 메서드입니다.
seo-title: 대상 ID별 대상 반환
solution: Audience Manager
title: 대상 ID별 대상 반환
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 9%

---


# 대상 ID별 대상 반환 {#return-a-destination-by-destination-id}

지정한 `destinationId`의 대상을 반환하는 `GET` 메서드입니다.

<!-- r_get_all_destinations_order_id.xml -->

## 요청

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>URL의 `includeMappings=true`에 있는 `mappings` 필드를 채우려면

## 응답

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## 모든 대상 반환 {#return-all-destinations}

지정된 파트너의 모든 대상을 반환하는 `GET` 메서드입니다.

<!-- r_get_all_destinations.xml -->

### 요청

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(선택 사항)* 지정된 세그먼트 `containsSegment=<sid>` 에 매핑된 모든 대상의 배열을 반환하려면 전달됩니다. 예를 들어 쿼리는 다음과 비슷합니다.`GET .../destinations/?containsSegment=4321`.
   >
   >
* 전체 대상 개체를 반환하지 않습니다. 완전히 채워진 개체가 필요한 경우 데이터 순서로 대상을 가져옵니다.


### 선택적 쿼리 매개 변수

개체에 대해 *모든* 속성을 반환하는 API 메서드에서 이러한 선택적 매개 변수를 사용할 수 있습니다. 요청 문자열에서 해당 쿼리를 [!DNL API]에 전달할 때 이 옵션을 설정합니다. [선택적 매개 변수](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)를 참조하십시오.

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th>
   <th colname="col2" class="entry"> 설명 </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> 페이지 번호별로 결과를 반환합니다. 번호 매기는 0부터 시작됩니다. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> 요청에 의해 반환되는 응답 결과 수를 설정합니다(기본값 10). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">지정된 <span class="keyword"> JSON</span> 속성에 따라 결과를 정렬하고 반환합니다. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> 결과를 내림차순으로 정렬하고 반환합니다. 기본값은 오름차순입니다. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">검색 매개 변수로 사용할 지정된 문자열을 기반으로 결과를 반환합니다. 예를 들어 해당 항목에 대한 값 필드에 "Test"라는 단어가 있는 모든 모델의 결과를 찾으려고 합니다. 샘플 요청은 다음과 같습니다. <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>에서 보냅니다. </p> <p>"get all" 메서드에서 반환되는 모든 값을 검색할 수 있습니다. </p> </td>
  </tr>
 </tbody>
</table>

### 응답

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## 매핑 ID가 {#return-dest-mapping-id}인 대상 매핑을 반환합니다.

`mappingId`에 따라 개별 대상 매핑을 반환하는 `GET` 메서드입니다.

<!-- r_get_destination_trait_data_order.xml -->

### 요청

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### 응답

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## 반환 대상 매핑 {#return-dest-mappings}

대상에 대한 매핑을 반환하는 `GET` 메서드입니다.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>반환된 매핑은 대상 유형 및 구성에 따라 다릅니다.

### 요청

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>페이징 매개 변수를 지원합니다.

### 응답

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## 사용 가능한 모든 대상 플랫폼 반환 {#return-dest-platforms}

대상에 대해 사용 가능한 모든 장치 플랫폼을 반환하는 `GET` 메서드입니다.

<!-- r_get_dest_platforms.xml -->

### 요청

`GET /destinations/configurations/available-platforms/`

### 응답

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## 반환 S2S 및 벌크 S2S 대상 작업 내역 {#return-job-history}

아웃바운드 [!UICONTROL Server-to-Server]( [!UICONTROL S2S]) 및 벌크 [!UICONTROL S2S] 대상 작업 내역 정보를 반환하는 `GET` 메서드입니다.

<!-- r_get_job_history.xml -->

### 요청

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

필요한 쿼리 매개 변수:`startDate` = *&lt;`epochtime`* 및 `endDate` = *&lt;`epochtime`*

### 응답

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
