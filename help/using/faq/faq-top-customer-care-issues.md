---
description: 이 페이지에는 Audience Manager 고객 지원 센터에 보고된 주요 문제가 포함되어 있습니다.
seo-description: 이 페이지에는 Audience Manager 고객 지원 센터에 보고된 주요 문제가 포함되어 있습니다.
seo-title: 고객 지원 - 가장 자주 보고된 문제
solution: Audience Manager
title: 고객 지원 - 가장 자주 보고된 문제
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# 고객 지원 - 가장 자주 보고된 문제{#most-frequent-issues}

이 페이지에는 2019년 Audience Manager 고객 지원 센터에 보고된 주요 문제가 포함되어 있습니다.

## 읽기 전용 사용자가 트레이트와 세그먼트를 생성, 편집 또는 삭제할 수 있는 이유는 무엇입니까?

**질문**

읽기 전용 사용자가 트레이트와 세그먼트를 생성, 편집 또는 삭제할 수 있는 이유는 무엇입니까?

**답변**

관리 섹션에서 그룹 및 권한을 만드는 방법 외에도 고객 지원 센터(amsupport@adobe.com)에 연락하여 담당자가 계정에 대해 RBAC(역할 기반 액세스 제어)를 활성화할 수 있도록 해야 합니다.

<br> 

## 10월 15일경 온보딩 트레이트 인구가 0으로 떨어진 이유는 무엇입니까? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

2019년 10월 14일경, 장치 ID 그래프에 대한 내 온보드 트레이트 모집단이 0으로 줄어들었다는 것을 발견했습니다. 이전에는 이 수가 훨씬 더 많았습니다.

![장치 ID 드롭 이미지](/help/using/support-issues/assets/device_id_populationdrop.png)

**답변**

10월 15일, Audience Manager의 프로필 병합 규칙 기능에 대한 업데이트가 크로스 장치 데이터 소스에 업로드된 CRM ID의 온보드 데이터가 더 이상 장치 ID에 대해 실현되지 않는 위치로 변경되었습니다.  이전에는 Audience Manager가 크로스 장치 ID(또는 CRM ID)와 관련된 할당을 Audience Manager UUID(장치 ID)에 복사했을 뿐만 아니라 이를 구현했습니다.  트레이트 데이터의 특성과 실현되는 프로파일을 보다 정확하게 반영하기 위해 변경되었습니다.

트레이트 재연결을 보려면 트레이트 보기의 오른쪽 상단 모서리에 있는 드롭다운에서 &quot;장치 간 ID&quot; 옵션을 선택하십시오.

![장치 간 ID별 재할당 보기](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## 중복 보고서 페이지에 트레이트 또는 세그먼트가 표시되지 않는 이유는 무엇입니까?

트레이트 및 세그먼트가 겹침 보고서 페이지에 표시되지 않는 이유에 대한 설명입니다.

**질문**

중복 보고서를 실행하려고 할 때 중복 보고서 페이지에 특정 트레이트와 세그먼트가 표시되지 않는 이유는 무엇입니까?

**답변**

중복 보고서에 트레이트 또는 세그먼트를 표시하려면 최소 고유 방문자 요구 사항을 충족해야 합니다.


* 트레이트:28000 - 14일 기간
* 세그먼트:14일 동안 실시간 사용자 70000

이에 대한 자세한 내용은 선택한 Audience Manager 보고서의 [데이터 샘플링 및 오류 비율을 참조하십시오](/help/using/reporting/report-sampling.md).