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
source-wordcount: '447'
ht-degree: 4%

---

# 글로벌 데이터 소스 {#global-data-sources}

## 개요

글로벌 데이터 소스는 모든 Audience Manager 고객이 액세스할 수 있으며 [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] 및 [!DNL Android] 장치 제조사와 같은 장치 제조업체에서 생성한 장치 광고 ID를 포함합니다. 이러한 ID는 광고 목적으로 제조 업체에서 사용할 수 있습니다. Audience Manager 고객은 전역 데이터 소스를 사용하여 장치 ID를 동기화하고 이러한 매핑에서 데이터를 가져오거나 내보낼 수 있습니다.

다음 표에서는 Audience Manager에서 지원하는 글로벌 데이터 소스에 대해 설명합니다.

| 데이터 Source ID | 설명 |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** ID는 [!DNL Android] 운영 체제를 실행하는 장치를 나타냅니다. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** ID는 [!DNL iOS] 운영 체제를 실행하는 장치를 나타냅니다. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]**&#x200B;개의 ID가 [!DNL Roku]개의 스트리밍 장치를 나타냅니다. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** ID는 [!DNL Windows 10] 운영 체제를 실행하는 장치를 나타냅니다. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]**&#x200B;개의 ID가 [!DNL Samsung]개의 스마트 TV를 나타냅니다. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]**&#x200B;은(는) [!DNL Amazon Fire OS]을(를) 실행하는 장치를 나타냅니다. |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]**&#x200B;은(는) [!DNL LG webOS] 운영 체제를 실행하는 장치를 나타냅니다. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]**&#x200B;은(는) Vizio 스마트 TV 운영 체제를 실행하는 장치를 나타냅니다. |

## 글로벌 데이터 소스에서 데이터 가져오기

[실시간 데이터 전송](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) 및 [일괄 데이터 전송](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)을 통해 글로벌 데이터 원본에서 장치 ID를 가져올 수 있습니다.

>[!IMPORTANT]
>
>글로벌 장치 ID를 사용하여 Audience Manager에 데이터를 보낼 때 해당 장치 ID에 해당하는 데이터 소스를 사용해야 합니다. 예: [!DNL Apple IDFA]에 대한 데이터를 가져오려면 데이터 원본 ID 20915을 사용하십시오.

## 제한

[!DNL iOS] 및 [!DNL Android] 운영 체제를 실행하는 장치에서는 기본 응용 프로그램만 장치 광고 ID([!UICONTROL DAID])를 검색하고 사용할 수 있습니다. 모바일 브라우저에서 실행되는 웹 애플리케이션은 장치 광고 ID에 액세스할 수 없습니다.

## 전역 장치 ID 유효성 검사

Audience Manager은 해당 형식을 기반으로 하여 고객이 가져온 장치 광고 ID([!UICONTROL DAID])를 확인하여, 장치 제조 업체에 설명한 표준 형식과 일치하는지 확인합니다. 글로벌 데이터 소스에 대한 장치 광고 ID의 자세한 매핑과 각 ID에 대한 적절한 형식은 [Audience Manager의 ID 색인](../reference/ids-in-aam.md)을 참조하십시오. 장치 유형에 따라 올바른 형식으로 장치 ID를 가져오고 있는지 확인하십시오. Audience Manager은 적절한 형식을 충족하지 않는 장치 ID를 거부하고 ID가 거부되었음을 나타내는 오류 메시지를 반환합니다.

* 일괄 데이터 전송에 대한 오류 메시지는 다음에 요약되어 있습니다. [온보딩 상태 보고서 용어 및 정의](../reporting/onboarding-status-report.md#report-terms-conditions).
* 실시간 데이터 전송에 대한 오류 메시지는 [DCS 오류 코드, 메시지 및 예제](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)에 설명되어 있습니다.

## 장치 ID 만료 정책

Audience Manager은 [AAM UUID](../faq/faq-privacy.md)와 같이 120일 동안 활동이 없으면 장치 광고 ID를 자동으로 버립니다.

## 새 글로벌 데이터 소스 요청

Audience Manager에 추가할 새 글로벌 데이터 소스를 요청하려면 Adobe Consulting 또는 Adobe 고객 지원 센터에 연락하여 필요한 데이터 소스에 대한 자세한 정보를 제공하십시오.

* 요청한 플랫폼의 이름(예: [!UICONTROL Apple IDFA]);
* 플랫폼을 관리하는 회사/조직의 이름(예: [!UICONTROL Apple Inc.]);
* 장치 광고 ID 네임스페이스에 대한 기술 사양의 링크(예: [AdSupport 설명서](https://developer.apple.com/documentation/adsupport)).
