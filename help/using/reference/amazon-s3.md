---
description: Amazon Simple Storage Service (Amazon S3)에 대한 정보입니다.
seo-description: Amazon Simple Storage Service (Amazon S3)에 대한 정보입니다.
seo-title: Amazon S3 정보
solution: Audience Manager
title: Amazon S3 정보
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: 참조
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3: 설명{#amazon-s-about}

Amazon Simple Storage Service (Amazon S3)에 대한 정보입니다.

가장 좋은 방법으로서, 파일에서 를 가져오고 파트너에게 전달하는 방법으로 FTP 대신 Amazon S3를 사용하는 것이 좋습니다. Amazon S3는 웹 어디에서나 모든 양의 데이터를 저장하고 검색하는 데 사용할 수 있는 간단한 웹 서비스 인터페이스를 제공합니다.

Amazon S3를 사용하면 다음과 같은 이점이 있습니다.

* **확장성:** Amazon S3는 거의 무제한 확장성을 제공합니다.
* **안정성 및 가용성:** Amazon S3는 고내구성 및 고가용성 스토리지 서비스를 제공합니다.
* **속도:** Amazon S3를 사용하면 빠른 데이터 전송을 수행할 수 있습니다.
* **사용 편의성:** Amazon S3는 사용과 구현이 매우 쉽습니다. 구현은 약 1시간 후에 작동 및 실행될 수 있습니다. FTP 디렉토리를 구현하는 데 훨씬 시간이 오래 걸립니다.
* **다중 부분 업로드:** 대용량 파일을 다중 부분 파일 업로드처럼 빠르고 효율적으로 업로드할 수 있습니다.
* **보안:** Amazon S3는 강력한 보안을 제공합니다.

   * 모든 디렉토리는 해당 고객 또는 클라이언트에만 액세스할 수 있습니다.
   * 업로드 및 다운로드에 대한 HTTPS 프로토콜 지원. [!DNL Audience Manager]에서 파일을 전송할 때는 항상 HTTPS를 사용해야 합니다.
   * Amazon S3는 [아웃바운드 데이터 파일](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)을 암호화하기 위한 암호 대기 시간을 제공합니다. Adobe에서는 [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) 암호화 방법을 사용하여 암호화 키를 Amazon S3에서 자동으로 생성 및 관리할 수 있습니다.

* **디버그 및 백업 지원:** Amazon S3 [!DNL Audience Manager] 을 사용하면 파일의 정확한 사본을 유지하여 디버깅이나 다시 전송할 수 있습니다.

Amazon S3에 대한 자세한 내용은 다음 리소스를 참조하십시오.

[Amazon 웹 서비스 웹 사이트의 Amazon Simple Storage Service(Amazon S3)](https://aws.amazon.com/s3/) 에 게시됩니다.

[AWS 설명서 웹 사이트](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 에서 Amazon Simple Storage Service를 시작합니다.
