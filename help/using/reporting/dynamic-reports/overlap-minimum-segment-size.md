---
description: 중복 보고서 업데이트 프로세스에 필요한 세그먼트 크기 및 작성 시간 요구 사항을 설명합니다.
seo-description: 중복 보고서 업데이트 프로세스에 필요한 세그먼트 크기 및 작성 시간 요구 사항을 설명합니다.
seo-title: 중복 보고서 업데이트 일정 및 최소 세그먼트 크기
solution: Audience Manager
title: 중복 보고서 업데이트 일정 및 최소 세그먼트 크기
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 중복 보고서:업데이트 일정 및 최소 세그먼트 크기{#overlap-reports-update-schedule-and-minimum-segment-size}

중복 보고서 업데이트 프로세스에 필요한 세그먼트 크기 및 작성 시간 요구 사항을 설명합니다.

## 업데이트 일정 및 요구 사항 {#update-schedule}

[!UICONTROL Overlap] 보고서는 일요일에 매주 업데이트됩니다. 보고서 사전 처리는 토요일에 시작됩니다. 이는 월요일에 중복 보고서에 새 세그먼트나 기존 세그먼트가 표시되는 방식에 영향을 줍니다. 중복 보고서에 포함하려면 다음을 수행합니다.

* 세그먼트는 지난 14일 동안 최소 70,000명의 실시간 사용자를 포함해야 합니다. 트레이트 및 세그먼트에 [대한 최소 고유 방문자 요구 사항을 참조하십시오](../../reporting/report-sampling.md#data-sampling-ratio).
* 세그먼트는 오전 12시(목요일 UTC) 이전에 만들어야 합니다(주별 오버랩 보고서 업데이트 프로세스가 시작되기 2일 전).
* 회사는 전체 [!DNL Audience Manager] 고객이어야 합니다. 자세한 내용은 컨설턴트나 고객 지원 센터에 [!DNL Audience Manager] 문의하십시오.

## 세그먼트 크기 및/또는 생성 시간이 보고에 영향을 줍니다. {#segment-size}

보고서 중 하나에 세그먼트가 표시되지 않는 경우 세그먼트가 이러한 최소 요구 사항을 충족하지 않기 때문일 수 있습니다. [!UICONTROL Overlap]

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 크기가 너무 작음</b> </p> </td> 
   <td colname="col2"> <p>오전 12시(목요일 UTC) 이전에 세그먼트를 만들었지만 총 70,000명 미만의 실시간 사용자가 포함되어 있다고 가정합니다. 이 세그먼트는 사용자 임계값 요구 사항을 충족하기 전까지 <span class="wintitle"> 중복</span> 보고서에 나타나지 않습니다. 또한 세그먼트는 목요일 마감 기간에 대해 필요한 사용자 수를 충족해야 합니다. 주간 마감 시간이 맞지 않으면, 이 세그먼트는 다가오는 일요일 <span class="wintitle"> 데이터</span> 실행 후 주 동안 겹치기 보고서에 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트가 너무 늦게 생성됨</b> </p> </td> 
   <td colname="col2"> <p>금요일에 세그먼트를 만들면 총 70,000명 이상의 실시간 사용자가 포함되어 있습니다. 이 세그먼트는 보고서 업데이트 <span class="wintitle"> 기간</span> 2일 전에 만들어졌기 때문에 다음 주 동안 중복 보고서에 나타나지 않습니다. 하지만 다음 주별 업데이트 후에 세그먼트가 겹치기 <span class="wintitle"> 보고서에</span> 표시됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [특성-특성 중복 보고서](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [세그먼트-특성 중복 보고서](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [세그먼트-세그먼트 중복 보고서](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

