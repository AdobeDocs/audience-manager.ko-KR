---
description: 인바운드 특성 데이터 파일 서식을 지정할 때 따라야 할 필수 필드, 구문 및 규칙입니다.
seo-description: 인바운드 특성 데이터 파일 서식을 지정할 때 따라야 할 필수 필드, 구문 및 규칙입니다.
seo-title: 인바운드 데이터 파일 내용 구문, 잘못된 문자, 변수 및 예제
solution: Audience Manager
title: 인바운드 데이터 파일 내용 구문, 잘못된 문자, 변수 및 예제
uuid: 88699 B 29-1502-4183-A 9 A 4-BE 70692 A 02 BB
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

인바운드 특성 데이터 파일 서식을 지정할 때 따라야 할 필수 필드, 구문 및 규칙입니다.

## File Content Syntax {#file-content-syntax}

인바운드 데이터 파일의 필드는 아래 표시된 순서대로 표시되어야 합니다. In this example, the `<` `>` symbols have been added to help separate each element visually. 데이터 파일에 이러한 사항을 포함할 필요는 없습니다.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

For other accepted file content formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>인바운드 데이터 파일에서 전송된 각 사용자 ID에 대해 처리할 수 있는 200 개 라인의 제한이 있습니다. 예를 들어 사용자 ID에 대해 300 라인을 전송하는 경우 처음 200 개 줄이 유지되고 100 개 라인이 추가로 무시됩니다. 아래 예에서는 사용자 ID 1 및 사용자 ID 2에 대해 각각 3 개의 라인을 보내는 것이 좋습니다. Adobe는 한 줄에 포함되는 트레이트 또는 키-값 쌍의 수에 제한을 두지 않습니다.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## File Variables Defined {#file-variables-defined}

