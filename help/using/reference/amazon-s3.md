---
description: Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.
seo-description: Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.
seo-title: Amazon S3 정보
solution: Audience Manager
title: Amazon S3 정보
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3:정보{#amazon-s-about}

Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.

FTP 대신 Amazon S3를 사용하여 파일을 가져오고 파트너에게 파일을 전달하는 것이 좋습니다. Amazon S3는 웹상의 어느 곳에서나 모든 양의 데이터를 저장하고 검색하는 데 사용할 수 있는 간단한 웹 서비스 인터페이스를 제공합니다.

Amazon S3를 사용하면 다음과 같은 이점이 있습니다.

* **** 확장성:Amazon S3는 거의 모든 확장성을 제공합니다.
* **** 안정성 및 가용성:Amazon S3는 높은 내구성 및 고가용성 스토리지 서비스를 제공합니다.
* **** 속도:Amazon S3를 사용하면 데이터를 빠르게 전송할 수 있습니다.
* **** 사용 편의성:Amazon S3는 사용하기 쉽고 구현하기 쉽습니다. 약 한 시간 후에 구현 작업을 시작할 수 있습니다. FTP 디렉토리 구현은 훨씬 더 오래 걸립니다.
* **** 다중 부분 업로드:대용량 파일은 여러 부분으로 이루어진 파일을 업로드하는 것만큼 빠르고 효율적으로 업로드할 수 있습니다.
* **** 보안:Amazon S3는 강력한 보안을 제공합니다.

   * 모든 디렉토리는 해당 고객 또는 클라이언트에서만 액세스할 수 있습니다.
   * 업로드 및 다운로드에 대한 HTTPS 프로토콜 지원. 파일을 전송할 때는 항상 HTTPS를 사용해야 합니다 [!DNL Audience Manager].
   * Amazon S3는 [아웃바운드 데이터 파일을](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)암호화하기 위해 AT-REST 암호화를 제공합니다. SSE- [S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) 암호화 방법을 사용하여 암호화 키를 Amazon S3에서 자동으로 생성 및 관리할 수 있습니다.

* **** 디버그 및 백업 지원:Amazon S3를 사용하면 파일의 정확한 복사본을 [!DNL Audience Manager] 유지하여 디버깅이나 다시 전송을 보다 쉽게 수행할 수 있습니다.

Amazon S3에 대한 자세한 내용은 다음 리소스를 참조하십시오.

[Amazon Simple Storage Service(Amazon S3)](https://aws.amazon.com/s3/) (Amazon Web Services 웹 사이트)를 참조하십시오.

[AWS 설명서 웹 사이트에서 Amazon](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Simple Storage Service를 시작합니다.
