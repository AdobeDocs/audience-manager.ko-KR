---
description: Audience Manager은 매일 엄청난 양의 데이터를 수신합니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 내용은 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 미치는지 설명합니다. 또한 여기에 설명된 시간 및 일정은 일반적인 지침만 있습니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe은 사전 예고 없이 시간과 일정을 언제든지 변경할 수 있습니다.
seo-description: Audience Manager은 매일 엄청난 양의 데이터를 수신합니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 내용은 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 미치는지 설명합니다. 또한 여기에 설명된 시간 및 일정은 일반적인 지침만 있습니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe은 사전 예고 없이 시간과 일정을 언제든지 변경할 수 있습니다.
seo-title: 데이터 전달 및 파일 처리 시간이 보고서에 미치는 영향
solution: Audience Manager
title: 데이터 전달 및 파일 처리 시간이 보고서에 미치는 영향
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 5%

---


# 데이터 전달 및 파일 처리 시간이 보고서에 미치는 영향{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager은 매일 엄청난 양의 데이터를 수신합니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 내용은 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 미치는지 설명합니다. 또한 여기에 설명된 시간 및 일정은 일반적인 지침만 있습니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe은 사전 예고 없이 시간과 일정을 언제든지 변경할 수 있습니다.

## 보고 번호 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

다음 표에서는 일반 및 실시간 보고서의 시간 간격을 나열하고 설명합니다.


| 데이터 유형 | 설명 |
|---|---|
| 실시간 데이터 | 오늘의 실시간 숫자는 어제로부터 23:59:59 UTC까지 00:00에 대한 것입니다. |
| 일반 보고서 데이터 | [일반 보고서](../reporting/general-reports.md#general-reports-overview)의 데이터는 다른 작업 프로세스의 성공적인 완료와 특정 날짜에 수신된 데이터의 양에 따라 달라집니다. 대부분의 경우, [!UICONTROL General Report] 데이터는 매일 18:00 UTC까지 업데이트해야 합니다. |

## 인바운드 및 아웃바운드 파일 전송 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 이 섹션에 설명된 일정에 따라 인바운드 및 아웃바운드  [!UICONTROL Server-to-Server (S2S)] 파일 전송을 처리하고 전송합니다. 이러한 일정과 잘라내기 시간이 주어지면 실시간 및 총 세그먼트 번호 간의 새 세그먼트와 불일치가 생길 수 있습니다.

| 파일 형식 | 설명 |
|---|---|
| 인바운드 파일 통합(오프라인 데이터) | 파일 처리가 하루에 두 번 실행됩니다. 이러한 절차에서는 데이터를 수집하여 배달할 준비를 합니다. 파일 배달 시간은 처리해야 하는 총 고객 데이터의 양에 영향을 받기 때문에 다릅니다. Audience Manager에 파일이 업로드되는 순간과 보고 및 활성화를 위해 데이터를 사용할 수 있을 때까지 최대 지연 시간은 48시간입니다. |
| 아웃바운드(내보내기) 파일 | 파일 처리 및 배달은 약 14:00 UTC에 하루에 한 번 이루어집니다. 처리 및 배달은 이러한 파일의 총 수와 크기에 영향을 받습니다. 경우에 따라 파일 처리가 24시간 동안 지연될 수 있습니다. 이 경우 Audience Manager은 특정 날짜에 대해 1개 대신 2개의 파일을 전송합니다. 우리는 드물지만 Audience Manager이 파일 처리를 모두 중단해야 하는 경우 고객에게 통지할 것입니다. 이러한 상황에서 아웃바운드 데이터의 배달 시간을 예상하는 것은 어렵습니다. 전체 파일 세트를 받았는지 확인하려면 타임스탬프를 확인하고 누락된 요일이 있는지 확인합니다. 파일이 생성된 시간을 기록하는 13자리 UNIX UTC 타임스탬프입니다. [실시간 아웃바운드 데이터 전송](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)을 참조하십시오. |
| 광고 서버 로그 파일 | 시간별 파일이 준비되면 거의 실시간으로 로그 파일 레코드를 인제스트하는 파일 처리가 실행됩니다. 보고를 위한 파일을 준비하는 프로세스는 하루에 한 번 실행됩니다. 파일 배달 시간은 처리해야 하는 총 고객 데이터의 양에 영향을 받기 때문에 다릅니다. 파일을 Audience Manager에 업로드하는 순간과 보고 및 활성화를 위해 데이터를 사용할 수 있는 순간 사이의 최대 지연 시간은 48시간입니다. |

>[!MORELIKETHIS]
>
>* [인바운드 고객 데이터 섭취 FAQ](../faq/faq-inbound-data-ingestion.md)

