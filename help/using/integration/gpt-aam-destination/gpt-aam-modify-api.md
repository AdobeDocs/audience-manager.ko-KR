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
source-wordcount: '274'
ht-degree: 7%

---

# GPT 수정 `setTargeting` API 호출 {#modify-the-gpt-settargeting-api-call}

를 호출하기 전에 Audience Manager 쿠키를 확인하는 if 문 추가 [!DNL Google Publisher Tag] `.setTargeting` 메서드를 사용합니다.

## 다음을 사용하여 Audience Manager 쿠키 확인 `IF` 명령문

다음 `.setTargeting` 메서드는 Audience Manager 대상 쿠키 및 고유한 사용자 ID 쿠키( )에서 데이터를 가져옵니다. `aam_uuid`). 그러나 다음과 같은 경우에는 `.setTargeting` 다음 시간 이전에 호출됩니다. [!UICONTROL DIL] 이 쿠키를 작성하거나 쿠키가 비어 있는 경우 페이지가 로드될 때 오류가 표시될 수 있습니다. 이를 방지하려면 다음을 래핑하십시오. `.setTargeting` 의 메서드 `if` 이러한 쿠키를 확인하는 문입니다. 설정되지 않은 경우 이 문은 `.setTargeting` (으)로 호출하여 `AamGpt` 함수.

### `IF` 명령문 코드 샘플

이 예에서 Audience Manager 대상 쿠키 이름은 입니다. `Sample`. Audience Manager 사용자 인터페이스에서 대상 쿠키를 만들 때 이 이름을 설정합니다. [!UICONTROL DIL] 를 설정합니다. `aam_uuid` 쿠키 및 이름은 변경할 수 없습니다.

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
>을 통합하는 방법에 따라 [!DNL Google Ad Manager], 위의 코드 샘플에 있는 줄 중 일부만 있으면 됩니다.
>
>* 클라이언트측 통합: 라인 1-3만 사용합니다.
>* 서버 측 통합: 필요한 행이 없습니다.
>* 수집 [!DNL Google Ad Manager] 보고를 위한 로그 파일 [!DNL Audience Manager]: 4-6행만 사용합니다. 이 코드는 `aam_uuid` 보고를 위해 수집할 수 있도록 로그에 쿠키를 추가합니다.


### `AamGpt` 함수 및 데이터 유형

에 사용되는 주요 변수를 정의합니다. `if` 명령문입니다.

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
   <td colname="col3"> <p>키-값 세그먼트 쌍의 키를 반환합니다. 예를 들어, 키-값 쌍이 <code> color=blue </code>, 반환 <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>문자열 배열 </p> </td> 
   <td colname="col3"> <p>배열의 값을 반환합니다(예: ). <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>정수 </p> </td> 
   <td colname="col3"> <p>Audience Manager 사용자 ID 반환(예: ) <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [GPT 대상 만들기](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google Publisher Tag용 Audience Manager 코드](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

