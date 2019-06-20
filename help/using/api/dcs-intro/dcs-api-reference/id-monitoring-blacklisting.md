---
description: DCS는 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 모니터링하고 블랙리스트에 표시합니다.
keywords: id; 모니터링; 블랙 리스트; DCS
seo-description: DCS는 짧은 시간 동안 비정상적으로 높은 비율로 전송되는 ID를 모니터링하고 블랙리스트에 표시합니다.
seo-title: ID 모니터링 및 블랙 리스트
solution: Audience Manager
title: ID 모니터링 및 블랙 리스트
uuid: 498 E 0316-CF 1 B -43 E 9-88 BA -338 EE 0 DAF 225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID 모니터링 및 블랙 리스트

The [!UICONTROL DCS] monitors the IDs it receives and blacklists those that are being sent at an unusually high rate over a short period of time.

## 개요

To protect the Audience Manager infrastructure against malicious activity, the [!UICONTROL DCS] uses an advanced algorithm to monitor the IDs it receives. These can be [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), or [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). See [Index of IDs in Audience Manager](../../../reference/ids-in-aam.md) for detailed explanations of the IDs supported by Audience Manager.

The [!UICONTROL DCS] monitors the frequency at which it receives these IDs to detect potential malicious activity. When the [!UICONTROL DCS] detects an unusually large amount of [!UICONTROL DCS] requests for any given ID in a short amount of time, that ID is blacklisted.

## 오류 코드

You can identify blacklisted IDs by the error codes received from the [!UICONTROL DCS]. 받을 수 있는 오류 코드는 다음과 같습니다.

* 303: 차단된 고객 ID;
* 306: 차단된 장치 ID;
* 307: ID에 대한 차단된 프로필 작업입니다.

See [DCS Error Codes, Messages, and Examples](dcs-error-codes.md) for details on the error codes that you may receive.

## 블랙리스트에 없는 목록

블랙리스트에 추가된 ID는 잘못된 데이터 보고로 이어질 수 있으므로 향후 요청에서 사용할 수 없습니다. The [!UICONTROL DCS] does not support un-blacklisting of IDs.

## ID 동기화 시 영향

[!UICONTROL DCS] 호출에는 하나 또는 여러 유형의 ID가 포함될 수 있습니다. ID가 차단된 경우 단일 ID를 포함하는 호출은 무시되며, 이 경우 ID 동기화가 발생하지 않습니다.

When a multiple ID call also includes a blacklisted ID, the [!UICONTROL DCS] disregards the blacklisted ID and only uses the remaining, non-blacklisted IDs for synchronization.

## ID 블랙리스트에 대한 원인 및 수정 사항

ID가 블랙리스트에 추가된 가장 자주 발생하는 원인은 고객 인프라와 Audience Manager 간의 잘못된 통합입니다. 블랙리스트에 추가된 ID를 식별할 때 Audience Manager 통합을 철저히 검토해야 합니다. See **Implementation and Integration Guides** for detailed explanations of how you should configure Audience Manager to work with other Experience Cloud solutions or external systems.

Another frequent cause of blacklisted IDs are indexing bots (web crawlers), which generally cause increases in traffic, leading to the same IDs being sent to the [!UICONTROL DCS] multiple times. ID 블랙리스트에 대한 이유로 인덱싱 보트를 식별하는 경우 웹 사이트에 대한 보트 액세스를 제한해야 합니다.

통합 문제를 파악하는 데 어려움이 있는 경우 언제든지 고객 지원에 문의하십시오. Prior to opening a support request, make sure to keep the `.har` `HTTP` archive of your browser ready. 이 보관을 통해 지원 팀은 ID 블랙리스트가 발생한 이유를 식별할 수 있습니다.