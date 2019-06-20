---
description: DCS API 코드, 메서드 및 프로세스에 대한 개념 정보, 설명 및 정의
seo-description: AAM (Adobe Audience Manager) 의 DCS API 코드, 메서드 및 프로세스에 대한 개념 정보, 설명 및 정의입니다.
seo-title: AAM (Adobe Audience Manager) 의 DCS API 참조 개요
title: DCS API 참조 개요
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# DCS API 참조 개요

DCS API 코드, 메서드 및 프로세스에 대한 개념 정보, 설명 및 정의

* [DCS API 메서드](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   GET 또는 POST 메서드를 사용하여 DCS API로 데이터를 전송합니다.

* [DCS 오류 코드, 메시지 및 예제](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   DCS (데이터 수집 서버) 가 생성한 오류 코드 및 메시지는 코드 ID 별로 숫자 순서로 나열됩니다.

* [ID 모니터링 및 블랙 리스트](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-blacklisting.md)

   DCS는 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 모니터링하고 블랙리스트에 표시합니다.

* [DCS 영역 ID, 위치 및 호스트 이름](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   DCS를 호출하려면 지역 DCS 서버 호스트 이름이 필요합니다. DCS는 지리적으로 사이트 방문자와 가까운 데이터 센터에 정보를 저장하기 때문입니다. 잘못된 DCS로 전송하는 경우 쿼리가 작동하지만 이러한 호출은 비효율적이며 응답을 지연시킬 수 있습니다. DCS 요청을 수행하려면 해당 지역 ID와 해당 지역 호스트 이름을 일치시키고 쿼리를 적절한 호스트 이름으로 구성합니다.

* [DCS 호출에서 키-값 쌍 서식 지정](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   전화 통화를 할 때 DCS는 표준 또는 직렬 형식으로 키-값 데이터를 수락합니다. 표준 및 일련 번호 데이터의 형식 지정 데이터에 대한 자세한 내용은 이 섹션을 검토하십시오.

* [레이스 조건 및 오류 처리](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   레이스 조건 및 DCS 오류 처리를 방지하는 방법을 설명합니다.

* [DCS API 호출에 지원되는 속성](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   DCS (데이터 수집 서버) 에 전달할 수 있는 구문 및 지원되는 속성 (또는 키-값 쌍) 를 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환된 매개 변수를 이해하는 데 도움이 됩니다.
