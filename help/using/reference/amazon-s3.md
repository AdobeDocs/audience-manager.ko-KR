---
description: Amazon Simple Storage Service (Amazon S 3) 에 대한 정보입니다.
seo-description: Amazon Simple Storage Service (Amazon S 3) 에 대한 정보입니다.
seo-title: Amazon S 3 About
solution: Audience Manager
title: Amazon S 3 About
uuid: 8197 ecdf-df 8 f -488 d-bbc 0-d 8 d 4205 b 42 b 4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

Amazon Simple Storage Service (Amazon S 3) 에 대한 정보입니다.

파일을 가져오고 파트너에게 파일을 전달하기 위한 방법으로서 FTP 대신 Amazon S 3를 사용하는 것이 좋습니다. Amazon S 3는 웹상의 어디에서든지 데이터 저장 및 검색에 사용할 수 있는 간단한 웹 서비스 인터페이스를 제공합니다.

Amazon S 3를 사용할 때의 이점은 다음과 같습니다.

* **확장성:** Amazon S 3는 무한한 확장성을 제공합니다.
* **안정성 및 가용성:** Amazon S 3는 높은 가용성 및 고가용성 저장소 서비스를 제공합니다.
* **속도:** Amazon S 3 에서는 빠른 데이터 전송을 허용합니다.
* **사용 용이성:** Amazon S 3는 매우 쉽게 사용하고 구현할 수 있습니다. 약 1 시간 내에 구현이 가능합니다. FTP 디렉토리 구현 시간이 더 오래 걸립니다.
* **다중 파트 업로드:** 여러 부분으로 구성된 파일 업로드로 대용량 파일을 신속하고 효율적으로 업로드할 수 있습니다.
* **보안:** Amazon S 3는 강력한 보안을 제공합니다.

   * 모든 디렉토리는 해당 고객 또는 클라이언트에서만 액세스할 수 있습니다.
   * 업로드 및 다운로드를 위한 HTTPS 프로토콜 지원 You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **디버그 및 백업 지원:** Amazon S 3 에서는 [!DNL Audience Manager] 파일의 정확한 복사본을 유지하여 디버깅하거나 재전송할 수 있습니다.

Amazon S 3에 대한 자세한 내용은 다음 리소스를 참조하십시오.

[Amazon Simple Storage Service (Amazon S 3)](https://aws.amazon.com/s3/) 를 참조하십시오.

[AWS Documentation 웹 사이트에서 Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) 를 시작하십시오.
