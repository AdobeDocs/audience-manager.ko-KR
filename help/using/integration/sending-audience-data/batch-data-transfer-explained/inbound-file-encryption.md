---
description: Audience Manager으로 보낼 때 PGP 암호화로 데이터 파일을 암호화할 수 있습니다.
seo-description: Audience Manager으로 보낼 때 PGP 암호화로 데이터 파일을 암호화할 수 있습니다.
seo-title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
solution: Audience Manager
title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 11%

---


# 인바운드 데이터 유형에 대한 파일 PGP 암호화{#file-pgp-encryption-for-inbound-data-types}

데이터 파일을 Audience Manager으로 보낼 때 [!DNL PGP] 암호화로 데이터 파일을 암호화할 수 있습니다.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 암호에는 파일 압축이 포함됩니다. [!DNL PGP] 암호화된 인바운드 파일을 전송할 때는 gzip(`.gz`)을 사용하여 [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)하지 않아야 합니다.
>
>[!DNL PGP] audience manager에서 압축도  [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 잘못된 암호화된 인바운드 파일입니다.

인바운드 데이터 파일을 암호화하려면 아래 단계를 따르십시오.

1. [Audience Manager 공개 키](./assets/adobe_pgp.pub)를 다운로드합니다.
2. 공용 키를 신뢰할 수 있는 스토어로 가져옵니다.

   예를 들어 [!DNL GPG]을 사용하는 경우 명령은 다음과 유사할 수 있습니다.

   `gpg --import adobe_pgp.pub`

3. 다음 명령을 실행하여 키를 올바르게 가져왔는지 확인합니다.

   `gpg --list-keys`

   다음과 유사한 메시지가 표시됩니다.

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. 다음 명령을 사용하여 인바운드 데이터를 암호화합니다.

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   암호화된 모든 데이터는 파일 확장자(예:`.pgp` 또는 `.gpg`).`ftp_dpm_100_123456789.sync.pgp``ftp_dpm_100_123456789.overwrite.gpg`

   >[!NOTE]
   >
   >Audience Manager은 [!DNL Advanced Encryption Standard (AES)] 데이터 암호화 알고리즘만 지원합니다. Audience Manager은 모든 키 크기를 지원합니다.
