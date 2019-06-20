---
description: 데이터 파일에는 노출, 클릭 또는 전환 데이터가 포함됩니다. 형식이 올바르게 지정되면 이 데이터를 Audience Manager로 가져와서 대상 최적화 보고서에서 볼 수 있습니다. 이 섹션의 사양에 따라 데이터 파일의 형식을 지정합니다.
seo-description: 데이터 파일에는 노출, 클릭 또는 전환 데이터가 포함됩니다. 형식이 올바르게 지정되면 이 데이터를 Audience Manager로 가져와서 대상 최적화 보고서에서 볼 수 있습니다. 이 섹션의 사양에 따라 데이터 파일의 형식을 지정합니다.
seo-title: 대상 최적화 보고서용 데이터 파일
solution: Audience Manager
title: 대상 최적화 보고서용 데이터 파일
uuid: c 19 eb 0 c 7-47 c 1-4 cdf -8 a 6 c-cd 15 fe 04 c 379
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Files for Audience Optimization Reports{#data-files-for-audience-optimization-reports}

데이터 파일에는 노출, 클릭 또는 전환 데이터가 포함됩니다. 형식이 올바르게 지정되면 이 데이터를 Audience Manager로 가져와서 대상 최적화 보고서에서 볼 수 있습니다. 이 섹션의 사양에 따라 데이터 파일의 형식을 지정합니다.

## 개요 {#overview}

A properly named and formatted data file lets you import impression, click, or conversion data into the [Audience Optimization Reports](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). This is useful when working with a partner who is not integrated with [!DNL Audience Manager] and you want to work with their data in that report suite. 이 프로세스에는 노출, 클릭 및 전환 데이터에 대해 별도의 파일이 필요합니다. 이러한 이벤트를 하나의 파일에서 혼합하지 마십시오.

데이터 파일은 메타데이터 파일과 함께 있어야 합니다. 메타데이터 파일 컨텐츠는 보고서 메뉴에서 사용자가 읽을 수 있는 관련 레이블을 데이터 파일 정보와 일치시킵니다. For more information, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## Naming Conventions for Data Files {#naming-conventions}

다음 구문은 올바른 형식의 데이터 파일 이름 구조를 정의합니다. *기울임꼴은* 파일 컨텐츠에 따라 변경되는 변수 자리 표시자를 나타냅니다.

**구문:** <pre><code><i>이벤트 유형</i>_<i>yyyymmdd</i></code></pre>

파일 이름:

* 이벤트 유형은 해당 파일에 노출 횟수, 클릭 수 또는 전환 횟수가 있음을 나타냅니다. 각 이벤트 유형에 대해 별도의 파일을 만듭니다.
* 밑줄이 이벤트 유형과 1 년 날짜 타임스탬프를 구분합니다.
* Before uploading, compress your files using gzip and save them with the `.gz` file extension.

이러한 요구 사항을 충족하려면 다음과 같은 내용을 기반으로 데이터 파일의 이름을 지정하십시오.

* 노출 횟수 데이터: <pre><code>impressions_<i>yyyymmdd<i>.gz</code></pre>
* 데이터 클릭: <pre><code>clicks_<i>yyyymmdd</i>.gz</code></pre>
* 전환 데이터: <pre><code>conversions_<i>yyyymmdd</i>.gz</code></pre>

## Content Format for Data Files {#content-format}

다음 구문은 형식이 잘 구성된 데이터 파일에서 컨텐츠 구조를 정의합니다. Note, *italics* indicates a variable placeholder and is replaced with an label in an actual data file.

**구문:** <pre><code><i>머리글 레이블 1</i> | <i>머리글 레이블 2</i> ... <i>헤더 레이블 N</i> | <i>version</i></code></pre>

파일 컨텐츠에서:

* 헤더 레이블은 아래 표에 표시된 순서대로 표시되어야 합니다. 노출 횟수 및 클릭은 동일한 레이블을 사용합니다. 전환 파일에는 추가 헤더가 포함됩니다.
* If you don&#39;t have data for a particular column, populate that field with a `NULL` object or `-1`.

* Files *must* end with a version number. 현재 버전은 1.1 입니다.
* 파일 헤더와 내용을 인쇄할 수 없는 ASCII 001 문자로 구분합니다. ASCII 001를 사용할 수 없는 경우, 헤더와 데이터를 탭 구분 기호로 구분하십시오. As these are non-printing characters, the syntax example above shows a pipe `"|"` for display purposes only.

**필드 레이블**

아래 표는 데이터 파일의 열 헤더를 나열하고 설명한 것입니다. 헤더는 대/소문자를 구분하며 표에서 순서가 지정된 대로 표시되어야 합니다. 다른 언급이 없는 한 모든 데이터 유형은 정수 (정수) 입니다.

<table id="table_D8C5068741C3460380505F95F3016757"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 레이블 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>타임스탬프 </p> </td> 
   <td colname="col2"> <p>노출, 클릭 또는 전환 이벤트의 UTC 날짜 및 시간입니다. <code> YYYY-DD-MM HH: MM: SS</code> 형식. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>user-id </p> </td> 
   <td colname="col2"> <p>Your ID for a site visitor, also known as the <span class="term"> data provider unique user ID</span> or DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>advertiser-id </p> </td> 
   <td colname="col2"> <p>광고주의 데이터 소스 ID 또는 통합 코드. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bu-id </p> </td> 
   <td colname="col2"> <p>사업부 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>campaign-id </p> </td> 
   <td colname="col2"> <p>캠페인 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>creative-id </p> </td> 
   <td colname="col2"> <p>광고 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>site-id </p> </td> 
   <td colname="col2"> <p>사이트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>placement-id </p> </td> 
   <td colname="col2"> <p> 광고 서버의 숫자 배치 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>insertion-order-id </p> </td> 
   <td colname="col2"> <p>삽입 순서 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>tactic-id </p> </td> 
   <td colname="col2"> <p>전술 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>vertical-id </p> </td> 
   <td colname="col2"> <p>업종 수직 또는 카테고리에 대한 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>수량 </p> </td> 
   <td colname="col2"> <p> 전환 이벤트에서 판매된 항목의 수입니다. </p> <p> <i>전환 데이터 파일에만 해당됩니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>수입 </p> </td> 
   <td colname="col2"> <p>구매 또는 기타 전환 금액. 데이터 유형: float. </p> <p> <i>전환 데이터 파일에만 해당됩니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>기타 데이터 </p> </td> 
   <td colname="col2"> <p>전환 랜딩 페이지의 URL. 데이터 유형: 문자열. </p> <p> <i>전환 데이터 파일에만 해당됩니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>event-type </p> </td> 
   <td colname="col2"> <p>전환 유형. 전환이 일치하는지 여부를 나타냅니다. 옵션은 다음과 같습니다. </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code></code>0: 노출 횟수 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code></code>1: click </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: unattributed or unknown </li> 
    </ul> <p> <i>전환 데이터 파일에만 해당됩니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>버전 </p> </td> 
   <td colname="col2"> <p>노출, 클릭 또는 전환 데이터 파일의 모든 행 끝에 표시되는 필수 버전 번호입니다. 현재 버전은 1.1 입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Delivery Methods for Data Files {#delivery-methods}

Upload your impression, click, or conversion data files to an Amazon S3 directory for your [!DNL Audience Manager] account. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

**배달 경로 구문 및 예제**

데이터는 Amazon S 3 디렉토리의 각 고객에 대해 별도의 네임스페이스에 저장됩니다. 파일 경로는 아래 표시된 구문을 따릅니다. *기울임꼴은* 변수 자리 표시자를 나타냅니다. 다른 요소는 상수 또는 키이며 변경되지 않습니다.

**구문:** <pre><code>.../log_ ingenting/pid = <i>aam id<i>/dpid = <i>d_ src</i>/logs/ <i>file type</i>_<i>yyyymmdd</i></code></pre>

다음 표에서는 이러한 각 요소를 파일 배달 경로에 정의합니다.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ ingiting/</code> </p> </td> 
   <td colname="col2"> <p>디렉토리 저장소 경로의 시작입니다. 모든 것이 설정되면 전체 경로를 받게 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid =<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 고객 ID가 포함된 이 키-값 쌍. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid =<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>이 키-값 쌍은 이벤트 호출에서 전달된 데이터 소스 ID를 포함합니다. 이 보고서는 데이터를 가져오는 에이전시를 식별하고 해당 데이터를 지원 메타데이터 파일에 연결합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 로그</code> </p> </td> 
   <td colname="col2"> <p> 데이터 파일에 대한 높은 수준의 디렉토리입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>포함된 데이터의 종류와 배달 타임스탬프를 나타내는 파일 유형 이름입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

**샘플 업로드 경로 및 파일 이름**

파일을 업로드할 때 경로는 다음과 비슷합니다.

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**파일 처리 시간 및 업데이트**

데이터 파일은 하루에 4 회 정기적으로 처리됩니다.

데이터를 업데이트하려면 특정 날짜에 대한 모든 노출 횟수, 클릭 수 또는 전환이 들어 있는 파일로 전송합니다. 이 경우, 하루는 24 시간 사이의 24 시간 기간입니다. 가장 좋은 방법은 UTC 시간을 사용하여 하루 간격을 정의하는 것입니다.

## 다음 단계 {#next-steps}

메타데이터 파일 이름 지정 및 만들기에 대한 요구 사항을 검토하십시오. To get started, see [Overview and Mappings for Metadata Files](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
