---
description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
keywords: DPID;DPUUID;CID;UUID;uuid;uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
seo-title: Audience Manager의 ID 인덱스
solution: Audience Manager
title: Audience Manager의 ID 인덱스
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: ee11fe79cd81a17659c371b279536fd156aa360b

---


# Audience Manager의 ID 인덱스{#index-of-ids-in-audience-manager}

Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.

| ID| 이름 및 설명| 예||—|—|—||| [!DNL AAM UUID] | Audience Manager 고유 사용자 ID. Audience Manager가 상호 작용하는 각 장치에 연결하는 38자리 숫자 장치 ID입니다. Audience Manager UI에서 고유한 사용자에 대한 언급이 나타날 때마다 이 ID를 생각해 보십시오. Audience Manager는 이 ID를 `demdex.net` 타사 도메인에 쿠키로 저장합니다. Audience Manager UUID는 이벤트 호출에서 `d_uuid` 신호로 전송됩니다. | `demdex = 07955261652886032950143702505894272138` |
| [!DNL ImsOrgId]|조직 ID. 이것은 Experience Cloud 등록 시 회사가 제공하는 ID입니다. 회사의 조직 ID를 찾는 방법에 대해 알아보려면 조직 ID [찾기를 참조하십시오](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |`5DC5123F5245B1D20A490D46@AdobeOrg`||PID|파트너 ID. PID 파섹 Audience Manager [!DNL imsOrgId] [!DNL PID]를 에 연결합니다. |`1352`|
|[!DNL ECID], [!DNL MID]|Experience Cloud ID. Experience Cloud ID([!DNL ECID]이전 약자 [!DNL MID] 또는 [!DNL MCID]이전 약어)는 조직 ID 및 Audience Manager 고유 사용자 ID에서 수학적으로 파생됩니다. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. 쿠키 및 Experience Cloud ID 문서에서 ECID에 대한 [자세한 내용을](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) 볼 수 있습니다. |`mid = 08382830887934830189014177072406221371` ||[!DNL SID]|특성 ID. 특성 ID는 Audience Manager 환경에서 트레이트를 고유하게 식별합니다. 특성 ID는 사용자 인터페이스(UI)의 각 트레이트에 할당됩니다. |`289983`||SID|세그먼트 ID. 세그먼트 ID는 Audience Manager 환경에서 세그먼트를 고유하게 식별합니다. 세그먼트 ID는 UI의 각 세그먼트에 할당됩니다. |`4798574`||[!DNL csegID]|기존 세그먼트 ID. 이 ID는 Audience Manager 환경에서 세그먼트를 고유하게 식별합니다. UI의 각 세그먼트에 기존 세그먼트 ID가 할당됩니다. |`741232`|
|[!DNL destID]|Destination ID. 대상 ID는 Audience Manager 환경에서 대상을 고유하게 식별합니다. ID는 UI의 각 대상에 지정됩니다. |`2523`||[!DNL DPID]|데이터 원본 ID(데이터 공급자 ID라고도 함). 데이터 소스 ID 파섹 ID는 UI의 각 데이터 소스(데이터 공급자)에 할당됩니다. | `39217` ||[!DNL DPUUID]|데이터 공급자 고유 사용자 ID(라고도 함 [!DNL CRM ID]) 타사 ID입니다. 이 ID는 [!DNL CRM] 시스템에서 최종 사용자를 식별하는 데 사용됩니다. Audience Manager [!DNL DPUUIDs] 와 동기화할 [!DNL UUIDs] 수 있으며 ID 동기화 프로세스에서 [!DNL DPUUIDs] 다른 데이터 소스([!DNL DPIDs])와 동기화할 수 있습니다. |`2132-3423vn-343fds-3432r`||[!DNL CRM ID]|DPUUID를 참조하십시오.`2132-3423vn-343fds-3432r`|[!DNL CID]||[!DNL CID_IC],|고객 ID, 고객 ID 통합 코드. 및 [!DNL CID] 키-값 [!DNL CID_IC] 쌍은 [!DNL DPID] 및 를 대체합니다 [!DNL DPUUID]. 이 매개 변수는 [!DNL DPID] 및 [!DNL DPUUID]과 동일한 기능을 제공하지만 단일 키-값 쌍에 데이터 공급자 ID 및 사용자 ID(또는 통합 코드)를 포함하므로 보다 효율적입니다. ||
|[!DNL DAID]|Device Advertising ID. 각 하드웨어 장치에 고유한 ID로서, 광고 목적으로 사용됩니다. 일반적으로 장치 또는 장치 운영 체제의 제조업체에서 제공합니다. |전역 [장치 ID를 참조하십시오](#global-device-ids). |

## 전역 장치 ID {#global-device-ids}

전역 장치 ID는 장치 제조업체 또는 운영 체제에서 제공하는 각 장치에 고유한 장치 광고 ID입니다. 아래 표에서는 이러한 ID가 무엇이고 형식이 무엇인지에 대해 설명합니다.

| ID | 이름 및 설명 | 예 |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [!DNL IDFA] | [!DNL Identifier for Advertisers] ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 iOS 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 대문자 16진수로 구성되며 8-4-4-4-12 형식은 총 36자입니다. 예: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | [!DNL Google Advertising ID]s는 Android 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL Android] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 소문자 16진수로 구성되며 총 36자의 경우 8-4-4-4-12 형식으로 구성됩니다. 예: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | [!DNL Roku IDs for Advertising] 는 [!DNL Roku] 스트리밍 디바이스를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 소문자 16진수로 구성되며 총 36자의 경우 8-4-4-4-12 형식으로 구성됩니다. 예: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | [!DNL Microsoft Advertising ID]s는 [!DNL Windows 10] 장치별로 사용자별로 생성된 디바이스 식별자입니다. | [!DNL MAID]s는 영숫자 문자열로 서식이 지정됩니다. |
| [!DNL DUID] | [!DNL Samsung DUID]s는 삼성 스마트 TV에서 제공하는 장치 식별자입니다. | 삼성은 [!DNL DUID]영숫자 문자열로 포맷됩니다. |
| [!DNL Amazon Fire TV Advertising ID] | 운영 체제를 실행하는 장치를 나타내는 장치 식별자입니다. [!DNL Fire OS] | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분된 32개의 소문자 16진수로 구성되며 총 36자의 경우 8-4-4-4-12 형식으로 구성됩니다. 예: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
