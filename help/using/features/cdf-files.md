---
description: 고객 데이터 피드 (CDF) 파일 및 시작 방법에 대한 기본 정보입니다. CDF 파일을 받거나 더 많은 정보를 원한다면 여기에서 시작하십시오.
keywords: 제 2 자 데이터; 제 2 자; 제 2 자 데이터; 제 2 자
seo-description: 고객 데이터 피드 (CDF) 파일 및 시작 방법에 대한 기본 정보입니다. CDF 파일을 받거나 더 많은 정보를 원한다면 여기에서 시작하십시오.
seo-title: 고객 데이터 피드
solution: Audience Manager
title: 고객 데이터 피드
uuid: A 5 DE 1630-2 C 7 A -4862-9 BA 0-F 8343 CDD 2782
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feeds {#customer-data-feeds}

Basic information about [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) files and instructions on how to get started. Start here if you're interested in receiving [!UICONTROL CDF] files or just want more information.

## File Contents and Purpose {#file-contents-purpose}

<!-- cdf-intro.xml -->

[!UICONTROL CDF] 파일에는 [!DNL Audience Manager] 이벤트 호출 ( `/event`) 이 Adobe 서버로 보내는 동일한 데이터가 들어 있습니다. 여기에는 사용자 ID, 특성 ID, 세그먼트 ID 및 이벤트 호출에 의해 캡처된 기타 모든 매개 변수와 같은 데이터가 포함됩니다. Internal [!DNL Audience Manager] systems processes event data into a [!UICONTROL CDF] file with content organized into fields that appear in a set order. [!DNL Audience Manager] 시간별 [!UICONTROL CDF] 파일을 생성하여 [!DNL Amazon S3] 서버의 안전한 고객별 버킷에 저장합니다. We provide these files so you can work with [!DNL Audience Manager] data outside of the limits imposed by our user interface.

>[!NOTE]
>
>You should not use [!UICONTROL CDF] files as a proxy to monitor page traffic, reconcile report discrepancies, or for billing, etc.

## 시작하기 {#getting-started}

There is no self-service process to start [!UICONTROL CDF] file delivery. Contact your [!DNL Audience Manager] consultant or Customer Care to get started. During implementation, your [!DNL Audience Manager] representative will:

* [!DNL Amazon S3] 저장소 버킷을 설정합니다.
* Provide read-only [!DNL S3] authentication credentials to your file storage bucket. 다른 고객에게 속한 디렉토리와 파일을 보거나 액세스할 수 없습니다.

File notifications and [!UICONTROL CDF] files will appear in your [!DNL S3] bucket when they're ready for download. You're responsible for monitoring and downloading files from your assigned [!DNL S3] directory. [고객 데이터 피드 파일 처리 알림을 참조하십시오](#cdf-file-processing-notifications).

## 다음 단계 {#next-steps}

The sections below and the [Customer Data Feed FAQ](../faq/faq-cdf.md) can help you become more familiar with this service.

## Customer Data Feed Contents Defined {#cdf-defined}

Lists and defines the data elements and arrays in a [!UICONTROL CDF] file, by order of appearance. Definitions include data types, but this information is not part of a [!UICONTROL CDF] file.

## 정의 {#definitions}

<!-- cdf-contents-defined.xml -->

[!UICONTROL CDF] 파일에는 아래 정의된 필드 중 일부 또는 전체가 포함되어 있습니다. For information about internal file organization, see [Customer Data Feed File Structure](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 데이터 유형 </th> 
   <th colname="col3" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> 이벤트 시간</code> </p> </td> 
   <td colname="col2"> <p>timestamp </p> </td> 
   <td colname="col3"> <p>The time a CDF file was processed by the <span class="wintitle"> Data Collection Servers</span> (DCS). The timestamp uses the <i>yyyy-mm-dd hh:mm:ss</i> format and is set in the UTC time zone. </p> <p> <p>Note: The Event Time <i>is not</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">페이지 이벤트 또는 이벤트 호출 자체의 시간 (해당 시점에 가까울수 있음) </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">파일 이름의 DCS 시간과 관련이 있습니다. <a href="#different-processing-times"> 고객 데이터 피드 파일 이름 시간 및 파일 컨텐츠 시간도 참조하십시오.</a> </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 장치</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>This is the <span class="wintitle"> Unique User ID</span> (UUID), which is a 38-digit device ID for your site visitor. <a href="../reference/ids-in-aam.md">Audience Manager의 ID 색인</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 컨테이너 ID</code> </p> </td> 
   <td colname="col2"> <p>숫자 </p> </td> 
   <td colname="col3"> <p>ID 동기화를 실행하는 컨테이너의 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 구현된 특성</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>이벤트 호출에서 방문자가 실현한 모든 트레이트가 포함된 트레이트 ID 배열. </p> <p>이 배열에는 방문자가 이전에 자격을 가졌던 트레이트와 이 이벤트 호출을 통해 재자격이 있는 트레이트가 포함될 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 세그먼트 실현</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>이벤트 호출에서 방문자가 실현한 모든 세그먼트를 포함하는 세그먼트 ID 배열. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 요청 매개 변수</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>모든 매개 변수 (변수, ID, 키-값 쌍 등) 를 캡처하는 문자열 이벤트 호출에 전달됩니다. </p> <p>축약된 예: </p> <p> <code> d_ RTBD: json, c_ contextdata. a. carriername: mobile, c_ contextdata. a. adid: 92 d 56353-49 c 5-431 e-b 474-fc 528 d 585810, c_ contextdata. a, runmode: 응용 프로그램 c_ contextdata. a. dayssincelastupgrade: 61, d_ cid_ ic: XID % 01 Eacb 6 e 40-ac 65-4012-9 fe 9-abd 59965 e 9 c 4% 011, c_ contextdata. a. prevsessionlength: 583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer 데이터 유형</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>참조 페이지의 인코딩되지 않은 URL (있는 경우). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP 데이터 유형</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>이벤트 호출에서 캡처한 방문자의 IP 주소. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Mcdevice </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Experience Cloud</span> ID (MID) assigned to the site visitor. <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 쿠키 및 TheExperience Cloud ID 서비스를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 모든 세그먼트</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>이전에 구현된 세그먼트와 방문자의 자격이 있는 새 세그먼트가 포함된 세그먼트 ID 배열입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> 모든 트레이트</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>이전에 생성된 트레이트 및 방문자가 마지막으로 생성된 데이터 피드 이후 자격을 갖춘 새로운 트레이트가 포함된 타사 특성 및 타사 특성. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Structure {#cdf-file-structure}

Lists and defines the data structure of a [!UICONTROL CDF] file. 여기에는 데이터 시퀀스, 필드 구분 기호 및 구분 기호, 데이터 파일 맵 및 샘플 파일이 포함됩니다.

## Data Field Identifiers and Sequence {#identifiers-and-sequence}

<!-- cdf-file-structure.xml -->

[!UICONTROL CDF] 파일에 레이블이 지정된 열 또는 필드 헤더가 없습니다. Instead, a [!UICONTROL CDF] file defines fields and arrays with non-printing [!DNL ASCII] characters. [!UICONTROL CDF] 또한 파일은 각 필드와 배열을 특정 순서로 나열합니다. 필드 식별자 및 순서를 이해하면 파일을 제대로 분석하는 데 도움이 됩니다.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF 파일 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>필드 구분 기호 및 구분 기호 </p> </td> 
   <td colname="col2"> <p>이러한 인쇄되지 않는 문자는 CDF 파일의 요소 및 구조를 정의합니다. </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII <code> 001</code> or <code> ^A</code>) separates data in individual fields with a non-printing space indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII <code> 002</code> or <code> ^B</code>) separates data an array and request parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII <code> 003</code> or <code> ^C</code>) defines key-value pairs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>필드 시퀀스 </p> </td> 
   <td colname="col2"> <p> <p>Important: <span class="keyword"> Audience Manager</span> reserves the right to add new fields to the end of the CDF file in future releases. 즉, 파일 구문 분석 시스템의 기술 디자인은 고정된 수의 열을 간주해서는 안 됩니다 (기존 열에 대한 고정 순서가 있을 수 있음). </p> </p> <p>CDF 파일의 데이터는 아래 표시된 순서대로 표시됩니다. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">이벤트 시간 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">장치 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">컨테이너 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">구현된 특성 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">세그먼트 실현 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">요청 매개 변수 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 주소 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud 장치 ID (또는 MID). <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> 쿠키 및 Experience Cloud ID 서비스 참조</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">모든 세그먼트 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">모든 트레이트 </li> 
     </ol> </p> <p>For field descriptions, see <a href="#cdf-defined"> Customer Data Feed Contents Defined</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## CDF File Map {#cdf-file-map}

[!UICONTROL CDF] 파일 데이터는 아래 표시된 순서대로 표시됩니다.

![](assets/sequence-map.png)

## 배열 식별

Arrays in a [!UICONTROL CDF] file start and end with the `Ctrl + a` field separator. 이렇게 하면 배열의 첫 번째 요소가 독립 실행형 데이터 필드와 같이 나타납니다. For example, the realized traits array starts with `^A1234`. The array delimiter and ID `^B5678` follows this entry. As a result, you might be tempted to think that the first element in the realized traits array is ID 5678 (because it starts with `^B`). 이것은 사실이 아닙니다. 따라서 데이터 파일의 순서와 구조에 익숙해야 합니다. Even though the first element in the realized trait array (or any of the other arrays in a [!UICONTROL CDF] file) starts with `^A`, the order of appearance or position in the file defines the start of an array. And, the first element in an array is always separated from the preceding entry by `^A`.

## Sample CDF File {#sample-file}

A sample [!UICONTROL CDF] file could look similar to the following. 이 예에서는 페이지에 맞게 줄이 줄바꿈되었습니다.

![](assets/CDF-sample.png)

## Customer Data Feed File Naming Conventions {#cdf-naming-conventions}

The sections below list and define the elements in your [!UICONTROL CDF] file name.

## CDF File Name: Syntax and Example {#cdf-file-name}

<!-- cdf-file-name.xml -->

A typical [!UICONTROL CDF] file name contains the elements listed below. Note, *italics* indicates a variable placeholder:

* **구문**

<pre><code>S 3: //aam-cdf/your<i>s 3 버킷 이름</i>/day =<i>yyyy-mm-dd</i>/hour =<i>hh</i>/<i>aam_ cdf_ 파트너 ID_ AAM 프로세스 ID</i>_0.gz</code>
</pre>

* **예**

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

[!DNL S3] 저장소 버킷에서 파일은 파트너 ID ([!UICONTROL PID]), 일 및 시간에 따라 오름차순으로 정렬됩니다.

## CDF File Name Elements Defined {#cdf-file-name-elements}

The following table lists and defines the elements in a [!UICONTROL CDF] file name.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 이름 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> S 3: //aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>이것은 Amazon S 3 서버에서 CDF 파일의 기본 루트 저장소 버킷입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>S 3 버킷 이름</i></code> </p> </td> 
   <td colname="col2"> <p>CDF 파일이 들어 있는 읽기 전용, S 3 버킷의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day =<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>파일이 처리된 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour =<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>24 시간 표기법으로 표현된 시간 값으로 UTC 표준 시간대에서 설정됩니다. <a href="#different-processing-times"> 고객 데이터 피드 파일 이름 시간 및 파일 컨텐츠 시간도 참조하십시오.</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>파트너 ID</i></code> </p> </td> 
   <td colname="col2"> <p>파트너 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>AAM 프로세스 ID</i>_ 0</code> </p> </td> 
   <td colname="col2"> <p>An internal, <span class="keyword"> Audience Manager</span> process ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>GZIP 파일 확장자. CDF 파일은 GZIP 압축됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Processing Notifications {#cdf-file-processing-notifications}

[!DNL Audience Manager] 디렉토리에 `.info` 파일을 [!DNL S3] 작성하여 [!UICONTROL Customer Data File] ([!UICONTROL CDF]) 를 다운로드 준비가 되었을 때 알 수 있도록 합니다. The `.info` file also includes [!DNL JSON] formatted metadata about the contents of your [!UICONTROL CDF] files. 이 알림 파일에서 사용하는 구문 및 필드에 대한 자세한 내용은 이 섹션을 검토하십시오.

## Sample Info File {#sample-info-file}

<!-- cdf-notifications.xml -->

Each `.info` file contains a `Files` and `Totals` section. `Files` 섹션에는 시간별 파일에 대한 특정 지표를 보유하는 배열이 포함되어 있습니다. `Totals` 섹션에는 특정 날짜에 대한 [!UICONTROL CDF] 모든 파일에 대해 집계된 지표가 포함됩니다. `.info` 파일의 내용은 다음 예와 비슷합니다.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Info File Fields Defined {#info-file-fields-defined}

The following tables list and define the elements in a [!UICONTROL CDF] `.info` file.

### 파일 객체

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 파일</code> </p> </td> 
   <td colname="col2"> <p>CDF 파일에 대한 메타데이터가 포함된 배열을 시작합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>파일 크기 (바이트). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S 3 ETAG. 하이픈 다음에 오는 숫자는 다중 부분 업로드를 하는 동안 파일을 빌드하는 데 사용된 부분의 수를 보여줍니다. <code> ETAG</code> 는 파일의 MD 5 체크섬과 동일하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 파일 이름</code> </p> </td> 
   <td colname="col2"> <p>파일 이름입니다. <a href="#cdf-naming-conventions"> 고객 데이터 피드 파일 이름 지정 규칙을 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filesequencenumber</code> </p> </td> 
   <td colname="col2"> <p>각 파일의 인덱스 번호입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 합계 개체

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> 총계</code> </p> </td> 
   <td colname="col2"> <p>모든 CDF 파일에 대한 집계 데이터가 들어 있는 개체를 시작합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 일</code> </p> </td> 
   <td colname="col2"> <p>데이터를 사용할 수 있는 날. <i>YYYY-MM-DD</i> 형식을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 시간</code> </p> </td> 
   <td colname="col2"> <p>데이터를 사용할 수 있는 시간입니다. UTC 표준 시간대에서 24 시간 형식을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>해당 날짜에 대한 모든 CDF 파일의 총 크기 (바이트) 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>S 3 디렉토리에 업로드된 총 파일 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customer Data Feed File Name Times and File Content Times are Different {#different-processing-times}

Your [!UICONTROL CDF] file contains timestamps in the file name and file contents. These timestamps record different event processes for the same [!UICONTROL CDF] file. 동일한 파일의 이름과 콘텐트에서 다른 타임스탬프를 보는 것은 드문 일이 아닙니다. 각 타임스탬프를 이해하면 이 데이터를 사용하여 작업하거나 시간 기준으로 정렬할 때 일반적인 실수를 방지할 수 있습니다.

## Locating CDF File Timestamps {#locating-timestamps}

<!-- cdf-time-differences.xml -->

[!UICONTROL CDF] 파일의 경우 2 개의 위치에서 시간이 다르게 기록됩니다.

![](assets/cdf-timestamp.png)

## Understanding the Difference Between Timestamps {#understanding-timestamps}

The following table provides additional details about your [!UICONTROL CDF] file timestamps along with information about how to use them properly.

| 타임스탬프 위치 | 설명 |
|--- |--- |
| 파일 이름 | The timestamp in your CDF file name marks the time when [!DNL Audience Manager] started preparing your file for delivery. 이 타임스탬프는 UTC 표준 시간대에서 설정됩니다. It uses the `hour=` parameter, with time formatted as a 2-digit hour in 24-hour notation. 이 시간은 파일 컨텐츠에 기록된 이벤트 시간과 다를 수 있습니다. Breakwhen working with CDF files, sometimes that your S 3 bucket is empty for a specific hour. 빈 버킷은 다음 중 하나를 의미할 수 있습니다.<ul><li>특정 시간에 대한 데이터가 없습니다. </li><li> 우리 서버는 부하가 너무 많아서 특정 시간에 파일을 처리할 수 없습니다. 서버가 캐치되면 이전 시간 버킷 파일에 갔어야 하는 파일이 차후 시간 값이 있는 버킷에 저장됩니다. For example, you'll see this when a file that should have been in the hour 17 bucket appear in the hour 18 bucket (with `hour=18` in the file name). 이 경우 서버는 17 시간 내에 파일 처리를 시작했지만 해당 시간 간격 내에 파일을 완료할 수 없었습니다. 대신, 파일이 다음 시간별 시간 버킷으로 푸시됩니다.</li></ul><br>**중요**: 시간별 이벤트를 그룹화하려면 파일 이름 타임스탬프를 사용하지 마십시오. If you need to group by time, use the `EventTime` timestamp in the file contents. |
| 파일 컨텐츠 | CDF 파일 내용의 타임스탬프는 데이터 수집 서버가 파일 처리를 시작한 시간을 나타냅니다. 이 타임스탬프는 UTC 표준 시간대에서 설정됩니다. It uses the `EventTime` field, with time formatted as *`yyyy-mm-dd hh:mm:ss`*. This time is close to the actual time of the event on the page, but it can be different than the hour indicator in the file name. <br> **팁**: 파일 이름의 `hour=` 타임스탬프와 달리 시간별 데이터를 `EventTime` 그룹화하는 데 사용할 수 있습니다. |

>[!MORE_ like_ this]
>
>* [고객 데이터 피드 FAQ](../faq/faq-cdf.md)

