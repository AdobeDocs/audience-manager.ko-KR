---
description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
seo-title: Audience Manager의 ID 인덱스
solution: Audience Manager
title: Audience Manager의 ID 인덱스
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: f8916812a31513d3d8401a0598f37dae02a3fd02

---


# Audience Manager의 ID 인덱스{#index-of-ids-in-audience-manager}

## 개요 {#overview}

Audience Manager는 여러 ID를 사용하여 전송한 데이터를 식별하고 관리합니다. Adobe Audience Manager ID의 전체 목록과 함께 사용해야 하는 접두사의 예를 살펴보려면 이 문서를 참조하십시오.

## ID 접두어 {#prefixing}

이러한 ID의 대부분은 독립 실행형 이름으로 참조할 수 있지만 대부분의 ID는 DCS 호출을 통해 데이터를 전달할 때 다양한 접두사와 함께 사용됩니다. 이러한 ID 중 일부는 Audience Manager에서 사용자에게 노출되지 않고 사용되지만 다른 ID는 UI(사용자 인터페이스)에도 표시됩니다.

다음 예에서 사용되는 접두사를 이해하려면 DCS API [호출에 지원되는 특성을 참조하십시오.](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Audience Manager ID 목록 {#id-list}

| ID | 이름 및 설명 | 사용 및 예 | UI 위치 |
|---|---|---|---|
| [!DNL AAM UUID] | Audience Manager 고유 사용자 ID. Audience Manager가 상호 작용하는 각 장치에 연결하는 38자리 숫자 장치 ID입니다. Audience Manager UI에서 고유한 사용자에 대한 언급이 나타날 때마다 이 ID를 생각해 보십시오. Audience Manager는 이 ID를 `demdex.net` 타사 도메인에 쿠키로 저장합니다. | 호출에서 [!DNL DCS] 앞에 `uuid` `d_` 접두사가 붙습니다. <br>예: `d_uuid = 07955261652886032950143702505894272138` | Audience Manager UI에 표시되지 않습니다. |
| [!DNL ImsOrgId] | 조직 ID. Experience Cloud 계정 등록 시 회사가 제공하는 ID입니다. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Audience Manager UI에 표시되지 않습니다. 회사의 조직 ID를 찾는 방법에 대해 알아보려면 조직 ID [찾기를 참조하십시오](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| PID | 파트너 ID. PID 파섹 Audience Manager [!DNL imsOrgId] [!DNL PID]를 에 연결합니다. | `1352` | Audience Manager UI에 표시되지 않습니다. |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID. Experience Cloud ID([!DNL ECID]이전 약자 [!DNL MID] 또는 [!DNL MCID]이전 약어)는 조직 ID 및 Audience Manager 고유 사용자 ID에서 수학적으로 파생됩니다. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. 쿠키 및 Experience Cloud ID 문서에서 ECID에 대한 [자세한 내용을](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 볼 수 있습니다. | `mid = 08382830887934830189014177072406221371` | Audience Manager UI에 표시되지 않습니다. |
| [!DNL SID] | 트레이트 ID. 특성 ID는 Audience Manager 환경에서 트레이트를 고유하게 식별합니다. | 호출에서 [!DNL DCS] 앞에 `SID` `d_` 접두사가 붙습니다. <br>예 `d_sid=289983`. | 특성 ID는 각 트레이트에 할당되고 UI의 트레이트 [페이지에서 볼 수](../features/traits/trait-details-page.md) 있습니다. |
| [!DNL SID] | 세그먼트 ID. 세그먼트 ID는 Audience Manager 환경에서 세그먼트를 고유하게 식별합니다. | 호출에서 [!DNL DCS] 앞에 `SID` `d_` 접두사가 붙습니다. <br>예 `d_sid=4798574`. | 세그먼트 ID 파섹  [](../features/segments/segment-summary-view.md) |
| [!DNL csegID] | 기존 세그먼트 ID. 이 ID는 Audience Manager 환경에서 세그먼트를 고유하게 식별합니다. | `741232` | 기존 세그먼트 ID는 각 세그먼트에 할당되고 세그먼트 페이지에서 UI에 [표시됩니다](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | 대상 ID. 대상 ID는 Audience Manager 환경에서 대상을 고유하게 식별합니다. ID는 UI의 각 대상에 지정됩니다. | `2523` | 대상 ID는 각 대상에 할당되고 대상 페이지에서 UI에 [표시됩니다](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | 데이터 소스 ID(데이터 공급자 ID라고도 함). 데이터 소스 ID 파섹 ID는 UI의 각 데이터 소스(데이터 공급자)에 할당됩니다. | 호출에서 [!DNL DCS] 앞에 `dpid` `d_` 접두사가 붙습니다. <br>예: `d_dpid=39217`. | 데이터 공급자 ID는 각 데이터 소스에 할당되고 UI에서 데이터 소스 [페이지에 표시됩니다](../features/datasources-list-and-settings.md) . |
| [!DNL DPUUID] | 데이터 공급자 고유 사용자 ID(라고도 [!DNL CRM ID]함). 타사 ID입니다. 이 ID는 [!DNL CRM] 시스템에서 최종 사용자를 식별하는 데 사용됩니다. Audience Manager [!DNL DPUUIDs] 와 동기화할 [!DNL UUIDs] 수 있으며 ID 동기화 프로세스에서 [!DNL DPUUIDs] 다른 데이터 소스([!DNL DPIDs])와 동기화할 수 있습니다. | DCS 호출에서 `dpuuid` 앞에 `d_` 접두사가 붙습니다. <br> 예 `d_dpuuid=2132-3423vn-343fds-3432r`. | Audience Manager UI에 표시되지 않습니다. |
| [!DNL CRM ID] | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. |
| [!DNL CID], [!DNL CID_IC] | 고객 ID, 고객 ID 통합 코드. 및 [!DNL CID] 키-값 [!DNL CID_IC] 쌍은 [!DNL DPID] 및 를 대체합니다 [!DNL DPUUID]. 이 매개 변수는 [!DNL DPID] 및 [!DNL DPUUID]과 동일한 기능을 제공하지만 단일 키-값 쌍에 데이터 공급자 ID 및 사용자 ID(또는 통합 코드)를 포함하므로 보다 효율적입니다. | DCS 호출에서 이러한 ID 앞에는 `d_` 접두사가 붙습니다. <br>예: `d_cid_ic=39217_myIntegrationCode`. | 를 `DPID` 참조하십시오 `DPUUID`. |
| [!DNL DAID] | 장치 광고 ID. 각 하드웨어 장치에 고유한 ID로서, 광고 목적으로 사용됩니다. 일반적으로 장치 또는 장치 운영 체제의 제조업체에서 제공합니다. | 전역 [장치 ID를 참조하십시오](#global-device-ids). |  |

## 전역 장치 ID {#global-device-ids}

전역 장치 ID는 장치 제조업체 또는 운영 체제에서 제공하는 각 장치에 고유한 장치 광고 ID입니다. 아래 표에서는 이러한 ID가 무엇이고 형식이 무엇인지에 대해 설명합니다. 전역 장치 ID와 Audience Manager에서 사용하는 방법에 대한 자세한 내용은 전역 데이터 [소스를 참조하십시오](/help/using/features/global-data-sources.md).

| ID | 전역 데이터 소스 ID | 이름 및 설명 | 예 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 iOS 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 대문자 16진수로 구성되며 8-4-4-4-12 형식은 총 36자입니다.<br> 예: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s는 Android 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL Android] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 소문자 16진수로 구성되며 총 36자의 경우 8-4-4-4-12 형식으로 구성됩니다. <br>예: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 는 [!DNL Roku] 스트리밍 디바이스를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 소문자 16진수로 구성되며 총 36자의 경우 8-4-4-4-12 형식으로 구성됩니다. <br>예: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s는 [!DNL Windows 10] 장치별로 사용자별로 생성된 디바이스 식별자입니다. | [!DNL MAID]s는 영숫자 문자열로 서식이 지정됩니다. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s는 삼성 스마트 TV에서 제공하는 장치 식별자입니다. | 삼성은 [!DNL DUID]영숫자 문자열로 포맷됩니다. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 운영 체제를 실행하는 장치를 나타내는 장치 식별자입니다. [!DNL Fire OS] | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 소문자 16진수로 구성되며 총 36자의 경우 8-4-4-4-12 형식으로 구성됩니다. <br>예: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

