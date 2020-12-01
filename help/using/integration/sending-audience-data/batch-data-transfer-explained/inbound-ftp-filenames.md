---
description: Audience Manager으로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기에 대해 설명합니다. Audience Manager FTP 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.
seo-description: Audience Manager으로 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기에 대해 설명합니다. Audience Manager FTP 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.
seo-title: 인바운드 데이터 파일에 대한 FTP 이름 및 파일 크기 요구 사항
solution: Audience Manager
title: 인바운드 데이터 파일에 대한 FTP 이름 및 파일 크기 요구 사항
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: f037a12af641da44ed67e62a249c41487da7ac07
workflow-type: tm+mt
source-wordcount: '1042'
ht-degree: 8%

---


# [!DNL FTP]인바운드 데이터 파일에 대한 이름 및 파일 크기 요구 사항{#ftp-name-and-file-size-requirements-for-inbound-data-files}

데이터를 [!DNL Audience Manager]으로 보낼 때 따라야 할 필수 필드, 구문, 이름 지정 규칙 및 파일 크기에 대해 설명합니다. Audience Manager [!DNL FTP] 디렉토리로 데이터를 전송할 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.

>[!WARNING]
>
>[!DNL FTP] 구성에 대한 지원을 단계적으로 중단할 예정입니다. 기존 [!DNL FTP] 통합에서 인바운드 데이터 파일 회수가 여전히 지원되지만 새 통합을 위해 오프라인 데이터를 온보드([!DNL Amazon S3])하는 것이 좋습니다. 자세한 내용은 [인바운드 데이터 파일에 대한 Amazon S3 이름 및 파일 크기 요구 사항](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)을 참조하십시오.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## 파일 이름 구문 {#file-name-syntax}

[!DNL FTP] 파일 이름에는 다음과 같은 필수 요소와 선택 사항이 포함됩니다.

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

허용되는 다른 파일 이름 포맷은 [사용자 지정 파트너 통합](/help/using/integration/sending-audience-data/custom-partner-integrations.md)을 참조하십시오.

>[!NOTE]
>
>[!DNL Audience Manager] 프로세스 [!DNL ASCII] 와  [!DNL UTF-8] 인코딩된 파일만 처리합니다.

