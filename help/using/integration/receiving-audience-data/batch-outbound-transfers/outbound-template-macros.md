---
description: 아웃바운드 템플릿을 만드는 데 사용할 수 있는 매크로를 나열합니다. 여기에는 파일 이름 매크로, 헤더 매크로 및 컨텐츠 매크로가 포함됩니다.
seo-description: 아웃바운드 템플릿을 만드는 데 사용할 수 있는 매크로를 나열합니다. 여기에는 파일 이름 매크로, 헤더 매크로 및 컨텐츠 매크로가 포함됩니다.
seo-title: 아웃바운드 템플릿 매크로
solution: Audience Manager
title: 아웃바운드 템플릿 매크로
uuid: Dec 082 D 3-306 B -4 FF 5-AFB 2-418 BD 543 D 8 D 0
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# 아웃바운드 템플릿 매크로 {#outbound-template-macros}

아웃바운드 템플릿을 만드는 데 사용할 수 있는 매크로를 나열합니다. 여기에는 파일 이름 매크로, 헤더 매크로 및 컨텐츠 매크로가 포함됩니다.

## 파일 이름 및 파일 헤더 매크로 {#file-name-header-macros}

아래 표에서는 파일 이름에서 사용할 수 있는 매크로와 헤더 필드를 정의하는 방법을 설명합니다. 코드 샘플은 [아웃바운드 매크로 예제를](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)참조하십시오.

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> macro </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_ SOH </code> </p> </td> 
   <td colname="col2"> <p>인쇄할 수 없는 ASCII 문자입니다. 이것은 행 또는 컨텐츠 섹션의 시작을 나타냅니다. 파일의 데이터 열을 구분하는 데에도 사용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpid </code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> master_ dpid </code> </p> </td> 
   <td colname="col2"> <p>사용자 ID 주요 데이터 공급자 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> order_ id </code> </p> </td> 
   <td colname="col2"> <p>주문/대상 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> pid_ alias </code> </p> </td> 
   <td colname="col2"> <p>주문/대상 ID에 대한 별칭. </p> <p>별칭은 관리자 UI에 설정됩니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> splitnum </code> </p> </td> 
   <td colname="col2"> <p>아웃바운드 파일을 여러 부분으로 분할하는 것을 나타냅니다. 파일 이름에 있는 Splitnum 섹션을 0 앞에 있는 part 번호로 대체하면 Splitnum 섹션에 최소 3 자를 사용할 수 있습니다.</p>
   <p>Splitnum 매크로를 &lt; &gt; 문자로 묶지 않아도 됩니다.</p><p>예: <code>&lt; sync_ type &gt;_ &lt; order_ id &gt;_ &lt; dpid &gt;_ &lt; dpid &gt;_ &lt; timestamp &gt; splitnum. csv</code>
<p>s 3_ 123456_ 9999_ full_ 1566906141001. csv</p> 
<p>s 3_ 123456_ 9999_ full_ 1566906141002. csv</p> 
<p>s 3_ 123456_ 9999_ full_ 1566906141003. csv</p> 
<p>위의 예에서 마지막 세 자리 (001,002,003) 는 Splitnum 식별자입니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sync_ mode </code> </p> </td> 
   <td colname="col2"> <p>는 동기화 유형을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> 전체 </code>: 전체 동기화. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> Iter </code>: 증분 동기화. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sync_ type </code> </p> </td> 
   <td colname="col2"> <p>데이터 전송 방법을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> FTP </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> S 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> tab </code> </p> </td> 
   <td colname="col2"> <p>이 매크로는 구분 문자로 사용되며 필드 사이에 탭을 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> timestamp </code> </p> </td> 
   <td colname="col2"> <p>10 자리, UTC, Unix 타임스탬프. </p> <p>또한 <code> &lt; timestamp; format = "yyyymmddhhmmss" &gt; </code> 다음 Java 날짜/타임스탬프 서식 규칙. </p> </td> 
  </tr>

</tbody> 
</table>

## 컨텐츠 매크로 {#content-macros}

