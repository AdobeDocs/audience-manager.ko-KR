---
description: 데이터를 Audience Manager으로 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기에 대해 설명합니다. 데이터를 Audience Manager/Amazon S3 디렉토리에 보낼 때 이러한 사양에 따라 파일의 이름과 크기를 설정합니다.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: 인바운드 데이터 파일에 대한 Amazon S3 이름 및 파일 크기 요구 사항
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 2%

---

# 인바운드 데이터 파일에 대한 [!DNL Amazon S3] 이름 및 파일 크기 요구 사항 {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

[!DNL Audience Manager]에 데이터를 보낼 때 따라야 하는 필수 필드, 구문, 이름 지정 규칙 및 파일 크기를 설명합니다. 데이터를 [!DNL Audience Manager] / [!DNL Amazon S3] 디렉터리로 보낼 때 이러한 사양에 따라 파일의 이름과 크기를 설정하십시오.

>[!NOTE]
>
>텍스트 스타일(`monospaced text`, *기울임체*, 괄호 `[ ]``( )` 등)은 이 문서에서는 코드 요소 및 옵션을 나타냅니다. 자세한 내용은 [코드 및 텍스트 요소에 대한 스타일 규칙](../../../reference/code-style-elements.md)을 참조하십시오.

## 파일 이름 구문 {#file-name-syntax}

[!DNL S3] 파일 이름에는 다음과 같은 필수 요소와 선택적 요소가 포함되어 있습니다.

* **[!DNL S3]접두사:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **파일 이름 요소:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

허용되는 다른 파일 이름 형식은 [사용자 지정 파트너 통합](/help/using/integration/sending-audience-data/custom-partner-integrations.md)을 참조하십시오.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager]은(는) [!DNL ASCII] 및 [!DNL UTF-8]개의 인코딩된 파일만 처리합니다.

### 요소 이름 지정

