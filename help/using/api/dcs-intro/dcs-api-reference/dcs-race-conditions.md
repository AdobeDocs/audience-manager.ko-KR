---
description: 경합 조건 및 DCS 오류 처리를 방지하는 방법에 대해 설명합니다.
seo-description: 경합 조건 및 DCS 오류 처리를 방지하는 방법에 대해 설명합니다.
seo-title: 경합 조건 및 오류 처리
solution: Audience Manager
title: 경합 조건 및 오류 처리
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# 경합 조건 및 오류 처리 {#race-conditions-and-error-handling}

경합 조건 및 [!DNL DCS] 오류 처리를 방지하는 방법에 대해 설명합니다.

## 경합 조건 방지 {#prevent-race-conditions}

초기 쿼리에 응답하고 사용자 쿠키에 데이터를 쓰기 전에 [!DNL DCS]에 동시에 여러 호출을 전송하거나 신속하게 연속해서 보낼 경우 경합 조건이 발생할 수 있습니다. 경합 조건은 쿠키 데이터를 손상하거나 잘못 덮어쓸 수 있으므로 바람직하지 않습니다. 이 문제를 방지하는 가장 좋은 방법은 다음 방법을 사용하는 것입니다.

* 동일한 사용자의 [!DNL DCS] 을 동시에 호출하거나 연속해서 호출하지 마십시오.
* 후속 호출을 하기 전에 각 응답이 돌아올 때까지 기다립니다.

## {#error-handling} 처리 오류

잘못된 쿼리 또는 형식이 잘못된 쿼리에 대해 오류 처리가 제한됩니다. 잘못된 요청이 `HTTP 200 OK` 응답을 반환하고 데이터가 없습니다. 또한 [!DNL DCS] 은 요청 처리를 중단하고, 트레이트 데이터를 삭제하고, 사용자가 다음과 같이 되면 `HTTP 200 OK` 응답을 반환합니다.

* Audience Manager 또는 파트너 수준에서 추적을 옵트아웃합니다.
* 잘못된/선택되지 않은 지리적 영역에서 가져옵니다.
* 브라우저 쿠키를 비활성화합니다(모두 또는 타사).

또한, [DCS 오류 코드, 메시지 및 예제](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)도 참조하십시오.
