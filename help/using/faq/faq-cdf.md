---
description: 고객 데이터 피드(CDF) 파일에 대한 FAQ입니다.
seo-description: Frequently asked questions about Customer Data Feed (CDF) files.
seo-title: Customer Data Feed FAQ
solution: Audience Manager
title: 고객 데이터 피드 FAQ
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
exl-id: a948accc-6bec-4748-bcc8-2b77acf6b96a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 100%

---

# 고객 데이터 피드 FAQ{#customer-data-feed-faq}

고객 데이터 피드(CDF) 파일에 대한 FAQ입니다.

## Amazon S3 저장소 {#amazon-s3-storage}

**[!DNL Amazon]에서 CDF 파일은 어디에 저장됩니까?**

CDF 파일은 [!DNL Amazon S3] 서버의 `aam-cdf` 루트 디렉토리에 저장됩니다. 이 기본 버킷은 [!DNL Audience Manager]에서 관리합니다. [고객 데이터 피드 파일 이름 지정 규칙](../features/cdf-files.md#cdf-naming-conventions)을 참조하십시오.

<br> 

**내 저장소 버킷은 안전합니까?**

예. 고객은 자신의 저장소만 액세스할 수 있습니다. 저장소 버킷에 대한 읽기 전용 액세스 권한만 갖게 됩니다. 쓰기 액세스 권한은 없습니다.

<br> 

**저장소 버킷을 사용자 지정하거나 다른 디렉토리에 파일을 저장할 수 있습니까?**

아니요. 사용자 지정 및 대체 저장소 옵션은 사용할 수 없습니다.

<br> 

**특정 시간 동안 디렉토리에 파일이 없습니다. 어디 있습니까?**

파일이 누락되었다는 것은 [!DNL Audience Manager]가 해당 시간 동안 CDF 파일을 처리할 수 없었다는 의미입니다. 이런 일은 일반적으로 서버의 CDF 파일 처리가 밀려 있을 때 발생합니다. 이 경우 파일이 유실되지는 않습니다. 시스템이 따라잡을 수 있게 되면 이후의 시간별 디렉토리에 표시됩니다. [고객 데이터 피드 파일 처리 알림](../features/cdf-files.md#cdf-file-processing-notifications)도 참조하십시오.

<br> 

**CDF 파일이 준비되는 때는 어떻게 알 수 있습니까?**

[고객 데이터 피드 파일 처리 알림](../features/cdf-files.md#cdf-file-processing-notifications)을 참조하십시오.

<br> 

## 파일 크기 {#file-sizes}

**어떤 파일 크기를 예상해야 합니까? 평균 CDF 파일의 크기는 얼마입니까?**

파일 크기를 추정하는 것은 어렵습니다. 또한 각 파일의 크기는 다를 수 있습니다. 크기는 시시각각, 일별로 달라집니다. CDF 파일을 수신하려면 많은 데이터를 관리할 준비가 되어 있어야 합니다.

<br> 

**몇 개의 파일을 받게 됩니까?**

이것도 추정하기가 어렵습니다. 그러나 CDF 파일을 수신하려면 많은 데이터를 관리할 준비가 되어 있어야 합니다.

<br> 

## 데이터 무결성 {#data-integrity}

**Amazon S3에 업로드된 데이터의 무결성은 어떻게 확인할 수 있습니까?**

[!DNL Amazon]에서는 큰 파일을 작은 부분들로 분할하고 다중 부분 업로드 기능을 사용하여 [!DNL Amazon S3]에 업로드합니다. 그런 다음 다중 부분 업로드에 대한 `ETag` 값을 생성합니다. 먼저 업로드된 각 부분의 개별 MD5 체크섬을 계산한 다음 하나의 문자열로 연결합니다. 그런 다음 문자열의 MD5 체크섬을 계산합니다. 하이픈 다음에 업로드에 사용되는 총 부분 파일 수로 표시되는 결과 체크섬(`ETag`)이 추가됩니다. 예를 들어 업로드하는 동안 다섯 부분으로 분할된 파일의 `ETag`는 다음과 유사하게 표시됩니다. `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## 데이터 유지 {#data-retension}

**CDF 파일을 얼마나 오래 저장합니까?**

데이터는 8일 후 삭제됩니다.

<br> 

**CDF 파일을 소급하여 받거나 이전 날짜에 받을 수 있습니까?**

지난 8일 동안의 CDF 파일만 생성할 수 있습니다. 지난 8일보다 오래된 간격의 CDF 파일은 다시 생성할 수 없습니다.

>[!MORELIKETHIS]
>
>* [고객 데이터 피드](../features/cdf-files.md)

