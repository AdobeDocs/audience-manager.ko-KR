---
description: 일반 매크로 중 일부를 사용하여 아웃바운드 파일 템플릿을 만드는 방법의 예.
seo-description: 일반 매크로 중 일부를 사용하여 아웃바운드 파일 템플릿을 만드는 방법의 예.
seo-title: 아웃바운드 매크로 예제
solution: Audience Manager
title: 아웃바운드 매크로 예제
uuid: 823 d 85 d 4-d 683-45 cf -9 e 60-c 12 b 7 d 52 a 498
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 아웃바운드 매크로 예제 {#outbound-macro-examples}

일반 매크로 중 일부를 사용하여 아웃바운드 파일 템플릿을 만드는 방법의 예.

>[!NOTE]
>
>In the tables, **boldface** type identifies each macro with its related output. For the format examples, the `<` `>` symbols have been added to help visually separate each macro.

## File Name Macros {#file-name-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> macro </th> 
   <th colname="col2" class="entry"> 형식 및 출력 예제 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dpid </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> master_ dpid </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> order_ id </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output: <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sync_ mode </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>출력: </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Full: <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incremental: <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sync_ type </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>출력: </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> timestamp </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Output: <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Header Row Macros {#header-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> macro </th> 
   <th colname="col2" class="entry"> 형식 및 출력 예제 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> tab </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>Output: <code> 888 full.sync </code> </p> <p>출력에서 인쇄되지 않는 탭 문자는 각 요소를 분리합니다. </p> </td>
  </tr>
 </tbody>
</table>

## File Content Macros {#file-content-macros}

For a list of available macros and definitions, see [Outbound Template Macros](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> macro </th> 
   <th colname="col2" class="entry"> 형식 및 출력 예제 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> dp_ uuid </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dp_ uuid_ list </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dpuuids </code> </p> </td> 
   <td colname="col2"> <p>아래 섹션을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removed_ segment_ list </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ list </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (segment_ list &amp; &amp; removed_ segment_ list) endif </code> </p> </td> 
   <td colname="col2"> <p><b>형식:</b> </p> <p> 
     <code>{"Advertiserid": " &lt; Pidalias &gt; "," datacenterid ": 2, "tdid": " &lt; dp_ uuid &gt; "," data ": [&lt; segment_ list: {seg|&lt; open_ para_ bracket &gt; "name": " &lt; seg. alias &gt; " &lt; close_ para_ bracket &gt;}; separator = "," &gt; &lt; if (segment_ list &amp; &amp; removed_ segment_ list) &gt; &lt; 쉼표 &gt; &lt; endif &gt; &lt; removed_ segment_ list: {seg|&lt; open_ para_ bracket &gt; "name": " &lt; seg. alias &gt; "," ttlinminutes ": 0 &lt; close_ para_ bracket &gt;}; separator = "," &gt;]} </code>
 </p><p><b>출력:</b></p> <p>
     <code>//First 예 {"Advertiserid": " 12345 "," Datacenterid ": 2, "tdid": " dfd 215 e 4-8 d 6 b -4 fdb -90 b 9-fab 4456 f 2 c 9 d "," data ": [{"name": " 4321 "}]} //Second 예 {" Advertiserid ": " 12345 "," Datacenterid ": 2, "tdid": " 9099 E 8 fe-abab -5114-abaa -28 bdaa 0539 ca "," data ": [{"name": " 4321 "}, {" name ": " 987 "," Ttlinminutes ": 0}, {"name": " 654 "," Ttlinminutes ": 0}]} </code>
 </p> <p> <p>Note:  In the first example, the macro only returns data for <code> SEGMENT_LIST </code> because <code> REMOVED_SEGMENT_LIST </code> is empty. 두 번째 예제는 두 매크로 모두에 대한 데이터를 반환합니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> set_ attributes </code> </p> </td> 
   <td colname="col2"> <p>형식: </p> <p> <code> &lt; pid &gt; &lt; tab &gt; &lt; uuid &gt; &lt; tab &gt; &lt; dp_ uuid &gt; &lt; tab &gt; &lt; set_ attributes &gt; &lt; tab &gt; &lt; opt_ out &gt; &lt; tab &gt; &lt; segment_ list: {seg|&lt; seg. type &gt;, &lt; seg. alias &gt;, &lt; output_ attribute_ value &gt;, &lt; seg. lastupdatetime &gt; &amp;} &gt; </code> </p> <p>출력: </p> <p> <code> 1159 000880085796836537415162975091516297500 17 T 0 AJ 01 B 120 HP 1 0 5,103714,1,1344114661000 &amp; 5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> tab </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output: <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>출력에서 인쇄되지 않는 탭 문자는 각 요소를 분리합니다. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> trait_ list </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Output: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` 예

`DPUUID` 매크로를 통해 데이터를 출력하는 방법을 이해할 수 있도록 다음과 같이 2 `DPID`s 매핑이 s로 `DPUUID`매핑되었다고 가정합니다.

* DPID `1111` maps to DPUUIDs `AAAA` (timestamp = 1) and `BBBB` (timestamp = 2).
* DPID `2222` maps to DPUUID `CCCC`.

이러한 조건에 따라 다음 표는 가능한 일부 형식 문자열 및 출력을 열거합니다.

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매핑 조건 </th> 
   <th colname="col2" class="entry"> 매크로 형식 </th> 
   <th colname="col3" class="entry"> output </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>단일 DPID에 대한 모든 매핑 반환 </p> </td> 
   <td colname="col2"> <p> <code> &lt; dpuuids; format = "dpids = 1111 | maxmappings = 0 | format = JSON" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111", "AAAA"], ["1111", "BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>모든 DPIDS에 대해 최대 1 개의 매핑 반환 </p> </td> 
   <td colname="col2"> <p> <code> &lt; dpuuids; format = "dpids = 1111,2222 | maxmappings = 1 | format = JSON" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111", "bbbb"], ["2222", "cccc"]] </code> </p> <p>For DPID <code> 1111 </code>, the macro maps to DPUUID <code> BBBB </code> only because that ID has the larger timestamp. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>단일 DPID에 대해 최대 2 개의 매핑 반환 </p> </td> 
   <td colname="col2"> <p> <code> &lt; dpuuids; format = "dpids = 2222 | maxmappings = 2 | format = JSON" &gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222", "CCCC"]] </code> </p> <p><code> Maxmappings = 2 </code>임에도 불구하고 이 매크로는 DPUUID 매핑에 1 DPID만 반환합니다. 지정된 DPID에 DPUUID가 하나만 있기 때문입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

[아웃바운드 템플릿 매크로](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)