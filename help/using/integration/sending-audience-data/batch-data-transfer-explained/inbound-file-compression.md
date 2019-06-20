---
description: 옵션으로 데이터 파일을 Audience Manager로 보낼 때 압축할 수 있습니다.
seo-description: 옵션으로 데이터 파일을 Audience Manager로 보낼 때 압축할 수 있습니다.
seo-title: 인바운드 데이터 전송 파일을 위한 파일 압축
solution: Audience Manager
title: 인바운드 데이터 전송 파일을 위한 파일 압축
uuid: 2 A 68 F 69 C -60 B 0-4002-863 B -302 D 2320 E 356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

옵션으로 데이터 파일을 Audience Manager로 보낼 때 압축할 수 있습니다.

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

또한 Audience Manager는 압축되지 않은 파일을 지원합니다.

>[!IMPORTANT]
>
>현재 동일한 인바운드 데이터 파일에서 암호화 및 압축을 지원하지 않습니다. You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Amazon S 3 압축

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. 압축 파일은 1 GB 이상이어야 합니다. 파일이 더 큰 경우 고객 지원 센터와 파일 및 전송 프로세스를 논의하십시오. Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>[!DNL FTP] 클라이언트는 압축되거나 암호화된 파일을 전송하기 위해 이진 모드를 사용해야 합니다. Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## 우수 사례

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* The maximum compressed file size for a `.gz` compressed file is 1 GB.
* 파일의 가장 빠른/가장 빠른 처리를 위한 최적의 분할 크기는 약 1 GB 압축되지 않거나 200-300 MB 압축됩니다.
* [!DNL Amazon S3] 업로드한 파일에 5 GB의 파일 크기 제한을 적용합니다.