---
description: 데이터 파일에는 노출, 클릭 또는 전환 데이터가 포함되어 있습니다. 형식이 제대로 지정되면 이 데이터를 Audience Manager으로 가져와 Audience Optimization 보고서 및 실행 가능한 로그 파일에 사용할 수 있습니다. 이 섹션의 사양에 따라 데이터 파일의 형식을 지정합니다.
seo-description: A data file contains impression, click, or conversion data. When formatted properly, you can import this data into Audience Manager and use it in the Audience Optimization reports and for Actionable Log Files. Format your data files according to the specifications in this section.
seo-title: Data Files for Audience Optimization Reports and Actionable Log Files
solution: Audience Manager
title: Audience Optimization 보고서 및 실행 가능 로그 파일용 데이터 파일
uuid: c19eb0c7-47c1-4cdf-8a6c-cd15fe04c379
feature: Log Files
exl-id: 0da2c1d3-5ff8-40dd-b831-21d8941688ce
source-git-commit: db90a6f1aaf85b10e31e93e316c257b7c3a904aa
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 1%

---

# Audience Optimization 보고서 및 실행 가능 로그 파일용 데이터 파일 {#data-files-for-audience-optimization-reports}

데이터 파일에는 노출, 클릭 또는 전환 데이터가 포함되어 있습니다. 형식이 제대로 지정되면 이 데이터를 Audience Manager으로 가져와 [Audience Optimization 보고서](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)에서 보고 [실행 가능한 로그 파일](/help/using/integration/media-data-integration/actionable-log-files.md)을 통해 데이터를 사용하여 트레이트를 만들 수 있습니다. 이 섹션의 다음 사양에 따라 데이터 파일의 형식을 지정합니다.

## 개요 {#overview}

이름이 올바르고 형식이 지정된 데이터 파일을 사용하면 노출, 클릭 또는 변환 데이터를 [Audience Optimization 보고서](../../../reporting/audience-optimization-reports/audience-optimization-reports.md)(으)로 가져올 수 있습니다. 이 기능은 [!DNL Audience Manager]과(와) 통합되지 않은 파트너와 함께 작업할 때 유용하며 해당 보고서 세트에서 해당 파트너의 데이터를 사용할 수 있습니다. 이 프로세스에는 노출, 클릭 및 전환 데이터에 대해 별도의 파일이 필요합니다. 이러한 이벤트를 단일 파일에서 혼합하지 마십시오.

데이터 파일은 메타데이터 파일과 함께 있어야 합니다. 메타데이터 파일 콘텐츠는 보고서 메뉴에서 사람이 읽을 수 있는 관련 레이블에 데이터 파일 정보를 일치시킵니다. 자세한 내용은 [메타데이터 파일에 대한 개요 및 매핑](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)을 참조하십시오.

## 데이터 파일에 대한 이름 지정 규칙 {#naming-conventions}

다음 구문은 올바른 형식의 데이터 파일 이름 구조를 정의합니다. *기울임꼴*&#x200B;은(는) 파일 내용에 따라 변경되는 변수 자리 표시자를 나타냅니다.

**구문:** <pre><code><i>이벤트 유형</i>_<i>yyyymmdd</i></code></pre>

파일 이름:

* 이벤트 유형은 파일에 노출 횟수, 클릭 수 또는 변환 수가 포함되어 있음을 나타냅니다. 각 이벤트 유형에 대해 별도의 파일을 만듭니다.
* 밑줄은 이벤트 유형과 연도-월-날짜 타임스탬프를 구분합니다.
* 업로드하기 전에 gzip을 사용하여 파일을 압축한 다음 `.gz` 파일 확장명으로 저장하십시오.

이러한 요구 사항이 주어지면 다음과 같이 해당 콘텐츠를 기반으로 데이터 파일의 이름을 지정합니다.

* 노출 데이터: <pre><code>노출 수_<i>yyyymmdd</i>.gz</code></pre>
* 데이터 클릭: <pre><code>clicks_<i>yyyymmdd</i>.gz</code></pre>
* 전환 데이터: <pre><code>전환_<i>yyyymmdd</i>.gz</code></pre>

## 데이터 파일에 대한 컨텐츠 형식 {#content-format}

다음 구문은 올바른 형식의 데이터 파일에서 콘텐츠 구조를 정의합니다. 참고: *기울임꼴*&#x200B;은(는) 변수 자리 표시자를 나타내며 실제 데이터 파일의 레이블로 대체됩니다.

**구문:** <pre><code><i>헤더 레이블 1</i> | <i>헤더 레이블 2</i> ... <i>헤더 레이블 n</i> | <i>버전</i></code></pre>

파일 내용:

* 머리글 레이블은 아래 표에 표시된 대로 순서대로 표시되어야 합니다. 노출 횟수와 클릭 수에 동일한 레이블이 사용됩니다. 변환 파일에 추가 헤더가 포함되어 있습니다.
* 특정 열에 대한 데이터가 없는 경우 해당 필드를 `-1`(으)로 채웁니다.

* *must* 파일이 버전 번호로 끝납니다. 현재 버전은 1.1입니다.
* 인쇄되지 않는 ASCII 001 문자로 파일 헤더와 내용을 구분합니다. ASCII 001을 사용할 수 없는 경우 탭 구분 기호로 헤더와 데이터를 구분하십시오. 인쇄되지 않는 문자이므로 위의 구문 예제에서는 표시 목적으로만 파이프 `"|"`을(를) 보여 줍니다.

**필드 레이블**

