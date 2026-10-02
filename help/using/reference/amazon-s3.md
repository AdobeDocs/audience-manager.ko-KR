---
description: Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3 정보
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
TQID: 'https://experienceleague.adobe.com/HRLp9cXzF3yRFulThePWxGt6TRD1HxgecSiFlnSAxlA'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: 6a8f3a31-6f0b-5101-9878-fb698e568543
    internal-label: Reference
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%
---
# Amazon S3: 정보{#amazon-s-about}

Amazon Simple Storage Service(Amazon S3)에 대한 정보입니다.

파트너로부터 파일을 가져와 파트너에게 전달하는 방법으로 FTP 대신 Amazon S3를 사용하는 것이 좋습니다. Amazon S3는 웹의 어디에서나 언제든지 원하는 양의 데이터를 저장하고 검색하는 데 사용할 수 있는 간단한 웹 서비스 인터페이스를 제공합니다.

Amazon S3 사용의 이점은 다음과 같습니다.

* **확장성:** Amazon S3는 거의 무제한 확장성을 제공합니다.
* **안정성 및 가용성:** Amazon S3는 높은 내구성 및 고가용성 스토리지 서비스를 제공합니다.
* **속도:** Amazon S3를 사용하면 데이터를 빠르게 전송할 수 있습니다.
* **사용 편이성:** Amazon S3는 사용 및 구현이 매우 쉽습니다. 약 1시간 후에 구현을 시작하고 실행할 수 있습니다. FTP 디렉터리를 구현하는 데 훨씬 많은 시간이 소요됩니다.
* **다중 부분 업로드:** 다중 부분 파일을 업로드할 때 대용량 파일을 빠르고 효율적으로 업로드할 수 있습니다.
* **보안:** Amazon S3는 강력한 보안을 제공합니다.

  * 모든 디렉토리는 해당 고객 또는 클라이언트만 액세스할 수 있습니다.
  * 업로드 및 다운로드에 대한 HTTPS 프로토콜 지원. [!DNL Audience Manager]에서 파일을 전송할 때는 항상 HTTPS를 사용해야 합니다.
  * Amazon S3에서는 [아웃바운드 데이터 파일](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md)을 암호화하기 위해 사용하지 않는 암호화를 제공합니다. Amazon S3에서 암호화 키를 자동으로 생성하고 관리할 수 있는 [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) 암호화 방법을 사용합니다.

* **디버그 및 백업 지원:** Amazon S3를 사용하면 [!DNL Audience Manager]에서 디버깅이나 다시 전송을 더 쉽게 하기 위해 정확한 파일 복사본을 유지할 수 있습니다.

Amazon S3에 대한 자세한 내용은 다음 리소스를 참조하십시오.

Amazon Web Services 웹 사이트의 [Amazon 단순 저장소 서비스(Amazon S3)](https://aws.amazon.com/s3/).

AWS 설명서 웹 사이트에서 [Amazon Simple Storage Service를 시작합니다](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html).
