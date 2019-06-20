---
description: CDF (Customer Data Feed) 파일에 대한 FAQ 입니다.
seo-description: CDF (Customer Data Feed) 파일에 대한 FAQ 입니다.
seo-title: 고객 데이터 피드 FAQ
solution: Audience Manager
title: 고객 데이터 피드 FAQ
uuid: 7183 B 3 E 2-E 999-4 E 1 E -892 F -2 BAB 335 C 13 B 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feed FAQ{#customer-data-feed-faq}

CDF (Customer Data Feed) 파일에 대한 FAQ 입니다.

## Amazon S3 Storage {#amazon-s3-storage}

**CDF 파일은[!DNL Amazon]어디에 저장됩니까?**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. [고객 데이터 피드 파일 이름 지정 규칙을 참조하십시오](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**저장소 버킷은 안전합니까?**

예. 고객은 고유한 저장 공간에 대해서만 액세스할 수 있습니다. 저장소 버킷에 대한 읽기 전용 액세스 권한이 있습니다. 쓰기 액세스 권한이 없습니다.

<br> 

**저장소 버킷을 사용자 정의하거나 파일을 다른 디렉토리에 저장할 수 있습니까?**

아니요. 사용자 정의 및 대체 저장소 옵션은 사용할 수 없습니다.

<br> 

**내 디렉토리에 특정 시간에 대한 파일이 없습니다. Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. 일반적으로 서버는 CDF 파일을 처리할 때 비공개로 처리됩니다. 이 경우 파일이 손실되지 않습니다. 시스템은 시스템이 캐치된 후 시간별 디렉토리에 나타납니다. [고객 데이터 피드 파일 처리 알림을 참조하십시오](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**CDF 파일이 준비되면 어떻게 알 수 있습니까?**

[고객 데이터 피드 파일 처리 알림을 참조하십시오](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**어떤 유형의 파일 크기를 예상해야 합니까? How big is an average CDF file?**

파일 크기를 예측하기는 어렵습니다. 또한 각 파일의 크기가 달라질 수 있습니다. 크기는 시간과 시간에 따라 다릅니다. CDF 파일을 받을 경우 많은 데이터를 관리할 수 있도록 준비하는 것이 도움이 됩니다.

<br> 

**몇 개의 파일을 받게 됩니까?**

이를 예측하기 어렵습니다. 그러나 CDF 파일을 받을 경우 많은 데이터를 관리할 준비가 되어 있습니다.

<br> 

## Data Integrity {#data-integrity}

**Amazon S 3에 업로드된 데이터의 무결성을 확인하려면 어떻게 합니까?**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] 다중 부분 업로드에 대한 `ETag` 값을 생성합니다. 먼저 업로드된 각 부분의 개별 MD 5 체크섬을 계산한 다음 단일 문자열로 연결합니다. 그런 다음 문자열의 MD 5 체크섬을 계산합니다. The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**CDF 파일을 얼마나 오랫 동안 저장하십니까?**

데이터는 8 일 후 삭제됩니다.

<br> 

**이전 날짜에 CDF 파일을 소급하여 받을 수 있습니까?**

지난 8 일 동안의 CDF 파일만 생성할 수 있습니다. 지난 8 일 이전의 간격에 대한 CDF 파일은 다시 생성할 수 없습니다.

>[!MORE_ like_ this]
>
>* [고객 데이터 피드](../features/cdf-files.md)

