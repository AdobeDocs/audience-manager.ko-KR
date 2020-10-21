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


# ID의 색인 [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## 개요 {#overview}

[!DNL Audience Manager] 여러 ID를 사용하여 전송한 데이터를 식별하고 관리합니다. ID의 전체 목록과 함께 [!DNL Audience Manager] ID를 사용해야 하는 접두사가 나와 있습니다.

## ID 사전 수정 {#prefixing}

이러한 ID의 대부분을 독립 실행형 이름으로 참조할 수 있지만 대부분의 ID는 호출을 통해 데이터를 전달할 때 다양한 접두사와 함께 사용됩니다 [!DNL DCS] . 이러한 ID 중 일부는 사용자에게 노출되지 [!DNL Audience Manager] 않고 사용되지만, 다른 ID는 UI(사용자 인터페이스)에서도 볼 수 있습니다.

다음 예에서 사용되는 접두사를 이해하려면 DCS API 호출에 [대해 지원되는 특성을 참조하십시오](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] ID 목록 {#id-list}

| ID | 이름 및 설명 | 사용 및 예 | 사용자 인터페이스 위치 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]으로 알려져 [!UICONTROL Device ID]있습니다. 상호 작용하는 각 장치에 [!DNL Audience Manager] 연결하는 38자리 숫자 장치 ID입니다. UI에서 고유한 사용자에 대한 언급이 나타날 때마다 이 ID를 [!DNL Audience Manager] 고려하십시오. Audience Manager은 이 ID를 타사 도메인 [!DNL cookie] 에 `demdex.net` 저장합니다. | 호출에서 [!DNL DCS] 앞에 `uuid` `d_` 접두사가 붙습니다. <br>예: `d_uuid = 07955261652886032950143702505894272138` | 유사 모델 [!DNL traits] 을 만들 [!UICONTROL Device ID] 때 [필터링하고 세그먼트를](../features/algorithmic-models/create-model.md)작성할 수 있습니다 [](../features/segments/segment-builder.md). 트레이트에 대한 [!UICONTROL Device ID] 일반 보고서 [및 트레이트에 대한 트렌드 보고서](../reporting/general-reports.md) 를 실행할 때 결과를 필터링할 수도 있습니다 [](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. 이것은 [!DNL Experience Cloud] 계정 등록 시 회사가 제공하는 ID입니다. | `5DC5123F5245B1D20A490D46@AdobeOrg` | 사용자 인터페이스에 표시되지 [!DNL Audience Manager] 않습니다. 회사 ID를 찾는 방법에 대한 자세한 내용은 조직 ID [!DNL Organization ID]찾기를 참조하십시오 [](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. 회사 [!DNL PID] 의 ID입니다 [!DNL Audience Manager]. Audience Manager은 한 사람 [!DNL imsOrgId] 에 연결합니다 [!DNL PID]. | `1352` | 사용자 인터페이스에 표시되지 [!DNL Audience Manager] 않습니다. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. ID( [!DNL Experience Cloud] 기존 약어[!DNL ECID]또는 [!DNL MID] )는 사용자 [!DNL MCID]및 [!DNL Organization ID] ID에서 수학적으로 파생됩니다 [!DNL Audience Manager] [!UICONTROL Unique User ID]. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. 동일한 값 [!DNL Organization ID] 으로 언제든지 동일한 [!DNL Audience Manager] [!DNL UUID] [!DNL ECID] 가치를 얻을 수 있습니다. 쿠키 및 Experience Cloud ID 설명서 [!DNL ECID] 에서 [해당 항목에 대한 자세한 내용을](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 볼 수 있습니다. | `mid = 08382830887934830189014177072406221371` | 사용자 인터페이스에 표시되지 [!DNL Audience Manager] 않습니다. |
| [!DNL SID] | [!UICONTROL Trait ID]. 환경 [!UICONTROL Trait ID] 에서 [!DNL traits] 고유하게 식별됩니다 [!DNL Audience Manager] . | 호출에서 [!DNL DCS] 앞에 `SID` `d_` 접두사가 붙습니다. <br>예 `d_sid=289983`. | A [!UICONTROL Trait ID] 가 각 [!DNL trait]에 할당되고 사용자 인터페이스의 트레이트 [페이지에 표시됩니다](../features/traits/trait-details-page.md) . |
| [!DNL SID] | [!UICONTROL Segment ID]. 환경 [!UICONTROL Segment ID] 에서 [!DNL segments] 고유하게 식별됩니다 [!DNL Audience Manager] . | 호출에서 [!DNL DCS] 앞에 `SID` `d_` 접두사가 붙습니다. <br>예 `d_sid=4798574`. | A [!UICONTROL Segment ID] 가 각 세그먼트 [!DNL segment]에 할당되고 세그먼트 [페이지에서 사용자 인터페이스에 표시됩니다](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | [!DNL Legacy Segment ID]. 이 ID는 [!DNL Audience Manager] 환경에서 세그먼트를 고유하게 식별합니다. | `741232` | 세그먼트 [!UICONTROL Legacy Segment ID] 는 각 세그먼트에 할당되고 사용자 인터페이스에 [세그먼트](../features/segments/segment-summary-view.md) 페이지에 표시됩니다. |
| [!DNL destID] | [!UICONTROL Destination ID]. 환경 [!UICONTROL Destination ID] 에서 [!DNL destinations] 고유하게 식별됩니다 [!DNL Audience Manager] . 사용자 인터페이스의 각 [!DNL destination] 에 ID가 할당됩니다. | `2523` | A [!UICONTROL Destination ID] 가 각 [!DNL destination]에 할당되고 대상 페이지의 사용자 인터페이스에 [표시됩니다](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | [!UICONTROL Data Source ID] (라고도 [!UICONTROL Data Provider ID]함). ID 또는 [!UICONTROL Data Source ID] 의 네임스페이스입니다 [!DNL traits]. ID는 사용자 인터페이스의 각 [!DNL data source] (데이터 공급자)에 할당됩니다. | 호출에서 [!DNL DCS] 앞에 `dpid` `d_` 접두사가 붙습니다. <br>예: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] 가 각 [!DNL data source]에 할당되고 사용자 인터페이스에 [ [Data Sources] 페이지에 표시됩니다](../features/datasources-list-and-settings.md) . |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], also called to [!DNL CRM ID] or [!UICONTROL Cross-Device ID]. 타사 ID. 자신의 시스템에서 최종 사용자를 식별하는 ID입니다 [!DNL CRM] . ID 동기화 프로세스 [!DNL DPUUIDs] 에서 [!DNL Audience Manager] 동기화 [!DNL UUIDs] 를 [!DNL DPUUIDs] 하고 다른 [!UICONTROL Data Sources] ([!DNL DPIDs])에서 동기화할 수 있습니다. | 호출에서 [!DNL DCS] 앞에 `dpuuid` `d_` 접두사가 붙습니다. <br> 예 `d_dpuuid=2132-3423vn-343fds-3432r`. | 유사 모델 [!DNL traits] 을 만들 [!UICONTROL Cross-Device ID] 때 [필터링하고 세그먼트를](../features/algorithmic-models/create-model.md)작성할 수 있습니다 [](../features/segments/segment-builder.md). 트레이트에 대한 [!UICONTROL Cross-Device ID] 일반 보고서 [및 트레이트에 대한 트렌드 보고서](../reporting/general-reports.md) 를 실행할 때 결과를 필터링할 수도 있습니다 [](../reporting/trend-reports.md). |
| [!DNL CRM ID] | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. 및 [!DNL CID] 키-값 쌍 [!DNL CID_IC] 이 and를 대체합니다 [!DNL DPID] [!DNL DPUUID]. 데이터 제공자는 [!DNL DPID] 및 [!DNL DPUUID]와 동일한 기능을 제공하지만 단일 키-값 쌍에 데이터 공급자 ID 및 사용자 ID(또는 통합 코드)를 포함하므로 보다 효율적입니다. | 호출에서 [!DNL DCS] 이러한 ID 앞에 `d_` 접두사가 붙습니다. <br>예: `d_cid_ic=39217_myIntegrationCode`. | 및 `DPID` 을 참조하십시오 `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. 각 하드웨어 장치에 고유한 ID로서, 광고 목적으로 사용됩니다. 일반적으로 장치 또는 장치 운영 체제의 제조업체가 제공합니다. | 전역 [장치 ID를 참조하십시오](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

전역 장치 ID는 장치 제조업체 또는 운영 체제에서 제공하는 각 장치에 고유한 장치 광고 ID입니다. 아래 표는 이러한 ID가 무엇이고 형식이 무엇인지에 대해 설명합니다. 전역 장치 ID와 장치 ID를 사용하는 방법에 대한 자세한 내용 [!DNL Audience Manager]은 [전역 데이터 소스를 참조하십시오](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | 이름 및 설명 | 예 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL iOS] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 다섯 그룹으로 표시되고 하이픈으로 구분되는 32개의 대문자 16진수 숫자(총 36자)로 엄격히 구성됩니다.<br> 예: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s는 Android 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL Android] 운영 체제를 실행하는 장치를 나타냅니다. | 형식은 5개 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 엄격히 구성되며, 총 36자입니다. <br>예: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 는 [!DNL Roku] 스트리밍 장치를 나타냅니다. | 형식은 5개 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 엄격히 구성되며, 총 36자입니다. <br>예: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s는 사용자별로 장치 단위 [!DNL Windows 10] 로 생성된 장치 식별자입니다. | [!DNL MAID]의 형식은 영숫자 문자열로 지정됩니다. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 은 스마트 TV에서 제공하는 장치 [!DNL Samsung] 식별자입니다. | [!DNL Samsung] [!DNL TIFA] ID는 영숫자 문자열로 서식이 지정됩니다. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 운영 체제를 실행하는 장치를 나타내는 장치 [!DNL Fire OS] 식별자입니다. | 형식은 5개 그룹으로 표시되고 하이픈으로 구분되는 32개의 소문자 16진수로 엄격히 구성되며, 총 36자입니다. <br>예: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |