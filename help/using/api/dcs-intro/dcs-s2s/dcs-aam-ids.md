---
description: 이 섹션에서는 DCS 응답을 분석하여 DCS를 실시간 호출하는 데 필요한 방문자 및 지역 ID를 검색하는 방법에 대해 설명합니다.
seo-description: 이 섹션에서는 DCS 응답을 분석하여 DCS를 실시간 호출하는 데 필요한 방문자 및 지역 ID를 검색하는 방법에 대해 설명합니다.
seo-title: DCS 응답에서 사용자 ID 및 지역 가져오기
solution: Audience Manager
title: DCS 응답에서 사용자 ID 및 지역 가져오기
uuid: 08036045-3 B 26-4 D 40-8 E 94-7 D 0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

[!UICONTROL DCS] 응답에는 사이트 방문자에 대한 데이터가 포함됩니다. You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* 사용자 ID는 데이터를 식별하고 특정 방문자와 연결하는 데 필요합니다.
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

이러한 매개 변수는 아래에 설명되어 있습니다. *기울임꼴로* 된 코드는 변수 자리 표시자를 나타냅니다.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 데이터 유형 </th> 
   <th colname="col3" class="entry"> 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>" uuid ": <i>사용자 ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p> <code> " uuid ": " 123456789 "</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>" dcs_ region ":<i>지역 ID</i></code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p> <code> " dcs_ region ": 9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

This simple response shows the `UUID` and region `ID`. 참고: 이것은 샘플 데이터뿐입니다. 로그 파일이 더 길고 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 다음 단계 {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
