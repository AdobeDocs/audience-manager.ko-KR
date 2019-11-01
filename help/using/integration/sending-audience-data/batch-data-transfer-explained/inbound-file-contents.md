---
description: 인바운드 특성 데이터 파일의 서식을 지정할 때 따라야 하는 필수 필드, 구문 및 규칙입니다.
seo-description: 인바운드 특성 데이터 파일의 서식을 지정할 때 따라야 하는 필수 필드, 구문 및 규칙입니다.
seo-title: 인바운드 데이터 파일 내용 구문, 잘못된 문자, 변수 및 예제
solution: Audience Manager
title: 인바운드 데이터 파일 내용 구문, 잘못된 문자, 변수 및 예제
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 인바운드 데이터 파일 내용:구문, 잘못된 문자, 변수 및 예제{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

인바운드 특성 데이터 파일의 서식을 지정할 때 따라야 하는 필수 필드, 구문 및 규칙입니다.

## 파일 컨텐츠 구문 {#file-content-syntax}

인바운드 데이터 파일의 필드는 아래에 표시된 순서대로 표시되어야 합니다. 이 예에서는 각 요소를 시각적으로 구분하는 데 도움이 되도록 `<` `>` 기호가 추가되었습니다. 데이터 파일에 포함할 필요는 없습니다.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

허용되는 다른 파일 컨텐츠 포맷에 대해서는 사용자 지정 파트너 [통합을 참조하십시오](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>인바운드 데이터 파일에서 전송된 각 사용자 ID에 대해 처리할 수 있는 줄이 200개로 제한됩니다. 예를 들어 사용자 ID에 대해 300개의 행을 전송하는 경우 처음 200개의 줄이 유지되고 추가 100개의 줄이 무시됩니다. 아래 예에서는 사용자 ID 1 및 사용자 ID 2에 대해 각각 3개의 라인을 전송하므로 좋습니다. Adobe는 한 줄에 포함되는 트레이트 또는 키-값 쌍의 수에 제한을 두지 않습니다.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## 정의된 파일 변수 {#file-variables-defined}

이 표에서는 올바른 형식의 인바운드 데이터 파일에 사용되는 변수를 나열하고 정의합니다. *기울임꼴*&#x200B;은 변수 자리 표시자를 나타냅니다.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>사용자 ID는 다음과 같습니다. </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Audience Manager에서 할당한 고유 사용자 <span class="keyword"> ID </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">CRM 시스템에 할당된 고유 사용자 ID(Audience Manager의 <a href="../../../reference/ids-in-aam.md"> DPUUID </a>)입니다. </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">모바일 운영 체제에서 노출한 대로 수정되지 않은 원본 형식의 모바일 Android 또는 iOS 장치 ID입니다. </li> 
     </ul> </p> <p>모바일 ID의 경우: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA 형식:ID는 대문자여야 하며 해시되지 않아야 합니다. 예, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android 형식:ID는 소문자여야 하며 해시되지 않아야 합니다. 예, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>사용자 ID와 트레이트 ID를 단일 탭 구분 기호로 구분합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager </span> 트레이트 ID. 인바운드 데이터 파일에 <i>온보딩된 특성만</i> 포함시켜 주시기 바랍니다. 인바운드 데이터 전송에서 다른 특성 유형은 처리하지 않습니다. </p> <p> <p>참고: 트레이트 ID는 모든 트레이트에 대한 세부 사항을 반환하는 GET 메서드를 사용하여 찾을 수 있습니다. 자세한 내용은 트레이트 API <a href="../../../api/rest-api-main/api-traits.md"> 메서드를 참조하십시오 </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 특성 ID 서식 지정 {#formatting-trait-ids}

다음 표에서는 인바운드 데이터 파일에서 특성 이름 또는 ID를 식별하는 접두사를 설명합니다. 예는 [샘플 파일을](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) 참조하십시오.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 접두사 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>이 <code> d_sid </code> 접두사는 ID가 Audience Manager <span class="keyword"> 트레이트 ID임을 시스템에 알려줍니다 </span> . 사용자 인터페이스에 표시되는 ID와 동일합니다. API <code> GET </code> 메서드로 트레이트 ID를 반환할 수도 있습니다. 트레이트 <a href="../../../api/rest-api-main/api-traits.md"> API 메서드를 참조하십시오 </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>데이터가 접두사로 추가되면 해당 트레이트에서 사용자가 <code> d_unsid </code> 제거됩니다. 접두사는 <code> d_unsid </code> <code> overwrite </code> 파일에서 무시됩니다. </p> <p>이 <code> d_unsid= </code> 접두사는 ID가 Audience Manager <span class="keyword"> 트레이트 ID임을 시스템에 알려줍니다 </span> . 사용자 인터페이스에 표시되는 ID와 동일합니다. API <code> GET </code> 메서드로 트레이트 ID를 반환할 수도 있습니다. 트레이트 <a href="../../../api/rest-api-main/api-traits.md"> API 메서드를 참조하십시오 </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 트레이트 규칙을 </a> 사용하여 트레이트 자격에 대한 기준을 설정할 수 있습니다. 트레이트 규칙의 형식을 <code> ic == trait ID </code>쉼표로 구분된 간단한 목록으로 전송할 수 있습니다. </p> <p>예를 들어 다음과 같은 세 가지 특성 규칙을 만든다고 가정해 봅시다. </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>이러한 트레이트는 <code> ic </code> 키와 연결됩니다. 이렇게 하면 데이터 파일에서 보다 간단한 트레이트 목록을 만들 수 있습니다. 또한 <code> ic </code> 접두사를 포함할 필요가 없습니다. 따라서 데이터 파일의 내용은 다음과 같이 표시될 수 있습니다. </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>키-값 쌍 </p> </td> 
   <td colname="col2"> <p>특성 데이터는 영숫자 문자열을 사용하여 키-값 쌍으로 형식을 지정할 수 있습니다. 다음과 같이 키-값 쌍의 서식을 지정할 수 있는 방법에는 여러 가지가 있습니다. </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> <code> product = tablet </code> 은 올바른 형식의 키-값 쌍의 모든 예입니다. </p> </td> 
  </tr>
 </tbody>
</table>

## 트레이트 ID, 사용자 ID 및 키-값 쌍의 잘못된 문자 {#invalid-chars}

### 특성 ID

트레이트 ID는 숫자 문자로만 구성됩니다. 인바운드 데이터 파일에 *온보딩된 특성만* 포함시켜 주시기 바랍니다. 인바운드 데이터 전송에서 다른 특성 유형은 처리하지 않습니다.

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
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>인코딩된 콜론() 또는 인코딩되지 않은 콜론( :)을 사용하지 마십시오</i> <code> %3A </code>.) 기호를 DPUUID에 추가했습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 iOS(IDFA) 또는 Android 장치 ID </p> </td> 
   <td colname="col2"> <p>모바일 장치 ID는 아래와 같이 엄격하게 형식이어야 합니다. </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA 형식:ID는 대문자여야 하며 해시되지 않아야 합니다. 예, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android 형식:ID는 소문자여야 하며 해시되지 않아야 합니다. 예, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 키-값 쌍

키-값 쌍에서 값 이름의 형식이 잘못되어 문제가 발생합니다. 키-값 쌍에서 값을 만들거나 이름을 지정할 때는 다음 규칙을 따르십시오.

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 문자 </th> 
   <th colname="col2" class="entry"> 요구 사항 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>따옴표 문자(") </p> </td> 
   <td colname="col2"> <p>다음과 같이 키와 키-값 쌍의 값 부분에서 인용 문자를 사용할 수 있습니다. </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>대시 문자(-) </p> </td> 
   <td colname="col2"> <p>우리는 열쇠가 시작될 때 대시 기호를 무시합니다. 예를 들어, 는 <code> -product = camera </code> 으로 해석됩니다 <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>키-값 쌍에서 빈 값</i> <code> TAB </code> 대신 사용하지 마십시오. 인바운드 데이터 <code> TAB </code> 파일에서 변수를 구분하는 용도로만 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>키 또는 값에 새 줄 또는 탭 문자( <code> \n, \t </code>)를 사용하지 마십시오. </p> </td> 
  </tr>
 </tbody>
</table>

## 데이터 파일 예 {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 파일 형식 </th> 
   <th colname="col2" class="entry"> 설명 및 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>사용 <code> d_sid </code> 또는 <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>이 데이터 파일은 트레이트 24, 26, 27의 자격을 갖춘 사용자를 보여주며 트레이트 28 및 29에서 제거되었습니다. </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>참고:  <p>d_unsid를 사용하는 대신 다음 구문을 사용하여 사용자 프로필에서 트레이트를 제거할 수도 있습니다. </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>포함 <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>이러한 트레이트가 <code> ic </code> 접두사가 있는 트레이트 규칙에 추가되었습니다. 이와 같이 데이터 파일에 쉼표로 구분하여 추가할 수 있습니다. 탭에서는 UUID와 트레이트 ID를 구분합니다. 파일에 <code> ic </code> 접두사가 필요하지 않습니다. </p> <p><b>숫자 ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>문자열 ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>키-값 쌍 사용 </p> </td> 
   <td colname="col2"> 이 파일 데이터는 키-값 쌍을 사용하여 데이터를 Audience Manager에 <span class="keyword"> 전달합니다 </span>. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[추가 예가 필요한 경우 샘플 데이터 파일을 다운로드합니다](assets/ftp_dpm_1234_1445374061.overwrite) . 다운로드 파일의 `.overwrite` 파일 확장명은 다음과 같습니다. 간단한 텍스트 편집기를 사용하여 열 수 있습니다.

## 예제 매트릭스 {#examples-matrix}

아래 차트는 ID [유형 및 프로필에 트레이트를 추가할 방법에 따라 인바운드 파일의 형식을](../../../reference/ids-in-aam.md) 올바르게 지정하는 방법의 예를 보여줍니다.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 유형/작업 </th> 
   <th colname="col2" class="entry"> d_sid를 사용하여 사용자 프로필에 트레이트 추가 </th> 
   <th colname="col3" class="entry"> 사용자 프로필에서 트레이트를 제거하려면 d_unsid를 사용합니다. </th> 
   <th colname="col4" class="entry"> 키-값 쌍으로 전송하여 사용자 프로필에 트레이트 추가 </th> 
   <th colname="col5" class="entry"> Ic 접두사를 사용하여 사용자 프로필에 트레이트 추가 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> 예제 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> 예제 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> 예제 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> 예 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Android 장치용 Google 광고 ID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> 예제 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> 예 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> 예 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> 예 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>iOS 디바이스용 Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> 예제 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 예 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 예 10 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 예 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>고유한 CRM ID(DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 예 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 예 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 예 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 예 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

특성 ID를 사용하여 Audience Manager UUID에 대한 트레이트 자격 정보를 전송합니다.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

특성 ID를 사용하여 Audience Manager UUID에 대한 트레이트 결격 정보를 전송합니다.

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

키-값 쌍을 전송하여 Audience Manager UUID에 대한 트레이트 자격 정보를 추가합니다.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

또는 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

Audience Manager UUID에 대한 트레이트 자격 정보를 전송하려면 ic 접두사를 사용합니다.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

특성 ID를 사용하여 Android 장치에 대한 트레이트 자격 정보를 전송합니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

특성 ID를 사용하여 Android 장치에 대한 트레이트 결격 정보를 전송합니다.

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

키-값 쌍을 전송하여 Android 장치에 대한 트레이트 자격 정보를 추가합니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

Android 장치에 대한 트레이트 자격 정보를 전송하려면 ic 접두사를 사용하십시오.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

특성 ID를 사용하여 iOS 장치에 대한 트레이트 자격 정보를 전송합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

특성 ID를 사용하여 iOS 장치에 대한 트레이트 결격 정보를 전송합니다.

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

키-값 쌍을 전송하여 iOS 장치에 대한 트레이트 자격 정보를 추가합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

iOS 장치에 대한 트레이트 자격 정보를 전송하려면 ic 접두사를 사용하십시오.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

특성 ID를 사용하여 DPUUID에 대한 트레이트 자격 정보를 전송합니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

특성 ID를 사용하여 DPUUID에 대한 트레이트 결격 정보를 전송합니다.

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

키-값 쌍을 전송하여 DPUUID에 대한 트레이트 자격 정보를 추가합니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

또는 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

DPUUID에 대한 트레이트 자격 정보를 전송하려면 ic 접두사를 사용합니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [특성 빌더](../../../features/traits/about-trait-builder.md)

