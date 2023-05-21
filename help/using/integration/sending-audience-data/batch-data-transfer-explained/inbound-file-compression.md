---
description: 데이터 파일을 Audience Manager으로 보낼 때 압축할 수 있습니다.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: 인바운드 데이터 전송 파일에 대한 파일 압축
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 7%

---

# 인바운드 데이터 전송 파일에 대한 파일 압축{#file-compression-for-inbound-data-transfer-files}

데이터 파일을 Audience Manager으로 보낼 때 압축할 수 있습니다.

<!-- inbound-file-compression.xml -->

Audience Manager이 gzip 지원(`.gz`) 인바운드 비동기 데이터 전송을 위한 압축입니다.

Audience Manager은 압축되지 않은 파일도 지원합니다.

>[!IMPORTANT]
>
>gzip( )을 사용하여 압축된 인바운드 파일에 대한 암호화를 지원하지 않습니다.`.gz`).
>
>인바운드 파일을 암호화하거나 압축하려면 [PGP 암호화](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] 암호화에는 파일 압축이 포함됩니다.

## Amazon S3 압축

(으)로 게재 [!DNL Amazon S3], 다음을 사용해야 합니다. `.gz` 또는 압축이 해제된 파일. 압축된 파일은 1GB 이하여야 합니다. 파일이 더 큰 경우 고객 지원 센터와 파일 및 전송 프로세스에 대해 논의하십시오. 그러나 [!DNL Audience Manager] 대용량 파일을 처리할 수 있으므로 파일 크기를 줄이거나 데이터를 보다 효율적으로 전송할 수 있습니다.

>[!IMPORTANT]
>
>사용자 [!DNL FTP] 클라이언트는 압축되었거나 암호화된 파일을 전송하려면 이진 모드를 사용해야 합니다. 압축 또는 암호화된 파일 전송 [!DNL ASCII] 모드에서는 데이터 전송 파일이 손상됩니다.

## 우수 사례

* 파일은 다음과 같아야 합니다 [!DNL .gzip] 압축(및 [!DNL .gz] 파일 확장명).
* 의 최대 압축 파일 크기 `.gz` 압축된 파일은 1GB입니다.
* 가장 빠른/가장 빠른 파일 처리를 위해 최적의 분할 크기는 압축되지 않은 약 1GB 또는 압축된 200-300MB입니다.
* [!DNL Amazon S3] 은 업로드된 파일에 고유한 5GB 파일 크기 제한을 지정합니다.
