---
description: Audience Manager의 방문자 인증 상태는 새 트레이트 정보가 방문자의 인증된 프로필이나 데이터가 수집되는 장치 프로필에 기록되는지 여부를 결정합니다. Audience Manager은 동일한 방식으로 이벤트 호출에서 방문자 ID 인증 상태 알 수 없음 및 LOGGED_OUT을 처리합니다.
keywords: dpm.demdex.net
seo-description: Audience Manager의 방문자 인증 상태는 새 트레이트 정보가 방문자의 인증된 프로필이나 데이터가 수집되는 장치 프로필에 기록되는지 여부를 결정합니다. Audience Manager은 동일한 방식으로 이벤트 호출에서 방문자 ID 인증 상태 알 수 없음 및 LOGGED_OUT을 처리합니다.
seo-title: Audience Manager의 방문자 인증 상태
solution: Audience Manager
title: Audience Manager의 방문자 인증 상태
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: 참조
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 5%

---

# Audience Manager의 방문자 인증 상태{#visitor-authentication-states-in-audience-manager}

Audience Manager의 방문자 인증 상태는 새 트레이트 정보가 방문자의 인증된 프로필이나 데이터가 수집되는 장치 프로필에 기록되는지 여부를 결정합니다. Audience Manager은 동일한 방식으로 이벤트 호출에서 방문자 ID 인증 상태 알 수 없음 및 LOGGED_OUT을 처리합니다.

[!DNL Experience Cloud] ID 서비스 v1.5+부터 `setCustomerID` 메서드에는 선택적 `AuthState` 개체가 포함됩니다. `AuthState` 인증 상태에 따라 방문자를  [식별합니다](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] 호출에서 전달된 인증 상태와 세그멘테이션에 사용하는  [프로필 병합 ](../features/profile-merge-rules/merge-rules-dashboard.md) 규칙에 따라 실현된 트레이트를 다르게 처리합니다.

## 인증 상태:알 수 없음 {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>요청 값 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>인증된 </b> 프로필의 읽기 정보 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>인증된 </b> 프로필에 새 트레이트 쓰기 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>예, 인증된 옵션 병합 규칙 = "마지막으로 인증된 프로필"인 경우. </p> </td> 
   <td colname="col3" morerows="1"> <p>아니요, 특성 데이터가 장치 프로필에 추가됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>아니요, 인증된 옵션 병합 규칙 = "현재 인증된 프로필" 또는 "인증된 프로필 없음"인 경우. </p> </td> 
  </tr> 
 </tbody> 
</table>

샘플 호출(인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 인증 상태:인증된 {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>요청 값 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>인증된 </b> 프로필의 읽기 정보 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>인증된 </b> 프로필에 새 트레이트 쓰기 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>예, 인증된 옵션 병합 규칙 = "현재 인증된 프로필" 또는 "마지막으로 인증된 프로필"인 경우. </p> </td> 
   <td colname="col3" morerows="1"> <p>예, 트레이트 데이터는 인증된 프로필에 추가됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>아니요, 인증된 옵션 병합 규칙 = "인증된 프로필 없음"인 경우. </p> </td> 
  </tr> 
 </tbody> 
</table>

샘플 호출(인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 인증 상태:LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>요청 값 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>인증된 </b> 프로필의 읽기 정보 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>인증된 </b> 프로필에 새 트레이트 쓰기 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> 예, 인증된 옵션 병합 규칙 = "마지막으로 인증된 프로필" </td> 
   <td colname="col3" morerows="1"> <p>아니오. 트레이트 데이터는 장치 프로파일에 기록됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 아니요, 인증된 옵션 병합 규칙 = "현재 인증된 프로필" 또는 "인증된 프로필 없음"인 경우 </td> 
  </tr> 
 </tbody> 
</table>

샘플 호출(인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 3개의 경우 모두 [에서 CID와 ](../reference/ids-in-aam.md) UUID 간의 ID 동기화를 수행합니다.

>[!MORELIKETHIS]
>
>* [고객 ID 및 인증 상태](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

