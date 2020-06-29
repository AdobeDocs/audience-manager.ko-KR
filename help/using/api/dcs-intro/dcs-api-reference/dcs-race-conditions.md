---
description: 레이스 조건 및 DCS 오류 처리를 방지하는 방법에 대해 설명합니다.
seo-description: 레이스 조건 및 DCS 오류 처리를 방지하는 방법에 대해 설명합니다.
seo-title: 경합 조건 및 오류 처리
solution: Audience Manager
title: 경합 조건 및 오류 처리
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---


# 경합 조건 및 오류 처리 {#race-conditions-and-error-handling}

레이스 조건 및 오류 처리를 방지하는 방법에 대해 [!DNL DCS] 설명합니다.

## 경주 조건 방지 {#prevent-race-conditions}

레이스 조건은 초기 쿼리에 응답하고 사용자 쿠키에 데이터를 쓰기 전에 동시에(또는 빠르게 연속해서) 여러 호출을 보낼 [!DNL DCS] 경우 발생할 수 있습니다. 쿠키 데이터를 손상시키거나 부적절하게 덮어쓸 수 있으므로 경합 조건은 바람직하지 않습니다. 이 문제를 방지하려면 다음 방법을 고려하십시오.

* 같은 사용자의 통화 통화 통화 [!DNL DCS] 를 동시에 수행하지 마십시오.
* 이후 호출을 하기 전에 각 응답이 돌아올 때까지 기다립니다.

## 오류 처리 {#error-handling}

형식이 잘못되었거나 낮은 쿼리에 대한 오류 처리가 제한됩니다. 잘못된 요청은 응답을 반환하며 데이터가 `HTTP 200 OK` 없습니다. 또한 요청 처리를 [!DNL DCS] 중지하고, 특성 데이터를 삭제하고, 사용자가 다음을 수행할 때 `HTTP 200 OK` 응답을 반환합니다.

* Audience Manager 또는 파트너 수준에서 추적을 옵트아웃합니다.
* 잘못된/선택되지 않은 지리적 영역에서 가져옵니다.
* 브라우저 쿠키를 비활성화합니다(모두 또는 타사).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).