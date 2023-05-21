---
description: Overlap Report 업데이트 프로세스에 필요한 세그먼트 크기 및 생성 시간 요구 사항에 대해 설명합니다.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Overlap Reports 일정 및 최소 세그먼트 크기 업데이트
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Overlap Reports: 일정 및 최소 세그먼트 크기 업데이트{#overlap-reports-update-schedule-and-minimum-segment-size}

Overlap Report 업데이트 프로세스에 필요한 트레이트 및 세그먼트 크기와 생성 시간 요구 사항에 대해 설명합니다.

## 일정 및 요구 사항 업데이트 {#update-schedule}

[!UICONTROL Overlap] 보고서는 매주 일요일에 업데이트됩니다. 보고서 사전 처리가 토요일부터 시작됩니다. 이 기능은 월요일에 새 세그먼트 또는 기존 세그먼트가 중복 보고서에 표시되는 방식에 영향을 줍니다. 중복 보고서에 포함하려면 다음을 수행합니다.

* 세그먼트는 지난 14일 동안 최소 70,000명의 총 실시간 사용자를 포함해야 합니다.
* 트레이트에는 28,000개가 포함되어야 합니다. [고유 트레이트 실현](/help/using/features/traits/trait-and-segment-qualification-reference.md) 지난 14일 동안
* 세그먼트는 UTC 목요일 오전 12시(주별 겹치기 보고서 업데이트 프로세스가 시작되기 2일 전) 이전에 생성되어야 합니다.
* 회사가 전체여야 합니다. [!DNL Audience Manager] 고객. 다음으로 문의하십시오. [!DNL Audience Manager] 자세한 내용은 컨설턴트나 고객 지원 센터를 참조하십시오.

## 세그먼트 크기 및/또는 생성 시간이 보고에 영향을 줌 {#segment-size}

다음 중 하나에 세그먼트가 표시되지 않는 경우 [!UICONTROL Overlap] reports, 세그먼트가 이러한 최소 요구 사항을 충족하지 않기 때문일 수 있습니다.

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
   <td colname="col2"> <p>목요일 오전 12시(UTC) 이전에 세그먼트를 생성한다고 가정해 보겠습니다. 하지만 여기에는 총 70,000명 미만의 실시간 사용자가 포함됩니다. 이 세그먼트는 다음에 표시되지 않습니다. <span class="wintitle"> 중복 보고서</span> 사용자 임계값 요구 사항을 충족할 때까지. 또한 이 세그먼트는 목요일 마감 기간 또는 그 이전에 필요한 사용자 수를 충족해야 합니다. 주별 마감을 충족하지 못하면 세그먼트가에 표시됩니다. <span class="wintitle"> 겹치기 보고서</span> 다가오는 일요일 데이터 실행 다음 주 동안. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>세그먼트가 너무 늦게 생성됨</b> </p> </td> 
   <td colname="col2"> <p>금요일에 세그먼트를 만들고 총 70,000명 이상의 실시간 사용자를 포함한다고 가정해 보겠습니다. 이 세그먼트는 다음에 표시되지 않습니다. <span class="wintitle"> 겹치기 보고서</span> 보고서 업데이트 기간 2일 이전에 생성되었기 때문에 다음 주에 대해 생성할 수 있습니다. 하지만 세그먼트가에 표시됩니다. <span class="wintitle"> 중복 보고서</span> 다음 주 업데이트 이후. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [특성-특성 Overlap Reports](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [세그먼트-특성 Overlap Reports](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [세그먼트-세그먼트 Overlap Reports](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

