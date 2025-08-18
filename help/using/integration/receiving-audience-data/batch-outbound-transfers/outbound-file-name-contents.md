---
description: 아웃바운드 데이터 파일의 이름을 지정하는 데 사용되는 필수 필드, 구문 및 규칙에 대해 설명합니다.
seo-description: Describes the required fields, syntax, and conventions used to name an outbound data file.
seo-title: Outbound Data File Name  Syntax and Examples
solution: Audience Manager
title: 아웃바운드 데이터 파일 이름 구문 및 예
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Outbound Data Transfers
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 5%

---

# 아웃바운드 데이터 파일 이름: 구문 및 예{#outbound-data-file-name-syntax-and-examples}

아웃바운드 데이터 파일의 이름을 지정하는 데 사용되는 필수 필드, 구문 및 규칙에 대해 설명합니다.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>이 문서의 스타일 요소(`monospaced text`, *기울임꼴*, 대괄호 `[ ]` `( )` 등)는 코드 요소와 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## 구문 및 파일 이름 요소 {#syntax-file-name}

아웃바운드 파일 이름에는 다음 요소가 포함됩니다. 아래의 모든 요소는 선택 사항입니다.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### 매개변수

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
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>데이터 전송 메서드를 참조하십시오. 전송 방법에는 다음이 포함됩니다. </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - SFTP를 사용하여 전송 </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3 </span> - <span class="keyword"> Amazon AWS </span>(으)로 전송 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>대상 ID. </p> <p><span class="keyword"> Audience Manager </span>에서 대상은 대상 가능한 세그먼트를 매핑할 수 있는 통합 인스턴스입니다. 고객은 비즈니스 요구 사항에 따라 여러 대상을 가질 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>데이터 공급자 또는 데이터 소스 ID. 이 ID는 파일 콘텐츠에 있는 사용자 ID의 유형을 식별합니다. 가장 일반적인 사용자 ID 키는 다음과 같습니다. </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google 광고주 ID </span>(원시, 해시되지 않음) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> 광고주용 Apple ID </span>(원시, 해시되지 않음) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">공급업체 ID - 서드파티 사용자 ID(웹/쿠키) </li> 
     </ul> </p> <p>자세한 내용은 <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html">글로벌 데이터 소스</a>를 참조하십시오.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> 타사 플랫폼의 고객 식별자입니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>동기화 모드는 동기화 유형에 따라 파일 이름에 레이블을 추가하는 매크로 자리 표시자입니다. 동기화 유형에는 전체 및 증가분이 포함됩니다. 파일 이름에 <code> iter </code> 또는 <code> full </code>(으)로 표시됩니다. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: "반복" 또는 증분 동기화를 나타냅니다. 증분 파일에는 마지막 동기화 이후 수집된 새 데이터만 포함되어 있습니다. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: "전체" 동기화를 나타냅니다. 완전히 동기화된 파일에는 이전 데이터와 마지막 동기화 이후 수집된 새 데이터가 포함되어 있습니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>UTC 시간대의 13자리 UNIX 타임스탬프(밀리초). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>정수. 는 처리 시간을 개선하기 위해 여러 부분으로 분할된 파일의 일부를 식별합니다. 숫자는 데이터가 원본 파일의 어느 부분에 속하는지를 나타냅니다.</p>  <p>분할 크기가 100부보다 작은 경우 정수는 최소 3자리 길이여야 하며 앞에 0이 붙어야 합니다.</p>  <p>원본 파일에는 분할 숫자가 없습니다. 첫 번째 분할 파일은 001로 끝납니다. 아래 예를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP 압축입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 파일 이름 예 {#file-name-examples}

### 시나리오 1

파일이 [!DNL Amazon S3] 위치로 전송되었습니다. 파일 콘텐츠에는 *`PID_ALIAS="XYZCustomer"`*&#x200B;이(가) 있고 [!DNL Google Advertiser IDs]이(가) 있습니다.

예: 증분 파일:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

예: 전체 파일:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### 시나리오 2

[!DNL FTP]이(가) 없고 파일 콘텐츠에 *`PID_ALIAS`*&#x200B;이(가) 있는 [!DNL Apple Advertiser IDs] 위치로 전송된 파일:

예: 증분 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

예: 전체 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**시나리오 3**: [!DNL FTP]을(를) 사용하고 파일 콘텐츠에 타사 사용자 ID가 있는 *`PID_ALIAS="XYZCustomer"`* 위치로 보낸 파일(*`Vendor ID=45454`*):

예: 증분 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

예: 전체 파일:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## 아웃바운드 데이터 파일 내용: 구문 및 매개 변수 {#outbound-contents-syntax}

아웃바운드 데이터 파일에서 정보를 구성하는 데 사용되는 필수 필드, 구문 및 규칙에 대해 설명합니다. 이러한 사양에 따라 데이터 형식을 지정합니다.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>이 문서의 스타일 요소(`monospaced text`, *기울임꼴*, 대괄호 `[ ]` `( )` 등)는 코드 요소와 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

### 구문

데이터 파일의 필드는 다음 순서로 표시됩니다.

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### 매개변수

표에는 데이터 파일의 내용을 정의하는 변수가 나열되어 있습니다.

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager </span>이(가) 할당한 고유 사용자 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>공백으로 UUID 및 세그먼트 데이터 분리 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>방문자가 속한 세그먼트 ID입니다. 여러 세그먼트는 쉼표로 구분합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>사용자가 자격을 박탈당한 세그먼트 ID입니다. 여러 세그먼트는 쉼표로 구분합니다. 전체 동기화를 사용하면 데이터 파일에 사용자에 대한 현재 세그먼트의 전체 목록이 포함되므로 제거된 세그먼트를 무시할 수 있습니다. 일반적으로 제거된 세그먼트가 아니라 사용자가 속한 세그먼트에 대해 알고 싶을 수 있습니다. <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> 아웃바운드 데이터 파일 이름: 구문 및 예제 </a>도 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 예: 기본 파일 형식

적절한 형식의 데이터 파일은 다음 샘플과 유사할 수 있습니다. 이 파일 항목은 사용자가 세그먼트 24, 26 및 27에 적합함을 나타냅니다. 필요에 따라 공백으로 `UUID`과(와) 세그먼트 ID를 구분합니다. 다른 공백은 세그먼트 ID 세트를 구분합니다. 이 예에서, 사용자는 세그먼트 24, 26, 27에 속한다. 세그먼트 25와 28에서 제거되었습니다.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
