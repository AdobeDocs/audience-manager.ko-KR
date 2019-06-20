---
description: 옵션으로, Audience Manager로 보낼 때 PGP 암호화를 사용하여 데이터 파일을 암호화할 수 있습니다.
seo-description: 옵션으로, Audience Manager로 보낼 때 PGP 암호화를 사용하여 데이터 파일을 암호화할 수 있습니다.
seo-title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
solution: Audience Manager
title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
uuid: 89 CAACE 1-0259-48 FC -865 B-D 525 EC 7822 F 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>현재 동일한 인바운드 데이터 파일에서 암호화 및 압축을 지원하지 않습니다. You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

아래 설명된 단계에 따라 인바운드 데이터 파일을 암호화합니다.

1. [Audience Manager 공개 키를 다운로드합니다](./assets/adobe_pgp.pub).
1. 공개 키를 신뢰할 수 있는 스토어로 가져옵니다.

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. 다음 명령을 실행하여 키를 올바르게 가져왔는지 확인합니다.

   `gpg --list-keys`

   다음과 유사한 메시지가 표시됩니다.

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. 다음 명령을 사용하여 인바운드 데이터를 암호화합니다.

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager는 모든 키 크기를 지원합니다.