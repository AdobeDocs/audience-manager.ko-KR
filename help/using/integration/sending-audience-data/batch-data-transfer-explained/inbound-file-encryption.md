---
description: 데이터 파일을 Audience Manager으로 보낼 때 PGP 암호화로 암호화할 수 있습니다.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: 인바운드 데이터 유형에 대한 파일 PGP 암호화
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
TQID: 'https://experienceleague.adobe.com/eUhGeYNzSeQxjQ0VWydB8vnmgFh9GnWQQ3VmAG73w-k'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%
---
# 인바운드 데이터 유형에 대한 파일 PGP 암호화{#file-pgp-encryption-for-inbound-data-types}

데이터 파일을 Audience Manager으로 보낼 때 [!DNL PGP] 암호화로 암호화할 수 있습니다.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] 암호화에 파일 압축이 포함되어 있습니다. [!DNL PGP]개의 암호화된 인바운드 파일을 보낼 때 gzip(`.gz`)을 사용하여 [압축](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)하지 않도록 하십시오.
>
>[압축](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)된 [!DNL PGP]개의 암호화된 인바운드 파일도 Audience Manager에서 사용할 수 없습니다.

인바운드 데이터 파일을 암호화하려면 아래에 설명된 단계를 따르십시오.

1. [Audience Manager 공개 키](./assets/adobe_pgp.pub)를 다운로드합니다.
2. 공개 키를 신뢰할 수 있는 저장소로 가져옵니다.

   예를 들어 [!DNL GPG]을(를) 사용하는 경우 명령은 다음과 비슷할 수 있습니다.

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

   암호화된 모든 데이터는 파일 확장명으로 `.pgp` 또는 `.gpg`을(를) 사용해야 합니다(예: `ftp_dpm_100_123456789.sync.pgp` 또는 `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager은 [!DNL Advanced Encryption Standard (AES)] 데이터 암호화 알고리즘만 지원합니다. Audience Manager은 모든 키 크기를 지원합니다.
