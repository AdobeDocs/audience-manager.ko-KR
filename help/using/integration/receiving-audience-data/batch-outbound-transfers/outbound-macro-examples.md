---
description: 일반적인 매크로 중 일부를 사용하여 아웃바운드 파일 템플릿을 만드는 방법의 예입니다.
seo-description: Examples of how some of the common macros are used to create outbound file templates.
seo-title: Outbound Macro Examples
solution: Audience Manager
title: 아웃바운드 매크로 예제
uuid: 823d85d4-d683-45cf-9e60-c12b7d52a498
feature: Outbound Data Transfers
exl-id: 7e3f2b25-7b7c-47fe-aa62-7ebd4e25f9ba
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---

# 아웃바운드 매크로 예제 {#outbound-macro-examples}

일반적인 매크로 중 일부를 사용하여 아웃바운드 파일 템플릿을 만드는 방법의 예입니다.

>[!NOTE]
>
>테이블에서 **boldface** 형식은 관련 출력으로 각 매크로를 식별합니다. 형식 예제의 경우 각 매크로를 시각적으로 구분할 수 있도록 `<` `>` 기호가 추가되었습니다.

## 파일 이름 매크로 {#file-name-macros}

사용 가능한 매크로 및 정의 목록은 [아웃바운드 템플릿 매크로](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)를 참조하십시오.

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매크로 </th> 
   <th colname="col2" class="entry"> 형식 및 출력 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>출력: <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>출력: <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>출력: <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>출력: </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">전체: <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">증분: <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>출력: </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>출력: <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 머리글 행 매크로 {#header-macros}

사용 가능한 매크로 및 정의 목록은 [아웃바운드 템플릿 매크로](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)를 참조하십시오.

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매크로 </th> 
   <th colname="col2" class="entry"> 형식 및 출력 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>출력: <code> 888 full.sync </code> </p> <p>출력에서 인쇄되지 않는 탭 문자는 각 요소를 구분합니다. </p> </td>
  </tr>
 </tbody>
</table>

## 파일 콘텐츠 매크로 {#file-content-macros}

사용 가능한 매크로 및 정의 목록은 [아웃바운드 템플릿 매크로](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)를 참조하십시오.

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매크로 </th> 
   <th colname="col2" class="entry"> 형식 및 출력 예 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;UUID&gt; </code> </p> <p>출력: <code> 123456 07955261652886032950143702505894272138 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>출력: <code> 07955261652886032950143702505894272138 DP_UUID1 DP_UUID2 DP_UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>아래의 별도 섹션을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>출력: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>출력: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p><b>형식:</b> </p> <p> 
     <code>
       {"AdvertiserId":"&lt;PIDALIAS&gt;",&nbsp;"DataCenterId":&nbsp;2,"TDID":"&lt;DP_UUID&gt;", "Data":[&lt;SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;"&lt;CLOSE_CURLY_BRACKET&gt;}; separator=","&gt;&lt;if(SEGMENT_LIST&nbsp;&amp;&amp;&nbsp;REMOVED_SEGMENT_LIST)&gt;&lt;COMMA&gt;&lt;endif&gt; &lt;REMOVED_SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;", "TtlInMinutes":0&lt;CLOSE_CURLY_BRACKET&gt;};&nbsp;separator=","&gt;]}
     </code></p><p><b>출력:</b></p> <p>
     <code>//First&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2, "TDID":"dfd215e4-8d6b-4fdb-90b9-fab4456f2c9d","Data":[{"Name":"4321"}]} //Second&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2,"TDID":"9099e8fe-abab-5114-abaa-28bdaa0539ca","Data":[{"Name":"4321"},{"Name":"987","TtlInMinutes":0}, {"Name":"654","TtlInMinutes":0}]} 
     </code></p> <p> <p>참고: 첫 번째 예제에서 <code> REMOVED_SEGMENT_LIST </code>이(가) 비어 있으므로 매크로는 <code> SEGMENT_LIST </code>에 대한 데이터만 반환합니다. 두 번째 예제에서는 두 매크로에 대한 데이터를 반환합니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>형식: </p> <p> <code> &lt;PID&gt;&lt;TAB&gt;&lt;UUID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt; &lt;SET_ATTRIBUTES&gt;&lt;TAB&gt;&lt;OPT_OUT&gt;&lt;TAB&gt;&lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.alias&gt;,&lt;OUTPUT_ATTRIBUTE_VALUE&gt;,&lt;seg.lastUpdateTime&gt;&amp;}&gt; </code> </p> <p>출력: </p> <p> <code> 1159 00088008579683653741516297509717335000 17t0aj01b120hp 1 0 5,103714,1,1344114661000&amp;5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>출력: <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>출력에서 인쇄되지 않는 탭 문자는 각 요소를 구분합니다. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>형식: <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>출력: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID`개의 예제

`DPUUID` 매크로가 데이터를 출력하는 방법을 이해하기 위해 아래와 같이 `DPUUID`에 2개의 `DPID`이(가) 매핑되어 있다고 가정합니다.

* DPID `1111`은(는) DPUUID `AAAA`(타임스탬프 = 1) 및 `BBBB`(타임스탬프 = 2)에 매핑됩니다.
* DPID `2222`이(가) DPUUID `CCCC`에 매핑됩니다.

다음 표에서는 이러한 조건이 주어지면 가능한 몇 가지 형식 문자열과 그 출력을 열거합니다.

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매핑 조건 </th> 
   <th colname="col2" class="entry"> 매크로 형식 </th> 
   <th colname="col3" class="entry"> 출력 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>단일 DPID에 대한 모든 매핑 반환 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111|maxMappings=0|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","AAAA"],["1111","BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모든 DPID에 대해 최대 1개의 매핑 반환 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111,2222|maxMappings=1|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","BBBB"],["2222","CCCC"]] </code> </p> <p>DPID <code> 1111 </code>의 경우 해당 ID에 더 큰 타임스탬프가 있으므로 매크로는 DPUUID <code> BBBB </code>에만 매핑됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>단일 DPID에 대해 최대 2개의 매핑 반환 </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=2222|maxMappings=2|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222","CCCC"]] </code> </p> <p><code> maxMappings=2 </code>이지만 지정한 DPID에 DPUUID가 하나만 있으므로 이 매크로는 1개의 DPID만 DPUUID 매핑으로 반환합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

[아웃바운드 템플릿 매크로](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)