테이블은 [!DNL S3] 파일 이름의 요소를 정의합니다.

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 이름 요소 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Amazon S3 버킷의 경로 및 이름입니다. S3 디렉토리 이름, 경로 및 자격 증명은 계정 관리자에게 문의하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>파일을 S3 버킷으로 보낼 때의 타임스탬프(UTC 시간 기준)입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>데이터 파일에 고유한 Audience Manager ID, Android ID, iOS ID 또는 <a href="/help/using/features/global-data-sources.md"> 글로벌 데이터 원본</a>에 속하는 기타 ID가 포함되어 있는지 여부를 <span class="keyword"> 사용자</span>에게 알리는 ID입니다. 다음 옵션을 적용합니다.</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>데이터 Source ID(데이터 공급자 ID라고도 함):</b> Audience Manager이 데이터 소스에 할당하는 고유한 ID입니다(ID </a>의 Audience Manager <a href="/help/using/reference/ids-in-aam.md"> 인덱스 참조). 고유한 사용자 ID가 포함된 데이터를 보낼 때 파일 이름에 이 할당된 ID를 사용하십시오. 예를 들어 <code>...ftp_dpm_21_123456789.sync</code>은(는) <span class="keyword"> Audience Manager</span>에게 데이터 원본 21에 속하는 ID로 데이터를 온보딩하도록 지시합니다. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android ID(GAID):</b> 데이터 파일 이름에 Android ID가 포함된 경우 ID 20914을 사용합니다. Android ID를 사용할 때는 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 필드를 사용해야 합니다. 예를 들어 <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code>은(는) 데이터 파일에 Android ID만 포함되어 있으며 ID가 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 데이터 소스에 속하는 트레이트에 적합해야 한다고 <span class="keyword"> Audience Manager</span>에 알려줍니다.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS ID(IDFA):</b> 데이터 파일 이름에 iOS ID가 포함된 경우 ID 20915을 사용합니다. iOS ID를 사용할 때는 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 필드를 사용해야 합니다. 예를 들어 <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code>은(는) 데이터 파일에 iOS ID만 포함되어 있으며 ID가 <code><i>_DPID_TARGET_DATA_OWNER</i></code> 데이터 소스에 속하는 트레이트에 적합해야 한다고 <span class="keyword"> Audience Manager</span>에 알려줍니다.</li>
     <li> <b>다른 글로벌 데이터 원본에 속하는 ID</b>: RIDA(Advertising), MAID(Microsoft Advertising ID) 및 기타 ID용 Roku ID를 온보딩할 수 있습니다. <a href="/help/using/features/global-data-sources.md"> 전역 데이터 원본 문서</a>에 설명된 대로 각 데이터 원본에 해당하는 ID를 사용하십시오.</li> 
    </ul> <p> <p>참고: 데이터 파일에서 ID 유형을 혼합하지 마십시오. 예를 들어 파일 이름에 Android 식별자가 포함된 경우 데이터 파일에 iOS ID 또는 사용자 ID를 추가하지 마십시오. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>이 필드는 데이터를 온보딩할 데이터 소스를 Audience Manager에게 알려줍니다. DPID를 Android ID, iOS ID 또는 글로벌 데이터 소스에 속하는 다른 ID로 설정하는 경우 이 필드는 필수입니다. 이렇게 하면 Audience Manager이 파일 데이터를 다시 조직에 연결할 수 있습니다. <br> 이 대상 데이터 원본은 회사가 소유해야 합니다. 제2자 데이터 공유를 위해 데이터를 다른 회사에 속한 대상 데이터 소스로 수집하려면 회사와 대상 데이터 소스 간에 액세스 매핑이 있어야 합니다. 매핑을 설정하려면 Adobe 컨설턴트나 고객 지원에 문의하십시오.</p> <p><b>중요 참고 사항:</b> <i>기존 데이터 공유 관계(2022년 3월 14일 이전에 데이터를 온보딩한 다른 회사에 속한 대상 데이터 소스의 경우)에 대한 매핑을 요청할 필요가 없습니다</i>. PID에 속하는 대상 데이터 소스에 데이터를 온보딩할 때도 매핑이 필요하지 않습니다. </p> <p>예: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code>은(는) 데이터 원본 21에 속하는 트레이트 또는 신호에 대해 데이터 원본 33에 속하는 고객 ID를 검증하고 있음을 Audience Manager에게 알려 줍니다. </li> 
     <li> <b>Android ID(GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code>은(는) 데이터 파일에 Android ID만 포함되어 있으며 ID가 데이터 소스 21에 속하는 트레이트에 적합해야 한다고 <span class="keyword"> Audience Manager</span>에게 알려줍니다.</li> 
     <li> <b>iOS ID(IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code>은(는) 데이터 파일에 iOS ID만 포함되어 있으며 ID가 데이터 소스 21에 속하는 트레이트에 적합해야 한다고 <span class="keyword"> Audience Manager</span>에게 알려 줍니다.</li>
     <li> <b>다른 전역 데이터 원본에 속하는 ID</b>: <code>...ftp_dpm_121963_21_1234567890.sync</code>은(는) <span class="keyword"> Audience Manager</span>에게 데이터 파일에 Roku ID만 포함되어 있으며 ID가 데이터 원본 21에 속하는 트레이트에 적합해야 한다고 알립니다. <a href="/help/using/features/global-data-sources.md"> 전역 데이터 원본 문서</a>에 설명된 대로 각 데이터 원본에 해당하는 ID를 사용하십시오.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에서 사용하는 회사 또는 조직 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>10자리 UTC UNIX 타임스탬프(초). 타임스탬프는 각 파일 이름을 고유하게 만드는 데 도움이 됩니다. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>다음을 포함하는 동기화 옵션: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: 서드파티 데이터 공급자가 Audience Manager 시스템에서 추가하거나 제거할 트레이트를 사용자별로 전송하는 일반적인 시나리오입니다. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: 데이터 공급자가 Audience Manager에 있는 이 데이터 공급자에 대한 이 사용자의 기존 타사 트레이트를 모두 덮어써야 하는 트레이트 목록을 사용자별로 보낼 수 있습니다. 덮어쓰기 파일에 모든 사용자를 포함할 필요는 없습니다. 변경하려는 사용자만 포함합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>정수. 처리 시간을 향상시키기 위해 큰 파일을 여러 부분으로 분할할 때 사용됩니다. 번호는 보내는 원본 파일의 일부를 나타냅니다. </p> <p>효율적인 파일 처리를 위해 데이터 파일을 표시된 대로 분할합니다. </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">압축되지 않음: 1GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">압축: 200-300MB </li> 
    </ul> <p>아래의 처음 2개의 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> 파일 이름 예제</a>를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Amazon S3에 파일을 보낼 때 gzip 압축만 사용하십시오. 압축하면 이 파일의 확장명은 <code> .gz</code>입니다. .zip 압축을 사용하지 마십시오. </p> <p>압축된 파일은 3GB 이하여야 합니다. 파일이 더 큰 경우 고객 지원 센터에 문의하십시오. Audience Manager은 대용량 파일을 처리할 수 있지만 파일 크기를 줄이고 데이터 전송을 보다 효율적으로 수행할 수 있습니다. 인바운드 데이터 전송 파일에 대한 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> 파일 압축</a>을(를) 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 파일 이름 예 {#file-name-examples}

다음 예제에서는 올바른 형식의 파일 이름을 보여 줍니다. 파일 이름이 비슷해 보일 수 있습니다.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

추가 예제를 원하는 경우 샘플 파일을 [다운로드](assets/ftp_dpm_1234_1445374061.overwrite)할 수 있습니다. 이 파일은 `.overwrite` 파일 확장명으로 저장되었습니다. 간단한 텍스트 편집기로 엽니다.

## 허용되는 파일 크기 {#accepted-file-sizes}

데이터를 [!DNL Audience Manager]/[!DNL Amazon S3] 디렉터리로 보낼 때 파일의 가장 빠른/가장 빠른 처리와 파일 크기 제한에 대해 아래 수치를 고려하십시오.

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
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>압축되지 않음</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>


>[!NOTE]
>
>인바운드 데이터 유효성 검사 프로세스는 빈 파일을 잘못된 것으로 표시하여 처리하지 않습니다.

## 라인 길이 제한 {#line-limits}

인바운드 데이터 파일의 라인 길이는 102400바이트로 제한됩니다. 이 한도를 초과하는 라인은 전송에서 제외됩니다.

>[!MORELIKETHIS]
>
>* [인바운드 데이터 파일에 대한 FTP 이름 요구 사항](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
