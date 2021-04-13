---
description: Audience Optimization 보고서의 크로스 채널 전환 옵션을 사용하면 오프라인 전환을 제공된 온라인 노출 횟수 또는 클릭 수에 적용할 수 있습니다.
seo-description: Audience Optimization 보고서의 크로스 채널 전환 옵션을 사용하면 오프라인 전환을 제공된 온라인 노출 횟수 또는 클릭 수에 적용할 수 있습니다.
seo-title: 크로스 채널 전환
solution: Audience Manager
title: 크로스 채널 전환
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: 대상 최적화 보고서
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 5%

---

# 크로스 채널 전환{#cross-channel-conversion}

Audience Optimization 보고서의 크로스 채널 전환 옵션을 사용하면 오프라인 전환을 제공된 온라인 노출 횟수 또는 클릭 수에 적용할 수 있습니다.

[!UICONTROL Cross Channel Conversion] 보고서는 [!DNL Google Campaign Manager] 플랫폼의 결과를 [!DNL Audience Manager] 전환 트레이트와 결합합니다. 이를 통해 오프라인 전환을 온라인 노출 또는 클릭에 연결할 수 있습니다.

[세그먼트 성능](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) 및 [최적 빈도](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) 보고서에 [!UICONTROL Cross Channel Conversion]을 사용할 수 있습니다.

[!UICONTROL Cross Channel Conversion] 보고서를 보려면 **[!UICONTROL Platform]** 드롭다운 목록에서 **[!UICONTROL AAM + Ad Server Name]** 항목을 선택합니다.

다음 표에는 [!UICONTROL Cross Channel Conversion]을(를) 설정할 때 고려해야 할 중요한 사항이 나와 있습니다.

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
   <td colname="col1"> <p><span class="wintitle"> 크로스 채널 전환</span> 보고서를 실행하려면 하나 이상의 전환 트레이트를 데이터 소스에 할당해야 합니다. 트레이트에 대한 자세한 내용은 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 트레이트</a>에 대한 기본 정보를 참조하십시오. </p> </td> 
  </tr>
  <tr> 
   <td> <p>속성 창 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google 캠페인 </span></b> 관리 창은 14일입니다. 즉, 지난 2주 동안 표시되었던 전환 특성만 고려합니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>마지막 접촉 방법론 </p> </td> 
   <td> <p>전환하기 전에 사용자가 마지막으로 본 크리에이티브는 전환을 받은 크리에이티브입니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>클릭 수 대 노출 수 </p> </td> 
   <td> <p>클릭이 정확히 같은 시간에 발생할 경우 속성을 결정할 때 노출보다 우선합니다. 예를 들어 여러 크리에이티브가 표시되는 페이지에서 클릭되는 크리에이티브가 전환을 받습니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>최근 데이터 </p> </td> 
   <td> <p>보고서는 항상 전날에 사용할 수 있는 데이터에 대해 계산됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
