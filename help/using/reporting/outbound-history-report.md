---
description: 지정된 대상 및 기간에 대한 아웃바운드 배치 작업 내역 정보를 봅니다.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: 아웃바운드 파일 기록
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 1%

---

# 아웃바운드 파일 기록 {#outbound-file-history}

지정된 대상 및 기간에 대한 아웃바운드 배치 작업 내역 정보를 봅니다.

<!-- 

t_reports_outbound_history.xml

 -->

1. **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**&#x200B;을(를) 클릭합니다.

   ![단계 결과](assets/outbound_history.png)

1. **[!UICONTROL Search for a Destination]** 상자에서 입력을 시작하고 원하는 대상을 선택합니다.
1. **[!UICONTROL Select a Date Range]** 상자에서 보고서의 시작 날짜와 종료 날짜를 지정한 다음 **[!UICONTROL Apply Date Filter]**&#x200B;을(를) 클릭합니다.

   ![단계 결과](assets/outbound_history_stats.png)

   다음 표에는 보고서의 열에 해당하는 정보가 포함되어 있습니다.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 라인 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 데이터 동기화 파일 이름 </td> 
   <td colname="col2"> <p>이 대상에 대해 <span class="keyword"> Adobe</span>이(가) 함께 생성한 모든 아웃바운드 파일 목록입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 성공 </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에서 대상으로 성공적으로 전송된 레코드 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 실패 </td> 
   <td colname="col2"> <p>대상으로 전송할 수 없는 레코드 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 기록 수신됨 </td> 
   <td colname="col2"> <p>파일에서 생성되어 대상으로 보내려고 시도한 총 레코드 <span class="keyword"> Adobe</span>의 수입니다. 대부분의 경우 성공한 파일과 실패한 파일의 총 수입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
