---
description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Adobe Audience Manager ID의 전체 목록은 이 문서를 참조하십시오.
seo-title: Audience Manager의 ID 색인
solution: Audience Manager
title: Audience Manager의 ID 색인
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 5%

---


# [!DNL Audience Manager] {#index-of-ids-in-audience-manager}에 있는 ID의 인덱스

## 개요 {#overview}

[!DNL Audience Manager] 여러 ID를 사용하여 전송한 데이터를 식별하고 관리합니다. [!DNL Audience Manager] ID의 전체 목록과 함께 이 ID를 사용해야 하는 접두사가 나와 있습니다.

## ID 접두어 {#prefixing}

이러한 ID의 대부분을 독립 실행형 이름으로 참조할 수 있지만 대부분의 ID는 [!DNL DCS] 호출을 통해 데이터를 전달할 때 다양한 접두사와 함께 사용됩니다. 이러한 ID 중 일부는 사용자에게 노출되지 않고 [!DNL Audience Manager]에 의해 사용되지만 다른 ID는 UI(사용자 인터페이스)에도 표시됩니다.

다음 예에서 사용되는 접두사를 이해하려면 [DCS API 호출](../api/dcs-intro/dcs-api-reference/dcs-keys.md)에 대해 지원되는 특성을 참조하십시오.

## [!DNL Audience Manager] ID 목록 {#id-list}

