---
description: DCS API 코드, 메서드 및 프로세스에 대한 개념 정보, 설명 및 정의입니다.
seo-description: AAM(Adobe Audience Manager)의 DCS API 코드, 메서드 및 프로세스에 대한 개념 정보, 설명 및 정의입니다.
seo-title: Adobe Audience Manager(AAM)의 DCS API 참조 개요
title: DCS API 참조 개요
feature: DCS
exl-id: 84d20041-0b98-4ba5-ba97-29c35f088ad9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 13%

---

# DCS API 참조 개요

[!DNL DCS API] 코드, 메서드 및 프로세스에 대한 개념 정보, 설명 및 정의입니다.

* [DCS API 메서드](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

   GET 또는 POST 메서드를 사용하여 데이터를 [!DNL DCS API]에 보내십시오.

* [DCS 오류 코드, 메시지 및 예제](/help/using/api/dcs-intro/dcs-api-reference/dcs-error-codes.md)

   코드 ID별로 숫자 순서로 나열된 DCS(데이터 수집 서버)에서 생성된 오류 코드 및 메시지입니다.

* [ID 모니터링 및 차단 목록에 추가](/help/using/api/dcs-intro/dcs-api-reference/id-monitoring-denylisting.md)

   DCS는 수신하는 ID를 모니터링하고 짧은 시간에 비정상적으로 높은 비율로 전송되는 ID를 차단 목록에 추가합니다.

* [DCS 지역 ID, 위치 및 호스트 이름](/help/using/api/dcs-intro/dcs-api-reference/dcs-regions.md)

   DCS를 호출하려면 지역 DCS 서버 호스트 이름이 필요합니다. 이것은 DCS가 사이트 방문자와 지리적으로 가까운 데이터 센터에 정보를 저장하기 때문입니다. 쿼리를 잘못된 DCS로 보낼 경우 쿼리 기능이 작동하지만 이러한 호출은 비효율적이고 응답을 지연시킬 수 있습니다. DCS 요청을 수행하려면 지역 ID를 해당 지역 호스트 이름과 일치시키고 올바른 호스트 이름으로 쿼리를 형성하십시오.

* [DCS 호출에서 키-값 쌍 형식 지정](/help/using/api/dcs-intro/dcs-api-reference/dcs-key-format.md)

   호출을 수행할 때 DCS는 키 값 데이터를 표준 또는 직렬화된 형식으로 허용합니다. 표준 및 직렬화된 키-값 데이터의 형식을 지정하는 방법에 대한 자세한 내용은 이 섹션을 검토하십시오.

* [경합 조건 및 오류 처리](/help/using/api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)

   경합 조건 및 DCS 오류 처리를 방지하는 방법에 대해 설명합니다.

* [DCS API 호출에 지원되는 특성](/help/using/api/dcs-intro/dcs-api-reference/dcs-keys.md)

   DCS(데이터 수집 서버)에 전달할 수 있는 구문 및 지원되는 속성(또는 키-값 쌍)을 나열하고 설명합니다. 이 정보는 DCS 요청의 형식을 지정하고 이 시스템에서 반환되는 매개 변수를 이해하는 데 도움이 될 수 있습니다.
