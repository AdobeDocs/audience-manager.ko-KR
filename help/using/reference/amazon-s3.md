---
description: Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.
seo-description: Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.
seo-title: Amazon S3 정보
solution: Audience Manager
title: Amazon S3 정보
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3: 설명{#amazon-s-about}

Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.

파일을 가져와 파트너에게 전달하는 방법으로 FTP 대신 Amazon S3를 사용하는 것이 좋습니다. Amazon S3는 웹 상에서 언제 어디서나 원하는 양의 데이터를 저장하고 검색하는 데 사용할 수 있는 간단한 웹 서비스 인터페이스를 제공합니다.

Amazon CS3를 사용하면 다음과 같은 이점이 있습니다.

* **확장성:** Amazon S3는 거의 무한한 확장성을 제공합니다.
* **안정성 및 가용성:** Amazon S3는 높은 내구성과 고가용성 스토리지 서비스를 제공합니다.
* **속도:** Amazon S3를 사용하면 데이터를 신속하게 전송할 수 있습니다.
* **사용 용이성:** Amazon S3는 사용 및 구현이 매우 쉽습니다. 약 1시간 안에 구현을 시작하고 실행할 수 있습니다. FTP 디렉토리 구현은 훨씬 더 오래 걸립니다.
* **다중 부분 업로드:** 대용량 파일은 여러 부분으로 구성된 파일을 업로드하는 것처럼 빠르고 효율적으로 업로드할 수 있습니다.
* **보안:** Amazon S3는 강력한 보안을 제공합니다.

   * 모든 디렉토리는 해당 고객 또는 클라이언트에서만 액세스할 수 있습니다.
   * 업로드 및 다운로드에 대한 HTTPS 프로토콜 지원. [!DNL Audience Manager]에서 파일을 전송할 때는 항상 HTTPS를 사용해야 합니다.
   * Amazon S3는 [아웃바운드 데이터 파일](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)을 암호화하기 위한 암호화-일시 중지 기능을 제공합니다. [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) 암호화 방법을 사용합니다. 이 방법을 통해 Amazon S3에서 암호화 키를 자동으로 생성 및 관리할 수 있습니다.

* **디버그 및 백업 지원:** Amazon S3를 사용하면 정확한 파일 사본 [!DNL Audience Manager] 을 그대로 유지하여 디버깅하거나 보다 손쉽게 다시 전송할 수 있습니다.

Amazon S3에 대한 자세한 내용은 다음 리소스를 참조하십시오.

[Amazon 웹 서비스 웹 사이트](https://aws.amazon.com/s3/) 에서 Amazon Simple Storage Service (Amazon S3)

[AWS 설명서 웹 사이트에서 Amazon Simple Storage ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Services를 시작합니다.
