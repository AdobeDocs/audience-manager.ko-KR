---
description: 온보딩 상태 보고서는 인바운드 데이터 소스 파일에서 레코드 처리에 대한 성공 및 실패율을 확인합니다. 이 보고서는 대화형 막대 차트에 데이터를 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. Analytics > 온보딩 상태 보고서에서 이 보고서를 찾을 수 있습니다. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.
seo-description: 온보딩 상태 보고서는 인바운드 데이터 소스 파일에서 레코드 처리에 대한 성공 및 실패율을 확인합니다. 이 보고서는 대화형 막대 차트에 데이터를 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. Analytics > 온보딩 상태 보고서에서 이 보고서를 찾을 수 있습니다. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.
seo-title: 온보딩 상태 보고서
solution: Audience Manager
title: 온보딩 상태 보고서
uuid: 6 ca 8 a 90 a -436 b -4 fce-adf 1-48 f 3 b 96 b 3 ed 2
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# Onboarding Status Report{#onboarding-status-report-about}

온보딩 상태 보고서는 인바운드 데이터 소스 파일에서 레코드 처리에 대한 성공 및 실패율을 확인합니다. 이 보고서는 대화형 막대 차트에 데이터를 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. Analytics &gt; 온보딩 상태 보고서에서 이 보고서를 찾을 수 있습니다. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.

