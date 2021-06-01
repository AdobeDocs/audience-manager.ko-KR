---
description: 옵션으로 데이터 파일을 Audience Manager에 보낼 때 데이터 파일을 압축할 수 있습니다.
seo-description: 옵션으로 데이터 파일을 Audience Manager에 보낼 때 데이터 파일을 압축할 수 있습니다.
seo-title: 인바운드 데이터 전송 파일에 대한 파일 압축
solution: Audience Manager
title: 인바운드 데이터 전송 파일에 대한 파일 압축
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: 인바운드 데이터 전송
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 11%

---

# 인바운드 데이터 전송 파일에 대한 파일 압축{#file-compression-for-inbound-data-transfer-files}

데이터 파일을 Audience Manager으로 보낼 때 데이터 파일을 압축할 수 있습니다.

<!-- inbound-file-compression.xml -->

Audience Manager은 인바운드 비동기 데이터 전송을 위해 gzip(`.gz`) 압축을 지원합니다.

Audience Manager은 압축되지 않은 파일도 지원합니다.

>[!IMPORTANT]
>
>gzip(`.gz`)을 사용하여 압축된 인바운드 파일에 대한 암호화를 지원하지 않습니다.
>
>인바운드 파일을 암호화하고 압축하려면 [PGP 암호화](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)를 사용합니다. [!DNL PGP] 암호에는 파일 압축이 포함됩니다.

## Amazon S3 압축

[!DNL Amazon S3]에 전달하려면 `.gz` 또는 압축되지 않은 파일을 사용해야 합니다. 압축된 파일은 1GB 이상이어야 합니다. 파일이 더 큰 경우 고객 지원 센터에서 파일 및 전송 프로세스에 대해 논의하십시오. [!DNL Audience Manager] 은 매우 큰 파일을 처리할 수 있지만 파일 크기를 줄이거나 데이터를 보다 효율적으로 전송할 수 있는 방법이 있을 수 있습니다.

>[!IMPORTANT]
>
>[!DNL FTP] 클라이언트는 이진 모드를 사용하여 압축되었거나 암호화된 파일을 전송해야 합니다. [!DNL ASCII] 모드로 보낸 압축되었거나 암호화된 파일이 데이터 전송 파일을 손상시킵니다.

## 우수 사례

* 파일은 [!DNL .gzip] 압축되어야 합니다(그리고 [!DNL .gz] 파일 확장자가 있어야 함).
* `.gz` 압축 파일의 최대 압축 파일 크기는 1GB입니다.
* 파일 처리 속도가 가장 빠르거나 가장 빠른 최적의 분할 크기는 약 1GB 압축되지 않거나 200-300MB로 압축됩니다.
* [!DNL Amazon S3] 업로드된 파일에 고유한 5GB 파일 크기 제한을 적용합니다.
