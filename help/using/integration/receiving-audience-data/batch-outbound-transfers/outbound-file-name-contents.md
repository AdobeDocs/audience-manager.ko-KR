---
description: 아웃바운드 데이터 파일 이름을 지정하는 데 사용되는 필수 필드, 구문 및 규칙을 설명합니다.
seo-description: 아웃바운드 데이터 파일 이름을 지정하는 데 사용되는 필수 필드, 구문 및 규칙을 설명합니다.
seo-title: 아웃바운드 데이터 파일 이름 구문 및 예
solution: Audience Manager
title: 아웃바운드 데이터 파일 이름 구문 및 예
uuid: effdcaf 6-c 37 c -45 f 3-9 d 2 f-a 938 a 9 da 47 a 6
translation-type: tm+mt
source-git-commit: e6f1a3b86658a882ebe927cefe55be6ddd40b906

---


# 아웃바운드 데이터 파일 이름: 구문 및 예제{#outbound-data-file-name-syntax-and-examples}

아웃바운드 데이터 파일 이름을 지정하는 데 사용되는 필수 필드, 구문 및 규칙을 설명합니다.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>스타일 요소 (`monospaced text`*, 기울임체*, 대괄호 `[ ]``( )`등) 는 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## 구문 및 파일 이름 요소 {#syntax-file-name}

아웃바운드 파일 이름에는 다음 요소가 포함됩니다. 아래의 모든 요소는 선택 사항입니다.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 매개 변수

이 표에서는 아웃바운드 데이터 파일 이름의 요소를 정의합니다.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 이름 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>sync_ type </i></code> </p> </td> 
   <td colname="col2"> <p>데이터 전송 방법을 참조합니다. 전송 방법에는 다음이 포함됩니다. </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Sftp를 사용하여 전송 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S 3 </span> - Amazon AWS로 <span class="keyword"> 전송 </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>did </i></code> </p> </td> 
   <td colname="col2"> <p>대상 ID. </p> <p><span class="keyword"> Audience Manager </span>에서 대상은 targetable 세그먼트를 매핑할 수 있는 통합의 인스턴스입니다. 고객은 비즈니스 요구 사항에 따라 여러 대상을 가질 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>master_ dpid </i></code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 또는 데이터 소스 ID. 이 ID는 파일 컨텐츠에 있는 사용자 ID 유형을 식별합니다. 가장 일반적인 사용자 ID 키는 다음과 같습니다. </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google 광고주 ID </span> (RAW, 해시 해제) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> 광고업체를 위한 Apple ID </span> (RAW, 해시 해제) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">공급업체 ID - 타사 사용자 ID (웹/쿠키) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>pid_ alias </i></code> </p> </td> 
   <td colname="col2"> 타사 플랫폼의 고객 식별자입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>sync_ mode </i></code> </p> </td> 
   <td colname="col2"> <p>동기화 모드는 동기화 유형을 기반으로 파일 이름에 레이블을 추가하는 매크로 자리 표시자입니다. 동기화 유형에는 전체 및 증분이 포함됩니다. 파일 이름에 <code> iter </code> 또는 <code> full </code>로 표시됩니다. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> Iter </code>: " 반복 "또는 증분 동기화를 가리킵니다. 증분 파일에는 마지막 동기화 이후 수집된 새 데이터만 포함됩니다. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> 전체 </code>: " 전체 "동기화를 나타냅니다. 완전히 동기화된 파일에는 이전 데이터 및 마지막 동기화 이후에 수집된 새로운 데이터가 포함됩니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>timestamp </i></code> </p> </td> 
   <td colname="col2"> <p>UTC 표준 시간대에서 13 자리 UNIX 타임스탬프의 밀리초 단위 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>splitnum</i></code></p> </td> 
   <td colname="col2"> <p>정수. 처리 시간을 개선하기 위해 여러 부분으로 분할된 파일의 일부를 식별합니다. 숫자는 데이터가 속하는 원본 파일의 부분을 나타냅니다.</p>  <p>분할 크기가 100 픽셀보다 작으면 정수에는 3 자리가 있어야 하며 앞에 0 이 있어야 합니다.</p>  <p>원본 파일에는 분할 번호가 없습니다. 첫 번째 분할 파일은 001로 끝납니다. 아래 예를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (선택 사항) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP 압축. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 파일 이름 예 {#file-name-examples}

### 시나리오 1

파일 컨텐츠에서 [!DNL Amazon S3] 위치와 함께 *`PID_ALIAS="XYZCustomer"`*[!DNL Google Advertiser IDs] 위치에 전송된 파일.

E.g. 증분 파일:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

E.g. 전체 파일:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### 시나리오 2

파일 내용 없이 [!DNL FTP]*`PID_ALIAS`* 위치로 [!DNL Apple Advertiser IDs] 보낸 파일:

E.g. 증분 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

E.g. 전체 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**시나리오 3**: 파일 콘텐트 () 에서 타사 사용자 ID와 함께 [!DNL FTP]*`PID_ALIAS="XYZCustomer"`* 위치로 보낸 *`Vendor ID=45454`*&#x200B;파일:

E.g. 증분 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

E.g. 전체 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## 아웃바운드 데이터 파일 컨텐츠: 구문 및 매개 변수 {#outbound-contents-syntax}

아웃바운드 데이터 파일에서 정보를 구성하는 데 사용되는 필수 필드, 구문 및 규칙을 설명합니다. 이러한 사양에 따라 데이터 형식을 지정합니다.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>스타일 요소 (`monospaced text`*, 기울임체*, 대괄호 `[ ]``( )`등) 는 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

### 구문

데이터 파일의 필드는 다음 순서로 표시됩니다.

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### 매개 변수

아래 표는 데이터 파일의 컨텐츠를 정의하는 변수를 보여줍니다.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 매개 변수 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager </span>에서 할당한 고유한 사용자 ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt; space &gt; </i></code> </p> </td> 
   <td colname="col2"> <p>UUID와 세그먼트 데이터를 공백으로 분리 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>segment_ n </i></code> </p> </td> 
   <td colname="col2"> <p>방문자가 속하는 세그먼트 ID. 여러 세그먼트를 쉼표로 구분합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>removed_ segment_ n </i></code> </p> </td> 
   <td colname="col2"> <p>사용자가 자격을 상실한 세그먼트 ID. 여러 세그먼트를 쉼표로 구분합니다. 전체 동기화를 사용하면 데이터 파일에 사용자에 대한 전체 세그먼트 목록이 들어 있으므로 제거된 세그먼트를 무시할 수 있습니다. 일반적으로 사용자는 제거된 세그먼트 대신 사용자가 속한 세그먼트에 대해 알고 있어야 합니다. 아웃바운드 데이터 파일 이름도 <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> 참조하십시오. 구문 및 예입니다 </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 예: 기본 파일 형식

올바른 형식의 데이터 파일은 다음 샘플과 비슷합니다. 이 파일 항목은 사용자가 세그먼트 24, 26 및 27에 대한 자격을 부여했음을 나타냅니다. 필요한 경우 공백은 `UUID` 세그먼트와 세그먼트 ID를 구분합니다. 또 다른 공간은 세그먼트 ID 세트를 구분합니다. 이 예에서, 사용자는 세그먼트 24, 26 및 27에 속합니다. 세그먼트 25 및 28에서 제거되었습니다.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
