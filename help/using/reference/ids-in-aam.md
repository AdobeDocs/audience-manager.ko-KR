---
description: Adobe Audience Manager ID의 전체 목록은 이 문서 를 참조하십시오.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
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

# 의 ID 색인 [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## 개요 {#overview}

[!DNL Audience Manager] 는 여러 ID를 사용하여 전송하는 데이터를 식별하고 관리합니다. 의 전체 목록은 이 문서 를 참조하십시오. [!DNL Audience Manager] 사용해야 하는 접두사의 예와 함께 ID입니다.

## ID 접두사 {#prefixing}

이러한 ID의 대부분은 독립형 이름으로 참조할 수 있지만, 데이터 전달 시 대부분 다양한 접두사와 함께 사용됩니다 [!DNL DCS] 호출. 이러한 ID 중 일부는 다음에서 사용됩니다. [!DNL Audience Manager] 다른 항목은 사용자에게 표시되지 않지만 UI(사용자 인터페이스)에서 볼 수도 있습니다.

다음 예제에 사용된 접두사를 이해하려면 다음을 참조하십시오 [DCS API 호출에 지원되는 특성](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] ID 목록 {#id-list}

| ID | 이름 및 설명 | 사용 및 예 | 사용자 인터페이스 위치 |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID]라고도 함 [!UICONTROL Device ID]. 숫자 38자리 장치 ID [!DNL Audience Manager] 는 상호 작용하는 각 디바이스에 연결합니다. 에서 고유 사용자에 대한 언급이 표시될 때마다 이 ID를 생각해 보십시오 [!DNL Audience Manager] UI. Audience Manager이 이 ID를 (으)로 저장 [!DNL cookie] 다음에서 `demdex.net` 타사 도메인. | 위치 [!DNL DCS] 호출, `uuid` 앞에 다음 문자가 옵니다. `d_` 접두사입니다. <br>예: `d_uuid = 07955261652886032950143702505894272138` | 필터링할 수 있습니다. [!DNL traits] 작성자: [!UICONTROL Device ID] 생성 시 [유사 모델](../features/algorithmic-models/create-model.md), 및 [세그먼트 작성](../features/segments/segment-builder.md). 다음을 기준으로 결과를 필터링할 수도 있습니다. [!UICONTROL Device ID] 실행 시 [트레이트에 대한 일반 보고서](../reporting/general-reports.md) 및 [트레이트에 대한 트렌드 보고서](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. 가입 시 회사에 제공되는 ID입니다. [!DNL Experience Cloud] 계정입니다. | `5DC5123F5245B1D20A490D46@AdobeOrg` | 에 표시되지 않음 [!DNL Audience Manager] 사용자 인터페이스. 회사의 [!DNL Organization ID], 읽기 [조직 ID 찾기](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. 다음 [!DNL PID] 은(는) 의 회사 ID입니다. [!DNL Audience Manager]. Audience Manager이 [!DNL imsOrgId] (으)로 [!DNL PID]. | `1352` | 에 표시되지 않음 [!DNL Audience Manager] 사용자 인터페이스. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. 다음 [!DNL Experience Cloud] ID ([!DNL ECID], 기존 약자 [!DNL MID] 또는 [!DNL MCID])은 에서 수학적으로 파생됩니다. [!DNL Organization ID] 및 [!DNL Audience Manager] [!UICONTROL Unique User ID]. 이러한 ID가 일정하게 유지되면 권한이 생성됩니다 [!DNL ECID] 특정 사용자에게는 단순한 수학 문제가 됩니다. 동일한 [!DNL Organization ID] 및 [!DNL Audience Manager] [!DNL UUID] 너도 마찬가지고 [!DNL ECID] 매번 값을 지정합니다. 다음에 대한 자세한 내용을 볼 수 있습니다. [!DNL ECID] 다음에서 [쿠키 및 Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) 설명서를 참조하십시오. | `mid = 08382830887934830189014177072406221371` | 에 표시되지 않음 [!DNL Audience Manager] 사용자 인터페이스. |
| [!DNL SID] | [!UICONTROL Trait ID]. 다음 [!UICONTROL Trait ID] 고유 식별 [!DNL traits] 다음에서 [!DNL Audience Manager] 환경. | 위치 [!DNL DCS] 호출, `SID` 앞에 다음 문자가 옵니다. `d_` 접두사입니다. <br>예 `d_sid=289983`. | A [!UICONTROL Trait ID] 다음에 할당됨: [!DNL trait], 및 의 사용자 인터페이스에 표시 [트레이트](../features/traits/trait-details-page.md) 페이지를 가리키도록 업데이트하는 중입니다. |
| [!DNL SID] | [!UICONTROL Segment ID]. 다음 [!UICONTROL Segment ID] 고유 식별 [!DNL segments] 다음에서 [!DNL Audience Manager] 환경. | 위치 [!DNL DCS] 호출, `SID` 앞에 다음 문자가 옵니다. `d_` 접두사입니다. <br>예 `d_sid=4798574`. | A [!UICONTROL Segment ID] 다음에 할당됨: [!DNL segment], 및 의 사용자 인터페이스에 표시 [세그먼트](../features/segments/segment-summary-view.md) 페이지를 가리키도록 업데이트하는 중입니다. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. 이 ID는 [!DNL Audience Manager] 환경. | `741232` | A [!UICONTROL Legacy Segment ID] 가 각 세그먼트에 할당되고 의 사용자 인터페이스에 표시됩니다. [세그먼트](../features/segments/segment-summary-view.md) 페이지를 가리키도록 업데이트하는 중입니다. |
| [!DNL destID] | [!UICONTROL Destination ID]. 다음 [!UICONTROL Destination ID] 고유 식별 [!DNL destinations] 다음에서 [!DNL Audience Manager] 환경. 각각에 ID가 할당됩니다 [!DNL destination] 을 참조하십시오. | `2523` | A [!UICONTROL Destination ID] 다음에 할당됨: [!DNL destination], 및 의 사용자 인터페이스에 표시 [대상](../features/destinations/destinations-home.md) 페이지를 가리키도록 업데이트하는 중입니다. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (또한으로 지칭됨) [!UICONTROL Data Provider ID]). 다음 [!UICONTROL Data Source ID] 는 ID용 네임스페이스이거나 [!DNL traits]. 각각에 ID가 할당됩니다 [!DNL data source] (데이터 공급자) 을 입력합니다. | 위치 [!DNL DCS] 호출, `dpid` 앞에 다음 문자가 옵니다. `d_` 접두사입니다. <br>예: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] 다음에 할당됨: [!DNL data source], 및 의 사용자 인터페이스에 표시 [데이터 소스](../features/datasources-list-and-settings.md) 페이지를 가리키도록 업데이트하는 중입니다. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID]이라고도 합니다. [!DNL CRM ID] 또는 [!UICONTROL Cross-Device ID]. 타사 ID. 최종 사용자를 직접 식별하는 ID입니다 [!DNL CRM] 시스템. 동기화할 수 있음 [!DNL DPUUIDs] 포함 [!DNL Audience Manager] [!DNL UUIDs] 동기화 가능 [!DNL DPUUIDs] 다른 항목에서 [!UICONTROL Data Sources] ([!DNL DPIDs])을 클릭하여 제품에서 사용할 수 있습니다. | 위치 [!DNL DCS] 전화, `dpuuid` 앞에 다음 문자가 옵니다. `d_` 접두사입니다. <br> 예 `d_dpuuid=2132-3423vn-343fds-3432r`. | 필터링할 수 있습니다. [!DNL traits] 작성자: [!UICONTROL Cross-Device ID] 생성 시 [유사 모델](../features/algorithmic-models/create-model.md), 및 [세그먼트 작성](../features/segments/segment-builder.md). 다음을 기준으로 결과를 필터링할 수도 있습니다. [!UICONTROL Cross-Device ID] 실행 시 [트레이트에 대한 일반 보고서](../reporting/general-reports.md) 및 [트레이트에 대한 트렌드 보고서](../reporting/trend-reports.md). |
| [!DNL CRM ID] | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. | 자세한 내용은 `DPUUID`를 참조하십시오. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. 다음 [!DNL CID] 및 [!DNL CID_IC] 키-값 쌍 바꾸기 [!DNL DPID] 및 [!DNL DPUUID]. 이는 와 동일한 기능을 제공합니다. [!DNL DPID] 및 [!DNL DPUUID]를 사용하는 대신 데이터 공급자 ID와 사용자 ID(또는 통합 코드)가 단일 키-값 쌍에 포함되므로 더 효율적입니다. | 위치 [!DNL DCS] 호출, 이러한 ID 앞에는 `d_` 접두사입니다. <br>예: `d_cid_ic=39217_myIntegrationCode`. | 다음을 참조하십시오 `DPID` 및 `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. 각 하드웨어 장치에 고유한 ID로서, 광고 목적으로 사용됩니다. 일반적으로 장치 또는 장치 운영 체제 제조업체가 제공합니다. | 다음을 참조하십시오 [글로벌 장치 ID](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

글로벌 장치 ID는 장치 제조업체 또는 운영 체제에서 제공하는 각 장치에 고유한 장치 광고 ID입니다. 아래 표는 이러한 ID의 의미와 해당 형식을 설명합니다. 전역 장치 ID와 전역 장치 ID를 사용하는 방법에 대한 자세한 내용은에서 확인하십시오. [!DNL Audience Manager], 읽기 [글로벌 데이터 소스](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | 이름 및 설명 | 예 |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] ID는 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL iOS] 운영 체제. | 형식은 엄격하게 32개의 대문자 16진수로 구성되며, 5개의 그룹으로 구분되고 하이픈으로 구분됩니다(8-4-4-4-12 형식). 총 36자입니다.<br> 예: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s는 Android 장치 제조업체에서 제공하는 모바일 장치 식별자입니다. 이러한 ID는 [!DNL Android] 운영 체제. | 형식은 엄격하게 32개의 소문자 16진수 숫자로 구성되며, 5개의 그룹으로 구분되고 하이픈으로 구분됩니다(8-4-4-4-12 형식). 총 36자의 문자입니다. <br>예: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] 표시 [!DNL Roku] 스트리밍 디바이스입니다. | 형식은 엄격하게 32개의 소문자 16진수 숫자로 구성되며, 5개의 그룹으로 구분되고 하이픈으로 구분됩니다(8-4-4-4-12 형식). 총 36자의 문자입니다. <br>예: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s는에서 생성한 디바이스 식별자입니다. [!DNL Windows 10] 디바이스별로, 사용자별로 | [!DNL MAID]s는 영숫자 문자열로 포맷됩니다. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] 은(는) 다음에서 제공하는 장치 식별자입니다. [!DNL Samsung] 스마트 TV. | [!DNL Samsung] [!DNL TIFA] ID는 영숫자 문자열로 포맷됩니다. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | 다음을 실행하는 장치를 나타내는 장치 식별자 [!DNL Fire OS] 운영 체제. | 형식은 엄격하게 32개의 소문자 16진수 숫자로 구성되며, 5개의 그룹으로 구분되고 하이픈으로 구분됩니다(8-4-4-4-12 형식). 총 36자의 문자입니다. <br>예: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | 다음을 실행하는 장치를 나타내는 장치 식별자 [!DNL LG webOS] 운영 체제. | 형식은 엄격하게 32개의 소문자 16진수 숫자로 구성되며, 5개의 그룹으로 구분되고 하이픈으로 구분됩니다(8-4-4-4-12 형식). 총 36자의 문자입니다. <br>예: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Vizio 스마트 TV 운영 체제를 실행하는 장치를 나타내는 장치 식별자입니다. | [!DNL Vizio IFA] ID는 영숫자 문자열로 포맷됩니다. <br>예: `7XCBNROQJQPYW`. |
