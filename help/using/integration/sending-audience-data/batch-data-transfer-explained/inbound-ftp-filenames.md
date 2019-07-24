---
description: Audience Manager로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기를 설명합니다. Audience Manager FTP 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.
seo-description: Audience Manager로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기를 설명합니다. Audience Manager FTP 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.
seo-title: 인바운드 데이터 파일에 대한 FTP 이름 및 파일 크기 요구 사항
solution: Audience Manager
title: 인바운드 데이터 파일에 대한 FTP 이름 및 파일 크기 요구 사항
uuid: 49 EAAFAC -5 CB 0-482 F -872 A -84 C 056016 BDB
translation-type: tm+mt
source-git-commit: ec2d05290874a95e9cc9b8318fcc5e1e1986f5b9

---


# FTP Name and File Size Requirements for Inbound Data Files{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Audience Manager로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기를 설명합니다. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager [!DNL FTP] directory.

>[!WARNING]
>
>인바운드 데이터 파일에 대한 FTP 전송은 더 이상 지원되지 않습니다. 오프라인 데이터를 사용하려면 Amazon S 3를 사용하십시오. See [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) for details.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## File Name Syntax {#file-name-syntax}

[!DNL FTP] 파일 이름에는 다음과 같은 필수 요소와 선택적 요소가 포함됩니다.

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

For other accepted file name formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance = "high"}
>
>[!DNL Audience Manager] 프로세스 [!DNL ASCII] 및 [!DNL UTF-8] 인코딩된 파일만 수행할 수 있습니다.

### 요소 이름 지정

The table defines the elements in an [!DNL FTP] file name.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 이름 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_ dpm_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> FTP 디렉토리의 경로 및 이름입니다. FTP 디렉토리 및 자격 증명에 대해서는 계정 관리자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>dpid</i></code> </p> </td> 
   <td colname="col2"> <p>An lD that tells <span class="keyword"> Audience Manager</span> if a data file contains your own user IDs or Android or iOS IDs. 다음 옵션을 수락합니다. </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>데이터 파트너 ID:</b> 이 ID는 회사 또는 조직에 할당된 고유한 ID 입니다. 사용자 ID가 포함된 데이터를 전송할 때 파일 이름에서 지정된 ID를 사용합니다. For example, <code>...ftp_dpm_21_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that a partner with ID 21 sent the file and it contains user IDs assigned by that partner. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID (Gaid):</b> 데이터 파일 이름에 Android ID가 포함된 경우 ID 20914를 사용합니다. For example, <code>...ftp_dpm_20914_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains Android IDs only. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID (IDFA):</b> 데이터 파일 이름에 iOS ID가 포함된 경우 ID 20915를 사용합니다. For example, <code>...ftp_dpm_20915_123456789.sync</code> tells <span class="keyword"> Audience Manager</span> that the data file contains iOS IDs only. </li> 
    </ul> <p> <p>참고: 데이터 파일에서 ID 유형을 혼합하지 마십시오. 예를 들어 파일 이름에 Android 식별자가 포함된 경우 데이터 파일에 iOS ID 또는 자체 ID를 넣지 마십시오. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>_ dpid_ target_ data_ owner</i></code> </p> </td> 
   <td colname="col2"> <p>ID에 대한 자리 표시자. For example, you could set it to your <span class="keyword"> Audience Manager</span> ID if you set the DPID to a data source ID or an Android or iOS ID. This lets <span class="keyword"> Audience Manager</span> link the file data back to your organization. </p> <p>예: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>... ftp_ dpm_ 33_ 21_ 1234567890. Sync</code> 는 ID 21 이 있는 파트너가 ID 33를 사용하는 데이터 소스의 데이터에 전송되었음을 보여줍니다. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>... ftp_ dpm_ 20914_ 21_ 1234567890. Sync</code> 는 ID 21 이 있는 파트너가 Android ID가 포함된 데이터로 전송되었음을 보여줍니다. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>... ftp_ dpm_ 20915_ 21_ 1234567890. Sync</code> 가 ID 21 이 있는 파트너가 iOS ID가 포함된 데이터로 전송되었음을 보여줍니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (. sync |. overwrite)</code> </p> </td> 
   <td colname="col2"> <p>다음을 포함한 동기화 옵션: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> 동기화</code>: 타사 데이터 공급자가 Audience Manager 시스템에서 추가 또는 제거될 사용자 단위 트레이트를 전송할 때의 일반적인 시나리오입니다. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> 덮어쓰기</code>: 고객 및 데이터 제공업체가 Audience Manager에서 주어진 데이터 소스에 대해 이 사용자의 기존 트레이트를 모두 덮어써야 하는 특성 목록을 사용자 단위로 보낼 수 있습니다. 덮어쓰는 파일에 모든 사용자를 포함할 필요는 없습니다. 변경하려는 사용자만 포함합니다. Target 데이터 소스에 할당되지 않은 트레이트는 지워지지 않습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>split_ number</i></code>] </p> </td> 
   <td colname="col2"> <p>정수. 큰 파일을 여러 부분으로 분할하여 처리 시간을 단축할 때 사용됩니다. 숫자는 전송 중인 원본 파일의 부분을 나타냅니다. </p> <p>효율적인 파일 처리를 위해 다음과 같이 데이터 파일을 분할합니다. </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">압축되지 않음: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">압축: 200-300 MB </li> 
    </ul> <p>See the first 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> file name examples</a> below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>timestamp</i></code> </p> </td> 
   <td colname="col2"> <p>10 자리, UTC UNIX 타임스탬프 (초 단위) 타임스탬프는 각 파일 이름을 고유하게 만드는 데 도움이 됩니다. </p> 
    <draft-comment> 
     <p> <p>참고: Audience Manager 에서는 인바운드 파일을 처리하는 동안 타임스탬프를 사용하지 않습니다. 파일 이름의 타임스탬프는 Audience Manager에서 더 이상 사용되지 않지만 이전 버전과의 호환성을 위해 필요합니다. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>GZIP는 FTP 파일 이름에 허용되는 압축 형식입니다. 파일 압축을 사용하는 경우 파일 이름의 확장자가 올바른지 확인하십시오. </p> <p>압축 파일은 3 GB 이상이어야 합니다. 파일 파일이 더 큰 경우 고객 지원 센터에 문의하십시오. Audience Manager는 대용량 파일을 처리할 수 있지만, Adobe는 파일 크기를 줄이고 데이터 전송을 보다 효율적으로 할 수 있도록 지원합니다. See <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> File Compression for Inbound Data Transfer Files</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Name Examples {#file-name-examples}

다음 예는 형식이 올바르게 지정된 파일 이름을 보여줍니다. 파일 이름은 비슷합니다.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> FTP_ DPM_ 478_ 1366545717. overwrite</code> </li> 
</ul>

[추가 예가](assets/ftp_dpm_1234_1445374061.overwrite) 필요한 경우 샘플 파일을 다운로드합니다. This file is saved with the `.overwrite` file extension. 간단한 텍스트 편집기를 사용하여 엽니다.

## Accepted File Sizes {#accepted-file-sizes}

Consider the figures below for fastest/earliest processing of your files as well as for file size limitations when you send data to an [!DNL Audience Manager] / [!DNL FTP] directory.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 형식 </th> 
   <th colname="col2" class="entry"> 최적의 크기 </th> 
   <th colname="col3" class="entry"> 최대 크기 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>압축</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>압축되지 않음</b> </td> 
   <td colname="col2"> <p>1GB </p> </td> 
   <td colname="col3"> <p>5GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

