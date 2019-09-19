---
description: DCS는 수신한 ID를 모니터링하고 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 블랙리스트에 표시합니다.
keywords: id;monitoring;blacklisting;dcs
seo-description: DCS는 수신한 ID를 모니터링하고 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 블랙리스트에 표시합니다.
seo-title: ID 모니터링 및 블랙 리스트
solution: Audience Manager
title: ID 모니터링 및 블랙 리스트
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID 모니터링 및 블랙 리스트

수신한 ID를 [!UICONTROL DCS] 모니터링하고 짧은 기간 동안 비정상적으로 높은 비율로 전송되는 ID를 블랙리스트에 표시합니다.

## 개요

Audience Manager 인프라를 악의적인 활동으로부터 보호하기 위해 고급 알고리즘을 [!UICONTROL DCS] 사용하여 수신한 ID를 모니터링합니다. 이 변수들은 [!UICONTROL Data Provider Unique User ID]s,[!UICONTROL CRM ID]s [!UICONTROL Audience Manager Unique User ID]또는[!UICONTROL AAM UUID]s(s) [!UICONTROL Experience Cloud ID][!UICONTROL ECID]일 수 있습니다. Audience [Manager에서](../../../reference/ids-in-aam.md) 지원되는 ID에 대한 자세한 내용은 Audience Manager의 ID 인덱스를 참조하십시오.

이 [!UICONTROL DCS] ID가 잠재적인 악의적인 활동을 감지하는 빈도를 모니터링합니다. 지정된 ID에 대한 비정상적으로 큰 [!UICONTROL DCS] [!UICONTROL DCS] 요청이 짧은 시간 내에 감지되면 해당 ID가 차단됩니다.

## 오류 코드

에서 받은 오류 코드로 블랙리스트에 추가된 ID를 식별할 수 [!UICONTROL DCS]있습니다. 수신할 수 있는 오류 코드는 다음과 같습니다.

* 303년:차단된 고객 ID;
* 306년:차단된 선언된 장치 ID;
* 307년:ID에 대한 프로필 작업이 차단되었습니다.

수신할 수 [있는 오류 코드에](dcs-error-codes.md) 대한 자세한 내용은 DCS 오류 코드, 메시지 및 예제를 참조하십시오.

## Un-blacklisting

블랙리스트에 추가된 ID는 잘못된 데이터 보고로 이어지므로 향후 요청에 사용해서는 안 됩니다. ID의 비블랙리스트는 [!UICONTROL DCS] 지원되지 않습니다.

## ID 동기화에 미치는 영향

[!UICONTROL DCS] 호출에는 하나 이상의 ID 유형이 포함될 수 있습니다. 이 경우 단일 ID가 포함된 호출은 해당 ID가 차단되고 ID 동기화가 발생하지 않는 경우 완전히 무시됩니다.

여러 ID 호출에 블랙리스트에 추가된 ID도 포함되어 있으면 블랙리스트에 추가된 ID는 [!UICONTROL DCS] 무시되고 나머지 블랙리스트에 포함되지 않은 ID만 동기화합니다.

## ID 블랙리스트의 원인 및 수정

차단되는 ID의 가장 빈번한 원인은 고객 인프라와 Audience Manager 간의 잘못된 통합입니다. 블랙리스트에 추가된 ID 파섹 다른 **Experience Cloud** 솔루션 또는 외부 시스템에서 작동하도록 Audience Manager를 구성하는 방법에 대한 자세한 설명은 구현 및 통합 가이드를 참조하십시오.

블랙리스트에 추가된 ID의 또 다른 원인은 색인 보트(웹 크롤러)로서 일반적으로 트래픽이 증가하여 동일한 ID가 여러 번 전송되는 [!UICONTROL DCS] 것입니다. ID 블랙리스트의 원인으로 인덱싱 보트를 식별하는 경우 웹 사이트에 대한 보트 액세스를 제한해야 합니다.

통합 문제를 식별하는 데 어려움이 있는 경우 언제든지 고객 지원에 문의하십시오. 지원 요청을 열기 전에 브라우저의 `.har` 아카이브를 `HTTP` 준비하십시오. 이 아카이브를 통해 지원 팀이 ID 블랙리스트가 발생한 이유를 식별할 수 있습니다.