---
description: 인바운드 특성 데이터 파일의 서식을 지정할 때 따라야 하는 필수 필드, 구문 및 규칙입니다.
seo-description: 인바운드 특성 데이터 파일의 서식을 지정할 때 따라야 하는 필수 필드, 구문 및 규칙입니다.
seo-title: 인바운드 데이터 파일 내용 구문, 잘못된 문자, 변수 및 예제
solution: Audience Manager
title: 인바운드 데이터 파일 내용 구문, 잘못된 문자, 변수 및 예제
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1193'
ht-degree: 4%

---


# 인바운드 데이터 파일 내용: 구문, 잘못된 문자, 변수 및 예 {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

인바운드 특성 데이터 파일의 서식을 지정할 때 따라야 하는 필수 필드, 구문 및 규칙입니다.

## 파일 컨텐츠 구문 {#file-content-syntax}

인바운드 데이터 파일의 필드는 아래에 표시된 순서대로 표시되어야 합니다. 이 예에서는 각 요소를 시각적으로 구분하는 데 도움이 되도록 `<` `>` 기호가 추가되었습니다. 데이터 파일에 포함할 필요는 없습니다.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

허용된 기타 파일 컨텐츠 포맷에 대해서는 [사용자 지정 파트너 통합을 참조하십시오](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>인바운드 데이터 파일에서 전송된 각 사용자 ID에 대해 처리할 수 있는 줄이 200개로 제한됩니다. 예를 들어 사용자 ID에 대해 300개의 줄을 전송하는 경우 처음 200개의 줄이 유지되고 추가 100개의 줄이 무시됩니다. 아래 예에서, 사용자 ID 1 및 사용자 ID 2에 대해 각각 3개의 줄을 전송하므로 유용합니다. Adobe에서는 한 줄에 포함되는 특성 또는 키-값 쌍의 수에 제한을 두지 않습니다.
>
>
```
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
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Audience Manager에 의해 할당된 고유 사용자 ID <span class="keyword"> ( </span> Audience Manager UUID <a href="../../../reference/ids-in-aam.md"> </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">CRM 시스템에 할당된 고유 사용자 ID( Audience Manager의 <a href="../../../reference/ids-in-aam.md"> DPUUID </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">모바일 운영 체제에서 노출되는 대로 원본 수정되지 않은 형식의 모바일 Android 또는 iOS 장치 ID. </li> 
     </ul> </p> <p>모바일 ID의 경우: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA 형식: ID는 대문자여야 하며 해시해서는 안 됩니다. 예, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android 형식: ID는 소문자여야 하며 해시해서는 안 됩니다. 예, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>단일 탭 구분 기호로 사용자 ID와 특성 ID를 구분합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Audience Manager <span class="keyword"> 특성 </span> ID. 인바운드 데이터 파일에 <i>온보딩된 특성만</i> 포함시키십시오. 인바운드 데이터 전송에서 다른 특성 유형은 처리하지 않습니다. </p> <p> <p>참고:  트레이트 ID는 모든 트레이트에 대한 세부 사항을 반환하는 GET 메서드를 사용하여 찾을 수 있습니다. 자세한 내용은 특성 API <a href="../../../api/rest-api-main/api-traits.md"> 메서드를 참조하십시오 </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 서식 [!UICONTROL Trait IDs] {#formatting-trait-ids}

다음 표에서는 인바운드 데이터 파일에서 이름 또는 ID를 식별하는 [!UICONTROL trait] 접두사를 설명합니다. 예제는 [샘플 파일을](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) 참조하십시오.

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
   <td colname="col2"> <p>접두사는 시스템 <code> d_sid </code> 에 ID가 Audience Manager 특성 ID임을 <span class="keyword"> </span> 알려줍니다. 사용자 인터페이스에 표시되는 ID와 동일합니다. API 메서드로 특성 ID를 반환할 수도 <code> GET </code> 있습니다. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>데이터가 접두사로 <code> d_unsid </code> 추가되면 해당 트레이트에서 사용자가 제거됩니다. 파일 <code> d_unsid </code> 에서 접두사가 <code> overwrite </code> 무시됩니다. </p> <p>접두사는 시스템 <code> d_unsid= </code> 에 ID가 Audience Manager 특성 ID임을 <span class="keyword"> </span> 알려줍니다. 사용자 인터페이스에 표시되는 ID와 동일합니다. API 메서드로 특성 ID를 반환할 수도 <code> GET </code> 있습니다. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> 트레이트 규칙을 </a> 사용하여 트레이트 자격에 대한 기준을 설정할 수 있습니다. 특성 규칙의 형식을 지정하는 경우 간단한 쉼표 형식 목록 <code> ic == trait ID </code>으로 트레이트를 보낼 수 있습니다. </p> <p>예를 들어 다음과 같은 세 가지 특성 규칙을 만든다고 가정해 봅시다. </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>이러한 트레이트는 키와 <code> ic </code> 연결됩니다. 이를 통해 데이터 파일에서 더 간단한 트레이트 목록을 만들 수 있습니다. 또한 <code> ic </code> 접두사를 포함할 필요는 없습니다. 따라서 데이터 파일의 내용은 다음과 같이 표시될 수 있습니다. </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>키-값 쌍 </p> </td> 
   <td colname="col2"> <p>특성 데이터는 영숫자 문자열을 사용하여 키-값 쌍으로 형식을 지정할 수 있습니다. 아래와 같이 키-값 쌍의 서식을 지정할 수 있는 방법에는 여러 가지가 있습니다. </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> <code> product = tablet </code> 는 올바른 형식의 키-값 쌍의 예입니다. </p> </td> 
  </tr>
 </tbody>
</table>

## 잘못된 문자 [!UICONTROL Trait IDs]와 [!UICONTROL User IDs] 키-값 쌍 {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] 숫자 문자로만 구성됩니다. 인바운드 데이터 파일 *에만[!UICONTROL onboarded traits]*포함시켜 주시기 바랍니다. 인바운드 데이터 전송에서 다른[!UICONTROL trait]유형은 처리하지 않습니다.

### [!UICONTROL User IDs]

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
   <td colname="col2"> <p><i>인코딩된 콜론() 또는 인코딩되지 않은 콜론(</i> <code> %3A </code>:)을 사용하지 마십시오. ) 기호를 DPUUID에 넣습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모바일 iOS(IDFA) 또는 Android 장치 ID </p> </td> 
   <td colname="col2"> <p>모바일 장치 ID는 아래와 같이 엄격하게 형식이어야 합니다. </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA 형식: ID는 대문자여야 하며 해시해서는 안 됩니다. 예, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android 형식: ID는 소문자여야 하며 해시해서는 안 됩니다. 예, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 키-값 쌍

키-값 쌍에서 값 이름의 형식이 잘못 지정되면 문제가 발생합니다. 키-값 쌍에서 값을 만들거나 이름을 지정할 때는 다음 규칙을 따르십시오.

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
   <td colname="col2"> <p>다음과 같이 키와 키-값 쌍의 값 부분에 인용 문자를 사용할 수 있습니다. </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>대시 문자(-) </p> </td> 
   <td colname="col2"> <p>우리는 열쇠 시작 시 부선 신호를 무시한다. 예를 들어, 는 <code> -product = camera </code> 로 해석됩니다 <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>키-값 쌍에서 빈 값</i> <code> TAB </code> 대신 사용하지 마십시오. 인바운드 데이터 파일 <code> TAB </code> 에서 변수를 구분하는 용도로만 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>키 또는 값에 새 줄이나 탭 문자( <code> \n, \t </code>)를 사용하지 마십시오. </p> </td> 
  </tr>
 </tbody>
</table>

## 데이터 파일 예제 {#data-file-examples}

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
   <td colname="col2"> <p>이 데이터 파일은 트레이트 24, 26, 27에 자격이 있는 사용자를 보여주며 트레이트 28 및 29에서 제거되었습니다. </p> <p> 
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
   <td colname="col2"> <p>이러한 트레이트는 접두사가 있는 트레이트 규칙에 <code> ic </code> 추가되었습니다. 이와 같이 쉼표로 구분하여 데이터 파일에 추가할 수 있습니다. 탭은 UUID와 특성 ID를 구분합니다. 파일에 <code> ic </code> 접두사가 필요하지 않습니다. </p> <p><b>숫자 ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>문자열 ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>키-값 쌍 사용 </p> </td> 
   <td colname="col2"> 이 파일 데이터는 키-값 쌍을 사용하여 데이터를 <span class="keyword"> Audience Manager에 전달합니다 </span>. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[추가 예제가 필요한 경우 샘플 데이터 파일을 다운로드합니다](assets/ftp_dpm_1234_1445374061.overwrite) . 다운로드 파일의 확장자는 `.overwrite` 파일입니다. 간단한 텍스트 편집기로 열 수 있습니다.

## 예제 매트릭스 {#examples-matrix}

아래 차트에는 ID [유형](../../../reference/ids-in-aam.md) 및 프로필에 추가하고자 하는 방법에 따라 인바운드 파일의 형식을 지정하는 올바른 방법에 대한 예 [!UICONTROL traits] 가 나와 있습니다.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID 유형/작업 </th> 
   <th colname="col2" class="entry"> d_sid를 사용하여 사용자 프로필에 트레이트 추가 </th> 
   <th colname="col3" class="entry"> 사용자 프로필에서 트레이트를 제거하려면 d_unsid를 사용합니다. </th> 
   <th colname="col4" class="entry"> 키-값 쌍으로 전송하여 사용자 프로필에 트레이트 추가 </th> 
   <th colname="col5" class="entry"> 사용자 프로필에 트레이트를 추가하려면 ic 접두사를 사용하십시오. </th> 
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
   <td colname="col1"> <p>iOS 디바이스용 Apple IDFA </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> 예제 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> 예 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> 예 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> 예 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>자신의 CRM ID(DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> 예 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> 예 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> 예제 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> 예 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

을 [!UICONTROL trait IDs] 사용하여 자격 [!UICONTROL trait] 정보를 [!DNL Audience Manager] [!DNL UUIDs]전송합니다.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

을 [!UICONTROL trait IDs] 사용하여 [!UICONTROL trait] 자격 조건 [!DNL Audience Manager] [!DNL UUIDs]을 지정합니다.

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

키-값 쌍으로 보내 [!UICONTROL trait] 자격 정보를 추가합니다 [!DNL Audience Manager][!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

또는 

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

접두사를 `ic` 사용하여 자격 [!UICONTROL trait] 정보를 [!DNL Audience Manager] [!DNL UUIDs]전송합니다.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

장치 [!UICONTROL trait IDs] 에 대한 [!UICONTROL trait] 자격 정보를 보내는 데 [!DNL Android] 사용합니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

장치 [!UICONTROL trait IDs] 에 대한 [!UICONTROL trait] 결격사유 정보를 전송하는 데 [!DNL Android] 사용합니다.

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

키-값 쌍으로 전송하여 장치의 [!UICONTROL trait] 자격 정보를 [!DNL Android] 추가합니다.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

장치의 `ic` 자격 정보 [!UICONTROL trait] 를 전송하려면 접두사를 [!DNL Android] 사용하십시오.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

또는 

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

장치 [!UICONTROL trait IDs] 에 대한 [!UICONTROL trait] 자격 정보를 보내는 데 [!DNL iOS] 사용합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

장치 [!UICONTROL trait IDs] 에 대한 [!UICONTROL trait] 결격사유 정보를 전송하는 데 [!DNL iOS] 사용합니다.

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

키-값 쌍으로 전송하여 장치의 [!UICONTROL trait] 자격 정보를 [!DNL iOS] 추가합니다.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

장치의 `ic` 자격 정보 [!UICONTROL trait] 를 전송하려면 접두사를 [!DNL iOS] 사용하십시오.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

또는 

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

를 [!UICONTROL trait IDs] 사용하여 자격 [!UICONTROL trait] 정보를 보낼 수 [!DNL DPUUIDs]있습니다.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

을 [!UICONTROL trait IDs] 사용하여 자격 [!UICONTROL trait] 상실 정보를 [!DNL DPUUIDs]전송합니다.

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

키-값 쌍으로 보내 [!UICONTROL trait] 자격 정보를 추가합니다 [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

또는 

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

접두사를 `ic` 사용하여 자격 [!UICONTROL trait] 정보를 보낼 수 [!DNL DPUUIDs]있습니다.

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

