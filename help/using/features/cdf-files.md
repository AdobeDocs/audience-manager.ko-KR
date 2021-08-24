---
description: 고객 데이터 피드(CDF) 파일에 대한 기본 정보 및 시작 방법에 대한 지침입니다. CDF 파일을 수신하거나 추가 정보를 원하는 경우 여기에서 시작하십시오.
keywords: 제2자 데이터;제2자;제2자 데이터;제2자
seo-description: 고객 데이터 피드(CDF) 파일에 대한 기본 정보 및 시작 방법에 대한 지침입니다. CDF 파일을 수신하거나 추가 정보를 원하는 경우 여기에서 시작하십시오.
seo-title: 고객 데이터 피드
solution: Audience Manager
title: 고객 데이터 피드
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: 고객 데이터 피드
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1930'
ht-degree: 3%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

[!UICONTROL Customer Data Feed]([!UICONTROL CDF]) 파일에 대한 기본 정보 및 시작 방법에 대한 지침입니다. [!UICONTROL CDF] 파일을 받거나 추가 정보를 원하는 경우 여기에서 시작하십시오.

## 파일 내용 및 목적 {#file-contents-purpose}

[!UICONTROL CDF] 파일에는 [!DNL Audience Manager] 이벤트 호출(`/event`)이 서버에 보내는 것과 동일한 데이터가 포함되어 있습니다. 여기에는 사용자 ID, [!UICONTROL trait IDs], [!UICONTROL segment IDs] 및 이벤트 호출로 캡처된 다른 모든 매개 변수와 같은 데이터가 포함됩니다. 내부 [!DNL Audience Manager] 시스템은 이벤트 데이터를 설정된 순서로 표시되는 필드로 구성된 컨텐츠가 있는 [!UICONTROL CDF] 파일로 처리합니다. [!DNL Audience Manager] 는  [!UICONTROL CDF] 시간별로 파일을 생성하여 서버의 안전한 고객별 버킷에  [!DNL Amazon S3] 저장합니다. Adobe에서는 이러한 파일을 제공하여 사용자 인터페이스가 부과한 제한을 벗어나는 [!DNL Audience Manager] 데이터로 작업할 수 있도록 합니다.

>[!IMPORTANT]
>
>CDF 파일을 사용할 때는 다음 제한 사항을 참고하십시오.
>
>* CDF 파일 전달을 설정하기 전에 타사 트레이트를 내보내기 위해 타사 데이터 공급자로부터 적절한 권한이 있는지 확인하십시오. Audience Manager은 현재 타사 데이터 공급자로부터 CDF 파일 전달 내보내기 권한을 요청하는 사용자 인터페이스 기능을 지원하지 않으므로 독립적으로 해당 사용자에게 문의하십시오.
>* [!UICONTROL CDF] 파일을 프록시로 사용하여 페이지 트래픽을 모니터링하고, 보고서 불일치를 조정하거나, 청구 등에 사용하지 않아야 합니다.


## 시작하기 {#getting-started}

[!UICONTROL CDF] 파일 전달을 시작하는 셀프 서비스 프로세스가 없습니다. 시작하려면 [!DNL Audience Manager] 컨설턴트나 고객 지원에 문의하십시오. 구현 중에 [!DNL Audience Manager] 담당자가

* [!DNL Amazon S3] 저장소 버킷을 설정합니다.
* 파일 저장소 버킷에 읽기 전용 [!DNL S3] 인증 자격 증명을 제공합니다. 다른 고객에 속한 디렉터리 및 파일을 보거나 액세스할 수 없습니다.

