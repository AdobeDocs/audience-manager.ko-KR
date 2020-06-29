---
description: Amazon Simple Storage Service(Amazon S3)를 사용하는 고객을 위한 아웃바운드 데이터 전송 프로세스에서는 버킷에 아웃바운드 데이터 파일을 전달하기 위해 Amazon S3 액세스 키와 비밀 키를 요청해야 합니다.
seo-description: Amazon Simple Storage Service(Amazon S3)를 사용하는 고객을 위한 아웃바운드 데이터 전송 프로세스에서는 버킷에 아웃바운드 데이터 파일을 전달하기 위해 Amazon S3 액세스 키와 비밀 키를 요청해야 합니다.
seo-title: 아웃바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용
solution: Audience Manager
title: 아웃바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# 아웃바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

고객 [!UICONTROL Outbound Data Transfer] 이 ( [!DNL Amazon Simple Storage Service] )을 사용하는[!DNL Amazon S3]경우, 버킷에 아웃바운드 데이터 파일을 전달하기 위해 사용자의 [!DNL Amazon S3] 액세스 키와 비밀 키를 요청해야 합니다.

액세스 [!DNL Amazon S3] 키와 비밀 키를 공유하지 않으려면 컨설턴트나 고객 지원 센터에 [!DNL Audience Manager] 문의하십시오. 그러면 관리자가 [!DNL Cross-Account Bucket Permissions] 자동으로 설정됩니다. Amazon [!DNL Amazon S3] S3 설명서에 설명된 대로 아웃바운드 데이터 파일을 수신할 버킷의 허용 목록에 계정 ID만 추가해야 [!DNL S3] 합니다 [](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). 컨설턴트 또는 고객 지원 센터에서 [!DNL Audience Manager] [!DNL Amazon S3] 계정 ID를 제공합니다.