---
description: 데이터 파일에는 노출, 클릭 또는 전환 데이터가 포함되어 있습니다. 형식이 제대로 지정되면 이 데이터를 Audience Manager으로 가져와 Audience Optimization 보고서와 실행 가능 로그 파일에서 사용할 수 있습니다. 이 섹션의 사양에 따라 데이터 파일의 형식을 지정합니다.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Audience Optimization 보고서 및 실행 가능 로그 파일을 위한 데이터 파일
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Audience Optimization 보고서 및 실행 가능 로그 파일을 위한 데이터 파일 {#data-files-for-audience-optimization-reports}

데이터 파일에는 노출, 클릭 또는 전환 데이터가 포함되어 있습니다. 형식을 제대로 지정하면 이 데이터를 Audience Manager으로 가져와서 [Audience Optimization 보고서](../../../reporting/audience-optimization-reports/audience-optimization-reports.md) 를 통해 데이터를 사용하여 트레이트를 만들 수 있습니다. [실행 가능 로그 파일](/help/using/integration/media-data-integration/actionable-log-files.md). 이 섹션의 이러한 사양에 따라 데이터 파일의 형식을 지정합니다.

## 개요 {#overview}

제대로 이름이 지정되고 형식이 지정된 데이터 파일을 사용하면 노출, 클릭 또는 변환 데이터를 [Audience Optimization 보고서](../../../reporting/audience-optimization-reports/audience-optimization-reports.md). 이 기능은 와 통합되지 않은 파트너와 작업할 때 유용합니다 [!DNL Audience Manager] 해당 보고서 세트의 데이터로 작업하려고 합니다. 이 프로세스에는 노출, 클릭 및 전환 데이터를 위해 별도의 파일이 필요합니다. 이러한 이벤트를 단일 파일에 혼합하지 마십시오.

데이터 파일에는 메타데이터 파일이 포함되어야 합니다. 메타데이터 파일 내용은 데이터 파일 정보와 보고서 메뉴의 사람이 읽을 수 있는 관련 레이블과 일치합니다. 자세한 내용은 [메타데이터 파일에 대한 개요 및 매핑](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).

## 데이터 파일에 대한 이름 지정 규칙 {#naming-conventions}

다음 구문은 올바른 형식의 데이터 파일 이름의 구조를 정의합니다. 참고, *기울임체* 파일 컨텐츠에 따라 변경되는 변수 자리 표시자를 나타냅니다.

**구문:** <pre><i>이벤트 유형</i>_<i>yymdd</i></code></pre>

파일 이름:

* 이벤트 유형은 파일에 노출 수, 클릭 수 또는 전환이 포함되어 있음을 나타냅니다. 각 이벤트 유형에 대해 별도의 파일을 만듭니다.
* 밑줄은 이벤트 유형과 연도 날짜 타임스탬프를 구분합니다.
* 업로드하기 전에 gzip을 사용하여 파일을 압축하고 `.gz` 파일 확장명을 사용합니다.

이러한 요구 사항이 주어지면 다음과 같이 내용을 기준으로 데이터 파일의 이름을 지정합니다.

* 노출 데이터: <pre>노출 횟수_<i>yymdd</i>.gz</code></pre>
* 데이터 클릭: <pre>클릭_<i>yymdd</i>.gz</code></pre>
* 전환 데이터: <pre>전환_<i>yymdd</i>.gz</code></pre>

## 데이터 파일에 대한 컨텐츠 형식 {#content-format}

다음 구문은 올바른 형식의 데이터 파일에서 컨텐츠 구조를 정의합니다. 참고, *기울임체* 변수 자리 표시자를 나타내며 실제 데이터 파일에서 레이블로 대체됩니다.

**구문:** <pre><i>헤더 레이블 1</i> | <i>헤더 레이블 2</i> ... <i>헤더 레이블 n</i> | <i>버전</i></code></pre>

파일 내용:

* 헤더 레이블은 아래 표에 표시된 대로 순서대로 표시되어야 합니다. 노출 횟수 및 클릭 수는 동일한 레이블을 사용합니다. 변환 파일에 추가 헤더가 포함되어 있습니다.
* 특정 열에 대한 데이터가 없는 경우 해당 필드를 `-1`.

* 파일 *반드시* 버전 번호로 끝납니다. 현재 버전은 1.1입니다.
* 인쇄되지 않는 ASCII 001 문자를 사용하여 파일 헤더와 내용을 구분합니다. ASCII 001을 사용할 수 없는 경우 헤더와 데이터를 탭 구분 기호로 구분합니다. 인쇄되지 않는 문자이므로 위의 구문 예는 파이프를 보여 줍니다 `"|"` 표시 전용.

**필드 레이블**

아래 표는 데이터 파일의 열 헤더를 나열하고 설명합니다. 헤더는 대/소문자를 구분하며 표에 정렬된 대로 표시되어야 합니다. 모든 데이터 유형은 별도로 지정하지 않는 한 정수(INT)입니다.

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
   <td colname="col2"> <p>노출, 클릭 또는 전환 이벤트에 대한 UTC 날짜 및 시간입니다. 를 사용하십시오 <code> yyyy-MM-dd HH:mm:ss</code> 형식 지정 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>사이트 방문자에 대한 ID( <span class="term"> 데이터 공급자 고유 사용자 ID</span> 또는 DPUUID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertiser-ID </p> </td> 
   <td colname="col2"> <p>광고주의 데이터 소스 ID 또는 통합 코드. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>비즈니스 단위 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign-ID </p> </td> 
   <td colname="col2"> <p>캠페인 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>광고 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>사이트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> 광고 서버의 숫자 배치 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>삽입 순서 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quotic-ID </p> </td> 
   <td colname="col2"> <p>전술 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>세로 ID </p> </td> 
   <td colname="col2"> <p>업계 카테고리 또는 카테고리의 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>수량 </p> </td> 
   <td colname="col2"> <p> 전환 이벤트에서 판매되는 항목 수입니다. </p> <p> <i>변환 데이터 파일에 대해서만.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>수입 </p> </td> 
   <td colname="col2"> <p>구매 또는 기타 전환 금액입니다. 데이터 유형: 이동. </p> <p> <i>변환 데이터 파일에 대해서만.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>기타 데이터 </p> </td> 
   <td colname="col2"> <p>전환 랜딩 페이지의 URL입니다. 데이터 유형: 문자열. </p> <p> <i>변환 데이터 파일에 대해서만.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>전환 유형입니다. 전환이 일치하는지 여부를 나타냅니다. 옵션은 다음과 같습니다. </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 노출 횟수 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 클릭 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: 연결되지 않았거나 알 수 없음 </li> 
    </ul> <p> <i>변환 데이터 파일에 대해서만.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>버전 </p> </td> 
   <td colname="col2"> <p>노출, 클릭 또는 전환 데이터 파일의 모든 행 끝에 표시되는 필수 버전 번호입니다. 현재 버전은 1.1입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 데이터 파일에 대한 전달 방법 {#delivery-methods}

사용자의 노출, 클릭 또는 전환 데이터 파일을 Amazon S3 디렉토리에 업로드합니다 [!DNL Audience Manager] 계정이 필요합니다. 배달/디렉터리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

>[!IMPORTANT]
>
> 시작하고 설정하려면 Audience Manager 컨설턴트나 고객 지원에 문의하십시오 [!DNL Amazon S3] 데이터 파일에 대한 디렉토리.

**배달 경로 구문 및 예**

데이터는 [!DNL Amazon S3] 디렉토리. 파일 경로는 아래에 표시된 구문을 따릅니다. 참고, *기울임체* 변수 자리 표시자를 나타냅니다. 다른 요소는 상수 또는 키이며 변경되지 않습니다.

**구문:** <pre>.../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>파일 형식</i>_<i>yymdd</i></code></pre>

다음 표에서는 파일 전달 경로에 이러한 각 요소를 정의합니다.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>디렉토리 저장소 경로의 시작입니다. 모든 것이 설정되면 전체 경로가 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>이 키-값 쌍에는 <span class="keyword"> Audience Manager</span> 고객 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>이 키-값 쌍에는 이벤트 호출 시 전달된 데이터 소스 ID가 포함되어 있습니다. 이 보고서는 이 데이터가 속한 기관을 식별하고 해당 데이터를 지원 메타데이터 파일에 연결합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 데이터 파일에 대한 상위 수준 디렉터리입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>포함된 데이터 유형과 게재 타임스탬프를 나타내는 파일 형식 이름입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

**샘플 업로드 경로 및 파일 이름**

파일을 업로드할 때 경로는 다음과 유사합니다.

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**파일 처리 시간 및 업데이트**

데이터 파일은 하루에 4번 정기적으로 처리됩니다.

데이터를 업데이트하려면 특정 날짜에 대한 모든 노출, 클릭 또는 전환이 포함된 파일을 보내야 합니다. 이 경우 한 날은 한 자정부터 다음 자정까지 24시간 기간입니다. 가장 좋은 방법으로서, UTC 시간을 사용하여 날짜 간격을 정의할 수 있습니다.

## 다음 단계 {#next-steps}

메타데이터 파일 이름 지정 및 작성에 대한 요구 사항을 검토하십시오. 시작하려면 다음을 참조하십시오 [메타데이터 파일에 대한 개요 및 매핑](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md).