아래 표에는 데이터 파일의 열 헤더가 나열되고 설명되어 있습니다. 헤더는 대/소문자를 구분하므로 표에 정렬된 대로 표시되어야 합니다. 달리 지정하지 않는 한 모든 데이터 유형은 정수(INT)입니다.

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
   <td colname="col2"> <p>노출, 클릭 또는 전환 이벤트에 대한 UTC 날짜 및 시간입니다. <code> yyyy-MM-dd HH:mm:ss</code> 형식을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>User-ID </p> </td> 
   <td colname="col2"> <p>사이트 방문자의 ID(<span class="term"> 데이터 공급자 고유 사용자 ID</span> 또는 DPUUID라고도 함). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>광고주 ID </p> </td> 
   <td colname="col2"> <p>광고주용 데이터 소스 ID 또는 통합 코드. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>BU-ID </p> </td> 
   <td colname="col2"> <p>사업부 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>캠페인 ID </p> </td> 
   <td colname="col2"> <p>캠페인 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creative-ID </p> </td> 
   <td colname="col2"> <p>Creative ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Site-ID </p> </td> 
   <td colname="col2"> <p>사이트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Placement-ID </p> </td> 
   <td colname="col2"> <p> 광고 서버의 숫자 배치 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Insertion-Order-ID </p> </td> 
   <td colname="col2"> <p>삽입 순서 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tactic-ID </p> </td> 
   <td colname="col2"> <p>전술 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>세로 ID </p> </td> 
   <td colname="col2"> <p>업계 카테고리 또는 카테고리에 대한 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>수량 </p> </td> 
   <td colname="col2"> <p> 전환 이벤트에서 판매된 항목 수입니다. </p> <p> <i>변환 데이터 파일에만 사용합니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>수입 </p> </td> 
   <td colname="col2"> <p>구매 또는 기타 전환 금액. 데이터 유형: 부동 소수점 </p> <p> <i>변환 데이터 파일에만 사용합니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>기타 데이터 </p> </td> 
   <td colname="col2"> <p>전환 랜딩 페이지의 URL입니다. 데이터 유형: 문자열. </p> <p> <i>변환 데이터 파일에만 사용합니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Event-Type </p> </td> 
   <td colname="col2"> <p>전환 유형. 전환이 일치하는지 여부를 나타냅니다. 옵션은 다음과 같습니다. </p> 
    <ul id="ul_DA8230D167F241F2B53F29367874D4B1"> 
     <li id="li_2BC2EBCAE12541029A5F62AC0785E7FE"> <code> 0</code>: 노출 횟수 </li> 
     <li id="li_2A4B1354891144D587624228D8FB5E77"> <code> 1</code>: 클릭 </li> 
     <li id="li_44E61419DB56471EB2091072595D3E5C"> <code> -1</code>: 특성을 지정하지 않았거나 알 수 없습니다 </li> 
    </ul> <p> <i>변환 데이터 파일에만 사용합니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>버전 </p> </td> 
   <td colname="col2"> <p>노출, 클릭 또는 전환 데이터 파일에서 모든 행의 끝에 표시되는 필수 버전 번호입니다. 현재 버전은 1.1입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 데이터 파일에 대한 전달 방법 {#delivery-methods}

노출, 클릭 또는 변환 데이터 파일을 [!DNL Audience Manager] 계정의 Amazon S3 디렉터리로 업로드합니다. 배달/디렉터리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

>[!IMPORTANT]
>
> 데이터 파일에 대한 [!DNL Amazon S3] 디렉터리를 시작하고 설정하려면 Audience Manager 컨설턴트나 고객 지원에 문의하십시오.

**게재 경로 구문 및 예제**

데이터는 [!DNL Amazon S3] 디렉터리의 각 고객에 대해 별도의 네임스페이스에 저장됩니다. 파일 경로는 아래에 표시된 구문을 따릅니다. *기울임꼴*&#x200B;은(는) 변수 자리 표시자를 나타냅니다. 다른 요소는 상수 또는 키이며 변경되지 않습니다.

**구문:** <pre><code>.../log_ingestion/pid= <i>AAM ID</i>/dpid= <i>d_src</i>/logs/ <i>파일 유형</i>_<i>yyyymmdd</i></code></pre>

다음 표는 파일 전달 경로의 이러한 각 요소를 정의합니다.

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
   <td colname="col2"> <p>디렉토리 스토리지 경로의 시작입니다. 모든 것이 설정되면 전체 경로를 받게 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>이 키-값 쌍에 <span class="keyword"> Audience Manager</span> 고객 ID가 포함되어 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>이 키-값 쌍에는 이벤트 호출 시 전달된 데이터 소스 ID가 포함되어 있습니다. 데이터를 가져온 기관을 식별하고 해당 데이터를 지원 메타데이터 파일에 연결합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> logs</code> </p> </td> 
   <td colname="col2"> <p> 데이터 파일에 대한 상위 수준 디렉터리입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>file type</i>_<i>yyyymmdd</i></code> </p> </td> 
   <td colname="col2"> <p>포함된 데이터 유형과 게재 타임스탬프를 나타내는 파일 유형 이름입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

**샘플 업로드 경로 및 파일 이름**

파일을 업로드할 때 경로는 다음과 유사합니다.

`.../log_ingestion/pid=1234/dpid=567/logs/impressions_20150902`

**파일 처리 시간 및 업데이트**

데이터 파일은 하루에 네 번 일정한 간격으로 처리됩니다.

데이터를 업데이트하려면 특정 날짜의 모든 노출 횟수, 클릭 수 또는 변환 수가 포함된 파일을 보내십시오. 이 경우 하루는 자정부터 다음 시간까지 24시간 동안 지속됩니다. 가장 좋은 방법은 UTC 시간을 사용하여 일 간격을 정의하는 것입니다.

## 다음 단계 {#next-steps}

메타데이터 파일 이름 지정 및 생성에 대한 요구 사항을 검토합니다. 시작하려면 [메타데이터 파일에 대한 개요 및 매핑](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)을 참조하세요.
