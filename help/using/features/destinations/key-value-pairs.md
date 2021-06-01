---
description: ' [!DNL key-value pair] 은 [!DNL related elements]로 구성됩니다. 키는 데이터 세트(예: 성별, 색상, 가격)와 값을 정의하는 상수, 즉 세트에 속하는 변수입니다(예: 남성/여성, 녹색, 100). 대상 빌더는 키-값 쌍으로 형식이 지정된 데이터를 보냅니다.'
solution: Audience Manager
title: 표준 및 직렬 [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: 대상 기본 사항
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 2%

---

# 표준 및 일련 키-값 쌍 {#standard-and-serial-key-value-pairs}

키-값 쌍은 관련 요소로 구성됩니다.키: 데이터 세트를 정의하는 상수(예:gender, color, price) 및 값(예: male/female, green, 100)입니다. [!UICONTROL Destination Builder] 는 키-값 쌍으로 형식이 지정된 데이터를 전송합니다.

## 기본 키-값 쌍 {#basic-key-value-pairs}

전체 형식의 기본 키-값 쌍 집합은 다음과 같을 수 있습니다.

* `gender = male`
* `color = green`
* `price > 100`

## 표준 및 일련 키-값 쌍 {#standard-serial-key-value-pairs}

대상은 *`standard`* 또는 *`serialized`* 형식의 키-값 데이터를 허용합니다.

* **표준 키-값 쌍:** 대상 데이터를 별도의 키-값 쌍으로 형식을 지정합니다. 각 키는 다른 값을 정의하는 데 다시 사용되는 경우에도 명시적으로 설명되어 있습니다.
* **직렬화된 키-값 쌍:** 여러 값을 단일 키-값 쌍으로 계산합니다. 직렬화된 키-값 쌍에서 특수 표시기는 키-값 세트 내의 값을 구분합니다.

표준 키와 직렬화된 키 값 모두 단일 또는 여러 값을 포함할 수 있습니다. 다음 표는 표준 및 일련 키-값 형식의 예를 제공합니다.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 서식 </th>
   <th colname="col2" class="entry"> 단일 키-값 쌍 </th>
   <th colname="col3" class="entry"> 여러 키-값 쌍 </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>표준</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>직렬화</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## 구분 기호 및 구분 기호 {#delimiters-separators}

키와 값 사이에 값을 구분하는 문자를 *`delimiters`* 및 *`separators`*&#x200B;이라고 합니다. 이러한 기능은 세그먼트를 직렬 형식으로 대상에 보낼 때 특히 중요합니다. 직렬화를 사용하면 단일 키로 여러 값을 전달하고 키-값 쌍을 결합할 수 있습니다. 구분 기호와 구분 기호는 다음과 같이 정의됩니다.

* **키-값 구분 기호:**  키-값 쌍 내에서 키와 값을 구분합니다.
* **키-값 구분 기호:** 키-값 쌍 집합을 구분합니다.
* **일련 구분 기호:** 직렬화된 키-값 쌍 집합 내에서 여러 값을 구분합니다.

## 예 {#examples}

[!UICONTROL Destination Builder]을 사용하면 여러 가지 방법으로 키-값 데이터의 형식을 지정할 수 있습니다. 각 유형에 대한 몇 가지 예를 살펴보겠습니다.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키-값 쌍 예 </th> 
   <th colname="col2" class="entry"> 예 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>표준 단일 키</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>간단한 키-값 쌍 세트입니다. 이 예에는 다음 요소가 포함되어 있습니다. </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">키:X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">값:1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">구분 기호:= </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">키-값 구분 기호:&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>여러 키-값 쌍</b> (비직렬) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>별도의 키-값 세트가 있는 값을 전달하는 여러 키-값 쌍 집합입니다. 이 예에는 다음 요소가 포함되어 있습니다. </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">키:X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">값:1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">구분 기호:= </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">키-값 구분 기호:&amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>직렬 단일 키</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>단일 키로 여러 값을 전달하는 키 값 집합입니다. 이 키는 여러 값을 가지므로 직렬화된 키-값 쌍이라고 합니다. 이 예에는 다음 요소가 포함되어 있습니다. </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">키:X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">값:1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">구분 기호:= </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">직렬 구분 기호:세미콜론 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>여러 키-값 쌍</b> (직렬) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>별도의 키에 여러 값을 전달하는 여러 키-값 쌍 집합입니다. 이 예에는 다음 요소가 포함되어 있습니다. </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">키:X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">값:1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">구분 기호:= </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">구분 기호: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">직렬 구분 기호:세미콜론 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 대상 직렬화 {#destination-serialized}

직렬화된 대상은 여러 트레이트를 단일 문자열로 결합하고 해당 정보를 대상에 보냅니다.

<!-- c_dest_serialized.xml -->

직렬화된 데이터 전송은 여러 특성이 동시에 실행되는 것이 아니라 순차적으로 실행되므로 효율성을 개선하는 데 도움이 됩니다. 이렇게 하면 대상 서버에 추가적인 요청에 응답하기 전에 데이터를 수신, 처리 및 반환하기에 충분한 시간이 제공됩니다.

### 지원되는 대상

[!DNL Audience Manager]에서 데이터를 serialize하고 작업하려는 대상에 대해서만 보낼 수 있습니다. 그러나 이 기능을 사용하기 전에 대상 [!DNL URL] 및 일부 필수 또는 선택적 매크로를 배치할 위치를 알고 있어야 합니다. 대상 파트너에서 매크로 배치에 대한 정보를 얻습니다. 자세한 내용은 [정의된 대상 매크로](../../features/destinations/destination-macros.md#destination-macros-defined)를 참조하십시오.
