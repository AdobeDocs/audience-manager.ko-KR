---
description: Audience Manager의 방문자 인증 상태는 새로운 트레이트 정보가 방문자의 인증된 프로필 또는 데이터를 수집한 장치 프로파일에 작성되었는지 여부를 결정합니다. Audience Manager는 같은 방식으로 이벤트 호출에서 방문자 ID 인증 상태를 알 수 없고 logged_ out를 처리합니다.
keywords: dpm.demdex.net
seo-description: Audience Manager의 방문자 인증 상태는 새로운 트레이트 정보가 방문자의 인증된 프로필 또는 데이터를 수집한 장치 프로파일에 작성되었는지 여부를 결정합니다. Audience Manager는 같은 방식으로 이벤트 호출에서 방문자 ID 인증 상태를 알 수 없고 logged_ out를 처리합니다.
seo-title: Audience Manager의 방문자 인증 상태
solution: Audience Manager
title: Audience Manager의 방문자 인증 상태
uuid: D 748 C 0 C 3-5833-4 FB 9-AB 3 E -793 F 5 F 252 E 47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

Audience Manager의 방문자 인증 상태는 새로운 트레이트 정보가 방문자의 인증된 프로필 또는 데이터를 수집한 장치 프로파일에 작성되었는지 여부를 결정합니다. Audience Manager는 같은 방식으로 이벤트 호출에서 방문자 ID 인증 상태를 알 수 없고 logged_ out를 처리합니다.

[!DNL Experience Cloud] ID 서비스 v 1.5 + 부터 `setCustomerID` 이 방법에는 선택적 `AuthState` 개체가 포함됩니다. `AuthState` 인증 상태에 따라 방문자를 [식별합니다](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). [!DNL Audience Manager] 호출에서 전달된 인증 상태와 세그멘테이션에 사용하는 [프로필 병합 규칙에](../features/profile-merge-rules/merge-rules-dashboard.md) 따라 구현된 트레이트를 다르게 처리합니다.

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>요청 값 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>인증된 프로필에서</b> 정보 읽기 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>인증된</b> 프로필에 새로운 특성 작성 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>예, 인증된 옵션 병합 규칙 = "마지막으로 인증된 프로파일" 인 경우 </p> </td> 
   <td colname="col3" morerows="1"> <p>아니요. 트레이트 데이터가 장치 프로필에 추가됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>아니요. 인증된 옵션인 Merge Rule = "Current Authenticated Profiles" 또는 "No Authenticated Profile" 이 있습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

샘플 호출 (인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>요청 값 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>인증된 프로필에서</b> 정보 읽기 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>인증된</b> 프로필에 새로운 특성 작성 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>예, 인증된 옵션인 Merge Rule = "Current Authenticated Profiles" 또는 "Last Authenticated Profiles" 입니다. </p> </td> 
   <td colname="col3" morerows="1"> <p>예. 트레이트 데이터가 인증된 프로필에 추가됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>아니요. 인증된 옵션인 merge rule = "Authenticated Profile" 이 없습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

샘플 호출 (인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>요청 값 </p> </th> 
   <th colname="col2" class="entry"> <p> <b>인증된 프로필에서</b> 정보 읽기 </p> </th> 
   <th colname="col3" class="entry"> <p> <b>인증된</b> 프로필에 새로운 특성 작성 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> 예, 인증된 옵션 병합 규칙 = "마지막으로 인증된 프로파일" </td> 
   <td colname="col3" morerows="1"> <p>아니요. 트레이트 데이터는 장치 프로필에 기록됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> 아니요. 인증된 옵션인 Merge Rule = "Current Authenticated Profiles" 또는 "No Authenticated Profile" </td> 
  </tr> 
 </tbody> 
</table>

샘플 호출 (인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 세 가지 경우에 [CID와 UUID](../reference/ids-in-aam.md) 간 ID 동기화를 수행합니다.

>[!MORE_ like_ this]
>
>* [고객 ID 및 인증 상태](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