>[!NOTE]
>
>관리자 권한이 있는 사용자만 Audience Manager 사용자 인터페이스에서 이 보고서를 볼 수 있습니다. 관리자가 아닌 사용자에게 보고서에 이메일을 추가하여 업로드된 인바운드 파일의 상태를 알릴 수 있습니다. See [Receive E-mail Notifications](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## Onboarding Status Report: About {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. 이 보고서는 대화형 막대 차트에 데이터를 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. You can find this report in **[!UICONTROL Analytics > Onboarding Status Report]**. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.

## Error Reporting and Error Sampling {#error-reporting-sampling}

Error reporting and error sampling are 2 separate features of the [!UICONTROL Onboarding Status] report.

<table id="table_4706D891D4C545E8BF9D8A0CC052CC48"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 기능 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>오류 보고</b> </p> </td>
   <td colname="col2"> <p>오류 보고는 인바운드 데이터 소스에서 처리된 레코드 수에 대한 성공 및 실패율을 보여줍니다. 대화형 누적 막대 그래프와 그래프 아래 표에서 요약 지표로 데이터를 반환합니다. </p> <p>오류 보고는 자동으로 수행됩니다. 모든 인바운드 데이터 소스에 대해 지속적으로 실행됩니다. 사전 설정된 시간 간격 범위 또는 달력 위젯으로 설정한 사용자 지정된 시간 간격에 따라 데이터를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오류 샘플링</b> </p> </td>
   <td colname="col2"> <p>오류 샘플링은 데이터 파일의 컨텐츠를 구문 분석하여 각 오류 유형에 대해 10 개의 가장 일반적인 오류를 반환합니다. 인바운드 데이터 파일의 오류로 인해 개별 레코드가 처리되지 않습니다. 이 보고서를 문제 해결 도구로 사용하여 파일 오류를 줄이고 처리 속도를 향상시킵니다. </p> <p>수동으로 오류 샘플링을 활성화해야 합니다. 활성화 날짜로부터 14 일 동안 실행되고 그 이후에 종료됩니다. 14 일 간격이 만료된 후 다시 오류 샘플링을 켤 수 있습니다. You activate error sampling when you <a href="../features/manage-datasources.md#create-data-source"> create an inbound data source</a> or by checking the <b><span class="uicontrol"> Error Sampling</span></b> check box from the <span class="wintitle"> Data Source Settings</span> section of an existing inbound data source. </p> <p>오류 샘플링은 계산이 필요한 프로세스입니다. 따라서 각 오류 카테고리에 대해 처음 10 개의 오류만 반환됩니다. 인바운드 데이터 소스에 포함된 모든 오류를 반환하도록 설계되지 않습니다. 이러한 오류는 잠재적으로 더 큰 유사 오류 그룹의 대표 샘플입니다. 이 보고서 플래그를 오류 유형으로 전체 파일을 검토하고 파일의 서식을 다시 지정한 다음 다시 전송합니다. </p> <p><a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 인바운드 데이터 파일 컨텐츠 참조: 구문, 변수 및 예제를</a> 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Error Report Bar Chart {#error-report-bar-chart}

오류 보고서는 다음 예와 같이 누적 막대 그래프에서 기록 처리를 위한 성공률과 실패율을 그래프로 보여줍니다. 그래프는 대화형입니다. 막대를 클릭하면 그래프 아래 표에 해당 날짜에 대한 요약 지표가 표시됩니다.

![](assets/stacked-graph.png)

## Error Report Tables {#error-report-tables}

오류 보고서는 표 그래프 아래에 표 형식의 데이터를 표시합니다. 이 표는 합계 및 비율과 함께 성공률과 실패율을 보여줍니다.

**성공 및 실패한 레코드**

이 기본 보기는 보고서에서 총 레코드 수의 빈도를 보여주며 오류 유형별로 오류 분류를 포함합니다.

![](assets/success-failure.png)

**총계 및 백분율**

Click **[!UICONTROL Totals & Percentages]** to see what % of your files were processed successfully.

![](assets/totals-percentages.png)

## Error Sampling Report for 14 Days {#error-reporting-14-days}

오류 샘플링이 활성화되면 보고서는 각 오류 유형에 대한 상위 10 개의 오류를 표시합니다. 보고서 맨 위에 있는 오류 유형 단추를 클릭하여 샘플링된 각 데이터 세트를 확인합니다.

>[!NOTE]
>
>이 현재 릴리스에서는 보고서가 기록되지 않습니다. To find and fix file errors, you should review the results and compare those to the specifications in the [Inbound Data File Contents](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) documentation.

![](assets/error-samples.png)

## Receive E-mail Notifications {#receive-email-notifications}

업로드된 인바운드 파일의 상태를 알릴 수신자의 이메일 주소를 추가할 수 있습니다. 데이터 소스에 대해 다른 수신자를 선택할 수 있습니다.

![](assets/mail-notifications.png)

## Create an Onboarding Status Report {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] returns the number records in a data source were processed successfully and how many failed. Follow these steps to generate a [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. **[!UICONTROL Analytics > Onboarding Status Report]** 이동. 데이터 소스를 검색하거나 목록에서 하나를 선택합니다.

2. 날짜 범위를 선택합니다. 옵션은 다음과 같습니다.

   * 고정된 보고서 간격 세트입니다.
   * 사용자 지정 날짜 범위를 만들 수 있는 달력 위젯입니다.

3. 클릭 **[!UICONTROL OK]**.

## Onboarding Status Report Terms and Definitions {#report-terms-conditions}

이 보고서에 사용된 레이블 및 용어에 대한 참조 가이드입니다.

<table id="table_1D44A2E6B4C847848B818190DD336841"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 용어 </th> 
   <th colname="col2" class="entry"> 정의 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>데이터 동기화 파일 이름</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 가 선택한 인바운드 데이터 소스에서 받아서 처리한 파일을 나열합니다. </p> <p>파일 이름의 형식이 잘못 지정되면 파일 처리가 실패합니다. File name requirements vary depending on how you send this data to <span class="keyword"> Audience Manager</span>. Delivery methods include <span class="keyword"> Amazon S3</span> and FTP. 파일 이름을 지정하는 방법에 대한 지침은 다음을 참조하십시오. </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>형식 오류</b> </p> </td> 
   <td colname="col2"> <p>구문 또는 형식 요구 사항과 일치하지 않아 처리가 실패한 레코드 수를 나열합니다. <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 인바운드 데이터 파일 컨텐츠 참조: 구문, 변수 및 예제를</a> 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>잘못된 AAM ID</b> </p> </td> 
   <td colname="col2"> <p>Lists the number of improperly formatted <span class="keyword"> Audience Manager</span> user IDs (UUID). 일반적으로 ID를 나타냅니다. </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">예상 38 자리 형식이 일치하지 않았습니다. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">알파벳 문자를 포함합니다. ID는 숫자여야 합니다. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>잘못된 장치 ID</b> </p> </td> 
   <td colname="col2"> <p>부적절하게 형식이 지정된 전역 장치 ID 수를 나열합니다. See <a href="../reference/ids-in-aam.md">Index of IDs in Audience Manager</a> and <a href="../features/global-data-sources.md">Global Data Sources</a>  for details on how device IDs should be formatted and what global data sources you should use, based on the device type.</p>
  <p>이 보고서의 오류 샘플링 섹션에는 다음과 같이 잘못된 장치 ID에 대한 자세한 정보가 포함되어 있습니다.</p>
   <ul>
    <li>잘못된 장치 ID에 해당하는 데이터 소스 ID;</li>
    <li>잘못된 장치 ID;</li>
    <li>데이터 소스를 기반으로 하는 예상 장치 ID 유형입니다.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>일치하는 AAM ID 없음</b> </p> </td> 
   <td colname="col2"> <p>These are onboarded IDs <span class="keyword"> Audience Manager</span> cannot match to an existing ID. <span class="keyword"> Audience Manager에서</span> 아직 ID 동기화를 수행하지 않았거나 동기화가 끝난 후에도 ID와 일치할 수 없는 경우 온보드 ID가 이 상태를 가질 수 있습니다. </p> <p>In the case of unmatched mobile IDs, <span class="keyword"> Audience Manager</span> will: </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">계속해서 저장하고 이 ID를 동기화합니다. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">Record it as a <span class="wintitle"> Stored Record</span> in the report if the ID cannot be synched. </li> 
    </ul> <p>온보드 파일에 모바일 ID가 포함된 경우 이러한 숫자를 다른 지표보다 약간 더 가볍게 처리할 수 있습니다. 이후 파일에 대한 성공률과 일치율에 영향을 주지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>실현되는 특성 없음</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager에서 온보드 트레이트와 연결할</span> 수 없는 트레이트를 나열합니다. 이는 다음과 같은 결과일 수 있습니다. </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">인바운드 데이터 파일에서 트레이트가 잘못 포맷되었습니다. For on how to format your data file, see <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> Inbound Data File Contents: Syntax, Variables, and Examples</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Traits that have not yet been defined in <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>성공률</b> </p> </td> 
   <td colname="col2"> <p>파일에서 성공적으로 저장된 레코드 비율입니다. Percent success = Records processed/number of records in a file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>받은 레코드</b> </p> </td> 
   <td colname="col2"> <p>수신된 총 레코드 수입니다. 대부분의 경우 이 번호는 인바운드 데이터 파일의 총 레코드 수 (줄) 와 일치해야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>저장된 레코드</b> </p> </td> 
   <td colname="col2"> <p>성공적으로 저장된 레코드 수. Because of file format errors, some of the records received may not be stored by <span class="keyword"> Audience Manager</span>. 저장된 레코드 수는 수신된 레코드 수보다 적을 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>총 구현 특성</b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 플랫폼에 저장된 모든 인바운드 파일의 모든 사용자에 대한 트레이트 수입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>사용되지 않은 총 신호 수</b> </p> </td> 
   <td colname="col2"> <p>보고서에서 받은 총 사용되지 않은 신호 수입니다. 이 합계는 성공적으로 저장된 총 레코드 수를 기반으로 합니다. </p> <p>See <a href="../reporting/dynamic-reports/unused-signals.md"> Unused Signals Report</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>
