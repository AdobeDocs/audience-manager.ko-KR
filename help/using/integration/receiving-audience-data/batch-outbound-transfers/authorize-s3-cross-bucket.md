---
description: Amazon Simple Storage Service(Amazon S3)를 사용하는 고객을 위한 아웃바운드 데이터 전송 프로세스에서는 버킷에 아웃바운드 데이터 파일을 전달하기 위해 Amazon S3 액세스 키와 비밀 키를 요청해야 합니다.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 아웃바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# 아웃바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

[!DNL Amazon Simple Storage Service] ([!DNL Amazon S3])을(를) 사용하는 고객을 위한 [!UICONTROL Outbound Data Transfer] 프로세스에서는 [!DNL Amazon S3] 액세스 키와 비밀 키를 요청하여 아웃바운드 데이터 파일을 버킷에 전달해야 합니다.

[!DNL Amazon S3] 액세스 키 및 비밀 키를 공유하지 않으려면 [!DNL Audience Manager] 컨설턴트나 고객 지원 팀에 연락하면 [!DNL Cross-Account Bucket Permissions]이(가) 자동으로 설정됩니다.

[Amazon S3 설명서](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)에 설명된 대로 아웃바운드 데이터 파일을 수신하려는 [!DNL S3] 버킷의 허용 목록에 [!DNL Amazon S3] 계정 ID만 추가하면 됩니다. [!DNL Audience Manager] 컨설턴트 또는 고객 지원 팀에서 [!DNL Amazon S3] 계정 ID를 제공합니다.