| ID | 이름 및 설명 | 사용 및 예 | 사용자 인터페이스 위치 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]으로 알려져  [!UICONTROL Device ID]있습니다. [!DNL Audience Manager]이(가) 상호 작용하는 각 장치에 연결하는 38자리 숫자 장치 ID입니다. [!DNL Audience Manager] UI에서 고유한 사용자에 대한 언급이 나타날 때마다 이 ID를 생각해 보십시오. Audience Manager은 이 ID를 `demdex.net` 타사 도메인에 [!DNL cookie]으로 저장합니다. | [!DNL DCS] 호출에서 `uuid` 앞에 `d_` 접두사가 붙습니다. <br>예: `d_uuid = 07955261652886032950143702505894272138` | [유사 모델](../features/algorithmic-models/create-model.md)을 만들 때 [!DNL traits]을(를) 기준으로 필터링하고 세그먼트](../features/segments/segment-builder.md)를 작성할 때 &lt;a0/>을(를) 필터링할 수 있습니다. [[!UICONTROL Device ID] [트레이트](../reporting/general-reports.md)에 대한 일반 보고서 및 [트레이트](../reporting/trend-reports.md)에 대한 트렌드 보고서를 실행할 때 결과를 [!UICONTROL Device ID]별로 필터링할 수도 있습니다. |
| [!DNL ImsOrgId] | [!DNL Organization ID]. 이 ID는 회사가 [!DNL Experience Cloud] 계정을 등록할 때 제공하는 ID입니다. | `5DC5123F5245B1D20A490D46@AdobeOrg` | [!DNL Audience Manager] 사용자 인터페이스에 표시되지 않습니다. 회사의 [!DNL Organization ID]을(를) 찾는 방법에 대해 알려면 [조직 ID 찾기](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)를 참조하십시오. |
| [!DNL PID] | [!DNL Partner ID]. [!DNL PID]은 [!DNL Audience Manager]에 있는 회사 ID입니다. Audience Manager은 [!DNL imsOrgId]을 [!DNL PID]에 연결합니다. | `1352` | [!DNL Audience Manager] 사용자 인터페이스에 표시되지 않습니다. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. [!DNL Experience Cloud] ID([!DNL ECID], 레거시 약자 [!DNL MID] 또는 [!DNL MCID])는 [!DNL Organization ID] 및 [!DNL Audience Manager] [!UICONTROL Unique User ID]에서 수학적으로 파생됩니다. 이러한 ID가 일정하게 유지되는 한 특정 사용자에 대해 오른쪽 [!DNL ECID]을(를) 생성하는 것은 단순히 수학 문제입니다. 동일한 [!DNL Organization ID] 및 [!DNL Audience Manager] [!DNL UUID]의 경우 항상 동일한 [!DNL ECID] 값을 받습니다. [쿠키 및 Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 설명서의 [!DNL ECID]에 대한 자세한 내용을 볼 수 있습니다. | `mid = 08382830887934830189014177072406221371` | [!DNL Audience Manager] 사용자 인터페이스에 표시되지 않습니다. |
| [!DNL SID] | [!UICONTROL Trait ID]. [!UICONTROL Trait ID]은 [!DNL Audience Manager] 환경에서 [!DNL traits]을(를) 고유하게 식별합니다. | [!DNL DCS] 호출에서 `SID` 앞에 `d_` 접두사가 붙습니다. <br>예 `d_sid=289983`. | [!UICONTROL Trait ID]은 각 [!DNL trait]에 할당되고 사용자 인터페이스에 [트레이트](../features/traits/trait-details-page.md) 페이지가 표시됩니다. |
| [!DNL SID] | [!UICONTROL Segment ID]. [!UICONTROL Segment ID]은 [!DNL Audience Manager] 환경에서 [!DNL segments]을(를) 고유하게 식별합니다. | [!DNL DCS] 호출에서 `SID` 앞에 `d_` 접두사가 붙습니다. <br>예 `d_sid=4798574`. | [!UICONTROL Segment ID]은 각 [!DNL segment]에 할당되고 사용자 인터페이스에 [세그먼트](../features/segments/segment-summary-view.md) 페이지에 표시됩니다. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. 이 ID는 [!DNL Audience Manager] 환경에서 세그먼트를 고유하게 식별합니다. | `741232` | [!UICONTROL Legacy Segment ID]은 각 세그먼트에 할당되고 사용자 인터페이스에 표시됩니다([세그먼트](../features/segments/segment-summary-view.md)). |
| [!DNL destID] | [!UICONTROL Destination ID]. [!UICONTROL Destination ID]은 [!DNL Audience Manager] 환경에서 [!DNL destinations]을(를) 고유하게 식별합니다. 사용자 인터페이스의 각 [!DNL destination]에 ID가 할당됩니다. | `2523` | [!UICONTROL Destination ID]은 각 [!DNL destination]에 할당되고 사용자 인터페이스에 [대상](../features/destinations/destinations-home.md) 페이지가 표시됩니다. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (라고도  [!UICONTROL Data Provider ID]함). [!UICONTROL Data Source ID]은 ID 또는 [!DNL traits]의 네임스페이스입니다. 사용자 인터페이스의 각 [!DNL data source](데이터 공급자)에 ID가 할당됩니다. | [!DNL DCS] 호출에서 `dpid` 앞에 `d_` 접두사가 붙습니다. <br>예: `d_dpid=39217`. | [!UICONTROL Data Provider ID]은 각 [!DNL data source]에 할당되고 사용자 인터페이스에 표시됩니다([Data Sources](../features/datasources-list-and-settings.md) 페이지). |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]를  [!DNL CRM ID] 또는이라고도  [!UICONTROL Cross-Device ID]합니다. 타사 ID. 이 ID는 사용자가 자신의 [!DNL CRM] 시스템에서 최종 사용자를 식별하는 데 사용됩니다. [!DNL DPUUIDs]을(를) [!DNL Audience Manager] [!DNL UUIDs]와 동기화할 수 있으며 ID 동기화 프로세스에서 다른 [!UICONTROL Data Sources]([!DNL DPIDs])의 [!DNL DPUUIDs]을 동기화할 수 있습니다. | [!DNL DCS] 호출에서 `dpuuid` 앞에 `d_` 접두사가 붙습니다. <br> 예 `d_dpuuid=2132-3423vn-343fds-3432r`. | [유사 모델](../features/algorithmic-models/create-model.md)을 만들 때 [!DNL traits]을(를) 기준으로 필터링하고 세그먼트](../features/segments/segment-builder.md)를 작성할 때 &lt;a0/>을(를) 필터링할 수 있습니다. [[!UICONTROL Cross-Device ID] [트레이트](../reporting/general-reports.md)에 대한 일반 보고서 및 [트레이트](../reporting/trend-reports.md)에 대한 트렌드 보고서를 실행할 때 결과를 [!UICONTROL Cross-Device ID]별로 필터링할 수도 있습니다. |
| [!DNL CRM ID] | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. [!DNL CID] 및 [!DNL CID_IC] 키-값 쌍은 [!DNL DPID] 및 [!DNL DPUUID]을 대체합니다. 이러한 ID는 [!DNL DPID] 및 [!DNL DPUUID]와 동일한 기능을 제공하지만 단일 키-값 쌍에 데이터 공급자 ID 및 사용자 ID(또는 통합 코드)를 포함하므로 보다 효율적입니다. | [!DNL DCS] 호출에서 이러한 ID 앞에 `d_` 접두사가 붙습니다. <br>예: `d_cid_ic=39217_myIntegrationCode`. | `DPID` 및 `DPUUID`을 참조하십시오. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. 각 하드웨어 장치에 고유한 ID로서, 광고 목적으로 사용됩니다. 일반적으로 장치 또는 장치 운영 체제의 제조업체가 제공합니다. | [전역 장치 ID](#global-device-ids)를 참조하십시오. |  |

## [!DNL Global Device IDs] {#global-device-ids}

전역 장치 ID는 장치 제조업체 또는 운영 체제에서 제공하는 각 장치에 고유한 장치 광고 ID입니다. 아래 표는 이러한 ID가 무엇이고 형식이 무엇인지에 대해 설명합니다. 전역 장치 ID에 대한 자세한 내용 및 [!DNL Audience Manager]전역 데이터 소스](/help/using/features/global-data-sources.md)를 참조하십시오.[

| ID | [!DNL Global Data Source ID] | 이름 및 설명 | 예 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915년 | [!DNL Identifier for Advertisers] ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL iOS] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분되는 32개의 대문자 16진수 숫자(총 36자)로 엄격히 구성됩니다.<br> 예: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914년 | [!DNL Google Advertising ID]s는 Android 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL Android] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 5개 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 엄격히 구성되며, 총 36자입니다. <br>예: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 는  [!DNL Roku] 스트리밍 장치를 나타냅니다. | 형식은 5개 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 엄격히 구성되며, 총 36자입니다. <br>예: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s는 사용자별로 장치 단위 [!DNL Windows 10] 로 생성된 장치 식별자입니다. | [!DNL MAID]의 형식은 영숫자 문자열로 지정됩니다. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 은 스마트 TV에서 제공하는 장치  [!DNL Samsung] 식별자입니다. | [!DNL Samsung] [!DNL TIFA] ID는 영숫자 문자열로 서식이 지정됩니다. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | [!DNL Fire OS] 운영 체제를 실행하는 장치를 나타내는 장치 식별자. | 형식은 5개 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 엄격히 구성되며, 총 36자입니다. <br>예: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |