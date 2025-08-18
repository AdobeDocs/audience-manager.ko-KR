---
description: Transfer-control(.info) 파일은 파트너가 Audience Manager에서 파일 전송을 올바르게 처리했는지 확인할 수 있도록 파일 전송에 대한 메타데이터 정보를 제공합니다.
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: 로그 파일 전송을 위한 전송 제어 파일
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# 로그 파일 전송을 위한 전송 제어 파일 {#transfer-control-files-for-log-file-transfers}

전송 제어([!DNL .info]) 파일은 파트너가 Audience Manager에서 파일 전송을 올바르게 처리했는지 확인할 수 있도록 파일 전송에 대한 메타데이터 정보를 제공합니다.

[!DNL Audience Manager]이(가) 파일을 전송할 때마다 전송 제어 파일을 파트너에게 보냅니다. [!DNL FTP] 게시자의 다중 스레드 특성으로 인해 실제 파일 전송이 완료되기 전에 전송 제어 파일이 전송될 수 있습니다.

[!DNL .info] 파일의 메타데이터를 통해 파트너는 다음을 수행할 수 있습니다.

* 전체 전송 주기가 완료되는 시기(시퀀스의 총 파일 수가 전달됨)를 결정합니다.
* 파일 크기(바이트)와 총 줄 수를 검사하여 시퀀스의 지정된 파일이 완료/올바른지 확인합니다.
* 원시 파일의 행 수를 확인하면 파일이 수신 단의 데이터베이스에 로드된 후의 행 수(행의 파일 크기)를 구합니다.

## 파일 이름 지정 규칙 {#file-naming-conventions}

전송 제어 파일의 이름이 배치/시퀀스의 루트와 같고 파일 확장명이 [!DNL .info]입니다.

예를 들어 시퀀스의 첫 번째 파일 이름이 [!DNL ftp_12345_67890_full_1500727351632-1.sync]인 경우 컨트롤 파일의 이름은 [!DNL ftp_12345_67890_iter_1500727351632.info]이(가) 됩니다.

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

>[!NOTE]
>
> 일괄 처리 총수는 [!DNL .info] 파일 자체를 제외합니다. 즉, 합계에 [!DNL .info] 파일, 바이트 크기 또는 줄 수가 포함되지 않습니다.
>
> 파일 및 라인 수의 바이트 크기는 모든 헤더 및 스페이서(빈) 라인/행을 포함합니다. 실제 데이터 라인/행의 개수를 구하려면 헤더를 뺍니다.
>
> 일괄 처리의 총 행과 총 바이트 크기는 모든 헤더와 공간 행을 포함합니다.
