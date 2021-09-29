---
description: Adobe Audience Manager ID의 전체 목록은 이 문서 를 참조하십시오.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Audience Manager의 ID 색인
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 5%

---

# [!DNL Audience Manager]에 있는 ID 색인 {#index-of-ids-in-audience-manager}

## 개요 {#overview}

[!DNL Audience Manager] 는 여러 ID를 사용하여 보내는 데이터를 식별하고 관리합니다. [!DNL Audience Manager] ID의 전체 목록과 함께 이러한 ID를 사용해야 하는 접두사의 예제를 보려면 이 문서를 참조하십시오.

## ID 사전 수정 {#prefixing}

이러한 ID의 대부분을 독립형 이름으로 참조할 수 있지만 대부분은 [!DNL DCS] 호출을 통해 데이터를 전달할 때 다양한 접두사와 함께 사용됩니다. 이러한 ID 중 일부는 사용자에게 노출되지 않고 [!DNL Audience Manager]에 의해 사용되지만, 다른 ID는 UI(사용자 인터페이스)에도 표시됩니다.

다음 예제에 사용된 접두사를 이해하려면 [DCS API 호출에 지원되는 특성](../api/dcs-intro/dcs-api-reference/dcs-keys.md)을 참조하십시오.

## [!DNL Audience Manager] ID 목록 {#id-list}

