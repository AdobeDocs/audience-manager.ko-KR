---
description: Adobe Audience Manager는 매일 엄청난 양의 데이터를 받고 있습니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 내용은 이러한 시간 간격이 Audience Manager 계정에 어떻게 영향을 주는지 설명합니다. 또한 여기에 설명된 시간 프레임 및 일정은 일반 지침입니다. 이러한 일정은 데이터 전달과 관련된 SLA (서비스 수준 계약) 또는 약정을 구성하지 않습니다. Adobe는 사전 통지 없이 언제든지 기간 및 일정을 변경할 수 있습니다.
seo-description: Adobe Audience Manager는 매일 엄청난 양의 데이터를 받고 있습니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 내용은 이러한 시간 간격이 Audience Manager 계정에 어떻게 영향을 주는지 설명합니다. 또한 여기에 설명된 시간 프레임 및 일정은 일반 지침입니다. 이러한 일정은 데이터 전달과 관련된 SLA (서비스 수준 계약) 또는 약정을 구성하지 않습니다. Adobe는 사전 통지 없이 언제든지 기간 및 일정을 변경할 수 있습니다.
seo-title: 데이터 배달 및 파일 처리 시간이 보고서에 미치는 영향
solution: Audience Manager
title: 데이터 배달 및 파일 처리 시간이 보고서에 미치는 영향
uuid: 4 B 975512-F 67 E -4749-A 7 EF -168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

Adobe Audience Manager는 매일 엄청난 양의 데이터를 받고 있습니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 내용은 이러한 시간 간격이 Audience Manager 계정에 어떻게 영향을 주는지 설명합니다. 또한 여기에 설명된 시간 프레임 및 일정은 일반 지침입니다. 이러한 일정은 데이터 전달과 관련된 SLA (서비스 수준 계약) 또는 약정을 구성하지 않습니다. Adobe는 사전 통지 없이 언제든지 기간 및 일정을 변경할 수 있습니다.

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

다음 표에서는 일반 및 실시간 보고서의 시간 간격을 나열하고 설명합니다.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 데이터 유형 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>실시간 데이터</b> </p> </td> 
   <td colname="col2"> <p> 오늘 실시간 번호는 어제까지의 UTC 시간 00:00 ~ 23:59:59 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>일반 보고서 데이터</b> </p> </td> 
   <td colname="col2"> <p><a href="../reporting/general-reports.md#general-reports-overview"> 일반 보고서의</a> 데이터는 다른 작업 프로세스의 성공적인 완료와 특정 날짜에 대해 받은 데이터의 양에 따라 달라집니다. Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 이 섹션에 설명된 일정에 따라 인바운드 및 아웃바운드 [!UICONTROL Server-to-Server (S2S)] 파일 전송을 처리하고 전송합니다. 이러한 일정과 종료 시간이 주어지면, 실시간 세그먼트와 총 세그먼트 번호 간의 새로운 세그먼트와 일치하지 않을 수 있습니다.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 형식 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>인바운드 파일 통합 (오프라인 데이터)</b> </p> </td> 
   <td colname="col2"> <p>파일 처리는 하루에 두 번 실행됩니다. 이러한 절차는 데이터를 인제스트하고 전달하도록 준비합니다. </p> <p>파일 배달 시간은 처리해야 하는 총 고객 데이터의 영향을 받으므로 다릅니다. You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>아웃바운드 (내보내기) 파일</b> </p> </td> 
   <td colname="col2"> <p>파일 처리 및 전달은 하루 약 14:00 UTC에 하루에 한 번 수행됩니다. 처리 및 전달은 이러한 파일의 총 수와 크기에 영향을 받습니다. 경우에 따라 24 시간 동안 파일 처리가 지연될 수 있습니다. When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. We will notify our customers in the rare case where <span class="keyword"> Audience Manager</span> has to stop processing a file altogether. 이러한 조건으로 아웃바운드 데이터에 대한 배달 시간을 예측하기는 어렵습니다. </p> <p>전체 파일 세트를 받았는지 확인하려면 타임스탬프를 확인하고 누락된 날을 찾습니다. 파일이 생성된 시간을 기록하는 13 자리 UNIX UTC 타임스탬프입니다. See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [인바운드 고객 데이터 통합 FAQ](../faq/faq-inbound-data-ingestion.md)

