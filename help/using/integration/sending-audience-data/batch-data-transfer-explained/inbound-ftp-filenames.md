---
description: Audience Manager로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기에 대해 설명합니다. Audience Manager FTP 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.
seo-description: Audience Manager로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기에 대해 설명합니다. Audience Manager FTP 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.
seo-title: 인바운드 데이터 파일에 대한 FTP 이름 및 파일 크기 요구 사항
solution: Audience Manager
title: 인바운드 데이터 파일에 대한 FTP 이름 및 파일 크기 요구 사항
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
translation-type: tm+mt
source-git-commit: 881ccf512e9776948e4507e321e972dd2079e21a

---


# 인바운드 데이터 파일에 대한 FTP 이름 및 파일 크기 요구 사항{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Audience Manager로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기에 대해 설명합니다. Audience Manager [!DNL FTP] 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.

>[!WARNING]
>
>FTP 구성에 대한 지원이 점차 축소되고 있습니다. 기존 FTP 통합에서 인바운드 데이터 파일 수집은 여전히 지원되지만, 새로운 통합을 위해 오프라인 데이터를 등록하려면 Amazon S3를 사용하는 것이 좋습니다. 자세한 [내용은 인바운드 데이터 파일에 대한 Amazon S3 이름 및 파일 크기 요구 사항을](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) 참조하십시오.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소와 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## 파일 이름 구문 {#file-name-syntax}

[!DNL FTP] 파일 이름에는 다음과 같은 필수 및 선택적 요소가 포함됩니다.

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

허용되는 다른 파일 이름 형식은 사용자 지정 파트너 [통합을 참조하십시오](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE] {importance="high"}
>
>[!DNL Audience Manager] 처리 [!DNL ASCII] 및 [!DNL UTF-8] 인코딩된 파일만 처리합니다.

### 요소 이름 지정

