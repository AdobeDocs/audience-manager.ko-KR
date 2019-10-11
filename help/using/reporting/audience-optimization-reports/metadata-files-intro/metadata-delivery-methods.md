---
description: Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-title: 메타데이터 파일에 대한 배달 방법
solution: Audience Manager
title: 메타데이터 파일에 대한 배달 방법
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 1ff46970470eae4bc30760468013d994c976e549

---


# 메타데이터 파일에 대한 배달 방법{#delivery-methods-for-metadata-files}

Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

## 배달 경로 구문 및 예 {#syntax}

데이터는 Amazon S3 디렉토리에 각 고객에 대한 별도의 네임스페이스에 저장됩니다. 파일 경로는 아래에 표시된 구문을 따릅니다. Note, *italics* indicates a variable placeholder. Brackets `[ ]` 는 선택적 매개 변수를 나타냅니다. 다른 요소는 상수이며 변경되지 않습니다.

**구문:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

다음 표에서는 파일 배달 경로에서 이러한 각 요소를 정의합니다.

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
   <td colname="col2"> <p>디렉토리 저장소 경로의 시작입니다. 모든 것이 설정되면 전체 경로를 받게 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>Audience Manager 고객 ID가 포함된 <span class="keyword"> 이</span> 키-값 쌍입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>이 키-값 쌍은 이벤트 호출에 전달된 데이터 소스 ID를 포함합니다. 데이터 소스 ID는 파일에 있는 모든 내용을 해당 파일이 속하는 실제 데이터에 연결하는 값입니다. </p> <p>예를 들어 ID 123과 이름이 "광고주 크리에이티브 A"인 크리에이티브가 있다고 가정해 봅시다. 이벤트 호출이 ID에서만 전달되므로 메타데이터 파일에 "광고주 Creative A"를 포함해야 합니다. 캠페인과 크리에이티브는 데이터 소스에 속합니다. 데이터 소스 ID는 이러한 ID를 함께 연결하여 이벤트 호출 시 전송된 ID에 파일 컨텐츠를 정확하게 연결할 수 있도록 해줍니다. 이벤트 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> 호출 ID가 파일 이름, 콘텐츠 및 배달 경로를</a>결정하는 방법을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>파일 이름입니다. 메타데이터 파일에 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> 대한 이름 지정 규칙을 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 파일 처리 시간 및 업데이트 {#processing-times}

메타데이터 파일은 정기적으로 하루에 4번 처리됩니다.

메타데이터 레코드를 업데이트하려면 새 정보가 포함된 파일을 보내기만 하면 됩니다. 매번 전체 업데이트를 전송할 필요가 없습니다.
