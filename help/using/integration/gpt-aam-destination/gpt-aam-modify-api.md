---
description: Google Publisher Tag. settargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인하려면 if 문을 추가합니다.
seo-description: Google Publisher Tag. settargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인하려면 if 문을 추가합니다.
seo-title: GPT 설정 수정 API 호출 수정
solution: Audience Manager
title: GPT 설정 수정 API 호출 수정
uuid: 0 cd 38 f 30-5 d 29-4511-a 779-d 32587 f 1 dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

Add an if statement to check for Audience Manager cookies before calling the [!DNL Google Publisher Tag] `.setTargeting` method.

## Check for Audience Manager Cookies With an `IF` Statement

`.setTargeting` 이 메서드는 Audience Manager 대상 쿠키와 고유한 사용자 ID 쿠키 ( `aam_uuid`) 의 데이터를 가져옵니다. However, if `.setTargeting` gets invoked before [!UICONTROL DIL] writes these cookies, or the cookies are empty, you may see errors when the page loads. To help avoid this, wrap the `.setTargeting` method in an `if` statement that checks for these cookies. If they're not set, this statement prevents `.setTargeting` from calling the `AamGpt` function.

### `IF` 문 코드 샘플

In this example, the Audience Manager destination cookie name is `Sample`. 대상 관리자 UI에서 대상 쿠키를 만들 때 이 이름을 설정합니다. [!UICONTROL DIL]`aam_uuid` 쿠키를 설정하고 이름을 변경할 수 없습니다.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Depending on how you want to integrate with [!DNL DFP], you only need some of the lines in the code sample above:
>
>* 클라이언트측 통합: 1-3 행을 사용합니다.
>* 서버측 통합: 어떤 줄도 필요하지 않습니다.
>* Ingest [!DNL DFP] log files for reporting in [!DNL Audience Manager]: use lines 4-6 only. This code inserts the value of the `aam_uuid` cookie into the logs so they can be ingested for reporting.


### `AamGpt` 함수 및 데이터 유형

Defines the key variables used in the `if` statement.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 함수로 플러그인 호출 </th> 
   <th colname="col2" class="entry"> 유형 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getkey </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>키-값 세그먼트 쌍의 키를 반환합니다. For example, if your key-value pair consisted of <code> color=blue </code>, this returns <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> aamgpt. getvalues </code> </p> </td> 
   <td colname="col2"> <p>문자열 배열 </p> </td> 
   <td colname="col3"> <p>Returns values in an array, e.g., <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getcookie </code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Returns the Audience Manager user ID, e.g., <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_ like_ this]
>
>* [GPT 대상 만들기](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher 태그를 위한 Audience Manager 코드](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

