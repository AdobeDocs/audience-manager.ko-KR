---
description: S3 상태 디렉토리에는 업로드된 파일에 대한 성공 및 실패 정보가 포함된 .info 파일이 있습니다. 이 파일에는 JSON 형식의 데이터가 포함되어 있으며 상태 결과는 배열에 있습니다.
seo-description: S3 상태 디렉토리에는 업로드된 파일에 대한 성공 및 실패 정보가 포함된 .info 파일이 있습니다. 이 파일에는 JSON 형식의 데이터가 포함되어 있으며 상태 결과는 배열에 있습니다.
seo-title: 메타데이터 파일에 대한 상태 업데이트
solution: Audience Manager
title: 메타데이터 파일에 대한 상태 업데이트
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: log files
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%

---


# 메타데이터 파일에 대한 상태 업데이트{#status-updates-for-metadata-files}

S3 상태 디렉토리에는 업로드된 파일에 대한 성공 및 실패 정보가 포함된 `.info` 파일이 저장됩니다. 이 파일에는 JSON 형식의 데이터가 포함되어 있으며 상태 결과는 배열에 있습니다.

파일의 내용은 이 `.info` 예제와 비슷합니다.

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## 정의된 메타데이터 키-값 쌍 {#key-value-pairs}

다음 표 목록을 작성하고 메타데이터 상태 파일의 `Files` 및 섹션 `Summary` 에서 키를 정의합니다.

**파일 배열의 키**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>처리가 실패한 이유에 대한 간단한 설명을 포함합니다. 처리가 성공하면 이 필드는 비어 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>파일 크기(바이트)입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>디렉터리에 업로드된 메타데이터 파일의 MD 5 체크섬 <code> meta</code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>디렉토리에 업로드된 메타데이터 파일의 <code> meta</code> 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>파일에 포함된 데이터 유형에 대해 읽을 수 있는 이름입니다. 파일 이름의 자식 ID를 기반으로 합니다. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>파일에 포함된 데이터 유형에 대해 읽을 수 있는 이름입니다. 파일 이름의 상위 ID를 기반으로 합니다. </p> <p>See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>메타데이터 파일의 처리 상태를 설명하는 2개의 텍스트 값을 반환합니다. </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**요약 개체의 키**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>파일 처리 날짜 형식을 <code><i>yyyy-mm-dd</i></code> 지정합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>하루 동안 모든 파일의 처리 상태를 설명하는 2개의 텍스트 값을 반환합니다. </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>처리되지 못한 파일 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>처리된 파일 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>처리 시작 시간에 대해 사람이 읽을 수 있는 타임스탬프를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>처리 시작 시간을 위한 UNIX 타임스탬프 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>하루 동안의 모든 메타데이터 파일에 대한 총 바이트 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>하루 동안 처리된 모든 파일의 총 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>