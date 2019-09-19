---
description: 온보딩 상태 보고서는 인바운드 데이터 소스 파일의 레코드 처리에 대한 성공 및 실패율을 확인합니다. 이 보고서는 데이터를 대화형 막대 차트에 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. 이 보고서는 Analytics > 온보딩 상태 보고서에서 찾을 수 있습니다. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.
seo-description: 온보딩 상태 보고서는 인바운드 데이터 소스 파일의 레코드 처리에 대한 성공 및 실패율을 확인합니다. 이 보고서는 데이터를 대화형 막대 차트에 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. 이 보고서는 Analytics > 온보딩 상태 보고서에서 찾을 수 있습니다. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.
seo-title: 온보딩 상태 보고서 정보
solution: Audience Manager
title: 온보딩 상태 보고서 정보
uuid: 6ca8a90a-436b-4fce-adf1-48f3b96b3ed2
translation-type: tm+mt
source-git-commit: dd5c3d28097251c58e1fb095aaf4076883d1c1a1

---


# 온보딩 상태 보고서{#onboarding-status-report-about}

온보딩 상태 보고서는 인바운드 데이터 소스 파일의 레코드 처리에 대한 성공 및 실패율을 확인합니다. 이 보고서는 데이터를 대화형 막대 차트에 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. 이 보고서는 Analytics &gt; 온보딩 상태 보고서에서 찾을 수 있습니다. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.

