---
description: Google 게시자 태그 .setTargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인할 if 문을 추가합니다.
seo-description: Google 게시자 태그 .setTargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인할 if 문을 추가합니다.
seo-title: GPT setTargeting API 호출 수정
solution: Audience Manager
title: GPT setTargeting API 호출 수정
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# GPT API `setTargeting` 호출 수정 {#modify-the-gpt-settargeting-api-call}

메서드를 호출하기 전에 Audience Manager 쿠키를 확인할 if 문을 [!DNL Google Publisher Tag] 추가합니다 `.setTargeting` .

## 문이 있는 Audience Manager 쿠키 `IF` 확인

이 `.setTargeting` 메서드는 Audience Manager 대상 쿠키와 고유한 사용자 ID 쿠키( `aam_uuid`)에서 데이터를 가져옵니다. 그러나 쿠키를 쓰기 전에 `.setTargeting` [!UICONTROL DIL] 호출되거나 쿠키가 비어 있는 경우 페이지가 로드될 때 오류가 표시될 수 있습니다. 이를 방지하려면 이러한 쿠키가 있는지 확인하는 `.setTargeting` `if` 문에서 메서드를 래핑하십시오. 이 문이 설정되지 않은 경우 이 문은 함수를 `.setTargeting` 호출할 수 없게 `AamGpt` 합니다.

### `IF` 문 코드 샘플

이 예에서는 Audience Manager 대상 쿠키 이름이 `Sample`입니다. Audience Manager UI에서 대상 쿠키를 만들 때 이 이름을 설정합니다. [!UICONTROL DIL] 쿠키를 `aam_uuid` 설정하고 이름을 변경할 수 없습니다.

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
>통합하려는 방법에 따라 위의 코드 샘플에 [!DNL DFP]있는 일부 줄만 있으면 됩니다.
>
>* 클라이언트측 통합:1-3줄만 사용하십시오.
>* 서버측 통합:어떤 선도 필요하지 않습니다.
>* 보고할 [!DNL DFP] 로그 파일 인제스트 [!DNL Audience Manager]:4-6줄만 사용하십시오. 이 코드는 보고용으로 인제스트될 수 있도록 `aam_uuid` 쿠키의 값을 로그에 삽입합니다.


### `AamGpt` 함수 및 데이터 유형

문에 사용된 주요 변수를 정의합니다. `if`

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
   <td colname="col3"> <p>키-값 세그먼트 쌍의 키를 반환합니다. 예를 들어 키-값 쌍이 <code> color=blue </code>로 구성된 경우 <code> 색상이 </code>반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>문자열 배열 </p> </td> 
   <td colname="col3"> <p>배열에서 값을 반환합니다(예: <code> ["value1","value2"] </code>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Audience Manager 사용자 ID(예: 12345)를 <code> 반환합니다 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKE_THIS]
>
>* [GPT 대상 만들기](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Google 게시자 태그의 Audience Manager 코드](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