이 표에서는 형식이 적절하게 지정된 인바운드 데이터 파일에 사용된 변수를 나열하고 정의합니다. *기울임꼴*&#x200B;은 변수 자리 표시자를 나타냅니다.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>사용자 ID </i> </code> </p> </td> 
   <td colname="col2"> <p>사용자 ID는 다음과 같습니다. </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B"><span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>) 에서 할당한 고유한 사용자 ID 입니다. </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">A unique user ID assigned in your CRM system ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">모바일 운영 체제에 의해 노출된 수정되지 않은 원본의 모바일 Android 또는 iOS 장치 ID 입니다. </li> 
     </ul> </p> <p>모바일 ID의 경우: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA 형식: ID는 대소문자가 아닌 대문자여야 합니다. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android 형식: ID는 소문자여야 하며 해시되지 않아야 합니다. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> tab </code> </p> </td> 
   <td colname="col2"> <p>사용자 ID와 특성 ID를 단일 탭 구분 기호로 구분합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>특성 ID </i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager </span> 특성 ID. We ask that you include <i>only onboarded traits</i> in inbound data files. 본사는 인바운드 데이터 전송에서 다른 트레이트 유형을 처리하지 않습니다. </p> <p> <p>참고: 특성 ID는 모든 특성에 대한 세부 사항을 반환하는 GET 메서드를 사용하여 찾을 수 있습니다. For more information, see <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatting Trait IDs {#formatting-trait-ids}

다음 표에서는 인바운드 데이터 파일에서 트레이트 이름 또는 ID를 식별하는 접두사를 설명합니다. See the [sample files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) for examples.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 접두사 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid = </code> </p> </td> 
   <td colname="col2"> <p><code> d_ sid </code> 접두사는 시스템에 ID가 <span class="keyword"> Audience Manager </span> 특성 ID 임을 알려줍니다. 이것은 사용자 인터페이스에 표시된 ID와 동일합니다. You can also return trait IDs with the API <code> GET </code> method. <a href="../../../api/rest-api-main/api-traits.md"> 특성 API 메서드를 </a>참조하십시오. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid = </code> </p> </td> 
   <td colname="col2"> <p>Data prefixed with <code> d_unsid </code> removes users from that trait. <code> d_ unsid </code> 접두사는 <code> 덮어쓰기 </code> 파일에서 무시됩니다. </p> <p><code> d_ unsid = </code> 접두사는 Adobe 시스템에 ID가 <span class="keyword"> Audience Manager </span> 특성 ID 임을 알려줍니다. 이것은 사용자 인터페이스에 표시된 ID와 동일합니다. You can also return trait IDs with the API <code> GET </code> method. <a href="../../../api/rest-api-main/api-traits.md"> 특성 API 메서드를 </a>참조하십시오. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> IC = </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 트레이트 규칙을 </a> 사용하여 트레이트 자격 조건에 대한 기준을 지정할 수 있습니다. If you format a trait rule as <code> ic == trait ID </code>, you can send in traits in a simple comma formatted list. </p> <p>예를 들어 다음과 같은 세 가지 특성 규칙을 만든다고 가정해 보겠습니다. </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic = = "123" </code> </li>
      <li> <code> ic = = "456" </code> </li>
      <li> <code> ic = = "789" </code> </li>
     </ul> </p> <p>These traits are associated with the <code> ic </code> key. 이렇게 하면 데이터 파일에서 간단한 트레이트 목록을 만들 수 있습니다. And, you do not need to include the <code> ic </code> prefix. 따라서 데이터 파일의 내용은 다음과 비슷합니다. </p> <p>
     <code><i>사용자 ID</i> &lt; tab &gt; 123,456,789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>키-값 쌍 </p> </td> 
   <td colname="col2"> <p>트레이트 데이터의 형식은 영숫자 문자열을 사용하여 키-값 쌍으로 지정할 수 있습니다. 다음과 같이 키-값 쌍의 서식을 지정하는 방법에는 몇 가지가 있습니다. </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> " key " = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> " key " =" value " </code> </li> 
     </ul><code> " age " =" 32 " </code> , <code> " gender " = m </code> , <code> model =" pickup truck " </code> , <code> product = 태블릿은 </code> 올바른 형식의 키-값 쌍의 모든 예입니다. </p> </td> 
  </tr>
 </tbody>
</table>

## Invalid Characters in Trait IDs, User IDs and Key-Value Pairs {#invalid-chars}

### 특성 ID

특성 ID는 숫자 문자로만 구성됩니다. We ask that you include *only onboarded traits* in inbound data files. 본사는 인바운드 데이터 전송에서 다른 트레이트 유형을 처리하지 않습니다.

### 사용자 ID

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 유형 </th> 
   <th colname="col2" class="entry"> 요구 사항 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dpuuid </p> </td> 
   <td colname="col2"> <p><i>인코딩된</i> 콜론 ( <code> % 3 A </code>) 또는 인코딩되지 않은 콜론 ( ) 기호를 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 iOS (IDFA) 또는 Android 디바이스 ID </p> </td> 
   <td colname="col2"> <p>모바일 장치 ID는 다음과 같이 명시적으로 형식을 지정해야 합니다. </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA 형식: ID는 대소문자가 아닌 대문자여야 합니다. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android 형식: ID는 소문자여야 하며 해시되지 않아야 합니다. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 키-값 쌍

키-값 쌍의 값 이름에 부적절하게 서식이 지정되더라도 문제가 발생합니다. 키-값 쌍의 값을 만들거나 지정할 때 다음 규칙을 따릅니다.

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 문자 </th> 
   <th colname="col2" class="entry"> 요구 사항 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>인용 부호 문자 (") </p> </td> 
   <td colname="col2"> <p>키와 키-값 쌍의 값 부분에서 따옴표 문자를 사용할 수 있습니다. </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city = "new york", d_ city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> " d_ city " =" new york "," d_ city " =" san francisco " </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>대시 문자 (-) </p> </td> 
   <td colname="col2"> <p>키 시작 시 대시 기호를 무시합니다. For example, <code> -product = camera </code> is interpreted as <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> tab </code> </p> </td> 
   <td colname="col2"> <p><i>키-값</i> 쌍의 빈 값 대신 <code> 탭을 </code> 사용하지 마십시오. Only use <code> TAB </code> to separate variables in the inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n,\ t </code> </p> </td> 
   <td colname="col2"> <p>Do not use the new line or tab characters ( <code> \n, \t </code>) in keys or in values. </p> </td> 
  </tr>
 </tbody>
</table>

## Data File Examples {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 파일 형식 </th> 
   <th colname="col2" class="entry"> 설명 및 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>With <code> d_sid </code> or <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>이 데이터 파일은 사용자가 트레이트 24, 26, 27에 대한 자격을 갖추고 있고 트레이트 28 및 29에서 제거되었습니다. </p> <p> 
     <code>5976755918126206006027887090901087098252 &amp; amp; nbsp; &amp; amp; nbsp; d_ sid = 24, d_ sid = 26, d_ sid = 27, d_ unsid = 28, d_ unsid = 29 </code>
  </p> <p>참고:  <p>d_ unsid를 사용하는 대신 다음 구문을 사용하여 사용자 프로필에서 트레이트를 제거할 수도 있습니다. </p> <p> 
      <code>5976755918126206006027887090901087098252 &amp; amp; nbsp; 28:0, &amp; amp; nbsp; 29:0 </code>
  </p> <p> 
      <code>5976755918126206006027887090901087098252 &amp; amp; nbsp; 28:-1, &amp; amp; nbsp; 29:-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>These traits have been added to a trait rule with the <code> ic </code> prefix. 따라서 표시된 대로 쉼표로 구분된 데이터 파일에 추가할 수 있습니다. 탭은 UUID와 특성 ID를 구분합니다. <code> 파일에 IC </code> 접두사가 필요하지 않습니다. </p> <p><b>숫자 ID</b> </p> <p> 
     <code>dbwfoc 3 dhfmncfbh 2 m 4 f 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; 30608,50354,50338,50352,30626 </code>
  </p> <p><b>문자열 ID</b> </p> <p> 
     <code>dbwfoc 3 dhfmncfbh 2 m 4 f 9 zkjexmnnrdh 2 pxvni 1 &amp; amp; nbsp; &amp; amp; nbsp; ic = 52, ic = 55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>키-값 쌍 사용 </p> </td> 
   <td colname="col2"> This file data uses key-value pairs to pass in data to <span class="keyword"> Audience Manager </span>. <p> 
     <code>5976755918126206006027887090901087098252 &amp; amp; nbsp; «gender» =» female», «luxury_ shopper» =» 예» </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[추가 예가](assets/ftp_dpm_1234_1445374061.overwrite) 필요한 경우 샘플 데이터 파일을 다운로드합니다. The download file has a `.overwrite` file extension. 간단한 텍스트 편집기로 열 수 있습니다.

## Examples Matrix {#examples-matrix}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md) and the method by which you want to add traits to profiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 유형/작업 </th> 
   <th colname="col2" class="entry"> d_ sid를 사용하여 사용자 프로필에 트레이트를 추가합니다. </th> 
   <th colname="col3" class="entry"> d_ unsid를 사용하여 사용자 프로필에서 트레이트 제거 </th> 
   <th colname="col4" class="entry"> 키-값 쌍을 사용하여 사용자 프로필에 트레이트를 추가합니다. </th> 
   <th colname="col5" class="entry"> IC 접두사를 사용하여 사용자 프로필에 트레이트를 추가합니다. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> 예제 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> 예제 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> 예제 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> 예제 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Android 장치용 Google 광고 ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 예제 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 예제 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 예제 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 예제 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>iOS 장치용 Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> 예제 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 예제 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 예제 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 예제 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>고유한 CRM ID (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 예제 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 예제 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 예제 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 예제 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

특성 ID를 사용하여 Audience Manager UUIDS에 대한 특성 자격 조건 정보를 전송합니다.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

특성 ID를 사용하여 Audience Manager UUIDS에 대한 특성 자격 증명 정보를 전송합니다.

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

또는 

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

또는 

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 3 {#example-3}

Audience Manager UUIDS에 대한 특성 자격 정보를 추가하려면 키-값 쌍을 참조하십시오.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

또는 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

ICS 접두사를 사용하여 Audience Manager UUIDS에 대한 특성 자격 조건 정보를 전송합니다.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

특성 ID를 사용하여 Android 장치에 대한 특성 자격 조건 정보를 전송합니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

특성 ID를 사용하여 Android 장치에 대한 특성 자격 증명 정보를 보냅니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 7 {#example-7}

키-값 쌍을 사용하여 Android 장치에 대한 특성 자격 정보를 추가합니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

IC 접두사를 사용하여 Android 장치에 대한 특성 자격 조건 정보를 전송합니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

특성 ID를 사용하여 iOS 장치에 대한 특성 자격 조건 정보를 전송합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

특성 ID를 사용하여 iOS 장치에 대한 특성 자격 증명 정보를 전송합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Example 11 {#example-11}

키-값 쌍을 사용하여 iOS 장치에 대한 특성 자격 정보를 추가합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

IC 접두사를 사용하여 iOS 장치에 대한 특성 자격 조건 정보를 전송합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

특성 ID를 사용하여 DPUUIDS에 대한 특성 자격 조건 정보를 전송합니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

특성 ID를 사용하여 DPUUIDS에 대한 특성 자격 증명 정보를 보냅니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

또는 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

또는 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 15 {#example-15}

키-값 쌍을 사용하여 DPUUIDS에 대한 특성 자격 조건 정보를 추가합니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

또는 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

IC 접두사를 사용하여 DPUUIDS에 대한 특성 자격 조건 정보를 전송합니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_ like_ this]
>
>* [특성 빌더](../../../features/traits/about-trait-builder.md)