| ID | 이름 및 설명 | 사용 및 예 | 사용자 인터페이스 위치 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]이라고도 합니다  [!UICONTROL Device ID]. [!DNL Audience Manager]이 상호 작용하는 각 장치에 연결하는 38자리 숫자 장치 ID입니다. [!DNL Audience Manager] UI에서 고유 사용자에 대한 언급이 표시될 때마다 이 ID를 생각해 보십시오. Audience Manager은 이 ID를 `demdex.net` 타사 도메인에 [!DNL cookie] 로 저장합니다. | [!DNL DCS] 호출에서 `uuid` 앞에는 `d_` 접두사가 붙습니다. <br>예: `d_uuid = 07955261652886032950143702505894272138` | [유사 모델](../features/algorithmic-models/create-model.md)을 만들 때 [!DNL traits]을(를) 기준으로 필터링하고 [세그먼트를 작성할 수 있습니다](../features/segments/segment-builder.md). [!UICONTROL Device ID] [트레이트](../reporting/general-reports.md) 및 [트레이트에 대한 트렌드 보고서](../reporting/trend-reports.md)를 실행할 때 [!UICONTROL Device ID]별로 결과를 필터링할 수도 있습니다. |
| [!DNL ImsOrgId] | [!DNL Organization ID]. 이 ID는 회사가 [!DNL Experience Cloud] 계정을 등록할 때 제공하는 ID입니다. | `5DC5123F5245B1D20A490D46@AdobeOrg` | [!DNL Audience Manager] 사용자 인터페이스에 표시되지 않습니다. 회사의 [!DNL Organization ID]을 찾는 방법에 대해 알려면 [조직 ID 찾기](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)를 읽어 보십시오. |
| [!DNL PID] | [!DNL Partner ID]. [!DNL PID]은 [!DNL Audience Manager]에 있는 회사의 ID입니다. Audience Manager은 [!DNL imsOrgId]을 [!DNL PID]에 연결합니다. | `1352` | [!DNL Audience Manager] 사용자 인터페이스에 표시되지 않습니다. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. [!DNL Experience Cloud] ID([!DNL ECID], 기존 약자 [!DNL MID] 또는 [!DNL MCID])는 [!DNL Organization ID] 및 [!DNL Audience Manager] [!UICONTROL Unique User ID]에서 수학적으로 파생됩니다. 이러한 ID가 일정하게 유지된다면, 특정 사용자에 대해 올바른 [!DNL ECID]을 생성하는 것은 단순한 수학 문제입니다. 동일한 [!DNL Organization ID] 및 [!DNL Audience Manager] [!DNL UUID]를 사용하면 항상 동일한 [!DNL ECID] 값을 얻을 수 있습니다. [쿠키 및 Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 설명서에서 [!DNL ECID]에 대해 자세히 읽어볼 수 있습니다. | `mid = 08382830887934830189014177072406221371` | [!DNL Audience Manager] 사용자 인터페이스에 표시되지 않습니다. |
| [!DNL SID] | [!UICONTROL Trait ID]. [!UICONTROL Trait ID]은 [!DNL Audience Manager] 환경에서 [!DNL traits]을 고유하게 식별합니다. | [!DNL DCS] 호출에서 `SID` 앞에는 `d_` 접두사가 붙습니다. <br>예 `d_sid=289983`. | [!UICONTROL Trait ID]은 각 [!DNL trait]에 할당되고 [트레이트](../features/traits/trait-details-page.md) 페이지에 사용자 인터페이스에 표시됩니다. |
| [!DNL SID] | [!UICONTROL Segment ID]. [!UICONTROL Segment ID]은 [!DNL Audience Manager] 환경에서 [!DNL segments]을 고유하게 식별합니다. | [!DNL DCS] 호출에서 `SID` 앞에는 `d_` 접두사가 붙습니다. <br>예 `d_sid=4798574`. | [!UICONTROL Segment ID]은(는) 각 [!DNL segment]에 할당되고 사용자 인터페이스에 [세그먼트](../features/segments/segment-summary-view.md) 페이지에 표시됩니다. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. 이 ID는 [!DNL Audience Manager] 환경에서 세그먼트를 고유하게 식별합니다. | `741232` | [!UICONTROL Legacy Segment ID] 은 각 세그먼트에 할당되고 [세그먼트](../features/segments/segment-summary-view.md) 페이지에 사용자 인터페이스에 표시됩니다. |
| [!DNL destID] | [!UICONTROL Destination ID]. [!UICONTROL Destination ID]은 [!DNL Audience Manager] 환경에서 [!DNL destinations]을 고유하게 식별합니다. ID는 사용자 인터페이스의 각 [!DNL destination]에 할당됩니다. | `2523` | [!UICONTROL Destination ID]은(는) 각 [!DNL destination]에 할당되고 [대상](../features/destinations/destinations-home.md) 페이지의 사용자 인터페이스에 표시됩니다. |
| [!DNL DPID] | [!UICONTROL Data Source ID] ( [!UICONTROL Data Provider ID]이라고도 합니다.) [!UICONTROL Data Source ID]은 ID 또는 [!DNL traits]의 네임스페이스입니다. ID는 사용자 인터페이스의 각 [!DNL data source](데이터 공급자)에 할당됩니다. | [!DNL DCS] 호출에서 `dpid` 앞에는 `d_` 접두사가 붙습니다. <br>예: `d_dpid=39217`. | [!UICONTROL Data Provider ID]은(는) 각 [!DNL data source]에 할당되고 [데이터 소스](../features/datasources-list-and-settings.md) 페이지에 사용자 인터페이스에 표시됩니다. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]이라고도  [!DNL CRM ID] 하는  [!UICONTROL Cross-Device ID]입니다. 타사 ID입니다. 자신의 [!DNL CRM] 시스템에서 최종 사용자를 식별하는 ID입니다. [!DNL DPUUIDs] 을 [!DNL Audience Manager] [!DNL UUIDs]와 동기화할 수 있으며 ID 동기화 프로세스에서 [!DNL DPUUIDs] 를 다른 [!UICONTROL Data Sources]([!DNL DPIDs])와 동기화할 수 있습니다. | [!DNL DCS] 호출에서 `dpuuid` 앞에는 `d_` 접두사가 붙습니다. <br> 예 `d_dpuuid=2132-3423vn-343fds-3432r`. | [유사 모델](../features/algorithmic-models/create-model.md)을 만들 때 [!DNL traits]을(를) 기준으로 필터링하고 [세그먼트를 작성할 수 있습니다](../features/segments/segment-builder.md). [!UICONTROL Cross-Device ID] [트레이트](../reporting/general-reports.md) 및 [트레이트에 대한 트렌드 보고서](../reporting/trend-reports.md)를 실행할 때 [!UICONTROL Cross-Device ID]별로 결과를 필터링할 수도 있습니다. |
| [!DNL CRM ID] | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. [!DNL CID] 및 [!DNL CID_IC] 키-값 쌍이 [!DNL DPID] 및 [!DNL DPUUID]을(를) 대체합니다. [!DNL DPID] 및 [!DNL DPUUID] 와 동일한 기능을 제공하지만, 데이터 공급자 ID 및 사용자 ID(또는 통합 코드)를 단일 키-값 쌍에 포함하므로 보다 효율적입니다. | [!DNL DCS] 호출에서 이러한 ID 앞에는 `d_` 접두사가 붙습니다. <br>예: `d_cid_ic=39217_myIntegrationCode`. | `DPID` 및 `DPUUID` 를 참조하십시오. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. 각 하드웨어 장치에 고유한 ID로서, 광고 목적으로 사용됩니다. 일반적으로 장치 또는 장치 운영 체제의 제조업체가 제공합니다. | [글로벌 장치 ID](#global-device-ids)를 참조하십시오. |  |

## [!DNL Global Device IDs] {#global-device-ids}

글로벌 장치 ID는 장치 제조업체 또는 운영 체제에서 제공하는 각 장치에 고유한 장치 광고 ID입니다. 아래 표는 이러한 ID가 무엇이고 ID의 형식이 무엇인지 설명합니다. 글로벌 장치 ID 및 [!DNL Audience Manager]에서 사용하는 방법에 대한 자세한 내용은 [글로벌 데이터 소스](/help/using/features/global-data-sources.md)를 참조하십시오.

| ID | [!DNL Global Data Source ID] | 이름 및 설명 | 예 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL iOS] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 개의 그룹으로 표시되고 하이픈으로 구분되는 32개의 대문자 16진수로 8-4-4-4-12 총 36자에 대해 구성됩니다.<br> 예: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]는 Android 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL Android] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 개의 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 구성되며, 총 36자8-4-4-4-12 형식입니다. <br>예: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 는  [!DNL Roku] 스트리밍 장치를 나타냅니다. | 형식은 다섯 개의 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 구성되며, 총 36자8-4-4-4-12 형식입니다. <br>예: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s는 장치별,  [!DNL Windows 10] 사용자별로 생성된 장치 식별자입니다. | [!DNL MAID]는 영숫자 문자열로 포맷됩니다. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 는  [!DNL Samsung] 스마트 TV에서 제공하는 장치 식별자입니다. | [!DNL Samsung] [!DNL TIFA] ID는 영숫자 문자열로 포맷됩니다. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | [!DNL Fire OS] 운영 체제를 실행하는 장치를 나타내는 장치 식별자입니다. | 형식은 다섯 개의 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 구성되며, 총 36자8-4-4-4-12 형식입니다. <br>예: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | [!DNL LG webOS] 운영 체제를 실행하는 장치를 나타내는 장치 식별자입니다. | 형식은 다섯 개의 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 구성되며, 총 36자8-4-4-4-12 형식입니다. <br>예: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Vizio 스마트 TV 운영 체제를 실행하는 장치를 나타내는 장치 식별자입니다. | [!DNL Vizio IFA] ID는 영숫자 문자열로 포맷됩니다. <br>예: `7XCBNROQJQPYW`. |
