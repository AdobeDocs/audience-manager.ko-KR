---
description: 데이터 파일을 Audience Manager으로 보낼 때 PGP 암호화로 암호화할 수 있습니다.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 8%

---

# 인바운드 데이터 유형에 대한 파일 PGP 암호화{#file-pgp-encryption-for-inbound-data-types}

다음을 사용하여 데이터 파일을 암호화할 수 있습니다 [!DNL PGP] Audience Manager에 보낼 때 암호화.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 암호화에는 파일 압축이 포함됩니다. 전송 시 [!DNL PGP] 암호화된 인바운드 파일을 사용하여 [압축](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) gzip(`.gz`).
>
>[!DNL PGP] 또한 암호화된 인바운드 파일 [압축됨](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) 은(는) Audience Manager에서 잘못되었습니다.

인바운드 데이터 파일을 암호화하려면 아래에 설명된 단계를 따르십시오.

1. 다운로드 [Audience Manager 공개 키](./assets/adobe_pgp.pub).
2. 공개 키를 신뢰할 수 있는 저장소로 가져옵니다.

   예를 들어 [!DNL GPG], 명령은 다음과 유사할 수 있습니다.

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

   암호화된 모든 데이터는 다음을 사용해야 합니다. `.pgp` 또는 `.gpg` 를 파일 확장명으로(예: `ftp_dpm_100_123456789.sync.pgp` 또는 `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager은 [!DNL Advanced Encryption Standard (AES)] 데이터 암호화 알고리즘. Audience Manager은 모든 키 크기를 지원합니다.
