---
description: 호출을 수행할 때 DCS는 표준 또는 직렬화된 형식으로 키-값 데이터를 수락합니다. 표준 및 직렬화된 키-값 데이터의 포맷을 지정하는 방법에 대한 자세한 내용은 이 섹션을 검토하십시오.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: DCS 호출에서 키-값 쌍 형식 지정
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 11%

---

# DCS 호출에서 키-값 쌍 형식 지정 {#formatting-key-value-pairs-in-dcs-calls}

호출 시 [!DNL DCS] 는 표준 또는 직렬화된 형식의 키-값 데이터를 허용합니다. 표준 및 직렬화된 키-값 데이터의 포맷을 지정하는 방법에 대한 자세한 내용은 이 섹션을 검토하십시오.

## 표준 및 직렬화된 키-값 쌍 {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키-값 유형 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
   <th colname="col3" class="entry"> 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>표준</b> </td> 
   <td colname="col2"> <p>표준 키-값 쌍은 단일 키와 값으로 구성됩니다. 이 구조는 데이터를 별도의 키-값 쌍으로 구성합니다. 각 키는 다른 값을 정의하는 데 다시 사용되는 경우에도 명시적으로 언급됩니다. 이는 DCS에 데이터를 전송하는 가장 일반적인 방법입니다. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>직렬화됨</b> </td> 
   <td colname="col2"> <p>직렬화된 키-값 쌍은 단일 키와 여러 값으로 구성됩니다. 이렇게 하면 데이터를 효율적으로 구성할 수 있지만, serialize된 키-값 쌍은 각 키와 각 키-값 집합을 구분하기 위해 특정 기호가 필요합니다. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## 직렬화된 키-값 쌍에 대한 구분 기호 및 구분 기호 {#delimiters-separators}

직렬화된 키-값 쌍을 사용하면 이러한 변수 내에서 그리고 변수 간에 값을 구분하는 마커를 지정해야 합니다. Audience Manager을 사용하려면 다음 구분 기호와 구분 기호가 필요합니다.

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 요구 사항 </th> 
   <th colname="col2" class="entry"> 기호 </th> 
   <th colname="col3" class="entry"> 개별 항목 구분 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>구분 기호</b> </td> 
   <td colname="col2"> 앰퍼샌드 &amp; </td> 
   <td colname="col3"> <p>키-값 쌍: </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>구분 문자</b> </td> 
   <td colname="col2"> 쉼표 , </td> 
   <td colname="col3"> <p>키-값 쌍 내의 값: </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [DCS에 데이터 보내기](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS에서 지원하는 키-값 접두사 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [키-값 쌍 설명](../../../reference/key-value-pairs-explained.md)