파일 알림 및 [!UICONTROL CDF] 파일은 다운로드 준비가 되면 [!DNL S3] 버킷에 표시됩니다. 할당된 [!DNL S3] 디렉토리에서 파일을 모니터링하고 다운로드할 책임이 있습니다. [고객 데이터 피드 파일 처리 알림](#cdf-file-processing-notifications)을 참조하십시오.

## 다음 단계 {#next-steps}

아래 섹션과 [고객 데이터 피드 FAQ](../faq/faq-cdf.md)를 통해 이 서비스에 대해 더 잘 알 수 있습니다.

## [!UICONTROL Customer Data Feed] 정의된 콘텐츠 {#cdf-defined}

모양새 순서로 [!UICONTROL CDF] 파일의 데이터 요소와 배열을 나열하고 정의합니다. 정의는 데이터 유형을 포함하지만, 이 정보는 [!UICONTROL CDF] 파일의 일부가 아닙니다.

## 정의 {#definitions}

[!UICONTROL CDF] 파일에는 아래에 정의된 일부 또는 모든 필드가 포함되어 있습니다. 내부 파일 조직에 대한 자세한 내용은 [고객 데이터 피드 파일 구조](#cdf-file-structure)를 참조하십시오.

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
   <td colname="col2"> <p>Timestamp </p> </td> 
   <td colname="col3"> <p>CDF 파일이 <span class="wintitle"> 데이터 수집 서버</span> (DCS)에서 처리된 시간입니다. 타임스탬프는 <i>yyyy-mm-dd hh:mm:ss</i> 형식을 사용하며 UTC 표준 시간대에 설정됩니다. </p> <p> <p>참고: 이벤트 시간 <i>이</i>이 아닙니다. <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">페이지 이벤트 또는 이벤트의 시간은 해당 시간에 가깝할 수 있지만 자체 호출입니다. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">파일 이름의 DCS 시간과 관련되어 있습니다. 또한, <a href="#different-processing-times"> 고객 데이터 피드 파일 이름 시간 및 파일 컨텐츠 시간 을 참조하십시오.</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>사이트 방문자의 38자리 장치 ID인 <span class="wintitle"> 고유 사용자 ID</span>(UUID)입니다. <a href="../reference/ids-in-aam.md">Audience Manager의 ID 색인</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>숫자 </p> </td> 
   <td colname="col3"> <p>ID 동기화를 실행하는 컨테이너의 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>방문자가 이벤트 호출에서 실현된(에 자격)모든 트레이트를 포함하는 트레이트 ID의 배열입니다. </p> <p>이 배열에는 방문자가 이전에 자격을 취득한 트레이트와 이 이벤트 호출을 통해 자격을 다시 부여받은 트레이트가 포함될 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>방문자가 이벤트 호출에서 구현된(에 적합)모든 세그먼트를 포함하는 세그먼트 ID의 배열입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>모든 매개 변수(변수, ID, 키-값 쌍, 장치 광고 ID 등)를 캡처하는 문자열 이벤트 호출 시 전달됩니다. </p> <p>단축된 예: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>참조 페이지의 인코딩되지 않은 URL(있는 경우)입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>이벤트 호출에서 캡처된 방문자의 IP 주소입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>문자열 </p> </td> 
   <td colname="col3"> <p>사이트 방문자에게 지정된 <span class="keyword"> Experience Cloud</span> ID(MID)입니다. 또한, <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Adobe Experience Platform Identity 서비스</a>도 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>방문자가 자격을 갖는 새 세그먼트와 이전에 실현된 세그먼트를 포함하는 세그먼트 ID의 배열입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>숫자 배열 </p> </td> 
   <td colname="col3"> <p>마지막으로 생성된 데이터 피드 이후 방문자가 자격을 부여한 트레이트와 새로운 트레이트를 포함하는 자사 및 타사 트레이트 ID의 배열입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 파일 구조 {#cdf-file-structure}

[!UICONTROL CDF] 파일의 데이터 구조를 나열하고 정의합니다. 여기에는 데이터 시퀀스, 필드 구분 기호 및 구분 기호, 데이터 파일 맵 및 샘플 파일이 포함됩니다.

## 데이터 필드 식별자 및 시퀀스 {#identifiers-and-sequence}

[!UICONTROL CDF] 파일에 레이블이 지정된 열 또는 필드 머리글이 포함되어 있지 않습니다. 대신 [!UICONTROL CDF] 파일은 인쇄되지 않는 [!DNL ASCII] 문자가 있는 필드 및 배열을 정의합니다. 또한 [!UICONTROL CDF] 파일은 각 필드와 배열을 특정 순서로 나열합니다. 필드 식별자 및 순서를 이해하면 파일을 제대로 구문 분석하는 데 도움이 됩니다.

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
   <td colname="col2"> <p>이러한 인쇄되지 않는 문자는 CDF 파일의 요소와 구조를 정의합니다. </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a(ASCII <code> 001</code> 또는 <code> ^A</code>)는 인쇄되지 않는 공간 표시기로 개별 필드의 데이터를 구분합니다. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b(ASCII <code> 002</code> 또는 <code> ^B</code>)는 데이터와 배열 및 요청 매개 변수를 구분합니다. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c(ASCII <code> 003</code> 또는 <code> ^C</code>)는 키-값 쌍을 정의합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>필드 시퀀스 </p> </td> 
   <td colname="col2"> <p> <p>중요 사항: <span class="keyword"> Audience Manager</span>은(는) 향후 릴리스에서 CDF 파일의 끝에 새 필드를 추가할 수 있는 권한을 갖습니다. 즉, 파일 구문 분석 시스템의 기술 설계에서는 고정된 수의 열을 가정하지 않아야 합니다(하지만 기존 열에 대해 고정된 순서가 있을 수 있음). </p> </p> <p>CDF 파일의 데이터는 아래 표시된 순서대로 나타납니다. </p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">이벤트 시간 </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">장치 </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">컨테이너 ID </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">실현된 트레이트 </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">실현된 세그먼트 </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">요청 매개 변수 </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Referer </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP 주소 </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud 장치 ID(또는 MID). 또한, <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> 쿠키 및 Adobe Experience Platform Identity 서비스</a>도 참조하십시오 </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">모든 세그먼트 </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">모든 트레이트 </li> 
     </ol> </p> <p>필드 설명은 <a href="#cdf-defined"> 정의된 고객 데이터 피드 컨텐츠</a>를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] 파일 맵 {#cdf-file-map}

[!UICONTROL CDF] 파일 데이터는 아래 표시된 순서대로 나타납니다.

![](assets/sequence-map.png)

## 어레이 식별

[!UICONTROL CDF] 파일의 배열은 `Ctrl + a` 필드 구분 기호로 시작하고 끝납니다. 이렇게 하면 배열의 첫 번째 요소가 독립형 데이터 필드와 같이 표시됩니다. 예를 들어 구현된 [!UICONTROL traits] 배열은 `^A1234`로 시작됩니다. 배열 구분 기호 및 ID `^B5678`가 이 항목을 따릅니다. 따라서 실현된 [!UICONTROL traits] 배열의 첫 번째 요소가 ID 5678(`^B`로 시작되므로)이라고 생각할 수 있습니다. 그렇지 않으므로 데이터 파일의 시퀀스 및 구조를 잘 알고 있어야 합니다. 실현된 [!UICONTROL trait] 배열(또는 [!UICONTROL CDF] 파일의 다른 배열)의 첫 번째 요소가 `^A`로 시작되더라도 파일의 모양 또는 위치 순서는 배열의 시작을 정의합니다. 그리고 배열의 첫 번째 요소는 항상 `^A`으로 이전 항목과 분리됩니다.

## 샘플 [!UICONTROL CDF] 파일 {#sample-file}

샘플 [!UICONTROL CDF] 파일은 다음과 비슷합니다. 이 예제에 줄바꿈을 삽입하여 페이지에 맞게 구성했습니다.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] 파일 이름 지정 규칙 {#cdf-naming-conventions}

아래 섹션을 나열하고 [!UICONTROL CDF] 파일 이름에서 요소를 정의합니다.

## [!UICONTROL CDF] 파일 이름: 구문 및 예 {#cdf-file-name}

일반적인 [!UICONTROL CDF] 파일 이름에는 아래에 나열된 요소가 포함됩니다. 참고: *기울임체*&#x200B;는 변수 자리 표시자를 나타냅니다.

### 구문

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF-PARTNER-ID-AAM PROCESS-ID_0.gz
```

### 예

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_000058_0.gz
```

[!DNL S3] 저장소 버킷에서 파일은 파트너 ID([!UICONTROL PID]), 일 및 시간별로 오름차순으로 정렬됩니다.

## [!UICONTROL CDF] 정의된 파일 이름 요소 {#cdf-file-name-elements}

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
   <td colname="col2"> <p>Amazon S3 서버의 CDF 파일에 대한 기본 루트 저장소 버킷입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>CDF 파일을 포함하는 읽기 전용 S3 버킷의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>파일을 처리한 날짜입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>24시간 표기법으로 표시되며 UTC 표준 시간대로 설정된 시간 값입니다. 또한, <a href="#different-processing-times"> 고객 데이터 피드 파일 이름 시간 및 파일 컨텐츠 시간 을 참조하십시오.</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>파트너 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AAM process ID</i>_0</code> </p> </td> 
   <td colname="col2"> <p>내부, <span class="keyword"> Audience Manager</span> 프로세스 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>gzip 파일 확장자입니다. CDF 파일은 gzip 압축됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] 파일 처리 알림 {#cdf-file-processing-notifications}

[!DNL Audience Manager] 다운로드  `.info` 준비  [!DNL S3] 상태가 되면  [!UICONTROL Customer Data File] ([!UICONTROL CDF])을 알 수 있도록 디렉토리에 파일을 작성합니다. `.info` 파일에는 [!UICONTROL CDF] 파일의 내용에 대한 형식 메타데이터도 포함되어 있습니다. [!DNL JSON] 이 알림 파일에서 사용되는 구문 및 필드에 대한 자세한 내용은 이 섹션을 참조하십시오.

## 샘플 정보 파일 {#sample-info-file}

각 `.info` 파일에는 `Files` 및 `Totals` 섹션이 포함되어 있습니다. `Files` 섹션에는 시간별 각 파일에 대한 특정 지표를 포함하는 배열이 포함되어 있습니다. `Totals` 섹션에는 특정 날 동안 모든 [!UICONTROL CDF] 파일에 집계된 지표가 포함되어 있습니다. `.info` 파일의 내용은 다음 예제와 비슷합니다.

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

다음 표는 [!UICONTROL CDF] `.info` 파일에 요소를 나열하고 정의합니다.

### 파일 개체

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
   <td colname="col2"> <p>Amazon S3 ETag입니다. 하이픈 다음에 나오는 숫자는 다중 부분 업로드 중에 파일을 작성하는 데 사용되는 부품 수를 보여줍니다. <code> ETag</code> 은 파일의 MD5 체크섬과 동일하지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>파일 이름입니다. <a href="#cdf-naming-conventions"> 고객 데이터 피드 파일 이름 지정 규칙</a>을 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
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
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>모든 CDF 파일에 대해 집계된 데이터를 포함하는 개체를 시작합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>데이터를 사용할 수 있는 날짜입니다. <i>yyyy-mm-dd</i> 형식을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>데이터를 사용할 수 있는 시간입니다. UTC 표준 시간대에 설정된 24시간 형식을 사용합니다. </p> </td> 
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

## [!UICONTROL Customer Data Feed] 파일 이름 시간 및 파일 컨텐츠 시간이 다릅니다. {#different-processing-times}

[!UICONTROL CDF] 파일에는 파일 이름 및 파일 내용에 타임스탬프가 들어 있습니다. 이러한 타임스탬프는 동일한 [!UICONTROL CDF] 파일에 대해 다른 이벤트 프로세스를 기록합니다. 동일한 파일의 이름과 내용에 다른 타임스탬프가 표시되는 것은 일반적입니다. 각 타임스탬프를 이해하면 이 데이터를 사용하여 작업하거나 시간별로 정렬할 때 일반적인 실수를 방지할 수 있습니다.

## [!UICONTROL CDF] 파일 타임스탬프 찾기 {#locating-timestamps}

[!UICONTROL CDF] 파일은 두 개의 별도 위치에서 시간을 다르게 기록합니다.

![](assets/cdf-timestamp.png)

## 타임스탬프 간의 차이점 이해 {#understanding-timestamps}

다음 표에서는 파일 타임스탬프를 올바르게 사용하는 방법에 대한 정보와 함께 [!UICONTROL CDF] 파일에 대한 추가 세부 정보를 제공합니다.

| 타임스탬프 위치 | 설명 |
|--- |--- |
| 파일 이름 | [!DNL CDF] 파일 이름의 타임스탬프는 [!DNL Audience Manager] 파일이 배달될 준비를 시작한 시간을 표시합니다. 이 타임스탬프는 [!DNL UTC] 시간대에 설정됩니다. 이 코드는 24시간 표기법으로 2자리 시간으로 형식이 지정된 `hour=` 매개 변수를 사용합니다. 이 시간은 파일 컨텐츠에 기록된 이벤트 시간과 다를 수 있습니다. [!DNL CDF] 파일로 작업할 때 경우에 따라 특정 시간 동안 [!DNL S3] 버킷이 비어 있는 것을 알 수 있습니다. 빈 버킷은 다음 중 하나를 의미할 수 있습니다.<ul><li>특정 시간에 대한 데이터가 없습니다. </li><li> 서버의 부하가 너무 많아서 특정 시간 동안 파일을 처리할 수 없습니다. 서버가 포착되면 이전 시간 버킷 파일에 포함해야 하는 파일이 이후 시간 값이 있는 버킷으로 표시됩니다. 예를 들어 17시간 버킷에 있어야 하는 파일이 18시간 버킷에 나타나면(파일 이름에 `hour=18`이 있음) 이 표시됩니다. 이 경우 서버는 파일 처리를 17시간 내에 시작할 수 있지만 해당 시간 간격 내에 완료할 수 없습니다. 대신 파일이 다음 시간별 시간 버킷으로 푸시됩니다.</li></ul><br>**중요**: 파일 이름 타임스탬프를 사용하여 시간별로 이벤트를 그룹화하지 마십시오. 시간별로 그룹화해야 하는 경우 파일 컨텐츠에서 `EventTime` 타임스탬프를 사용합니다. |
| 파일 내용 | [!DNL CDF] 파일 내용의 타임스탬프는 [!DNL Data Collection Servers] 가 파일 처리를 시작한 시간을 표시합니다. 이 타임스탬프는 [!DNL UTC] 시간대에 설정됩니다. 이 코드는 `EventTime` 필드를 사용하며, 시간은 *`yyyy-mm-dd hh:mm:ss`* 형식으로 지정됩니다. 이 시간은 페이지에서 실제 이벤트 시간에 가깝지만 파일 이름에 있는 시간 표시기와 다를 수 있습니다. <br> **팁**: 파일  `hour=` 이름의 타임스탬프와 달리 를 사용하여 데이터를 시간 `EventTime` 으로 그룹화할 수 있습니다. |

>[!MORELIKETHIS]
>
>* [고객 데이터 피드 FAQ](../faq/faq-cdf.md)

