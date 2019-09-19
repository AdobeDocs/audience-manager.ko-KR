---
description: PGP 암호화를 사용하여 데이터 파일을 Audience Manager로 보낼 때 암호화할 수 있습니다.
seo-description: PGP 암호화를 사용하여 데이터 파일을 Audience Manager로 보낼 때 암호화할 수 있습니다.
seo-title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
solution: Audience Manager
title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
uuid: 89ace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 인바운드 데이터 유형에 대한 파일 PGP 암호화{#file-pgp-encryption-for-inbound-data-types}

데이터 파일을 Audience Manager로 보낼 때 [!DNL PGP] 암호화를 사용하여 데이터 파일을 암호화할 수 있습니다.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>현재 동일한 인바운드 데이터 파일에서 암호화 및 압축을 지원하지 않습니다. 인바운드 파일을 암호화하거나 [압축하도록](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 선택할 수 있습니다.

인바운드 데이터 파일을 암호화하려면 아래 설명된 단계를 따르십시오.

1. Audience Manager [공개 키를](./assets/adobe_pgp.pub)다운로드합니다.
1. 공용 키를 신뢰할 수 있는 스토어로 가져옵니다.

   예를 들어, 명령을 사용하는 [!DNL GPG]경우 다음과 유사할 수 있습니다.

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

   모든 암호화된 데이터는 파일 확장명(예: `.pgp` 또는 `.gpg` `ftp_dpm_100_123456789.sync.pgp` `ftp_dpm_100_123456789.overwrite.gpg`)으로 사용하거나 사용해야 합니다.

   >[!NOTE]
   >
   >Audience Manager는 [!DNL Advanced Encryption Standard (AES)] 데이터 암호화 알고리즘만 지원합니다. Audience Manager는 모든 키 크기를 지원합니다.