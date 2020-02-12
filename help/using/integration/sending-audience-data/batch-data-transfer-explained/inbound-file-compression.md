---
description: 데이터 파일을 Audience Manager로 보낼 때 데이터 파일을 압축할 수 있습니다.
seo-description: 데이터 파일을 Audience Manager로 보낼 때 데이터 파일을 압축할 수 있습니다.
seo-title: 인바운드 데이터 전송 파일에 대한 파일 압축
solution: Audience Manager
title: 인바운드 데이터 전송 파일에 대한 파일 압축
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: 8d2d841f8e94fd67c2165eb280b85ab18001d77e

---


# 인바운드 데이터 전송 파일에 대한 파일 압축{#file-compression-for-inbound-data-transfer-files}

데이터 파일을 Audience Manager로 보낼 때 데이터 파일을 압축할 수 있습니다.

<!-- inbound-file-compression.xml -->

Audience Manager는 인바운드 비동기 데이터 전송을 위해 gzip( `.gz`) 압축을 지원합니다.

Audience Manager는 압축되지 않은 파일도 지원합니다.

>[!IMPORTANT]
>
>현재 동일한 인바운드 데이터 파일에서 암호화 및 압축을 지원하지 않습니다. 인바운드 파일을 [암호화](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) 또는 압축하도록 선택할 수 있습니다.
>
> 그러나 PGP 암호에는 내장 압축이 포함되어 있습니다.

## Amazon S3 압축

전달하려면 [!DNL Amazon S3]파일 `.gz` 또는 압축되지 않은 파일을 사용해야 합니다. 압축된 파일은 1GB 이하여야 합니다. 파일이 더 큰 경우 해당 파일에 대해 알아보고 고객 지원 센터에 문의하십시오. 대용량 파일도 처리할 [!DNL Audience Manager] 수 있지만 파일 크기를 줄이거나 보다 효율적으로 데이터를 전송할 수 있는 방법이 있을 수 있습니다.

>[!IMPORTANT]
>
>클라이언트는 이진 모드를 사용하여 압축되거나 암호화된 파일을 전송해야 [!DNL FTP] 합니다. 압축 또는 암호화된 파일을 [!DNL ASCII] 모드로 전송하면 데이터 전송 파일이 손상됩니다.

## 우수 사례

* 파일을 [!DNL .gzip] 압축해야 합니다(그리고 [!DNL .gz] 파일 확장명이 있어야 합니다).
* 압축된 파일의 최대 압축 파일 크기는 1GB입니다. `.gz`
* 파일 처리 속도가 빠르고 빨라진 최적 분할 크기는 약 1GB 압축되지 않았거나 200-300MB 압축입니다.
* [!DNL Amazon S3] 업로드된 파일에 고유한 5GB 파일 크기 제한을 적용합니다.
