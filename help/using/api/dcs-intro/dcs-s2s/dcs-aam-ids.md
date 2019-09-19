---
description: 이 섹션에서는 DCS 응답을 분석하여 DCS에 대한 실시간 호출을 수행하는 데 필요한 방문자 및 지역 ID를 검색하는 방법에 대해 설명합니다.
seo-description: 이 섹션에서는 DCS 응답을 분석하여 DCS에 대한 실시간 호출을 수행하는 데 필요한 방문자 및 지역 ID를 검색하는 방법에 대해 설명합니다.
seo-title: DCS 응답에서 사용자 ID 및 지역 가져오기
solution: Audience Manager
title: DCS 응답에서 사용자 ID 및 지역 가져오기
uuid: 08036045-3b26-4d40-8e94-7d0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

이 섹션에서는 방문자를 실시간으로 호출하는 데 필요한 방문자 및 지역 ID를 검색하기 위한 [!UICONTROL DCS] 응답을 구문 분석하는 방법을 설명합니다 [!UICONTROL DCS].

## 사용자 및 지역 ID {#user-region-ids}

응답에는 사이트 방문자에 대한 데이터가 포함됩니다. [!UICONTROL DCS] 서버에 대한 서버 간 호출을 수행하려면 먼저 방문자 및 지역 ID가 필요합니다 [!UICONTROL DCS].

* 데이터를 식별하고 특정 방문자와 연결하려면 사용자 ID가 필요합니다.
* 지역 ID는 지역 서버 이름과 연결되어 있으므로 지역 ID가 필요합니다. 이 ID는 데이터를 [!UICONTROL DCS]로 보내야 합니다. 사이트 방문자에게 지리적으로 가장 가까운 데이터 센터에 정보를 [!UICONTROL DCS] 저장합니다. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

이러한 매개 변수는 아래에 설명되어 있습니다. 기울임꼴로 표시된 *코드는* 변수 자리 표시자를 나타냅니다.

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
   <td colname="col1"> <p><code>"uuid": <i>사용자 ID</i></code></span> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

이 간단한 응답은 `UUID` 및 지역을 보여줍니다 `ID`. 참고: 샘플 데이터만 있습니다. 로그 파일이 길어지고 복잡해질 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 다음 단계 {#next-steps}

사용자 ID와 지역 서버 이름이 있으면 [!UICONTROL DCS] 데이터 전송 및 수신을 시작할 수 있습니다. DCS [API 호출](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)만들기를 참조하십시오.