### 이름 요소

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> FTP 디렉토리의 경로 및 이름입니다. FTP 디렉토리 및 자격 증명은 계정 관리자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>데이터 파일에 사용자 ID, Android ID, iOS ID 또는 <a href="/help/using/features/global-data-sources.md"> 글로벌 데이터 소스</a>에 속하는 기타 ID가 포함된 경우 <span class="keyword"> Audience Manager</span>을 알려주는 ID입니다. 다음 옵션을 수락합니다.</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>데이터 소스 ID(데이터 공급자 ID라고도 함): </b> Audience Manager이 데이터 소스에 할당하는 고유한 ID입니다(ID의 Audience Manager  <a href="/help/using/reference/ids-in-aam.md">   </a>색인 참조). 사용자 ID가 포함된 데이터를 보낼 때 파일 이름에 이 할당된 ID를 사용합니다. 예를 들어 <code>...ftp_dpm_21_123456789.sync</code>은 <span class="keyword"> Audience Manager</span>에게 데이터 소스 21에 속하는 ID에 데이터를 올리도록 지시합니다. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID): 데이터 파일 이름에 </b> Android ID가 포함된 경우 ID 20914를 사용합니다. Android ID를 사용할 때는 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 필드를 사용해야 합니다. 예를 들어 <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code>은 <span class="keyword"> Audience Manager</span>에게 데이터 파일에 Android ID만 포함되며 ID는 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 데이터 소스에 속하는 트레이트를 사용할 수 있어야 한다고 알려줍니다.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA): </b> 데이터 파일 이름에 iOS ID가 포함된 경우 ID 20915를 사용합니다. iOS ID를 사용할 때는 필드 <code><i>_DPID_TARGET_DATA_OWNER</i></code>을 사용해야 합니다. 예를 들어 <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code>은 <span class="keyword"> Audience Manager</span>에게 데이터 파일에 iOS ID만 포함되며 ID는 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 데이터 소스에 속하는 트레이트를 사용할 수 있어야 한다고 알려줍니다.</li>
     <li> <b>다른 글로벌 데이터 소스에 속하는 ID</b>:RIDA(Advertising), Microsoft Advertising ID(WEDER) 및 기타 ID를 위한 Roku ID를 게시할 수 있습니다. <a href="/help/using/features/global-data-sources.md"> 글로벌 데이터 소스 아티클</a>에 설명된 대로 각 데이터 소스에 해당하는 ID를 사용하십시오.</li> 
    </ul> <p> <p>참고: 데이터 파일에 ID 유형을 혼합하지 마십시오. 예를 들어 파일 이름에 Android 식별자가 포함된 경우 iOS ID나 자신의 ID를 데이터 파일에 넣지 마십시오. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>이 필드에서는 데이터 입체를 위한 데이터 소스를 Audience Manager에 알려 줍니다. DPID를 Android ID 또는 iOS ID나 글로벌 데이터 소스에 속하는 다른 ID로 설정하는 경우 이 필드는 필수입니다. 이렇게 하면 <span class="keyword"> Audience Manager</span>에서 파일 데이터를 조직에 다시 연결할 수 있습니다. </p> <p>예: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> 데이터 소스 21에 속하는 트레이트 또는 신호에 대해 데이터 소스 33에 속하는 고객 ID를 Audience Manager에 알려줍니다. </li> 
     <li> <b>Android ID(GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> Audience Manager <span class="keyword"> 에게 데이터 파일에 Android ID만 포함되어 있고 ID는 데이터 소스 21에 속하는 트레이트를 사용할 수 있어야 한다고 </span> 알립니다.</li> 
     <li> <b>iOS ID(IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> 데이터 파일에 iOS ID만  <span class="keyword"> 포함되어 있고 ID는 데이터 소스 21에 속하는 트레이트를 사용할 수 있어야 한다고 Audience </span> Manager에게 알립니다.</li>
     <li> <b>다른 글로벌 데이터 소스에 속하는 ID</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code> 데이터 파일 <span class="keyword"> 에 Roku </span> ID만 있고 ID는 데이터 소스 21에 속하는 트레이트를 사용할 수 있어야 한다고 대상 관리자에게 알립니다. <a href="/help/using/features/global-data-sources.md"> 글로벌 데이터 소스 아티클</a>에 설명된 대로 각 데이터 소스에 해당하는 ID를 사용하십시오.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>다음을 포함하는 동기화 옵션 </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>:타사 데이터 공급자가 Audience Manager 시스템에서 추가 또는 제거되도록 사용자별로 트레이트를 보낼 때의 일반적인 시나리오입니다. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>:고객 및 데이터 제공업체는 Audience Manager의 지정된 데이터 소스에 대한 이 사용자의 기존 특성을 모두 덮어써야 하는 사용자 단위 트레이트 목록을 보낼 수 있습니다. 덮어쓰기 파일에 모든 사용자를 포함할 필요는 없습니다. 변경할 사용자만 포함합니다. 타겟 데이터 소스에 할당되지 않은 트레이트는 지워지지 않습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>정수입니다. 대용량 파일을 여러 부분으로 분할할 때 사용되므로 처리 시간이 향상됩니다. 숫자는 원본 파일의 어느 부분을 전송하는지를 나타냅니다. </p> <p>효율적인 파일 처리를 위해 다음과 같이 데이터 파일을 분할합니다. </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">압축되지 않음:1GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">압축:200-300MB </li> 
    </ul> <p>아래의 첫 번째 2개의 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> 파일 이름 예</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10자리 UTC UNIX 타임스탬프(초)입니다. 타임스탬프는 각 파일 이름을 고유하게 만드는 데 도움이 됩니다. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip은 FTP 파일 이름에 대해 허용되는 압축 형식입니다. 파일 압축을 사용하는 경우 파일 이름에 적절한 확장자가 있는지 확인합니다. </p> <p>압축된 파일은 3GB 이하여야 합니다. 파일 크기가 큰 경우 고객 지원 센터에 문의하십시오. Audience Manager은 대용량 파일을 처리할 수 있지만 파일 크기를 줄이고 데이터 전송을 보다 효율적으로 수행할 수 있습니다. <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">인바운드 데이터 전송 파일에 대한 파일 압축</a>을 참조하십시오 . </p> </td> 
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

[추가 ](assets/ftp_dpm_1234_1445374061.overwrite) 예제가 필요한 경우 샘플 파일을 다운로드합니다. 이 파일은 `.overwrite` 파일 확장자로 저장됩니다. 간단한 텍스트 편집기로 엽니다.

## 허용되는 파일 크기 {#accepted-file-sizes}

데이터를 [!DNL Audience Manager] / [!DNL FTP] 디렉토리로 전송할 때 파일 크기가 제한되므로 파일을 가장 빠르고 빨리 처리하기 위한 아래 수치를 고려합니다.

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

