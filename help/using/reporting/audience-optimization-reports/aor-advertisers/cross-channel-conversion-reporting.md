---
description: Audience Optimization 보고서의 채널 간 전환 옵션을 사용하면 오프라인 전환을 제공된 온라인 노출 또는 클릭에 표시할 수 있습니다.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: 크로스 채널 전환
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 3%

---

# 크로스 채널 전환{#cross-channel-conversion}

Audience Optimization 보고서의 채널 간 전환 옵션을 사용하면 오프라인 전환을 제공된 온라인 노출 또는 클릭에 표시할 수 있습니다.

다음 [!UICONTROL Cross Channel Conversion] 보고서는 다음과 같은 결과를 결합합니다 [!DNL Google Campaign Manager] 플랫폼 포함 [!DNL Audience Manager] 전환 트레이트. 이렇게 하면 오프라인 전환을 온라인 노출 또는 클릭에 연결할 수 있습니다.

다음을 사용할 수 있습니다. [!UICONTROL Cross Channel Conversion] 대상: [세그먼트 성능](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) 및 [최적 빈도](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) 보고서.

을(를) 보려면 [!UICONTROL Cross Channel Conversion] 보고서, 다음을 선택 **[!UICONTROL AAM + Ad Server Name]** 의 항목 **[!UICONTROL Platform]** 드롭다운 목록입니다.

다음 표에는 설정 시 고려해야 할 중요한 사항이 나와 있습니다 [!UICONTROL Cross Channel Conversion]:

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
   <td colname="col1"> <p>을(를) 위해 하나 이상의 전환 트레이트가 데이터 소스에 할당되어야 합니다. <span class="wintitle"> 채널 간 전환</span> 실행할 보고서. 다음을 참조하십시오 <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> 트레이트에 대한 기본 정보</a> 트레이트에 대한 자세한 내용을 보려면 여기를 클릭하십시오. </p> </td> 
  </tr>
  <tr> 
   <td> <p>속성 창 </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+Google 캠페인 관리자</span></b> 속성 기간은 14일입니다. 즉, 지난 2주 동안 표시된 전환 트레이트만 고려됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>마지막 터치 방식 </p> </td> 
   <td> <p>사용자가 전환하기 전에 마지막으로 본 크리에이티브는 전환에 성공한 크리에이티브입니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>클릭수 대 노출수 </p> </td> 
   <td> <p>속성이 정확히 동시에 발생하는 경우 속성을 결정할 때 클릭이 노출보다 우선합니다. 예를 들어, 여러 개의 크리에이티브가 표시된 페이지에서 클릭되는 크리에이티브에 전환이 부여됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>최근 데이터 </p> </td> 
   <td> <p>보고서는 항상 전날 사용 가능한 데이터에 대해 계산됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>
