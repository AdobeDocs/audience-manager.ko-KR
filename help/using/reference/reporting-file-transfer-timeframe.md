---
description: Audience Manager은 매일 엄청난 양의 데이터를 받습니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 콘텐츠는 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 주는지 설명합니다. 또한, 여기에 설명된 시간대 및 일정은 일반적인 지침입니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe은 사전 통지 없이 언제든지 시간대 및 일정을 변경할 수 있는 권한을 보유합니다.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: 데이터 전달 및 파일 처리 시간이 보고서에 미치는 영향
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 4%

---

# 데이터 전달 및 파일 처리 시간이 보고서에 미치는 영향{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager은 매일 엄청난 양의 데이터를 받습니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 콘텐츠는 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 주는지 설명합니다. 또한, 여기에 설명된 시간대 및 일정은 일반적인 지침입니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe은 사전 통지 없이 언제든지 시간대 및 일정을 변경할 수 있는 권한을 보유합니다.

## 보고 번호 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

다음 표에는 일반적인 보고서와 실시간 보고서의 시간 간격이 나열되고 설명되어 있습니다.


| 데이터 유형 | 설명 |
|---|---|
| 실시간 데이터 | 오늘 실시간 번호는 00:00부터 23시간까지입니다.:59:어제부터 59 UTC입니다. |
| 일반 보고서 데이터 | 의 데이터 [일반 보고서](../reporting/general-reports.md#general-reports-overview) 다른 작업 프로세스의 성공적인 완료와 특정 날짜에 받은 데이터의 양에 따라 다릅니다. 대부분의 경우, [!UICONTROL General Report] 데이터는 매일 18:00 UTC까지 업데이트되어야 합니다. |

## 인바운드 및 아웃바운드 파일 전송 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 인바운드 및 아웃바운드 처리 및 전송 [!UICONTROL Server-to-Server (S2S)] 이 섹션에 설명된 일정에 따라 파일을 전송합니다. 이러한 일정과 마감 시간이 주어지면 실시간 및 총 세그먼트 번호 간에 새 세그먼트와 불일치가 표시될 수 있습니다.

| 파일 형식 | 설명 |
|---|---|
| 인바운드 파일 섭취(오프라인 데이터) | 파일 처리는 하루에 두 번 실행됩니다. 이러한 절차는 데이터를 수집하여 게재할 준비를 합니다. 파일 전달 시간은 처리해야 하는 고객 데이터의 총량에 의해 영향을 받기 때문에 달라집니다. 파일이 Audience Manager에 업로드되는 순간과 보고 및 활성화에 데이터를 사용할 수 있을 때까지 최대 48시간의 지연 시간을 예상해야 합니다. |
| 아웃바운드(내보내기) 파일 | 파일 처리 및 게재는 하루에 한 번, 약 14:00 UTC에 이루어집니다. 처리 및 게재는 이러한 파일의 총 수와 크기에 의해 영향을 받습니다. 경우에 따라 최대 24시간 동안 파일 처리가 지연될 수 있습니다. 이 경우 Audience Manager은 특정 날짜에 대해 1개가 아닌 2개의 파일을 전송합니다. 드물게 Audience Manager이 파일 처리를 모두 중단해야 하는 경우 고객에게 알립니다. 이러한 조건이 주어지면 아웃바운드 데이터의 게재 시간을 예측하기 어렵습니다. 전체 파일 세트를 받았는지 확인하려면 타임스탬프를 확인하고 누락된 날짜를 찾습니다. 파일이 생성된 시간을 기록하는 13자리 UNIX UTC 타임스탬프입니다. 다음을 참조하십시오 [실시간 아웃바운드 데이터 전송](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| 광고 서버 로그 파일 | 파일 처리는 시간별 파일이 준비될 때 로그 파일 레코드를 수집하기 위해 거의 실시간으로 실행됩니다. 보고를 위해 파일을 준비하는 프로세스가 하루에 한 번 실행됩니다. 파일 전달 시간은 처리해야 하는 고객 데이터의 총량에 의해 영향을 받기 때문에 달라집니다. Audience Manager에 파일을 업로드하는 순간과 보고 및 활성화에 데이터를 사용할 수 있는 순간 사이에 최대 48시간의 지연 시간이 예상됩니다. |

>[!MORELIKETHIS]
>
>* [인바운드 고객 데이터 섭취 FAQ](../faq/faq-inbound-data-ingestion.md)

