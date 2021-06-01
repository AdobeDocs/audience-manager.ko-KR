---
description: 아웃바운드 템플릿을 만드는 데 사용할 수 있는 매크로를 나열합니다. 여기에는 파일 이름 매크로, 헤더 매크로 및 콘텐츠 매크로가 포함됩니다.
seo-description: 아웃바운드 템플릿을 만드는 데 사용할 수 있는 매크로를 나열합니다. 여기에는 파일 이름 매크로, 헤더 매크로 및 콘텐츠 매크로가 포함됩니다.
seo-title: 아웃바운드 템플릿 매크로
solution: Audience Manager
title: 아웃바운드 템플릿 매크로
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: 아웃바운드 데이터 전송
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 3%

---

# 아웃바운드 템플릿 매크로 {#outbound-template-macros}

아웃바운드 템플릿을 만드는 데 사용할 수 있는 매크로를 나열합니다. 여기에는 파일 이름 매크로, 헤더 매크로 및 콘텐츠 매크로가 포함됩니다.

## 파일 이름 및 파일 헤더 매크로 {#file-name-header-macros}

이 표에서는 파일 이름에 사용할 수 있는 매크로를 나열하고 설명하고 헤더 필드를 정의합니다. 코드 샘플은 [아웃바운드 매크로 예시](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)를 참조하십시오.

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매크로 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>인쇄되지 않는 ASCII 문자입니다. 행 또는 컨텐츠의 섹션의 시작을 나타냅니다. 파일에서 데이터 열을 분리하는 데에도 사용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>사용자 ID 키 데이터 공급자 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> 아웃바운드 주문에 대해 여러 줄 헤더를 만들 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>주문 / 대상 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>주문/대상 ID에 대한 별칭입니다. </p> <p>별칭은 관리자 UI에서 설정됩니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>아웃바운드 파일을 여러 부분으로 분할하는 것을 나타냅니다. 파일 이름의 SPLITNUM 섹션을 0으로 앞에 있는 부품 번호로 대체하여 SPLITNUM 섹션에 최소 3자를 사용할 수 있습니다.</p>
   <p>SPLITNUM 매크로를 &lt;&gt; 문자로 둘러싸지 않아도 됩니다.</p><p>예: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>위의 예에서 마지막 세 자리(001,002,003)는 SPLITNUM 식별자입니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>동기화 유형을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>:전체 동기화. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>:증분 동기화. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>데이터 전송 방법을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>구분 기호로 사용되는 이 매크로는 필드 사이에 탭을 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>10자리, UTC, Unix 타임스탬프. </p> <p>Java 날짜/타임스탬프 형식 규칙에 따라 <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> 형식을 지정할 수도 있습니다. </p> </td> 
  </tr>

</tbody> 
</table>

## 콘텐츠 매크로 {#content-macros}

데이터 파일의 내용을 포맷하는 데 사용되는 매크로입니다. 코드 샘플은 [아웃바운드 매크로 예시](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)를 참조하십시오.

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매크로 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>닫는 중괄호 <code>}</code> 문자를 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> 데이터 공급자 고유 사용자 식별자  </span>. </p> <p>아웃바운드 파일에서 로 데이터를 전송하는 데이터 파트너의 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>데이터 파트너의 여러 ID를 포함하는 목록을 반환합니다. 이 기능은 여러 하위 부서가 있는 대규모 조직이나 데이터를 공유할 수 있는 다른 조직 그룹이 있는 경우에 유용합니다. 이 매크로는 해당 하위 그룹의 ID 목록을 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>이 매크로의 출력은 데이터 공급자 ID(DPID)를 관련 DPUUID(고유 사용자 ID)에 매핑합니다. 이 매크로는 출력을 제어하려면 서식 문자열이 있어야 합니다. 샘플 출력은 다음과 비슷합니다. </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p><code> maxMappings </code> 설정은 매크로가 반환할 매핑 수를 결정합니다. <code> maxMappings=0 </code>에서는 이 매크로가 지정된 각 DPID에 대한 모든 매핑을 반환합니다. 데이터는 타임스탬프(가장 최근 첫 번째)로 정렬되고 가장 큰 타임스탬프가 있는 결과를 먼저 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>이러한 매크로 조합은 사용자가 속하고 제거된 세그먼트를 나열하는 조건문을 만듭니다. 두 조건이 모두 충족되지 않거나 데이터가 없는 경우 빈 문자열이 반환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud ID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>여는 중괄호 <code>{</code> 문자를 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. 사용하지 마십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>주문 또는 대상 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. 사용하지 마십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p><code> 1 </code> 을 정적 하드코딩된 값으로 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>파트너 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>주문/대상 ID에 대한 별칭입니다. </p> <p>별칭은 관리자 UI에서 설정됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>제거된 세그먼트 목록(있는 경우)을 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>목록의 세그먼트 목록 반환 다음 선택적 인수를 허용합니다. </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>:세그먼트 ID. 삭제 예정. <code> sid </code>를 사용하십시오.  </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>:고객 세그먼트 ID. 삭제 예정. <code> sid </code>를 사용하십시오.  </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>:세그먼트 ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>:데이터 <code> 5 </code>를 세그먼트 데이터로 식별하는 정적, 하드코딩된 값인 을 반환합니다. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: 삭제 예정. 사용하지 마십시오. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>:세그먼트가 마지막으로 실현된 시간을 나타내는 Unix 타임스탬프. </li> 
    </ul> <p>이러한 변수를 매크로 뒤에 중괄호로 묶습니다. 예를 들어 이 코드는 파이프 "|" 문자로 결과를 구분합니다.<code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>정적 하드코딩된 값으로 <code> 1 </code> 를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>동기화 유형을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>:전체 동기화. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>:증분 동기화. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>데이터 전송 방법을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>구분 기호로 사용되는 이 매크로는 필드 사이에 탭을 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>트레이트 목록을 반환합니다. 다음 선택적 인수를 허용합니다. </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>:숫자 ID로 트레이트 유형을 식별합니다. 반환: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> DPM 트레이트(오프라인, 인바운드 작업으로 온보딩됨)를 식별합니다. </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> 는 규칙 기반 트레이트(DCS를 통해 온보딩됨)를 식별합니다. </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>:트레이트 ID입니다. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>:트레이트가 마지막으로 실현된 시간입니다. Unix 타임스탬프. </li> 
    </ul> <p>이러한 변수를 매크로 뒤에 중괄호로 묶습니다. 예를 들어 이 코드는 파이프 "|" 문자로 결과를 구분합니다.<code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager  </span> 사용자 ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [아웃바운드 매크로 예제](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

