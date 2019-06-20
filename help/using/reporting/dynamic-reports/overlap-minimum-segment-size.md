---
description: 겹치는 보고서 업데이트 프로세스에 필요한 세그먼트 크기 및 작성 시간 요구 사항을 설명합니다.
seo-description: 겹치는 보고서 업데이트 프로세스에 필요한 세그먼트 크기 및 작성 시간 요구 사항을 설명합니다.
seo-title: 겹치는 보고서 업데이트 예약 및 최소 세그먼트 크기
solution: Audience Manager
title: 겹치는 보고서 업데이트 예약 및 최소 세그먼트 크기
uuid: 35 C 1 CB 39-E 28 D -4 D 20-88 C 9-5 FF 4 FE 154 E 9 E
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

겹치는 보고서 업데이트 프로세스에 필요한 세그먼트 크기 및 작성 시간 요구 사항을 설명합니다.

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] 보고서는 일요일에 매주 업데이트됩니다. 보고서 사전 처리는 토요일에 시작됩니다. 이것은 새 또는 기존 세그먼트가 월요일에 겹치는 보고서에 표시되는 방식에 영향을 줍니다. 겹침 보고서에 포함하려면:

* 세그먼트에 최근 14 일 동안 최소 70,000 명의 실시간 사용자가 포함되어야 합니다. Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* 세그먼트는 목요일 오전 12 시 이전에 만들어져야 합니다 (주간 겹치기 보고서 업데이트 프로세스가 시작되기 전 2 일 전).
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

[!UICONTROL Overlap] 보고서 중 하나에 세그먼트가 표시되지 않으면 세그먼트가 이러한 최소 요구 사항을 충족하지 않았기 때문일 수 있습니다.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트 크기가 너무 작습니다.</b> </p> </td> 
   <td colname="col2"> <p>목요일 오전 12 시 이전에 세그먼트를 만들었다고 가정해도 총 7만 명의 실시간 사용자가 포함됩니다. This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. 또한, 세그먼트는 목요일 종료 기간에 필요한 사용자 수를 충족해야 합니다. If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트가 너무 늦었습니다.</b> </p> </td> 
   <td colname="col2"> <p>금요일에 세그먼트를 만들면 총 70,000 명이 넘는 실시간 사용자가 포함됩니다. This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [특성-특성 중복 보고서](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [세그먼트-특성 중복 보고서](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [세그먼트-세그먼트 중복 보고서](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

