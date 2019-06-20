---
description: Transfer-Control (.info) 파일은 파트너가 Audience Manager에서 파일 전송을 올바르게 처리했는지 확인할 수 있도록 파일 전송에 대한 메타데이터 정보를 제공합니다.
seo-description: Transfer-Control (.info) 파일은 파트너가 Audience Manager에서 파일 전송을 올바르게 처리했는지 확인할 수 있도록 파일 전송에 대한 메타데이터 정보를 제공합니다.
seo-title: 로그 파일 전송을 위한 전송 제어 파일
solution: Audience Manager
title: 로그 파일 전송을 위한 전송 제어 파일
uuid: EF 58213 E -7 B 37-4 C 5 A -8556-0 DE 695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Transfer-Control Files for Log File Transfers {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.

[!DNL Audience Manager] 모든 파일 전송 시 파트너에게 전송 제어 파일을 전송합니다. [!DNL FTP] 게시자의 다중 스레드 특성으로 인해 실제 파일 전송을 완료하기 전에 전송 제어 파일이 전송될 수 있습니다.

[!DNL .info] 파일의 메타데이터를 통해 파트너는 다음을 수행할 수 있습니다.

* 전체 전환 주기가 완료되는 시점을 결정합니다 (시퀀스에 있는 파일의 총 수).
* 시퀀스에서 지정된 파일이 완료/올바른지 여부를 결정합니다 (바이트 크기와 총 라인 수 검사).
* Raw 파일의 행 수 확인 받는 쪽 (행의 파일 크기) 에 있는 데이터베이스에 파일이 로드된 행 수를 확인합니다.

## File Naming Conventions {#file-naming-conventions}

The transfer-control file has the same name as the root of the batch/sequence with a [!DNL .info] file extension.s

For example, if the first file in the sequence were named: [!DNL ftp_12345_67890_full_1500727351632-1.sync], the control file would be named [!DNL ftp_12345_67890_iter_1500727351632.info].

## 파일 형식 {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[참고]
>
> The batch total numbers are exclusive of the [!DNL .info] file itself. That is, the totals do not include the [!DNL .info] file, its byte size, or its line count.
>
> 파일 및 행 수에 대한 바이트 크기는 머리글 및 스페이서 (공백) 라인/행을 포함합니다. 실제 데이터 행/행 수를 가져오려면 헤더를 뺍니다.
>
> 총 묶음 및 총 바이트 크기는 머리글 및 공간 행을 포함할 수 있습니다.