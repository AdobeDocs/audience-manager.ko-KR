---
description: 글로벌 데이터 소스를 사용하여 장치 광고 ID를 가져옵니다.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: 글로벌 데이터 소스
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 6%

---

# 글로벌 데이터 소스 {#global-data-sources}

## 개요

글로벌 데이터 소스는 모든 Audience Manager 고객이 액세스할 수 있으며 다음과 같은 장치 제조업체에서 생성한 장치 광고 ID를 포함합니다. [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku], 및 [!DNL Android] 디바이스 제조업체. 이러한 ID는 광고 목적으로 제조 업체에서 사용할 수 있습니다. Audience Manager 고객은 전역 데이터 소스를 사용하여 장치 ID를 동기화하고 이러한 매핑에서 데이터를 가져오거나 내보낼 수 있습니다.

다음 표에서는 Audience Manager에서 지원하는 전역 데이터 소스에 대해 설명합니다.

| 데이터 소스 ID | 설명 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** ID는 를 실행하는 디바이스를 나타냅니다. [!DNL Android] 운영 체제. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** ID는 를 실행하는 디바이스를 나타냅니다. [!DNL iOS] 운영 체제. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** ID 는 [!DNL Roku] 스트리밍 디바이스입니다. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** ID는 를 실행하는 장치를 나타냅니다. [!DNL Windows 10] 운영 체제. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID 는 [!DNL Samsung] 스마트 TV. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** 실행 중인 장치 표시 [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** 를 실행하는 장치를 나타냅니다. [!DNL LG webOS] 운영 체제. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** vizio 스마트 TV 운영 체제를 실행하는 장치를 나타냅니다. |

## 글로벌 데이터 소스에서 데이터 가져오기

두 가지를 통해 글로벌 데이터 소스에서 장치 ID를 가져올 수 있습니다 [실시간 데이터 전송](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) 및 [일괄 데이터 전송](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>글로벌 장치 ID를 사용하여 데이터를 Audience Manager에 보낼 때 해당 장치 ID에 해당하는 데이터 소스를 사용해야 합니다. 예: 다음에 대한 데이터를 가져옵니다. [!DNL Apple IDFA], 데이터 소스 ID 20915 사용

## 제한

실행 중인 장치에서 [!DNL iOS] 및 [!DNL Android] 운영 체제에서는 기본 애플리케이션만 장치 광고 ID( )를 검색하고 사용할 수 있습니다.[!UICONTROL DAID]s). 모바일 브라우저에서 실행되는 웹 애플리케이션은 장치 광고 ID에 액세스할 수 없습니다.

## 전역 장치 ID 유효성 검사

Audience Manager이 장치 광고 ID([!UICONTROL DAID])를 가져왔습니다. 해당 형식을 기반으로 하여 장치 제조 업체에 설명한 표준 형식과 일치하는지 확인해야 합니다. 다음을 참조하십시오 [Audience Manager 내 ID 색인](../reference/ids-in-aam.md) 장치 광고 ID를 글로벌 데이터 소스에 상세하게 매핑하고 각 ID에 대해 적절한 형식을 지정합니다. 장치 유형에 따라 올바른 형식으로 장치 ID를 가져오고 있는지 확인하십시오. Audience Manager은 적절한 형식을 충족하지 않는 장치 ID를 거부하고 ID가 거부되었음을 나타내는 오류 메시지를 반환합니다.

* 배치 데이터 전송에 대한 오류 메시지는 다음에 요약되어 있습니다. [온보딩 상태 보고서 용어 및 정의](../reporting/onboarding-status-report.md#report-terms-conditions).
* 실시간 데이터 전송에 대한 오류 메시지는 다음과 같이 요약되어 있습니다. [DCS 오류 코드, 메시지 및 예제](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## 장치 ID 만료 정책

Audience Manager은 120일 동안 활동이 없으면 과 유사하게 장치 광고 ID를 자동으로 버립니다. [AAM UUID](../faq/faq-privacy.md)s.

## 새 글로벌 데이터 소스 요청

Audience Manager에 추가할 새 글로벌 데이터 소스를 요청하려면 Adobe 컨설팅 또는 고객 지원 센터 Adobe에 연락하여 필요한 데이터 소스에 대한 자세한 정보를 제공하십시오.

* 요청한 플랫폼의 이름(예: [!UICONTROL Apple IDFA]);
* 플랫폼을 관리하는 회사/조직의 이름(예: [!UICONTROL Apple Inc.]);
* 장치 광고 ID 네임스페이스에 대한 기술 사양 링크(예: [AdSupport 설명서](https://developer.apple.com/documentation/adsupport)).