>[!NOTE]
>
>관리자 권한이 있는 사용자만 Audience Manager 사용자 인터페이스에서 이 보고서를 볼 수 있습니다. 보고서에 해당 이메일을 추가하면 관리자가 아닌 사용자에게 업로드된 인바운드 파일의 상태에 대한 알림을 받을 수 있습니다. 이메일 [알림 받기를 참조하십시오](/help/using/reporting/onboarding-status-report.md#receive-email-notifications).

## 온보딩 상태 보고서:정보 {#onboarding-status-about}

The [!UICONTROL Onboarding Status Report] checks success and failure rates for processing records in your inbound data source files. 이 보고서는 데이터를 대화형 막대 차트에 표시하고 요약 지표를 표 형식으로 제공합니다. 또한 고정된 시간 간격 동안 파일을 샘플링하고 각 오류 유형에 대한 가장 일반적인 오류를 표시하는 옵션이 포함되어 있습니다. 이 보고서는 에서 찾을 수 **[!UICONTROL Analytics > Onboarding Status Report]**&#x200B;있습니다. 이 보고서는 인바운드 데이터 소스를 만들 때도 사용할 수 있습니다.

## 오류 보고 및 오류 샘플링 {#error-reporting-sampling}

오류 보고 및 오류 샘플링은 보고서의 두 가지 개별 기능입니다. [!UICONTROL Onboarding Status]

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
   <td colname="col2"> <p>오류 보고는 인바운드 데이터 소스에서 처리된 레코드 수의 성공 및 실패율을 보여줍니다. 그래프 아래의 표에서 요약 지표로 대화식 누적 막대 그래프의 데이터를 반환합니다. </p> <p>오류 보고는 자동으로 수행됩니다. 모든 인바운드 데이터 소스에 대해 지속적으로 실행됩니다. 달력 위젯으로 설정한 사전 설정 시간 간격 또는 사용자 정의된 시간 간격을 기반으로 데이터를 반환합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>오류 샘플링</b> </p> </td>
   <td colname="col2"> <p>오류 샘플링은 데이터 파일의 내용을 구문 분석하여 각 오류 유형에 대해 가장 일반적인 10개의 오류를 반환합니다. 인바운드 데이터 파일의 오류로 인해 개별 레코드가 처리되지 않습니다. 이 보고서를 문제 해결 도구로 사용하여 파일 오류 수를 줄이고 처리 속도를 향상시킵니다. </p> <p>오류 샘플링을 수동으로 활성화해야 합니다. 활성화일로부터 14일 동안 실행되고 자동으로 꺼집니다. 14일 간격이 만료된 후 오류 샘플링을 다시 활성화할 수 있습니다. 인바운드 데이터 소스를 <a href="../features/manage-datasources.md#create-data-source"> 만들 때 또는 기존 인바운드 데이터 소스의 데이터 소스 설정</a> 섹션에서 <b><span class="uicontrol"> 오류</span></b> 샘플링 <span class="wintitle"> 확인란을 선택하여</span> 오류 샘플링을 활성화합니다. </p> <p>오류 샘플링은 계산상 까다로운 프로세스입니다. 따라서 각 오류 범주에 대해 처음 10개의 오류만 반환합니다. 인바운드 데이터 소스에 포함된 모든 오류를 반환하도록 설계된 것은 아닙니다. 이러한 오류는 잠재적으로 더 큰 유사 오류 그룹의 대표적인 예입니다. 이 보고서에 표시되는 오류 유형에 대해 전체 파일을 검토하고 파일의 형식을 다시 지정한 다음 다시 전송합니다. </p> <p>인바운드 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 데이터 파일 컨텐츠를 참조하십시오.구문, 변수 및</a> 예제를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 오류 보고서 막대 차트 {#error-report-bar-chart}

오류 보고서는 다음 예와 같이 스택형 막대 그래프의 레코드 처리에 대한 성공 및 실패율을 그래프로 표시합니다. 그래프는 대화형입니다. 막대를 클릭하면 해당 날의 요약 지표가 그래프 아래의 표에 표시됩니다.

![](assets/stacked-graph.png)

## 오류 보고서 테이블 {#error-report-tables}

오류 보고서는 막대 그래프 아래에 표 형식의 데이터를 표시합니다. 이 표에서는 합계 및 백분율과 함께 성공 및 실패율을 보여줍니다.

**성공 및 실패 레코드**

이 기본 보기는 보고서의 총 레코드 수의 빈도 수를 보여주며 오류 유형별로 오류 분류를 포함합니다.

![](assets/success-failure.png)

**합계 및 백분율**

성공적으로 처리된 파일의 비율을 **[!UICONTROL Totals & Percentages]** 확인하려면 클릭하십시오.

![](assets/totals-percentages.png)

## 14일 동안 오류 샘플링 보고서 {#error-reporting-14-days}

오류 샘플링이 활성화되면 보고서에는 각 오류 유형에 대한 상위 10개의 오류가 표시됩니다. 보고서 상단에 있는 오류 유형 단추를 클릭하여 샘플링된 각 데이터 세트를 봅니다.

>[!NOTE]
>
>이 보고서는 현재 릴리스의 레코드 오류를 강조 표시하지 않습니다. 파일 오류를 찾아 수정하려면 결과를 검토하고 인바운드 데이터 파일 컨텐츠 [문서의 사양과 비교해야 합니다](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) .

![](assets/error-samples.png)

## 이메일 알림 받기 {#receive-email-notifications}

업로드된 인바운드 파일의 상태에 대해 알림을 받을 수신자의 전자 메일 주소를 추가할 수 있습니다. 다른 데이터 소스에 대해 다른 수신자를 선택할 수 있습니다.

![](assets/mail-notifications.png)

## 온보딩 상태 보고서 만들기 {#create-onboard-status-report}

A [!UICONTROL Sample Error Report] 는 성공적으로 처리된 데이터 소스의 레코드 수와 실패한 수를 반환합니다. 다음 단계에 따라 를 생성합니다 [!UICONTROL Sample Error Report].

<!-- 

create-onboarding-status-report.xml

 -->


1. 로 **[!UICONTROL Analytics > Onboarding Status Report]**&#x200B;이동합니다. 데이터 소스를 검색하거나 목록에서 하나를 선택합니다.

2. 날짜 범위를 선택합니다. 옵션은 다음과 같습니다.

   * 고정된 보고서 간격 집합.
   * 사용자 지정 날짜 범위를 만들 수 있는 달력 위젯입니다.

3. 클릭 **[!UICONTROL OK]**.

## 온보딩 상태 보고서 용어 및 정의 {#report-terms-conditions}

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
   <td colname="col2"> <p>Audience Manager <span class="keyword"> 가</span> 선택한 인바운드 데이터 소스에서 수신 및 처리한 파일을 나열합니다. </p> <p>파일 이름의 형식이 잘못되면 파일 처리가 실패합니다. 파일 이름 요구 사항은 이 데이터를 Audience Manager로 보내는 방법에 따라 <span class="keyword"> 다릅니다</span>. 배달 방법에는 <span class="keyword"> Amazon S3</span> 및 FTP가 포함됩니다. 파일 이름을 지정하는 방법에 대한 지침은 다음을 참조하십시오. </p> <p> 
     <ul id="ul_9A32906A14CA41C5AED0E13930DB31BA"> 
      <li id="li_A5A0E6ED711D4002B52092619F87C7D6"> <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md"> 인바운드 데이터 파일에 대한 Amazon S3 이름 요구 사항 </a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>형식 오류</b> </p> </td> 
   <td colname="col2"> <p>구문 또는 서식 요구 사항과 일치하지 않아 처리가 실패한 레코드 수를 나열합니다. 인바운드 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 데이터 파일 컨텐츠를 참조하십시오.구문, 변수 및</a> 예제를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>잘못된 AAM ID</b> </p> </td> 
   <td colname="col2"> <p>형식이 잘못된 Audience Manager 사용자 ID <span class="keyword"> (UUID</span> )의 수를 나열합니다. 일반적으로 이것은 ID를 나타냅니다. </p> 
    <ul id="ul_8304250E8F0F44918A50CF9D8D8D1F83"> 
     <li id="li_B100B4C2623B4E099E022869A4978357">예상 38자리 형식과 일치하지 않습니다. </li> 
     <li id="li_44E8A9AD13174A20A5742E56ED786634">알파벳 문자를 포함합니다. ID는 숫자여야 합니다. </li> 
    </ul> </td> 
  </tr>

<tr> 
   <td colname="col1"> <p> <b>잘못된 장치 ID</b> </p> </td> 
   <td colname="col2"> <p>부적절하게 형식이 지정된 글로벌 장치 ID의 수를 나열합니다. 장치 <a href="../reference/ids-in-aam.md">ID의</a> 형식 지정 방법과 장치 유형을 기반으로 사용해야 하는 글로벌 데이터 소스에 대한 자세한 내용은 Audience Manager의 <a href="../features/global-data-sources.md"></a> ID 색인과 전역 데이터 소스를 참조하십시오.</p>
  <p>보고서의 오류 샘플링 섹션에는 다음과 같은 잘못된 장치 ID에 대한 자세한 정보가 포함되어 있습니다.</p>
   <ul>
    <li>잘못된 장치 ID에 해당하는 데이터 소스 ID;</li>
    <li>잘못된 장치 ID;</li>
    <li>데이터 소스를 기반으로 예상 장치 ID의 유형입니다.</li>
   </ul>
  </tr>



<tr> 
   <td colname="col1"> <p> <b>일치하는 AAM ID 없음</b> </p> </td> 
   <td colname="col2"> <p>온보드 ID입니다. <span class="keyword"> Audience</span> Manager가 기존 ID와 일치하지 않습니다. Audience Manager에서 ID <span class="keyword"> 동기화를</span> 아직 수행하지 않았거나 동기화 후에도 ID와 일치하지 않는 경우 온보드 ID가 이 상태를 가질 수 있습니다. </p> <p>일치하지 않는 모바일 ID의 경우 Audience Manager <span class="keyword"> 는</span> 다음을 수행합니다. </p> 
    <ul id="ul_B0D6AF9EB27D4017B35E36824B403879"> 
     <li id="li_D141000A50D3463182CBA4571DCC5373">이 ID를 계속 저장하고 동기화하십시오. </li> 
     <li id="li_2EFCEE716F254ABCBC5FBF749B7564E6">ID를 동기화할 수 <span class="wintitle"> 없는</span> 경우 보고서에 저장된 레코드로 기록합니다. </li> 
    </ul> <p>온보드 파일에 모바일 ID 파섹 이 변수는 이후 파일의 성공 및 일치율에 영향을 주지 않습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>실현된 트레이트 없음</b> </p> </td> 
   <td colname="col2"> <p>Audience Manager <span class="keyword"> 가</span> 온보드 트레이트와 일치하지 않는 트레이트를 나열합니다. 이것은 다음의 결과일 수 있습니다. </p> 
    <ul id="ul_43619035AB6641B6949302FB50BDB5B1"> 
     <li id="li_D4C6306BF2B143198108702B309CE8CF">인바운드 데이터 파일에서 트레이트 형식이 잘못되었습니다. 데이터 파일의 형식을 지정하는 방법에 대한 자세한 내용은 인바운드 데이터 <a href="../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md"> 파일 내용을 참조하십시오.구문, 변수 및 예를 참조하십시오</a>. </li> 
     <li id="li_A1C708A007D24EE09B7C629AFC6E43C3">Audience Manager에서 아직 정의되지 않은 트레이트입니다 <span class="keyword"></span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>성공 비율</b> </p> </td> 
   <td colname="col2"> <p>파일에 성공적으로 저장된 레코드의 비율입니다. 성공 비율 = 처리된 레코드 / 파일의 레코드 수 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>받은 레코드</b> </p> </td> 
   <td colname="col2"> <p>받은 총 레코드 수입니다. 대부분의 경우 이 수는 인바운드 데이터 파일의 전체 레코드(라인) 수와 일치해야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>저장된 레코드</b> </p> </td> 
   <td colname="col2"> <p>저장된 레코드 수입니다. 파일 형식 오류로 인해 수신된 레코드 중 일부가 Audience Manager에 의해 저장되지 않을 수 <span class="keyword"> 있습니다</span>. 저장된 레코드 수는 받은 레코드 수보다 작을 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>총 실현 트레이트</b> </p> </td> 
   <td colname="col2"> <p>Audience Manager 플랫폼에 저장되는 모든 인바운드 파일의 모든 사용자에 대한 트레이트 <span class="keyword"> 수입니다</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>총 미사용 신호</b> </p> </td> 
   <td colname="col2"> <p>보고서에서 수신된 사용되지 않은 신호의 총 수입니다. 이 합계는 성공적으로 저장된 레코드의 총 수를 기반으로 합니다. </p> <p>자세한 <a href="../reporting/dynamic-reports/unused-signals.md"> 내용은</a> 미사용 신호 보고서를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>
