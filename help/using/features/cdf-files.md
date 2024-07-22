---
description: 고객 데이터 피드(CDF) 파일에 대한 기본 정보와 시작 방법에 대한 지침입니다. CDF 파일 수신에 관심이 있거나 더 많은 정보를 원하는 경우 여기에서 시작하십시오.
keywords: 제2자 데이터;제2자;제2자 데이터;제2자
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: 고객 데이터 피드
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1988'
ht-degree: 2%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

[!UICONTROL Customer Data Feed]([!UICONTROL CDF]) 파일에 대한 기본 정보 및 시작 방법에 대한 지침입니다. [!UICONTROL CDF]개의 파일을 받거나 자세한 정보를 보려면 여기에서 시작하십시오.

## 파일 내용 및 목적 {#file-contents-purpose}

[!UICONTROL CDF] 파일에 [!DNL Audience Manager] 이벤트 호출(`/event`)이 서버에 보내는 것과 동일한 데이터가 포함되어 있습니다. 여기에는 사용자 ID, [!UICONTROL trait IDs], [!UICONTROL segment IDs] 및 이벤트 호출로 캡처된 기타 모든 매개 변수 등의 데이터가 포함됩니다. 내부 [!DNL Audience Manager] 시스템은 정해진 순서로 표시되는 필드로 구성된 컨텐츠가 있는 [!UICONTROL CDF] 파일로 이벤트 데이터를 처리합니다. [!DNL Audience Manager]이(가) 매시간 [!UICONTROL CDF]개의 파일을 생성하여 [!DNL Amazon S3] 서버의 안전한 고객별 버킷에 저장하려고 합니다. 사용자 인터페이스에 지정된 제한을 벗어나는 [!DNL Audience Manager] 데이터로 작업할 수 있도록 이러한 파일을 제공합니다.

>[!IMPORTANT]
>
>CDF 파일을 사용할 때는 다음 제한 사항에 유의하십시오.
>
>* CDF 파일 전달을 설정하기 전에 타사 데이터 공급자의 타사 트레이트 내보내기에 대한 적절한 권한이 있는지 확인하십시오. Audience Manager은 현재 서드파티 데이터 공급자로부터 CDF 파일 게재 내보내기 권한을 요청하는 기능을 사용자 인터페이스에서 지원하지 않으므로 독립적으로 문의하십시오.
>* [!UICONTROL CDF] 파일을 프록시로 사용하여 페이지 트래픽을 모니터링하거나, 보고서 불일치를 조정하거나, 청구 등을 처리해서는 안 됩니다.

## 시작하기 {#getting-started}

[!UICONTROL CDF] 파일 배달을 시작하는 셀프 서비스 프로세스가 없습니다. 시작하려면 [!DNL Audience Manager] 컨설턴트나 고객 지원에 문의하십시오. 구현 중에 [!DNL Audience Manager] 담당자는 다음을 수행합니다.

* [!DNL Amazon S3] 저장소 버킷을 설정합니다.
* 파일 저장소 버킷에 읽기 전용 [!DNL S3] 인증 자격 증명을 제공하십시오. 다른 고객에 속한 디렉토리와 파일은 보거나 액세스할 수 없습니다.

