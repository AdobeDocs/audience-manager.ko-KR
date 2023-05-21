---
description: 게재 성능 보고서 로그 파일의 데이터를 ID만 포함된 테이블에 넣습니다. 파일 크기와 처리 시간을 줄이는 데 도움이 되도록 비ID 메타데이터를 별도의 조회 테이블에 배치합니다.
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: 조회 테이블을 사용하여 로그 파일 처리 시간 개선
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 18%

---

# 조회 테이블을 사용하여 로그 파일 처리 시간 개선{#improve-log-file-processing-times-with-lookup-tables}

게재 성능 보고서 로그 파일의 데이터를 ID만 포함된 테이블에 넣습니다. 파일 크기와 처리 시간을 줄이는 데 도움이 되도록 비ID 메타데이터를 별도의 조회 테이블에 배치합니다.

<!-- 

c_lookup_tables.xml

 -->

## 로그 파일 메타데이터로 파일 크기 및 처리 시간 증가

에서 사용하는 일반적인 로그 파일 [!UICONTROL Delivery Performance] 보고서에는 일반적으로 수천 개의 행과 수십 개의 열이 포함되어 있습니다. 숫자 ID와 크리에이티브, 광고주, 삽입 주문 등의 이름 등 사람이 읽을 수 있는 정보로 구성된다.

이 비 ID 정보를 라고 합니다. *`metadata`* (즉, 다른 정보에 대한 정보) 및 가 로그 파일의 각 행에 기록됩니다.

그러나 [!UICONTROL Delivery Performance] 보고서는 주로 로그 파일의 ID에서 작동합니다. 메타데이터는 유용하지만 반복적입니다. 파일 크기 및 데이터 수집 시간이 늘어납니다.

## 인덱스 테이블을 사용하여 파일 크기 감소 및 처리 시간 단축

성능을 향상시키려면 기본 데이터 파일에 ID만 포함되어야 합니다. 메타데이터를 별도의 조회(또는 인덱스) 테이블에 넣고 두 레코드 모두에 공통인 키 변수를 사용하여 이러한 레코드를 기본 파일에 연결합니다.

## 조회 테이블이 파일 크기를 줄이는 방법

아래 데이터 파일과 유사한 데이터 파일이 있다고 가정해 보겠습니다.

| 사용자 ID | 광고 ID | 광고 이름 | 주문 ID | 주문 이름 | 광고주 ID | 광고주 이름 |
|---|---|---|---|---|---|---|
| 1 | 111 | 신발 A | 456 | 운동화 | 27 | 회사 A |
| 2 | 111 | 신발 A | 456 | 운동화 | 27 | 회사 A |
| 3 | 111 | 신발 A | 456 | 운동화 | 27 | 회사 A |
| 4 | 222 | 신발 B | 789 | 하이킹 | 14 | 회사 B |
| 5 | 222 | 신발 B | 789 | 하이킹 | 14 | 회사 B |

<br> 

다음은 메타데이터가 제거된 동일한 로그 파일입니다. 파일은 ID로만 구성된 경우 크기가 더 작고 처리하기 더 쉽습니다.

| 사용자 ID | 광고 ID | 주문 ID | 광고주 ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

아래의 조회 파일은 메타데이터를 보관하며 광고 ID를 사용하여 기본 파일에 다시 연결할 수 있습니다. 크기도 적어 두십시오. 각 광고주를 여러 번 반복하지 않고 각각에 대해 하나의 참조만 있으면 됩니다.

| 광고 ID | 광고 이름 | 주문 이름 | 광고주 이름 |
|---|---|---|---|
| 111 | 신발 A | 운동화 | 회사 A |
| 222 | 신발 B | 하이킹 | 회사 B |

## API를 사용하면 조회 테이블이 필요 없습니다

광고 서비스 제공 시스템에 API가 있는 경우 조회 파일에서 메타데이터를 보낼 필요가 없을 수 있습니다. API를 통해 해당 정보를 얻을 수 있습니다. 이 경우 로그 파일에는 ID만 포함되어야 합니다. API를 통해 메타데이터를 가져올 수 있는지 여부를 결정하기 위해 사용자와 협력합니다.
