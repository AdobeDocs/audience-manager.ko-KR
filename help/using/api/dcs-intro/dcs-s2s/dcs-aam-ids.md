---
description: 이 섹션에서는 DCS를 실시간으로 호출하는 데 필요한 방문자 및 지역 ID를 검색하기 위해 DCS 응답을 구문 분석하는 방법에 대해 설명합니다.
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: DCS 응답에서 사용자 ID 및 지역 가져오기
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 16%

---

# DCS 응답에서 사용자 ID 및 지역 가져오기 {#get-user-ids-and-regions-from-a-dcs-response}

이 섹션에서는 다음을 구문 분석하는 방법을 설명합니다. [!DNL DCS] 에 대한 실시간 호출을 수행하는 데 필요한 방문자 및 지역 ID 검색에 대한 응답 [!DNL DCS].

## 사용자 및 지역 ID {#user-region-ids}

A [!DNL DCS] 응답에는 사이트 방문자에 대한 데이터가 포함됩니다. 에 대해 서버 간 호출을 하려면 방문자 및 지역 ID가 필요합니다. [!DNL DCS].

* 사용자 ID는 데이터를 식별하고 특정 방문자와 연결하는 데 필요합니다.
* 지역 ID는 데이터를 로 보내야 하는 지역 서버 이름에 연결되어 있기 때문에 필요합니다. [!DNL DCS]. 다음 [!DNL DCS] 사이트 방문자에게 지리적으로 가장 가까운 데이터 센터에 정보를 저장합니다. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

이러한 매개변수는 아래에 설명되어 있습니다. 의 코드 *기울임체* 변수 자리 표시자를 나타냅니다.

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
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

이 간단한 응답은 다음을 보여줍니다. `UUID` 및 지역 `ID`. 참고: 이 데이터는 샘플 데이터입니다. 로그 파일이 더 길고 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 다음 단계 {#next-steps}

사용자 ID와 지역 서버 이름이 있으면 송수신을 시작할 수 있습니다 [!DNL DCS] 데이터. 다음을 참조하십시오 [DCS API 호출 만들기](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
