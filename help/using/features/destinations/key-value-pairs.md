---
description: '키-값 쌍은 관련 요소로 구성됩니다. 이 키는 데이터 세트를 정의하는 상수 (예: 성별, 색상, 가격) 와 세트에 속하는 변수 (예: 남성/여성, 녹색, 100) 로 구성됩니다. 대상 빌더는 키-값 쌍으로 형식이 지정된 데이터를 전송합니다.'
seo-description: '키-값 쌍은 관련 요소로 구성됩니다. 이 키는 데이터 세트를 정의하는 상수 (예: 성별, 색상, 가격) 와 세트에 속하는 변수 (예: 남성/여성, 녹색, 100) 로 구성됩니다. 대상 빌더는 키-값 쌍으로 형식이 지정된 데이터를 전송합니다.'
seo-title: 표준 및 직렬 키-값 쌍
solution: Audience Manager
title: 표준 및 직렬 키-값 쌍
uuid: 43789419-5 B 3 F -4 E 62-B 2 E 0-2722340 BDD 41
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Standard and Serial Key-Value Pairs {#standard-and-serial-key-value-pairs}

키-값 쌍은 관련 요소로 구성됩니다. 데이터 세트를 정의하는 상수 (예: 성별, 색상, 가격) 와 세트에 속하는 변수 (예: 남성/여성, 녹색, 100) 입니다. [!UICONTROL Destination Builder] 키-값 쌍으로 서식이 지정된 데이터를 전송합니다.

## Basic Key-Value Pairs {#basic-key-value-pairs}

전체 키-값 쌍의 기본 세트는 다음과 비슷합니다.

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serial Key-Value Pairs {#standard-serial-key-value-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format.

* **표준 키-값 쌍:** 대상 데이터의 형식을 별도의 키-값 쌍으로 지정합니다. 각 키는 다른 값을 정의하기 위해 다시 사용되더라도 명시적으로 명시되어 있습니다.
* **직렬화된 키-값 쌍:** 여러 값을 하나의 키-값 쌍으로 정리합니다. 직렬화된 키-값 쌍의 특수 표시기는 키-값 세트 내의 값을 구분합니다.

표준 키와 직렬화된 키-값에는 모두 단일 값 또는 여러 개의 값이 포함될 수 있습니다. 다음 표는 표준 및 직렬 키-값 포맷의 예를 제공합니다.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 서식 지정 </th>
   <th colname="col2" class="entry"> 단일 키-값 쌍 </th>
   <th colname="col3" class="entry"> 여러 개의 키-값 쌍 </th>
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
   <td colname="col2"> <p> <code> x = 1; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1; 2 &amp; y = 3; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Delimiters and Separators {#delimiters-separators}

The characters that separate values within and between keys and values are known as *`delimiters`* and *`separators`*. 세그먼트를 대상으로 전송하는 경우 이러한 문제가 특히 중요해집니다. 직렬화를 사용하면 하나의 키를 사용하여 여러 값을 전달하고 키-값 쌍을 결합할 수 있습니다. 구분 기호 및 구분 기호는 다음과 같이 정의됩니다.

* **키-값 구분 기호:** 키-값 쌍 내에서 키와 값을 구분합니다.
* **키-값 구분 기호:** 키-값 쌍 집합을 구분합니다.
* **직렬 구분 문자:** 직렬화된 키-값 쌍 세트 내에서 여러 값을 구분합니다.

## 예 {#examples}

With [!UICONTROL Destination Builder] you can format key-value data in several different ways. 각 유형의 예를 살펴보겠습니다.

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
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td> 
   <td colname="col3"> <p>간단한 키-값 쌍 세트입니다. 이 예제에는 다음과 같은 요소가 포함됩니다. </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">키: x </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">값: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">구분 기호: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">키-값 구분 기호: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>여러 개의 키-값 쌍</b> (비일련화) </p> </td> 
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td> 
   <td colname="col3"> <p>별도의 키-값 세트로 값을 전달하는 여러 개의 키-값 쌍 집합. 이 예제에는 다음과 같은 요소가 포함됩니다. </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">키: x, y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">값: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">구분 기호: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">키-값 구분 기호: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Serial 단일 키</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1; 2; 3 </code> </p> </td> 
   <td colname="col3"> <p>단일 키를 사용하여 여러 값을 전달하는 키-값 세트입니다. 이 키에는 여러 값이 있으므로 직렬화된 키-값 쌍으로 알려져 있습니다. 이 예제에는 다음과 같은 요소가 포함됩니다. </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">키: x </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">값: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">구분 기호: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">직렬 구분 문자: 세미콜론 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>여러 개의 키-값 쌍</b> (일련 번호) </p> </td> 
   <td colname="col2"> <p> <code> x = 1; 2 &amp; y = 3; 4 </code> </p> </td> 
   <td colname="col3"> <p>별도의 키에 여러 값을 전달하는 여러 개의 키-값 쌍 집합. 이 예제에는 다음과 같은 요소가 포함됩니다. </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">키: x, y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">값: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">구분 기호: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">구분 기호: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">직렬 구분 문자: 세미콜론 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Destination Serialization {#destination-serialized}

직렬화된 대상은 여러 트레이트를 하나의 문자열로 결합하고 해당 정보를 대상에 보냅니다.

<!-- c_dest_serialized.xml -->

직렬화된 데이터 전송은 여러 트레이트가 동시에 아니라 순차적으로 실행되므로 효율성을 향상시켜 줍니다. 이렇게 하면 추가 요청에 응답하기 전에 데이터를 받기, 처리 및 반환할 충분한 시간이 대상 서버에 제공됩니다.

### 지원되는 대상

In [!DNL Audience Manager], you can serialize and send data to just about any destination you want to work with. However, before using this feature, you will need to know the destination [!DNL URL] and where to place some required or optional macros. 대상 파트너의 매크로 배치에 대한 정보를 얻습니다. See [Destination Macros Defined](../../features/destinations/destination-macros.md#destination-macros-defined) for more information.