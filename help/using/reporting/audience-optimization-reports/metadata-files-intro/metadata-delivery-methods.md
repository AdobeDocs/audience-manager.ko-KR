---
description: Audience Manager 계정에 대해 특별한 Amazon S 3 디렉토리로 보내 메타데이터 파일을 보내거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: Audience Manager 계정에 대해 특별한 Amazon S 3 디렉토리로 보내 메타데이터 파일을 보내거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-title: 메타데이터 파일의 배달 방법
solution: Audience Manager
title: 메타데이터 파일의 배달 방법
uuid: 5199 EE 9 B -920 D -423 D -8070-05 A 017 ECD 562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

Audience Manager 계정에 대해 특별한 Amazon S 3 디렉토리로 보내 메타데이터 파일을 보내거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

## Delivery Path Syntax and Examples {#syntax}

데이터는 Amazon S 3 디렉토리의 각 고객에 대해 별도의 네임스페이스에 저장됩니다. 파일 경로는 아래 표시된 구문을 따릅니다. *기울임꼴은* 변수 자리 표시자를 나타냅니다. Brackets `[ ]` indicate optional parameters. 다른 요소는 상수이며 변경되지 않습니다.

**구문:**
<pre><code>.../log_ ingenting/pid =<i>aam id</i>/dpid = <i>d_ src</i>/[meta | status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

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
   <td colname="col2"> <p>이 키-값 쌍은 이벤트 호출에서 전달된 데이터 소스 ID를 포함합니다. 데이터 소스 ID는 파일의 모든 컨텐츠를 실제 데이터에 연결하는 값입니다. </p> <p>예를 들어 ID 123와 이름이 "광고주 크리에이티브 A" 인 크리에이티브가 있다고 가정해 보십시오. 이벤트 호출은 ID를 메타데이터 파일에 포함시켜야 하는 ID만 전달합니다. 캠페인과 크리에이티브는 데이터 소스에 속합니다. 데이터 소스 ID는 이러한 둘을 연결하는 것으로서, 이벤트 호출에서 전송된 ID에 파일 컨텐츠를 정확하게 연결할 수 있도록 해줍니다. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> META</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> 메타</code> 파일 업로드/저장 디렉토리입니다. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> 상태는</code> 처리된 파일에 대한 성공 또는 실패 정보를 보유하는 디렉토리 경로입니다. After your file is processed, you'll see a <code> .info</code> file with <code> yyyymmdd</code> timestamp title. 상태 파일에는 JSON 개체의 데이터가 포함되어 있습니다. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Status Updates for Metadata Files</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>yyyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>파일 이름입니다. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**업로드 및 상태 경로 샘플**

To upload a metadata file or to [check its status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), the file paths will look similar to these:

* Upload path: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Processing status path: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## File Processing Times and Updates {#processing-times}

메타데이터 파일은 하루에 4 회 정기적으로 처리됩니다.

메타데이터 레코드를 업데이트하려면 새 정보가 들어 있는 파일을 전송하기만 하면 됩니다. 매번 전체 업데이트를 전송할 필요는 없습니다.
