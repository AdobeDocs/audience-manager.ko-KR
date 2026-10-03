---
description: Amazon Simple Storage Service(Amazon S3)를 사용하는 고객을 위한 아웃바운드 데이터 전송 프로세스에서는 버킷에 아웃바운드 데이터 파일을 전달하기 위해 Amazon S3 액세스 키와 비밀 키를 요청해야 합니다.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: 아웃바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
TQID: 'https://experienceleague.adobe.com/Ji1ltYPv4eoY5-eZiX62JyQ5SJzdMjFZdKeRzJnwKZg'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
    internal-label: Implementation
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: bcf89bb2-9d92-4897-90ec-483950be810f
    internal-label: Outbound data transfers
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%
---
# 아웃바운드 파일에 대한 Amazon S3 계정 간 버킷 권한 활용 {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

[!DNL Amazon Simple Storage Service]&#x200B;([!DNL Amazon S3])을(를) 사용하는 고객을 위한 [!UICONTROL Outbound Data Transfer] 프로세스에서는 [!DNL Amazon S3] 액세스 키와 비밀 키를 요청하여 아웃바운드 데이터 파일을 버킷에 전달해야 합니다.

[!DNL Amazon S3] 액세스 키 및 비밀 키를 공유하지 않으려면 [!DNL Audience Manager] 컨설턴트나 고객 지원 팀에 연락하면 [!DNL Cross-Account Bucket Permissions]이(가) 자동으로 설정됩니다.

[Amazon S3 설명서](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)에 설명된 대로 아웃바운드 데이터 파일을 수신하려는 [!DNL S3] 버킷의 허용 목록에 [!DNL Amazon S3] 계정 ID만 추가하면 됩니다. [!DNL Audience Manager] 컨설턴트 또는 고객 지원 팀에서 [!DNL Amazon S3] 계정 ID를 제공합니다.

>[!NOTE]
>
>Amazon S3 오브젝트 크기 제한으로 인해 Audience Manager은 최대 1TB의 분할 크기를 지원합니다. 분할 크기를 지정하지 않으면 1TB 제한이 자동으로 적용됩니다.

