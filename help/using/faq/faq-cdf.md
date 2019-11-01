---
description: CDF(Customer Data Feed) 파일에 대한 FAQ입니다.
seo-description: CDF(Customer Data Feed) 파일에 대한 FAQ입니다.
seo-title: 고객 데이터 피드 FAQ
solution: Audience Manager
title: 고객 데이터 피드 FAQ
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 고객 데이터 피드 FAQ{#customer-data-feed-faq}

CDF(Customer Data Feed) 파일에 대한 FAQ입니다.

## Amazon S3 스토리지 {#amazon-s3-storage}

**CDF 파일은 어디에[!DNL Amazon]저장됩니까?**

CDF 파일은 `aam-cdf` 서버의 [!DNL Amazon S3] 루트 디렉토리에 저장됩니다. 이 기본 버킷은 에 의해 [!DNL Audience Manager]관리됩니다. 고객 [데이터 피드 파일 이름 지정 규칙을 참조하십시오](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**내 저장소 버킷은 안전합니까?**

예. 고객은 자신의 스토리지 공간만 이용할 수 있습니다. 스토리지 버킷에 대한 읽기 전용 액세스 권한이 있습니다. 쓰기 액세스 권한이 없습니다.

<br> 

**저장소 버킷을 사용자 정의하거나 다른 디렉토리에 파일을 저장할 수 있습니까?**

아니요. 사용자 정의 및 대체 스토리지 옵션은 사용할 수 없습니다.

<br> 

**특정 시간 동안 내 디렉토리에 파일이 없습니다. 어디 있어?**

파일이 누락되어 해당 시간 동안 CDF 파일을 처리할 수 [!DNL Audience Manager] 없었습니다. 이는 일반적으로 서버에서 CDF 파일 처리가 지연될 때 발생합니다. 이 경우 파일이 손실되지 않습니다. 시스템이 따라잡을 수 있게 되면 시간별 차후에 나타납니다. 고객 데이터 피드 [파일 처리 알림도 참조하십시오](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**CDF 파일이 준비되었는지 어떻게 알 수 있습니까?**

고객 [데이터 피드 파일 처리 알림을 참조하십시오](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## 파일 크기 {#file-sizes}

**어떤 파일 크기를 예상해야 합니까? 평균 CDF 파일의 크기는 얼마입니까?**

파일 크기를 예상하기란 어렵습니다. 또한 각 파일의 크기가 다를 수 있습니다. 크기는 시간, 일, 일 단위로 다양합니다. CDF 파일을 수신하려면 많은 데이터를 관리할 준비가 필요합니다.

<br> 

**몇 개의 파일을 받게 됩니까?**

다시, 이것을 추정하기는 어렵다. 그러나 CDF 파일을 받으려면 많은 데이터를 관리할 준비를 해야 합니다.

<br> 

## 데이터 무결성 {#data-integrity}

**Amazon S3에 업로드된 데이터의 무결성을 어떻게 확인할 수 있습니까?**

크기가 16MiB를 초과하는 파일은 16MiB 청크로 분할되고 다중 부분 업로드를 [!DNL Amazon S3] 사용하여 업로드됩니다.

[!DNL Amazon] 다중 부분 업로드에 대한 `ETag` 값을 생성합니다. 먼저 업로드된 각 부품의 개별 MD5 체크섬을 계산한 다음 단일 문자열로 연결합니다. 그런 다음 문자열의 MD5 체크섬을 계산합니다. 결과 체크섬( `ETag`the)에는 하이픈과 업로드에 사용된 총 부품 수가 추가됩니다. 예를 들어, 업로드 중에 5개의 부분으로 분할된 파일의 `ETag` 경우 다음과 같이 표시될 수 있습니다. `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**CDF 파일은 얼마나 오래 저장됩니까?**

데이터는 8일 후 삭제됩니다.

<br> 

**CDF 파일을 소급 또는 이전 날짜로 가져올 수 있습니까?**

지난 8일 동안 CDF 파일만 생성할 수 있습니다. 지난 8일보다 오래된 간격에 대한 CDF 파일을 다시 생성할 수 없습니다.

>[!MORELIKETHIS]
>
>* [고객 데이터 피드](../features/cdf-files.md)

