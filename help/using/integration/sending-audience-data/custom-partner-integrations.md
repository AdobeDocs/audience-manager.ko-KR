---
description: 이 페이지에 Audience Manager와 데이터 파트너 간의 사용자 지정 통합 목록이 표시됩니다.
seo-description: 이 페이지에 Audience Manager와 데이터 파트너 간의 사용자 지정 통합 목록이 표시됩니다.
seo-title: 맞춤형 파트너 통합
solution: Audience Manager
title: 맞춤형 파트너 통합
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Custom Partner Integrations {#custom-partner-integrations}

이 페이지에 Audience Manager와 데이터 파트너 간의 사용자 지정 통합 목록이 표시됩니다.

## Oracle Data Cloud {#oracle-data-cloud}

**설명**

Audience Manager는 인바운드 데이터 파일을 통해 Oracle Data Cloud for Audience Marketplace의 쿠키 및 모바일 ID 데이터를 통합합니다. 아래 설명된 사용자 정의 통합 사양은 모바일 ID (IDFA 및 Android 디바이스 ID) 가 포함된 인바운드 데이터 파일에만 적용됩니다.

<br> 

**통합 관련 사항**

Inbound Data Files received from the Oracle Data Cloud differ from the standard inbound file name syntax described in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) and from the standard inbound file content syntax described in [Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

인바운드 데이터 파일에 대한 표준 구현 필드 외에 아래 강조된 요소가 필요합니다. 다른 모든 표준 필드 및 파일 이름 요소에 대한 설명은 위에 연결된 두 페이지에서 파일 이름 구문 및 파일 내용 구문을 참조하십시오.

<br> 

**파일 이름 지정**

ODC 파일 이름은 다음과 같이 구성됩니다.

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

`odc` 파일 이름 요소는 Oracle Data Cloud에서 가져온 파일을 식별하고 Audience Manager 인바운드 파일 유효성 검사기에 이러한 파일을 처리하도록 지시합니다.

<br> 

**파일 컨텐츠**

ODC 인바운드 데이터 파일의 필드는 아래 표시된 순서대로 표시되어야 합니다.

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;user ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,...</pre>

The `ID type` can be:

* IDFA
* Android 장치 ID

>[!IMPORTANT]
>
>동일한 인바운드 데이터 파일에서 IDFA 및 Android 장치 ID를 보내지 마십시오.

<br> 

**샘플 ODC 인바운드 파일**

[샘플 파일을 다운로드합니다](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). 이 파일은 트레이트 ID 38838에 대한 여러 idfas를 적용해 줍니다. 이 파일은 표준 텍스트 편집기 또는 코드 편집기에서 열 수 있습니다.