파일 알림 및 [!UICONTROL CDF] 파일은 다운로드할 준비가 되면 [!DNL S3] 버킷에 표시됩니다. 할당된 [!DNL S3] 디렉터리에서 파일을 모니터링하고 다운로드해야 합니다. [고객 데이터 피드 파일 처리 알림](#cdf-file-processing-notifications)을 참조하십시오.

## 다음 단계 {#next-steps}

아래 섹션 및 [고객 데이터 피드 FAQ](../faq/faq-cdf.md)를 통해 이 서비스에 더 익숙해질 수 있습니다.

## [!UICONTROL Customer Data Feed]개 콘텐츠 정의됨 {#cdf-defined}

[!UICONTROL CDF] 파일에 있는 데이터 요소와 배열을 표시 순서에 따라 나열하고 정의합니다. 정의에 데이터 형식이 포함되어 있지만 이 정보는 [!UICONTROL CDF] 파일에 포함되지 않습니다.

>[!IMPORTANT]
>
>CDF 구성에서는 기본적으로 이벤트 픽셀이 제외됩니다. 이벤트 픽셀을 CDF 파일에 포함하려면 클라이언트 관리에 요청에서 를 지정해야 합니다. 각 이벤트 픽셀은 CDF 파일에서 고유한 행으로 채워집니다.

## 정의 {#definitions}

[!UICONTROL CDF] 파일에 아래에 정의된 일부 또는 모든 필드가 포함되어 있습니다. 내부 파일 조직에 대한 자세한 내용은 [고객 데이터 피드 파일 구조](#cdf-file-structure)를 참조하십시오.

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
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>타임스탬프 </p> </td> 
   <td colname="col3"> <p>CDF 파일이 <span class="wintitle"> 데이터 수집 서버</span>(DCS)에서 처리된 시간입니다. 타임스탬프는 <i>yyyy-mm-dd hh:mm:ss</i> 형식을 사용하며 UTC 시간대로 설정됩니다. </p> <p> <p>참고: 이벤트 시간 <i>은(는) </i>이(가) 아닙니다. <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">페이지 이벤트 또는 이벤트 호출 시간이 해당 시간에 가까울 수 있지만 해당 시간 자체입니다. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">파일 이름의 DCS 시간과 관련되어 있습니다. <a href="#different-processing-times"> 고객 데이터 피드 파일 이름 시간 및 파일 내용 시간...</a>도 참조하세요. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>사이트 방문자의 38자리 장치 ID인 <span class="wintitle"> UUID(고유 사용자 ID</span>)입니다. </a> Audience Manager의 <a href="../reference/ids-in-aam.md"> ID 색인도 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>숫자 </p> </td> 
   <td colname="col3"> <p>ID 동기화를 실행하는 컨테이너의 ID입니다. 이 필드는 사이트 구현의 <i>d_nsid</i> 필드에 컨테이너 ID를 설정한 경우에만 채웁니다. 그렇지 않으면 기본값 0이 CDF 파일에 포함되지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>방문자가 이벤트 호출에서 실현(적격)한 모든 트레이트를 포함하는 트레이트 ID의 배열입니다. </p> <p>이 배열에는 방문자가 이전에 자격을 부여받은 트레이트와 이 이벤트 호출을 통해 자격을 다시 부여받은 트레이트가 포함될 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>방문자가 이벤트 호출에서 실현(적격)한 모든 세그먼트를 포함하는 세그먼트 ID 배열입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>모든 매개 변수(변수, ID, 키-값 쌍, 장치 광고 ID 등)를 캡처하는 문자열 이벤트 호출 시 전달되었습니다. </p> <p>축약된 예: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>참조 페이지의 인코딩이 해제된 URL(있는 경우)입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>이벤트 호출에서 캡처된 방문자의 IP 주소입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>사이트 방문자에게 할당된 <span class="keyword"> Experience Cloud</span> ID(MID)입니다. <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Adobe Experience Platform ID 서비스</a>도 참조하세요. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>방문자가 자격을 갖는 이전에 실현된 세그먼트 및 새 세그먼트를 포함하는 세그먼트 ID 배열입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>마지막으로 생성된 데이터 피드 이후 방문자가 자격을 부여한 이전에 실현된 트레이트 및 새 트레이트를 포함하는 자사 및 서드파티 트레이트 ID의 배열입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 파일 구조 {#cdf-file-structure}

[!UICONTROL CDF] 파일의 데이터 구조를 나열하고 정의합니다. 여기에는 데이터 시퀀스, 필드 구분 기호 및 구분 기호, 데이터 파일 맵 및 샘플 파일이 포함됩니다.

## 데이터 필드 식별자 및 시퀀스 {#identifiers-and-sequence}

[!UICONTROL CDF]개 파일에 레이블이 지정된 열 또는 필드 헤더가 없습니다. 대신 [!UICONTROL CDF] 파일은 인쇄되지 않는 [!DNL ASCII]자의 필드 및 배열을 정의합니다. 또한 [!UICONTROL CDF] 파일은 각 필드와 배열을 특정 순서로 나열합니다. 필드 식별자 및 순서를 이해하면 파일을 올바르게 구문 분석하는 데 도움이 됩니다.

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
   <td colname="col2"> <p>인쇄되지 않는 이러한 문자는 CDF 파일의 요소 및 구조를 정의합니다. </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a(ASCII <code> 001</code> 또는 <code> ^A</code>)는 인쇄되지 않는 공간 표시기로 개별 필드의 데이터를 구분합니다. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl+b(ASCII <code> 002</code> 또는 <code> ^B</code>)는 데이터와 요청 매개 변수를 구분합니다. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c(ASCII <code> 003</code> 또는 <code> ^C</code>)는 키-값 쌍을 정의합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>필드 시퀀스 </p> </td> 
   <td colname="col2"> <p> <p>중요: <span class="keyword"> Audience Manager</span>은(는) 향후 릴리스에서 CDF 파일의 끝에 새 필드를 추가할 수 있는 권한을 보유합니다. 즉, 파일 구문 분석 시스템의 기술 설계에서 고정된 수의 열을 가정해서는 안 됩니다(기존 열의 순서가 고정되어 있을 수도 있음).</p> </p> <p>CDF 파일의 데이터는 아래에 표시된 순서로 표시됩니다. 이러한 필드 대신 /N이 표시되어 null 값을 나타낼 수 있습니다.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">이벤트 시간 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">장치 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">컨테이너 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">실현된 트레이트 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">실현된 세그먼트 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">요청 매개 변수 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 주소 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud 장치 ID(또는 MID). <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Adobe Experience Platform Identity 서비스</a>도 참조하세요. </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">모든 세그먼트 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">모든 트레이트 </li> 
     </ol> </p> <p>필드 설명은 정의된 <a href="#cdf-defined"> 고객 데이터 피드 콘텐츠</a>를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] 파일 맵 {#cdf-file-map}

[!UICONTROL CDF] 파일 데이터가 아래 표시된 순서로 나타납니다.

![](assets/sequence-map.png)

## 배열 식별

[!UICONTROL CDF] 파일의 배열은 `Ctrl + a` 필드 구분 기호로 시작하고 끝납니다. 이렇게 하면 배열의 첫 번째 요소가 독립 실행형 데이터 필드처럼 표시됩니다. 예를 들어 실현된 [!UICONTROL traits] 배열은 `^A1234`(으)로 시작합니다. 배열 구분 기호 및 ID `^B5678`이(가) 이 항목 뒤에 옵니다. 따라서 실현된 [!UICONTROL traits] 배열의 첫 번째 요소가 ID 5678이라고 생각하게 됩니다(`^B`(으)로 시작됨). 그렇지 않으므로 데이터 파일의 시퀀스 및 구조에 익숙해야 합니다. 실현된 [!UICONTROL trait] 배열(또는 [!UICONTROL CDF] 파일의 다른 배열)의 첫 번째 요소는 `^A`(으)로 시작되지만 파일의 모양 또는 위치 순서는 배열의 시작을 정의합니다. 그리고 배열의 첫 번째 요소는 항상 `^A`만큼 이전 항목에서 분리됩니다.

## 샘플 [!UICONTROL CDF] 파일 {#sample-file}

샘플 [!UICONTROL CDF] 파일은 다음과 비슷합니다. 페이지에 맞게 하기 위해 이 예제에 줄바꿈을 삽입했습니다.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] 파일 이름 지정 규칙 {#cdf-naming-conventions}

아래 섹션에 [!UICONTROL CDF] 파일 이름의 요소를 나열하고 정의합니다.

## [!UICONTROL CDF] 파일 이름: 구문 및 예제 {#cdf-file-name}

일반적인 [!UICONTROL CDF] 파일 이름에는 아래 나열된 요소가 포함되어 있습니다. *기울임꼴*&#x200B;은(는) 변수 자리 표시자를 나타냅니다.

### 구문

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### 예

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

[!DNL S3] 저장소 버킷에서 파일은 파트너 ID([!UICONTROL PID]), 일 및 시간별로 오름차순으로 정렬됩니다.

## [!UICONTROL CDF]개의 파일 이름 요소가 정의됨 {#cdf-file-name-elements}

다음 표는 [!UICONTROL CDF] 파일 이름의 요소를 나열하고 정의합니다.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 이름 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 서버에서 CDF 파일의 기본 루트 스토리지 버킷입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>CDF 파일을 저장하는 읽기 전용 S3 버킷의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>파일이 처리된 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>24시간 표기법으로 표현되고 UTC 시간대로 설정된 시간 값입니다. <a href="#different-processing-times"> 고객 데이터 피드 파일 이름 시간 및 파일 내용 시간...</a>도 참조하세요. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>파트너 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>파일 시퀀스를 식별하는 값입니다. 순서는 0_0_0 , 0_1_0, 0_2_0....1_0_0과 같이 증가합니다.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip 파일 확장명. CDF 파일은 gzip으로 압축됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed]개의 파일 처리 알림 {#cdf-file-processing-notifications}

[!DNL Audience Manager]이(가) [!UICONTROL Customer Data File]([!UICONTROL CDF])을(를) 다운로드할 준비가 되면 알리기 위해 [!DNL S3] 디렉터리에 `.info` 파일을 씁니다. `.info` 파일에는 [!UICONTROL CDF] 파일의 내용에 대한 [!DNL JSON] 형식의 메타데이터도 포함되어 있습니다. 이 알림 파일에서 사용하는 구문과 필드에 대한 정보는 이 섹션을 검토하십시오.

## 샘플 정보 파일 {#sample-info-file}

각 `.info` 파일에는 `Files` 및 `Totals` 섹션이 있습니다. `Files` 섹션에는 각 시간별 파일에 대한 특정 지표를 포함하는 배열이 포함되어 있습니다. `Totals` 섹션에는 특정 날짜의 모든 [!UICONTROL CDF] 파일에서 집계된 지표가 포함되어 있습니다. `.info` 파일의 내용은 다음 예제와 비슷합니다.

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

## 정의된 정보 파일 필드 {#info-file-fields-defined}

다음 표는 [!UICONTROL CDF] `.info` 파일의 요소를 나열하고 정의합니다.

### Files 개체

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>CDF 파일에 대한 메타데이터가 포함된 배열을 시작합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>파일 크기(바이트)입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 ETag. 하이픈 다음에 나오는 숫자는 다중 부분 업로드 중에 파일을 작성하는 데 사용된 부분 수를 보여줍니다. <code> ETag</code>이(가) 파일의 MD5 체크섬과 동일하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>파일 이름입니다. <a href="#cdf-naming-conventions"> 고객 데이터 피드 파일 이름 지정 규칙</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>각 파일에 대한 색인 번호입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Totals 객체

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>모든 CDF 파일에 대한 집계된 데이터가 포함된 객체를 시작합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>데이터를 사용할 수 있는 날짜입니다. <i>yyyy-mm-dd</i> 형식을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>데이터를 사용할 수 있는 시간입니다. UTC 시간대로 설정된 24시간 형식을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>해당 날짜에 대한 모든 CDF 파일의 총 크기(바이트)입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>S3 디렉토리에 업로드된 총 파일 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 파일 이름 시간과 파일 내용 시간이 다릅니다. {#different-processing-times}

[!UICONTROL CDF] 파일에 파일 이름과 파일 내용에 타임스탬프가 있습니다. 이 타임스탬프는 동일한 [!UICONTROL CDF] 파일에 대해 다른 이벤트 프로세스를 기록합니다. 동일한 파일의 이름과 내용에서 서로 다른 타임스탬프를 보는 것은 드문 일이 아닙니다. 각 타임스탬프를 이해하면 이 데이터로 작업하거나 시간별로 정렬하려고 할 때 발생하는 일반적인 실수를 방지하는 데 도움이 됩니다.

## [!UICONTROL CDF]개 파일 타임스탬프 찾기 {#locating-timestamps}

[!UICONTROL CDF]개의 파일이 서로 다른 두 위치에서 시간을 다르게 기록합니다.

![](assets/cdf-timestamp.png)

## 타임스탬프 간 차이점 이해 {#understanding-timestamps}

다음 표에서는 [!UICONTROL CDF] 파일 타임스탬프에 대한 추가 세부 정보와 이를 올바르게 사용하는 방법에 대한 정보를 제공합니다.

| 타임스탬프 위치 | 설명 |
|--- |--- |
| 파일 이름 | [!DNL CDF] 파일 이름의 타임스탬프는 [!DNL Audience Manager]이(가) 배달을 위해 파일 준비를 시작한 시간을 표시합니다. 이 타임스탬프는 [!DNL UTC] 시간대로 설정되어 있습니다. 이 메서드는 `hour=` 매개 변수를 사용하며, 시간은 24시간 표기법으로 2자리 시간으로 형식이 지정됩니다. 이 시간은 파일 콘텐츠에 기록된 이벤트 시간과 다를 수 있습니다. [!DNL CDF] 파일을 사용하여 작업할 때 경우에 따라 [!DNL S3] 버킷이 특정 시간 동안 비어 있는 것을 확인할 수 있습니다. 빈 버킷 수단은 다음 중 하나를 의미할 수 있습니다.<ul><li>해당 시간에 대한 데이터가 없습니다. </li><li> 서버에 부하가 심해서 특정 시간 동안 파일을 처리할 수 없습니다. 서버가 작업을 완료하면 이전 시간 버킷 파일에 있어야 하는 파일을 이후 시간 값이 있는 버킷에 넣습니다. 예를 들어 17시간 버킷에 있어야 하는 파일이 18시간 버킷에 표시되면(파일 이름에 `hour=18`이(가) 있음) 이 표시됩니다. 이 경우 서버에서 17시간 내에 파일 처리를 시작했지만 해당 시간 간격 내에 완료할 수 없을 수 있습니다. 대신 파일이 다음 시간 버킷으로 푸시됩니다.</li></ul><br>**중요**: 파일 이름 타임스탬프를 사용하여 이벤트를 시간별로 그룹화하지 마십시오. 시간별로 그룹화해야 하는 경우 파일 콘텐츠의 `EventTime` 타임스탬프를 사용하십시오. |
| 파일 내용 | [!DNL CDF] 파일 컨텐츠의 타임스탬프는 [!DNL Data Collection Servers]이(가) 파일 처리를 시작한 시간을 표시합니다. 이 타임스탬프는 [!DNL UTC] 시간대로 설정되어 있습니다. 시간은 *`yyyy-mm-dd hh:mm:ss`* 형식의 `EventTime` 필드를 사용합니다. 이 시간은 페이지에서 이벤트의 실제 시간에 가깝지만 파일 이름의 시간 표시기와 다를 수 있습니다. <br> **팁**: 파일 이름의 `hour=` 타임스탬프와 달리 `EventTime`을(를) 사용하여 시간별로 데이터를 그룹화할 수 있습니다. |

>[!MORELIKETHIS]
>
>* [고객 데이터 피드 FAQ](../faq/faq-cdf.md)
