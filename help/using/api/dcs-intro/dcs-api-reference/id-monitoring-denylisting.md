---
description: DCS는 수신한 ID를 모니터링하고 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 거부 목록에 추가합니다.
keywords: id;monitoring;dcs
seo-description: DCS는 수신한 ID를 모니터링하고 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 거부 목록에 추가합니다.
seo-title: ID 모니터링 및 거부 목록
solution: Audience Manager
title: ID 모니터링 및 거부 목록
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID 모니터링 및 거부 목록

수신되는 ID를 [!UICONTROL DCS] 모니터링하고 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 거부 목록에 추가합니다.

## 개요

Audience Manager 인프라를 악성 활동으로부터 보호하기 위해 고급 알고리즘을 [!UICONTROL DCS] 사용하여 수신되는 ID를 모니터링합니다. 이러한 항목 [!UICONTROL Data Provider Unique User ID]은 ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s([!UICONTROL AAM UUID]s) 또는 [!UICONTROL Experience Cloud ID]s([!UICONTROL ECID]s)일 수 있습니다. Audience [Manager에서 지원하는 ID에 대한 자세한 설명은 Audience Manager](../../../reference/ids-in-aam.md) 의 ID 인덱스를 참조하십시오.

이 ID를 수신하는 빈도를 [!UICONTROL DCS] 모니터링하여 잠재적인 악성 활동을 감지합니다. 지정된 ID에 대한 비정상적으로 큰 [!UICONTROL DCS] [!UICONTROL DCS] 요청이 짧은 시간 내에 감지되면 해당 ID가 거부 목록에 추가됩니다.

## 오류 코드

에서 받은 오류 코드로 거부 목록에 추가된 ID를 식별할 수 있습니다 [!UICONTROL DCS]. 받을 수 있는 오류 코드는 다음과 같습니다.

* 303: 차단된 고객 ID;
* 306: 차단된 선언된 장치 ID;
* 307: ID에 대한 프로필 작업이 차단되었습니다.

수신할 수 있는 오류 코드에 대한 자세한 내용은 [DCS 오류 코드, 메시지 및 예제](dcs-error-codes.md) 를 참조하십시오.

## 거부 목록에서 ID 제거

거부 목록에 추가된 ID는 잘못된 데이터 보고로 이어지므로 이후 요청에 사용해서는 안 됩니다. 이 [!UICONTROL DCS] 는 거부 목록에서 ID 제거를 지원하지 않습니다.

## ID 동기화에 미치는 영향

[!UICONTROL DCS] 호출에는 하나 이상의 ID 유형이 포함될 수 있습니다. 이 ID가 거부 목록에 추가되고 이 경우 ID 동기화가 발생하지 않으면 단일 ID를 포함하는 호출은 완전히 무시됩니다.

여러 ID 호출에 비등록 ID도 포함되어 있는 경우, 거부된 ID는 [!UICONTROL DCS] 무시하고 나머지 허용된 ID만 동기화에 사용합니다.

## ID 중복 목록 원인 및 수정 사항

ID가 거부 목록에 추가되는 가장 빈번한 원인은 고객 인프라와 Audience Manager 간의 잘못된 통합입니다. 비등록 ID를 식별할 때는 Audience Manager 통합을 철저하게 검토하십시오. 다른 **Experience Cloud 솔루션이나 외부 시스템에서 작동하도록 Audience Manager를 구성하는 방법에 대한 자세한 설명은 구현 및** 통합 가이드를 참조하십시오.

거부 목록에 추가되는 ID의 또 다른 빈번한 원인은 색인 보트(웹 크롤러)이며, 일반적으로 트래픽이 증가하여 동일한 ID를 여러 번 보내는 것입니다 [!UICONTROL DCS] . 색인 보트를 거부 목록에 추가되는 ID의 원인으로 식별하는 경우 웹 사이트에 대한 보트 액세스를 제한해야 합니다.

통합 문제를 식별하는 데 어려움이 있는 경우 언제든지 고객 지원에 문의하십시오. 지원 요청을 열기 전에 브라우저의 `.har` 보관 파일을 `HTTP` 준비하십시오. 이 아카이브를 통해 지원 팀이 ID가 거부 목록에 추가된 이유를 확인할 수 있습니다.