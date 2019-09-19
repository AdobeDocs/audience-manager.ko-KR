---
description: Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-title: 메타데이터 파일에 대한 배달 방법
solution: Audience Manager
title: 메타데이터 파일에 대한 배달 방법
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 메타데이터 파일에 대한 배달 방법{#delivery-methods-for-metadata-files}

Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

## 배달 경로 구문 및 예 {#syntax}

데이터는 Amazon S3 디렉토리에 각 고객에 대한 별도의 네임스페이스에 저장됩니다. 파일 경로는 아래에 표시된 구문을 따릅니다. Note, *italics* indicates a variable placeholder. Brackets `[ ]` 는 선택적 매개 변수를 나타냅니다. 다른 요소는 상수이며 변경되지 않습니다.

**구문:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/ meta|status]/ <i>yyyyyyyyyyyymmdd</i>__ <i></i><i>PARENT_ID</i></code></pre>

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
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> is a file upload/storage directory. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> 는 처리된 파일에 대한 성공 또는 실패 정보를 포함하는 디렉토리의 경로입니다. 파일이 처리되면 yyyyymmdd 타임스탬프 제목이 있는 <code> .info</code> 파일이 <code></code> 표시됩니다. 상태 파일에는 JSON 개체에 데이터가 포함되어 있습니다. 메타데이터 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> 파일에 대한 상태 업데이트를 참조하십시오</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyyyymmdd</i>_<i>parent ID</i>_<i>자식 ID</i></code> </p> </td> 
   <td colname="col2"> <p>파일 이름입니다. 메타데이터 파일에 <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> 대한 이름 지정 규칙을 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**샘플 업로드 및 상태 경로**

메타데이터 파일을 업로드하거나 해당 상태를 [](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md)확인하려면 파일 경로가 다음과 유사하게 표시됩니다.

* 업로드 경로: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* 처리 상태 경로: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`Adobe

## 파일 처리 시간 및 업데이트 {#processing-times}

메타데이터 파일은 정기적으로 하루에 4번 처리됩니다.

메타데이터 레코드를 업데이트하려면 새 정보가 포함된 파일을 보내기만 하면 됩니다. 매번 전체 업데이트를 전송할 필요가 없습니다.