이 표에서는 [!DNL FTP] 파일 이름의 요소를 정의합니다.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 이름 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Audience Manager FTP 디렉토리의 <span class="keyword"> 경로와</span> 이름입니다. FTP 디렉토리 및 자격 증명은 계정 관리자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>데이터 파일에 사용자 <span class="keyword"> ID</span> 또는 Android 또는 iOS ID가 포함되어 있는지 Audience Manager에 알려주는 ID입니다. 다음 옵션을 수락합니다. </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b></b> 데이터 파트너 ID:이것은 Audience Manager가 회사 또는 조직에 할당하는 고유 ID입니다. 사용자 ID가 포함된 데이터를 보낼 때 파일 이름에 이 할당된 ID를 사용합니다. 예를 들어, Audience Manager <code>...ftp_dpm_21_123456789.sync</code> 에 <span class="keyword"></span> ID 21이 있는 파트너가 파일을 전송했으며 이 파일에는 해당 파트너가 할당한 사용자 ID가 포함되어 있다고 알려줍니다. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b></b> Android ID(GAID):데이터 파일 이름에 Android ID가 포함된 경우 ID 20914를 사용합니다. 예를 들어 데이터 파일에 Android <code>...ftp_dpm_20914_123456789.sync</code> ID만 <span class="keyword"></span> 포함되어 있음을 Audience Manager에 알려줍니다. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b></b> iOS ID(IDFA):iOS ID가 포함된 경우 데이터 파일 이름에 ID 20915를 사용합니다. 예를 들어 데이터 파일에 <code>...ftp_dpm_20915_123456789.sync</code> iOS ID만 <span class="keyword"></span> 포함되어 있음을 Audience Manager에 알려줍니다. </li> 
    </ul> <p> <p>참고: 데이터 파일에 ID 유형을 혼합하지 마십시오. 예를 들어 파일 이름에 Android 식별자가 포함되어 있는 경우 iOS ID 또는 자신의 ID를 데이터 파일에 넣지 마십시오. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>ID에 대한 자리 표시자 예를 들어 DPID를 데이터 <span class="keyword"> 소스 ID</span> 또는 Android 또는 iOS ID로 설정하는 경우 Audience Manager ID로 설정할 수 있습니다. 이렇게 하면 <span class="keyword"> Audience</span> Manager가 파일 데이터를 조직에 다시 연결할 수 있습니다. </p> <p>예: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> ID 21이 있는 파트너가 ID 33을 사용하는 데이터 소스에서 데이터를 전송했음을 보여줍니다. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> 은 Android ID가 포함된 데이터에서 보낸 ID 21의 파트너를 보여줍니다. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> 은 iOS ID가 포함된 데이터에서 보낸 ID 21의 파트너를 보여줍니다. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>다음을 포함하는 동기화 옵션 </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:타사 데이터 공급자가 사용자별로 트레이트를 전송하여 Audience Manager 시스템에서 추가 또는 제거할 수 있는 일반적인 시나리오입니다. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:고객 및 데이터 제공업체는 Audience Manager에서 지정된 데이터 소스에 대한 이 사용자의 기존 특성을 모두 덮어써야 하는 사용자별로 트레이트 목록을 보낼 수 있습니다. 모든 사용자를 덮어쓰기 파일에 포함할 필요는 없습니다. 변경할 사용자만 포함합니다. 타겟 데이터 소스에 할당되지 않은 트레이트는 지워지지 않습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>정수입니다. 대용량 파일을 여러 부분으로 분할할 때 사용되어 처리 시간이 향상됩니다. 번호는 원본 파일의 어느 부분을 전송하는지 나타냅니다. </p> <p>효율적인 파일 처리를 위해 지정된 대로 데이터 파일을 분할합니다. </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">압축되지 않음:1GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">압축:200-300MB </li> 
    </ul> <p>아래의 처음 2개의 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> 파일 이름 예를</a> 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10자리 UTC UNIX 타임스탬프(초 단위) 타임스탬프는 각 파일 이름을 고유하게 만드는 데 도움이 됩니다. </p> 
    <draft-comment> 
     <p> <p>참고: Audience Manager는 인바운드 파일을 처리하는 동안 타임스탬프를 사용하지 않습니다. 파일 이름의 타임스탬프는 Audience Manager에서 더 이상 사용되지 않지만 이전 버전과의 호환성을 위해 필요합니다. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip은 FTP 파일 이름에 대해 허용되는 압축 형식입니다. 파일 압축을 사용하는 경우 파일 이름의 확장자가 올바른지 확인하십시오. </p> <p>압축된 파일은 3GB 이하여야 합니다. 파일 크기가 큰 경우 고객 지원 센터에 문의하십시오. Adobe Audience Manager는 대용량 파일을 처리할 수 있지만 파일 크기를 줄이고 데이터 전송을 보다 효율적으로 수행할 수 있습니다. 인바운드 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> 데이터 전송 파일에 대한 파일 압축을 참조하십시오</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## 파일 이름 예 {#file-name-examples}

다음 예는 올바른 형식의 파일 이름을 보여줍니다. 파일 이름이 유사할 수 있습니다.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[추가 예제가 필요한 경우 샘플 파일을 다운로드합니다](assets/ftp_dpm_1234_1445374061.overwrite) . 이 파일은 `.overwrite` 파일 확장명으로 저장됩니다. 간단한 텍스트 편집기를 사용하여 엽니다.

## 허용되는 파일 크기 {#accepted-file-sizes}

파일 처리 속도가 빠르고 빨라진 것은 물론 데이터를 [!DNL Audience Manager] / [!DNL FTP] 디렉토리로 전송할 때 파일 크기 제한에 대한 아래 수치를 고려하십시오.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 형식 </th> 
   <th colname="col2" class="entry"> 최적 크기 </th> 
   <th colname="col3" class="entry"> 최대 크기 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>압축</b> </td> 
   <td colname="col2"> <p>200-300MB </p> </td> 
   <td colname="col3"> <p>3GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>압축되지 않음</b> </td> 
   <td colname="col2"> <p>1GB </p> </td> 
   <td colname="col3"> <p>5GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

