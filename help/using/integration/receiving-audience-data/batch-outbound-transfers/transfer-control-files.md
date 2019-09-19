---
description: Transfer-control(.info) 파일은 파트너가 Audience Manager가 파일 전송을 올바르게 처리했는지 확인할 수 있도록 파일 전송에 대한 메타데이터 정보를 제공합니다.
seo-description: Transfer-control(.info) 파일은 파트너가 Audience Manager가 파일 전송을 올바르게 처리했는지 확인할 수 있도록 파일 전송에 대한 메타데이터 정보를 제공합니다.
seo-title: 로그 파일 전송을 위한 전송 제어 파일
solution: Audience Manager
title: 로그 파일 전송을 위한 전송 제어 파일
uuid: ef58213e-7b37-4c5a-8556-0de695706793
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# 로그 파일 전송을 위한 전송 제어 파일 {#transfer-control-files-for-log-file-transfers}

Transfer-control ([!DNL .info]) 파일은 파트너가 Audience Manager가 파일 전송을 올바르게 처리했는지 확인할 수 있도록 파일 전송에 대한 메타데이터 정보를 제공합니다.

[!DNL Audience Manager] 전송 제어 파일을 전송할 때마다 파트너에게 전송합니다. 게시자의 다중 스레드 특성으로 인해 전송 제어 파일이 실제 파일 전송이 완료되기 전에 전송될 수 있습니다. [!DNL FTP]

이 파일의 메타데이터를 [!DNL .info] 통해 파트너는 다음을 수행할 수 있습니다.

* 전체 전송 주기가 완료된 시기(시퀀스에 있는 총 파일 수 제공)를 결정합니다.
* 시퀀스에 있는 지정된 파일의 전체/정답 여부 확인(파일의 크기(바이트 단위) 및 줄 수 확인);
* Raw 파일의 행 수를 확인하여 수신 끝(파일 크기)에 있는 데이터베이스에 파일이 로드된 후의 행 수를 기준으로 합니다.

## 파일 이름 지정 규칙 {#file-naming-conventions}

전송 제어 파일의 이름은 파일 확장명이 .s인 일괄 처리/시퀀스의 루트와 동일합니다. [!DNL .info]

예를 들어 시퀀스의 첫 번째 파일 이름이 다음과 같이 지정된 경우:그러면 [!DNL ftp_12345_67890_full_1500727351632-1.sync]컨트롤 파일의 이름이 [!DNL ftp_12345_67890_iter_1500727351632.info]지정됩니다.

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
> 일괄 처리 총수는 [!DNL .info] 파일 자체에만 적용됩니다. 즉, 합계에 [!DNL .info] 파일, 바이트 크기 또는 행 수가 포함되지 않습니다.
>
> 파일 및 행 수의 바이트 크기는 헤더와 스페이서(빈) 행/행을 포함합니다. 실제 데이터 라인/행 수를 가져오려면 머리글을 제외합니다.
>
> 묶음 및 총 바이트 크기의 전체 줄은 모든 머리글 행과 공백 행을 포함합니다.