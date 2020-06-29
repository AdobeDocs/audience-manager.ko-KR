---
description: 데이터 파일을 Audience Manager으로 보낼 때 데이터 파일을 압축할 수 있습니다.
seo-description: 데이터 파일을 Audience Manager으로 보낼 때 데이터 파일을 압축할 수 있습니다.
seo-title: 인바운드 데이터 전송 파일에 대한 파일 압축
solution: Audience Manager
title: 인바운드 데이터 전송 파일에 대한 파일 압축
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 10%

---


# 인바운드 데이터 전송 파일에 대한 파일 압축{#file-compression-for-inbound-data-transfer-files}

데이터 파일을 Audience Manager으로 보낼 때 압축할 수 있습니다.

<!-- inbound-file-compression.xml -->

Audience Manager은 인바운드, 비동기 데이터 전송을 위해 gzip(`.gz`) 압축을 지원합니다.

또한 Audience Manager은 압축되지 않은 파일도 지원합니다.

>[!IMPORTANT]
>
>gzip(`.gz`)을 사용하여 압축된 인바운드 파일의 암호화는 지원되지 않습니다.
>
>인바운드 파일을 암호화하고 압축하려면 [PGP 암호화를 사용하십시오](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] 암호에는 파일 압축이 포함됩니다.

## Amazon S3 압축

전달하려면 [!DNL Amazon S3]파일 `.gz` 또는 압축되지 않은 파일을 사용해야 합니다. 압축된 파일은 1GB 이하여야 합니다. 파일이 더 큰 경우 고객 지원 센터에 파일 및 전송 프로세스에 대해 문의하십시오. 대용량 파일을 처리할 [!DNL Audience Manager] 수 있지만 파일 크기를 줄이거나 보다 효율적으로 데이터를 전송할 수 있는 방법이 있을 수 있습니다.

>[!IMPORTANT]
>
>클라이언트는 [!DNL FTP] 이진 모드를 사용하여 압축되거나 암호화된 파일을 전송해야 합니다. 압축 또는 암호화된 파일이 [!DNL ASCII] 모드로 전송되면 데이터 전송 파일이 손상됩니다.

## 우수 사례

* 파일은 [!DNL .gzip] 압축해야 하며 확장자가 [!DNL .gz] 있어야 합니다.
* 압축된 파일의 최대 압축 파일 크기는 1GB입니다. `.gz`
* 파일의 가장 빠르고 빠른 처리를 위해 압축되지 않은 1GB 또는 200-300MB의 압축 크기로 최적의 분할 크기를 설정할 수 있습니다.
* [!DNL Amazon S3] 업로드된 파일에 고유한 5GB 파일 크기 제한을 적용합니다.
