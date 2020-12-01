---
description: 이 섹션에서는 DCS를 실시간으로 호출하는 데 필요한 방문자 및 지역 ID를 검색하기 위해 DCS 응답을 구문 분석하는 방법을 설명합니다.
seo-description: 이 섹션에서는 DCS를 실시간으로 호출하는 데 필요한 방문자 및 지역 ID를 검색하기 위해 DCS 응답을 구문 분석하는 방법을 설명합니다.
seo-title: DCS 응답에서 사용자 ID 및 지역 가져오기
solution: Audience Manager
title: DCS 응답에서 사용자 ID 및 지역 가져오기
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 17%

---


# DCS 응답에서 사용자 ID 및 지역 가져오기 {#get-user-ids-and-regions-from-a-dcs-response}

이 섹션에서는 [!DNL DCS]을(를) 실시간으로 호출하는 데 필요한 방문자 및 지역 ID를 검색하기 위해 [!DNL DCS] 응답을 구문 분석하는 방법을 설명합니다.

## 사용자 및 지역 ID {#user-region-ids}

[!DNL DCS] 응답에는 사이트 방문자에 대한 데이터가 포함됩니다. [!DNL DCS]에 대한 서버 간 호출을 하려면 방문자 및 지역 ID가 필요합니다.

* 데이터를 식별하고 특정 방문자와 연결하려면 사용자 ID가 필요합니다.
* 지역 ID는 지역 서버 이름과 연결되어 있으므로 [!DNL DCS]에 데이터를 보내야 합니다. [!DNL DCS]은 사이트 방문자와 지리적으로 가장 가까운 데이터 센터에 정보를 저장합니다. [DCS 영역 ID, 위치 및 호스트 이름](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md)을 참조하십시오.

이러한 매개 변수는 아래에 설명되어 있습니다. *기울임체*&#x200B;의 코드는 변수 자리 표시자를 나타냅니다.

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
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 샘플 응답 {#sample-response}

이 단순 응답에는 `UUID` 및 지역 `ID`이 표시됩니다. 참고, 이것은 샘플 데이터입니다. 로그 파일의 길이가 길어지고 복잡할 수 있습니다.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## 다음 단계 {#next-steps}

사용자 ID와 지역 서버 이름이 있으면 [!DNL DCS] 데이터 전송 및 수신을 시작할 수 있습니다. [DCS API 호출 만들기](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)를 참조하십시오.