데이터 파일의 컨텐츠 서식을 지정하는 데 사용되는 매크로입니다. 코드 샘플은 [아웃바운드 매크로 예제를](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)참조하십시오.

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> macro </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> close_ para_ bracket </code> </p> </td> 
   <td colname="col2"> <p>닫는 중괄호} 문자를 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dp_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> 데이터 공급자 고유 사용자 식별자 </span>. </p> <p>이것은 데이터를 아웃바운드 파일로 전송하는 데이터 파트너의 ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dp_ uuid_ list </code> </p> </td> 
   <td colname="col2"> <p>데이터 파트너의 여러 ID가 포함된 목록을 반환합니다. 이 기능은 여러 하위 분할 또는 데이터를 공유할 수 있는 기타 조직 그룹이 있는 대규모 조직이 있는 경우에 유용합니다. 이 매크로는 하위 그룹의 ID 목록을 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpid </code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dpuuids </code> </p> </td> 
   <td colname="col2"> <p>이 매크로의 출력은 데이터 공급자 ID (dpid) 를 관련 고유 사용자 ID (dpuuid) 에 매핑합니다. 이 매크로에는 출력을 제어할 수 있는 형식 지정 문자열이 있어야 합니다. 샘플 출력은 다음과 비슷합니다. </p> <p> <code> " dpids = dpid 1, dpid 2,... dpid n | maxmappings = n | format = JSON " </code> </p> <p><code> Maxmappings </code> 설정은 매크로를 반환할 매핑 수를 결정합니다. <code> Maxmappings = 0 </code>인 경우 이 매크로는 지정된 각 DPID에 대한 매핑을 반환합니다. 데이터는 타임스탬프 (가장 최근 것 먼저) 로 정렬되며 가장 큰 타임스탬프의 결과를 먼저 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (segment_ list &amp; &amp; removed_ segment_ list) endif </code> </p> </td> 
   <td colname="col2"> <p>이 매크로 조합은 사용자가 속해 있고 제거된 세그먼트를 나열하는 조건문을 만듭니다. 두 조건이 모두 충족되지 않았거나 데이터가 없는 경우 빈 문자열을 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> open_ para_ bracket </code> </p> </td> 
   <td colname="col2"> <p>여는 중괄호 {문자를 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_ OUT </code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. 사용하지 마십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> order_ id </code> </p> </td> 
   <td colname="col2"> <p>주문 또는 대상 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> output_ attribute_ type </code> </p> </td> 
   <td colname="col2"> <p>삭제 예정. 사용하지 마십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> output_ attribute_ value </code> </p> </td> 
   <td colname="col2"> <p><code> 1 </code> 를 정적 하드코드된 값으로 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>파트너 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Pidalias </code> </p> </td> 
   <td colname="col2"> <p>주문/대상 ID에 대한 별칭. </p> <p>별칭은 관리자 UI에 설정됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removed_ segment_ list </code> </p> </td> 
   <td colname="col2"> <p>제거된 세그먼트 목록을 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ list </code> </p> </td> 
   <td colname="col2"> <p>목록의 세그먼트 목록을 반환합니다. 다음 선택적 인수를 수락합니다. </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> Segmentid </code>: 세그먼트 ID. 삭제 예정. <code> SID </code>를 사용합니다. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> Csegid </code>: 고객 세그먼트 ID. 삭제 예정. <code> SID </code>를 사용합니다. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> SID </code>: 세그먼트 ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code></code>유형: 데이터를 세그먼트 데이터로 식별하는 정적, 하드코드된 값인 <code> 5 </code>를 반환합니다. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> Alias </code>: 가치 하락. 사용하지 마십시오. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> Lastupdatetime </code>: 세그먼트가 구현된 마지막 시간을 나타내는 UNIX 타임스탬프. </li> 
    </ul> <p>이러한 변수를 매크로 뒤에 중괄호로 넣습니다. 예를 들어 이 코드는|" 문자: <code> &lt; segment_ list: {seg|&lt; seg. type &gt;, &lt; seg. sid &gt;}; separator = "," &gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> set_ attributes </code> </p> </td> 
   <td colname="col2"> <p><code> 1 </code>를 하드 코딩된 정적 값으로 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sync_ mode </code> </p> </td> 
   <td colname="col2"> <p>는 동기화 유형을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> 전체 </code>: 전체 동기화. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> Iter </code>: 증분 동기화. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> sync_ type </code> </p> </td> 
   <td colname="col2"> <p>데이터 전송 방법을 나타내며 다음을 포함합니다. </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> FTP </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> S 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> tab </code> </p> </td> 
   <td colname="col2"> <p>이 매크로는 구분 문자로 사용되며 필드 사이에 탭을 삽입합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ list </code> </p> </td> 
   <td colname="col2"> <p>특성 목록을 반환합니다. 다음 선택적 인수를 수락합니다. </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code></code>유형: 숫자 ID로 트레이트 유형을 식별합니다. 반환: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> DPM </code> 트레이트 (오프라인 작업에서 온보딩된 오프라인) 를 식별하는 10. </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> 규칙 기반 트레이트 (DCS를 통해 온보딩된 실시간) 를 식별합니다. </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> Traitid </code>: 특성 ID. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> 래스트리스 </code>: 트레이트가 실현된 마지막 시간입니다. UNIX 타임스탬프. </li> 
    </ul> <p>이러한 변수를 매크로 뒤에 중괄호로 넣습니다. 예를 들어 이 코드는|" 문자: <code> &lt; trait_ list: {트레이트|&lt; trait. id &gt;, &lt; 특성. lastrealized &gt;}; separator = "," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> 사용자 ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [아웃바운드 매크로 예제](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

