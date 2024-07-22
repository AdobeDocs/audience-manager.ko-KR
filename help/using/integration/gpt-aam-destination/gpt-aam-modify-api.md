---
description: Google Publisher Tag .setTargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인하는 if 문을 추가합니다.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: GPT setTargeting API 호출 수정
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# GPT `setTargeting` API 호출 수정 {#modify-the-gpt-settargeting-api-call}

[!DNL Google Publisher Tag] `.setTargeting` 메서드를 호출하기 전에 Audience Manager 쿠키를 확인하는 if 문을 추가하십시오.

## `IF` 문을 사용하여 Audience Manager 쿠키 확인

`.setTargeting` 메서드는 Audience Manager 대상 쿠키 및 고유한 사용자 ID 쿠키(`aam_uuid`)에서 데이터를 가져옵니다. 그러나 [!UICONTROL DIL]이(가) 이러한 쿠키를 쓰기 전에 `.setTargeting`이(가) 호출되거나 쿠키가 비어 있는 경우 페이지가 로드될 때 오류가 표시될 수 있습니다. 이 문제를 방지하려면 이 쿠키를 확인하는 `if` 문으로 `.setTargeting` 메서드를 래핑하십시오. 이 문이 설정되지 않으면 `.setTargeting`에서 `AamGpt` 함수를 호출할 수 없습니다.

### `IF` 문 코드 샘플

이 예제에서 Audience Manager 대상 쿠키 이름은 `Sample`입니다. Audience Manager 사용자 인터페이스에서 대상 쿠키를 만들 때 이 이름을 설정합니다. [!UICONTROL DIL]이(가) `aam_uuid` 쿠키를 설정하므로 이름을 변경할 수 없습니다.

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
>[!DNL Google Ad Manager]과(와) 통합하는 방법에 따라 위의 코드 샘플에는 일부 줄만 있으면 됩니다.
>
>* 클라이언트측 통합: 라인 1-3만 사용합니다.
>* 서버 측 통합: 필요한 행이 없습니다.
>* [!DNL Audience Manager]에서 보고할 [!DNL Google Ad Manager] 로그 파일을 수집합니다. 4-6줄만 사용하십시오. 이 코드는 보고를 위해 수집할 수 있도록 `aam_uuid` 쿠키의 값을 로그에 삽입합니다.

### `AamGpt` 함수 및 데이터 형식

`if` 문에 사용되는 주요 변수를 정의합니다.

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
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>키-값 세그먼트 쌍의 키를 반환합니다. 예를 들어, 키-값 쌍이 <code> color=blue </code>(으)로 구성된 경우 <code> color </code>을(를) 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>문자열 배열 </p> </td> 
   <td colname="col3"> <p>배열의 값을 반환합니다(예: <code> ["value1","value2"] </code>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>Audience Manager 사용자 ID(예: <code> 12345 </code>)를 반환합니다. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [GPT 대상 만들기](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher Tag용 Audience Manager 코드](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
