---
description: 대상 최적화 보고서의 크로스 채널 전환 옵션을 사용하면 제공된 온라인 노출 또는 클릭에 오프라인 전환을 적용할 수 있습니다.
seo-description: 대상 최적화 보고서의 크로스 채널 전환 옵션을 사용하면 제공된 온라인 노출 또는 클릭에 오프라인 전환을 적용할 수 있습니다.
seo-title: 크로스 채널 전환
solution: Audience Manager
title: 크로스 채널 전환
uuid: 0fec23-e502-490b-b7dd-47a3753a3f75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 크로스 채널 전환{#cross-channel-conversion}

대상 최적화 보고서의 크로스 채널 전환 옵션을 사용하면 제공된 온라인 노출 또는 클릭에 오프라인 전환을 적용할 수 있습니다.

이 [!UICONTROL Cross Channel Conversion] 보고서는 [!DNL DoubleClick Campaign Manager] (DCM) 플랫폼의 결과와 [!DNL Audience Manager] 전환 트레이트를 결합합니다. 이를 통해 오프라인 전환을 온라인 노출 또는 클릭에 연결할 수 있습니다.

세그먼트 성능 및 [!UICONTROL Cross Channel Conversion] 최적 [빈도](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) 보고서에 사용할 [수](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) 있습니다.

보고서를 보려면 [!UICONTROL Cross Channel Conversion] 드롭다운 목록에서 **[!UICONTROL AAM+DCM]** **[!UICONTROL Platform]** 항목을 선택합니다.

다음 표에는 설정 시 고려해야 할 사항이 나와 [!UICONTROL Cross Channel Conversion]있습니다.

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
   <td colname="col1"> <p>크로스 채널 전환 보고서를 실행하려면 하나 이상의 전환 트레이트가 <span class="wintitle"> 데이터 소스에</span> 할당되어야 합니다. 트레이트에 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 대한 자세한 내용은</a> 트레이트에 대한 기본 정보를 참조하십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>최대 전환 트레이트 수 </p> </td> 
   <td colname="col1"> <p>보고서는 사용자로부터 <i>최대</i> 50개의 전환 트레이트를 가져옵니다. 최대값에 도달하면 보고서는 트레이트 ID를 기준으로 처음 50개의 전환 트레이트를 오름차순으로 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>속성 창 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+DCM</span></b> 속성 창은 14일입니다. 즉, 지난 2주 동안 표시된 전환 특성만 고려합니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>마지막 접촉 방법론 </p> </td> 
   <td> <p>사용자가 전환 전에 마지막으로 본 크리에이티브가 전환을 받은 크리에이티브입니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>클릭 수와 노출 수 </p> </td> 
   <td> <p>클릭이 정확하게 동시에 발생하는 경우 속성을 결정할 때 임프레션에 우선합니다. 예를 들어, 여러 크리에이티브가 표시되는 페이지에서 클릭되는 크리에이티브가 전환됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>최근 데이터 </p> </td> 
   <td> <p>보고서는 항상 이전 날에 사용할 수 있는 데이터에 대해 계산됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
