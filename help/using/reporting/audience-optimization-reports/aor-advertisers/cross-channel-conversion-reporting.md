---
description: 대상 최적화 보고서의 크로스 채널 전환 옵션을 사용하면 오프라인 전환을 온라인 노출 또는 클릭 수로 매핑할 수 있습니다.
seo-description: 대상 최적화 보고서의 크로스 채널 전환 옵션을 사용하면 오프라인 전환을 온라인 노출 또는 클릭 수로 매핑할 수 있습니다.
seo-title: 크로스 채널 전환
solution: Audience Manager
title: 크로스 채널 전환
uuid: 0 FECEC 23-E 502-490 B-B 7 DD -47 A 3753 A 3 F 75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 크로스 채널 전환{#cross-channel-conversion}

대상 최적화 보고서의 크로스 채널 전환 옵션을 사용하면 오프라인 전환을 온라인 노출 또는 클릭 수로 매핑할 수 있습니다.

[!UICONTROL Cross Channel Conversion] 보고서는 (DCM) 플랫폼의 결과를 [!DNL DoubleClick Campaign Manager][!DNL Audience Manager] 전환 트레이트와 결합합니다. 오프라인 전환을 온라인 노출 또는 클릭 수에 연결할 수 있습니다.

You can use the [!UICONTROL Cross Channel Conversion] for the [Segment Performance](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) and [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) reports.

[!UICONTROL Cross Channel Conversion] 보고서를 보려면 드롭다운 목록에서 **[!UICONTROL AAM+DCM]** 항목을 **[!UICONTROL Platform]** 선택합니다.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> 고려 사항 </th> 
   <th class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>최소 전환 트레이트 수 </p> </td> 
   <td colname="col1"> <p><span class="wintitle"> 크로스 채널 전환</span> 보고서를 실행하려면 하나 이상의 전환 트레이트를 데이터 소스에 할당해야 합니다. See <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basic Information for Traits</a> for more information on traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>최대 전환 트레이트 수 </p> </td> 
   <td colname="col1"> <p>The reports pull in a <i>maximum</i> of 50 conversion traits from the user. 최대값에 도달하는 경우, 보고서는 트레이트 ID를 기반으로 하는 처음 50 개의 전환 트레이트를 오름차순으로 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>기여도 분석 창 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM + DCM</span></b> 기여도 창은 14 일이며, 이것은 지난 2 주 동안 나타난 전환 트레이트만 고려됨을 의미합니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>마지막 접촉 방법론 </p> </td> 
   <td> <p>변환하기 전에 사용자가 마지막으로 본 크리에이티브가 전환을 받은 것입니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>클릭 수 및 노출 횟수 </p> </td> 
   <td> <p>기여도가 정확하게 동일한 시간에 발생하는 경우 기여도를 결정할 때 한 번의 클릭이 노출 횟수보다 우선합니다. 예를 들어 여러 크리에이티브가 표시되는 페이지에서 클릭되는 페이지에 전환이 부여됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>최근 데이터 </p> </td> 
   <td> <p>이전 날에 사용할 수 있는 데이터에 대해 항상 보고서가 계산됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
