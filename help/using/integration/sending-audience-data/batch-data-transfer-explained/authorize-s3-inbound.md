---
description: 자신의 Amazon S3 버킷에서 Audience Manager으로 데이터를 전송하려면 먼저 전용 Amazon S3 역할의 구성을 요청해야 합니다.
solution: Audience Manager
title: 인바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# 인바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

자신의 Amazon S3 버킷에서 Audience Manager으로 데이터를 전송하려면 먼저 전용 Amazon S3 역할의 구성을 요청해야 합니다.

이렇게 하려면 아래에 설명된 단계를 수행합니다.

1. 고객 지원 센터에 문의하여 파일을 Audience Manager에 보낼 수 있는 대체 방법을 요청하십시오.
2. 파일을 보내는 데 사용할 Amazon S3 계정의 역할에 대한 [!DNL Amazon Resource Name (ARN)]을(를) 고객 지원 센터에 제공합니다. _고객 지원 센터에 문의하기 전에 이 역할을 만들어야 합니다_. 구성이 완료되면 고객 지원 센터에서 새로 만든 역할에 대한 [!DNL Amazon Resource Name (ARN)]을(를) 제공합니다.
3. 고객 지원에서 제공한 역할을 수행하도록 기존 Amazon S3 역할의 권한을 편집합니다.

>[!NOTE]
>
>인바운드 데이터를 Audience Manager Amazon S3 버킷으로 전송할 때 Audience Manager가 데이터를 올바르게 처리하려면 `bucket-owner-full-control` [액세스 제어 목록](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html)을 사용해야 합니다.
>
>Amazon Web Services 명령의 예: `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
