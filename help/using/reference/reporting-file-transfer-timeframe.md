---
description: Audience Manager는 매일 엄청난 양의 데이터를 수신합니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 컨텐츠는 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 미치는지 설명합니다. 또한 여기에 설명된 시간 프레임과 일정은 일반적인 지침만 있습니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe는 사전 통보 없이 언제든지 시간 프레임 및 일정을 변경할 수 있는 권한을 보유합니다.
seo-description: Audience Manager는 매일 엄청난 양의 데이터를 수신합니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 컨텐츠는 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 미치는지 설명합니다. 또한 여기에 설명된 시간 프레임과 일정은 일반적인 지침만 있습니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe는 사전 통보 없이 언제든지 시간 프레임 및 일정을 변경할 수 있는 권한을 보유합니다.
seo-title: 데이터 배달 및 파일 처리 시간이 보고서에 미치는 영향
solution: Audience Manager
title: 데이터 배달 및 파일 처리 시간이 보고서에 미치는 영향
uuid: 4b975512-f67e-4749-a7ef-16841597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 데이터 배달 및 파일 처리 시간이 보고서에 미치는 영향{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager는 매일 엄청난 양의 데이터를 수신합니다. 이는 데이터를 처리하고 보고서 결과를 생성하는 데 걸리는 시간에 영향을 줍니다. 이 섹션의 컨텐츠는 이러한 시간 간격이 Audience Manager 계정에 어떤 영향을 미치는지 설명합니다. 또한 여기에 설명된 시간 프레임과 일정은 일반적인 지침만 있습니다. 이러한 일정은 데이터 전달과 관련된 SLA(서비스 수준 계약)나 약정을 구성하지 않습니다. Adobe는 사전 통보 없이 언제든지 시간 프레임 및 일정을 변경할 수 있는 권한을 보유합니다.

## 보고 번호 {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

다음 표는 일반 및 실시간 보고서의 시간 간격을 나열하고 설명합니다.

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
   <td colname="col2"> <p> 오늘의 실시간 숫자는 어제의 00:00 ~ 23:59:59 UTC에 대한 것입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>일반 보고서 데이터</b> </p> </td> 
   <td colname="col2"> <p>일반 보고서의 <a href="../reporting/general-reports.md#general-reports-overview"> 데이터는</a> 다른 작업 프로세스의 성공적인 완료와 특정 날짜에 수신된 데이터의 양에 따라 달라집니다. 대부분의 경우, 일반 <span class="wintitle"> 보고서</span> 데이터는 매일 18:00 UTC까지 업데이트해야 합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 인바운드 및 아웃바운드 파일 전송 {#inbound-outbound-file-transfers}

[!DNL Audience Manager] 이 섹션에 설명된 일정에 따라 인바운드 및 아웃바운드 [!UICONTROL Server-to-Server (S2S)] 파일 전송을 처리하고 전송합니다. 이러한 일정과 잘라내기 시간이 주어지면, 실시간 및 총 세그먼트 번호 사이에 새 세그먼트와 불일치가 있을 수 있습니다.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 파일 형식 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>인바운드 파일 통합(오프라인 데이터)</b> </p> </td> 
   <td colname="col2"> <p>파일 처리는 하루에 두 번 실행됩니다. 이러한 절차는 데이터를 인제스트하고 배달할 준비를 합니다. </p> <p>파일 배달 시간은 처리해야 하는 고객 데이터의 전체 양에 영향을 받기 때문에 다릅니다. Audience Manager에 파일이 업로드되는 순간과 보고 및 활성화에 <span class="keyword"> 데이터를 사용할 수 있을 때까지 최대</span> 대기 시간이 48시간이어야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>아웃바운드(내보내기) 파일</b> </p> </td> 
   <td colname="col2"> <p>파일 처리 및 배달은 약 14:00 UTC에 하루에 한 번 이루어집니다. 처리 및 배달은 이러한 파일의 총 수와 크기에 영향을 받습니다. 경우에 따라 24시간 동안 파일 처리가 지연될 수 있습니다. 이 경우 Audience Manager <span class="keyword"> 는</span> 특정 날짜에 대해 1개 대신 2개의 파일을 전송합니다. Adobe는 Audience Manager가 파일 처리를 <span class="keyword"> 모두</span> 중지해야 하는 드문 경우에 고객에게 알릴 것입니다. 이러한 상황에서 아웃바운드 데이터의 배달 시간을 예측하기는 어렵습니다. </p> <p>전체 파일 세트를 받았는지 확인하려면 타임스탬프를 확인하고 누락된 날짜를 찾습니다. 파일을 만든 시간을 기록하는 13자리 UNIX UTC 타임스탬프입니다. 실시간 <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> 아웃바운드 데이터 전송을 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKE_THIS]
>
>* [인바운드 고객 데이터 통합 FAQ](../faq/faq-inbound-data-ingestion.md)

