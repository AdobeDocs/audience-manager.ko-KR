---
description: 배달 성능 보고서 로그 파일에 ID만 포함하는 테이블로 데이터를 가져옵니다. 비 ID 메타데이터를 별도의 조회 표에 넣어 파일 크기 및 처리 시간을 줄일 수 있습니다.
seo-description: 배달 성능 보고서 로그 파일에 ID만 포함하는 테이블로 데이터를 가져옵니다. 비 ID 메타데이터를 별도의 조회 표에 넣어 파일 크기 및 처리 시간을 줄일 수 있습니다.
seo-title: 조회 테이블을 사용하여 로그 파일 처리 시간 개선
solution: Audience Manager
title: 조회 테이블을 사용하여 로그 파일 처리 시간 개선
uuid: FFC 77618-474 B -455 E -9 C 91-15 B 32 FC 151 A 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

배달 성능 보고서 로그 파일에 ID만 포함하는 테이블로 데이터를 가져옵니다. 비 ID 메타데이터를 별도의 조회 표에 넣어 파일 크기 및 처리 시간을 줄일 수 있습니다.

<!-- 

c_lookup_tables.xml

 -->

## 로그 파일 메타데이터를 사용하여 파일 크기 및 처리 시간 증가

[!UICONTROL Delivery Performance] 일반적으로 보고서에 사용되는 일반적인 로그 파일에는 수천 개의 행과 수십 개의 열이 포함됩니다. 이것은 숫자 ID와 크리에이티브, 광고주, 삽입 주문 등 사람이 읽을 수 있는 정보로 구성됩니다.

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. 메타데이터는 유용하지만 반복적입니다. 파일 크기 및 데이터 처리 시간이 늘어납니다.

## 색인 테이블로 파일 크기 축소 및 처리 시간 단축

성능을 향상시키기 위해 기본 데이터 파일은 ID만 포함해야 합니다. 메타데이터를 별도의 조회 (또는 색인) 테이블에 놓고 이러한 레코드를 기본 변수와 함께 기본 변수와 함께 기본 파일로 연결할 수 있습니다.

## 조회 테이블을 통해 파일 크기를 줄이는 방법

아래에 나와 있는 데이터 파일이 있는 경우

| 사용자 ID | 광고 ID | 광고 이름 | 주문 ID | 주문 이름 | 광고주 ID | 광고주 이름 |
|---|---|---|---|---|---|---|
| 1 | 111 | Shoe A | 456 | 운동화 | 27 | 회사 A |
| 2 | 111 | Shoe A | 456 | 운동화 | 27 | 회사 A |
| 3 | 111 | Shoe A | 456 | 운동화 | 27 | 회사 A |
| 4 | 222 | 신발 B | 789 | 하이킹 | 14 | 회사 B |
| 5 | 222 | 신발 B | 789 | 하이킹 | 14 | 회사 B |

<br> 

메타데이터가 제거된 동일한 로그 파일이 있습니다. ID 로만 구성하면 파일이 더 작아지고 처리됩니다.

| 사용자 ID | 광고 ID | 주문 ID | 광고주 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

아래 조회 파일은 메타데이터를 보유하고 있으며 광고 ID가 있는 기본 파일과 다시 연결할 수 있습니다. 크기도 확인하십시오. 각 광고주를 여러 번 반복하는 대신 각각에 대해 하나의 참조만 있으면 됩니다.

| 광고 ID | 광고 이름 | 주문 이름 | 광고주 이름 |
|---|---|---|---|
| 111 | Shoe A | 운동화 | 회사 A |
| 222 | 신발 B | 하이킹 | 회사 B |

## API를 통해 테이블을 조회할 필요가 없습니다.

광고 서비스 시스템에 API가 있는 경우 조회 파일에서 메타데이터를 전송할 필요가 없습니다. API를 통해 해당 정보를 얻을 수 있습니다. 이러한 경우 로그 파일은 ID만 포함해야 합니다. API를 통해 메타데이터를 얻을 수 있는지 확인하기 위해 협력합니다.

>[!MORE_ like_ this]
>
>* [전달 및 성과 보고서](../../reporting/dynamic-reports/delivery-performance-report.md)

