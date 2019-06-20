---
description: 전화 통화를 할 때 DCS는 표준 또는 직렬 형식으로 키-값 데이터를 수락합니다. 표준 및 일련 번호 데이터의 형식 지정 데이터에 대한 자세한 내용은 이 섹션을 검토하십시오.
seo-description: 전화 통화를 할 때 DCS는 표준 또는 직렬 형식으로 키-값 데이터를 수락합니다. 표준 및 일련 번호 데이터의 형식 지정 데이터에 대한 자세한 내용은 이 섹션을 검토하십시오.
seo-title: DCS 호출에서 키-값 쌍 서식 지정
solution: Audience Manager
title: DCS 호출에서 키-값 쌍 서식 지정
uuid: AF 02 F 2 A 1-4388-4074-AB 4 E -66 EE 82023 F 1 C
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!UICONTROL DCS] accepts key-value data in standard or serialized format. 표준 및 일련 번호 데이터의 형식 지정 데이터에 대한 자세한 내용은 이 섹션을 검토하십시오.

## Standard and Serialized Key-Value Pairs {#standard-serialized}

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
   <td colname="col2"> <p>표준 키-값 쌍은 하나의 키와 값으로 구성됩니다. 이 구조는 데이터를 별도의 키-값 쌍으로 구성합니다. 각 키는 다른 값을 정의하기 위해 다시 사용되더라도 명시적으로 명시되어 있습니다. DCS로 데이터를 전송하는 가장 일반적인 방법입니다. </p> </td>
   <td colname="col3"> <code> key 1 = val 1 &amp; key 2 = val 2 &amp; key 3 = val 3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>직렬화</b> </td> 
   <td colname="col2"> <p>직렬화된 키-값 쌍은 단일 키와 여러 값으로 구성됩니다. 이렇게 하면 데이터를 효율적으로 정리할 수 있지만 직렬화된 키-값 쌍은 각 키와 키-값 세트를 구분하기 위해 특정 심볼을 필요로 합니다. </p> </td> 
   <td colname="col3"> <code> key 1 = val 1, val 2, val 3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

직렬화된 키-값 쌍을 사용하는 경우, 이러한 변수 내 및 변수 간에 값을 구분하는 마커를 지정해야 합니다. Audience Manager 에는 다음 구분 기호 및 구분 기호가 필요합니다.

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 요구 사항 </th> 
   <th colname="col2" class="entry"> 기호 </th> 
   <th colname="col3" class="entry"> 개별 분리 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>구분 기호</b> </td> 
   <td colname="col2"> 앰퍼샌드 및 </td> 
   <td colname="col3"> <p>키-값 쌍: </p> <p><code> key 1 = val 1 &amp; key 2 = val 2, val 3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>구분 문자</b> </td> 
   <td colname="col2"> 쉼표 , </td> 
   <td colname="col3"> <p>키-값 쌍 내의 값: </p> <p><code> key 1 = val 1, val 2, val 3 &amp; key 2 = vala, valb, valc</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [DCS로 데이터 전송](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [DCS에서 지원하는 주요 값 접두어 및 변수](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [키-값 쌍을 설명했습니다.](../../../reference/key-value-pairs-explained.md)

