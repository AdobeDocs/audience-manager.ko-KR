---
description: 이 페이지에 Audience Manager와 데이터 파트너 간의 사용자 지정 통합 목록이 표시됩니다.
seo-description: 이 페이지에 Audience Manager와 데이터 파트너 간의 사용자 지정 통합 목록이 표시됩니다.
seo-title: 사용자 지정 파트너 통합
solution: Audience Manager
title: 사용자 지정 파트너 통합
feature: 타사 통합
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 22%

---

# 사용자 지정 파트너 통합 {#custom-partner-integrations}

이 페이지에 Audience Manager와 데이터 파트너 간의 사용자 지정 통합 목록이 표시됩니다.

## Oracle 데이터 클라우드 {#oracle-data-cloud}

### 설명

Audience Manager는 인바운드 데이터 파일을 통해 Oracle Data Cloud for Audience Marketplace의 쿠키 및 모바일 ID 데이터를 통합합니다. 아래에 설명된 사용자 지정 통합 사양은 모바일 ID(IDFA 및 Android 장치 ID)가 포함된 인바운드 데이터 파일만 참조합니다.

### 통합 세부 사항

oracle Data Cloud에서 받은 인바운드 데이터 파일은 인바운드 데이터 파일에 대한 [Amazon S3 이름 및 파일 크기 요구 사항](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)에 설명된 표준 인바운드 파일 이름 구문과 [인바운드 데이터 파일 컨텐츠에 설명된 표준 인바운드 파일 컨텐츠 구문과 다릅니다.구문, 잘못된 문자, 변수 및 예](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

인바운드 데이터 파일에 대한 표준 구현 필드 외에 아래에 강조 표시된 요소가 필요합니다. 기타 모든 표준 필드 및 파일 이름 요소에 대한 설명은 위에 링크된 두 페이지에서 파일 이름 구문 및 파일 컨텐츠 구문 을 참조하십시오.

### 파일 이름 지정

ODC 파일 이름은 다음과 같이 구성됩니다.

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

`odc` 파일 이름 요소는 파일을 Data Cloud Oracle에서 가져오는 것으로 식별하고 Audience Manager 인바운드 파일 유효성 검사기에 이와 같이 처리하도록 지시합니다.

### 파일 내용

ODC 인바운드 데이터 파일의 필드는 아래 표시된 순서대로 나타나야 합니다.

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

`ID type`은(는) 다음 경우에 사용할 수 있습니다.

* IDFA
* Android 장치 ID

>[!IMPORTANT]
>
>동일한 인바운드 데이터 파일에서 IDFA 및 Android 장치 ID를 전송하지 마십시오.

## 샘플 ODC 인바운드 파일

[샘플 파일](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync)을 다운로드하십시오. 이 파일은 트레이트 ID에 대한 여러 IDFA를 38838. 이 파일은 표준 텍스트 편집기나 코드 편집기에서 열 수 있습니다.
