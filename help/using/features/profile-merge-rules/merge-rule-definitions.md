---
description: 병합 규칙 옵션을 사용하면 Audience Manager에서 세그멘테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프 및/또는 Audience Manager과 통합된 기타 타사 장치 그래프 제공자에 의해 매핑된 장치 프로필이 포함될 수 있습니다. 최대 4개의 프로필 병합 규칙을 만들 수 있습니다.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: 정의된 프로필 병합 규칙 옵션
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules]개 옵션 정의됨 {#profile-merge-rule-options-defined}

[!UICONTROL profile merge rule] 옵션을 사용하면 [!DNL Audience Manager]이(가) 세분화에 사용하는 데이터 형식을 제어할 수 있습니다. [!UICONTROL profile merge rule]에는 [!UICONTROL Profile Link] 장치 그래프 및/또는 [!DNL Audience Manager]과(와) 통합된 다른 타사 장치 그래프 공급자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 4개의 [!UICONTROL Profile Merge Rules]을(를) 만들 수 있습니다. 네 번째 [!UICONTROL Profile Merge Rule]은(는) [!UICONTROL People-Based Destinations] 추가 기능을 구입한 고객에게만 제공됩니다.

[!UICONTROL Profile Merge Rule]에서 아래에 설명된 옵션을 선택하여 [!UICONTROL Profile Merge Rule Setup]을(를) 만듭니다.

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 옵션 개요 {#overview}

[!UICONTROL Profile Merge Rules]에서는 특정 사용 사례에 맞게 만들어진 다양한 규칙 조합을 사용할 수 있습니다. 각 규칙 조합을 사용할 시기에 대한 자세한 내용은 아래 표를 참조하십시오.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 가용성 | 평가 유형 | [!UICONTROL Audience Lab] 지원 | 사용 사례 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 모든 고객 | 실시간 및 일괄 처리 | 예 | [장치 타깃팅](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | 모든 고객 | 실시간 및 일괄 처리 | 아니오 | [확장된 장치 타깃팅](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 모든 고객 | 실시간 전용 | 아니오 | [공유된 장치 타깃팅](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 모든 고객 | 실시간 및 일괄 처리 | 예 | [온라인/오프라인 타깃팅](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 모든 고객 | 실시간 및 일괄 처리 | 예 | [장치 간 타깃팅](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | 모든 고객 | 실시간 및 일괄 처리 | 아니오 | [고급 교차 장치 타깃팅](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 해당 없음 | [사용자 기반 대상](../destinations/people-based-destinations-overview.md) 고객에게만 제공 | 일괄 처리만 | 아니오 | [사용자 기반 대상에 대한 타깃팅](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 평가 {#segment-evaluation}

[!UICONTROL Profile Merge Rules] 구성에 따라 [!DNL Audience Manager]은(는) 실시간으로, 일괄적으로 또는 둘 다로 [!UICONTROL segment] 평가를 수행할 수 있습니다.

* 실시간 [!UICONTROL segment] 평가를 수행하려면 [!DNL DCS]이(가) 방문자가 실시간으로 디지털 속성에 액세스하는 것을 보고 [!UICONTROL segment]에 대한 자격을 얻어야 합니다.
* 이전에 정규화된 [!UICONTROL segment]에 대해 일괄 처리 [!UICONTROL traits] 평가를 수행합니다.
* 실시간 및 일괄 처리 [!UICONTROL Profile Merge Rules] 평가를 모두 지원하는 [!UICONTROL segment]은(는) 실시간 방문자 활동을 이전에 자격이 부여된 [!UICONTROL traits]과(와) 결합합니다.

## [!UICONTROL Profile Merge Rules] 보고 대기 시간 {#reporting-latency}

실시간 [!UICONTROL segment] 평가는 [!UICONTROL Profile Merge Rules] 보고서에 즉시 반영됩니다.

[!UICONTROL segment] 일괄 처리 평가는 [프로필 병합 규칙 보고서](profile-link-metrics.md)에 반영하는 데 최대 24시간이 걸릴 수 있습니다.

## [!UICONTROL Cross-Device Options] {#auth-options}

[!UICONTROL Cross-Device Options]을(를) 사용하면 인증된 사용자와 인증되지 않은 사용자를 선택하고 세그멘테이션을 위해 장치 간 프로필을 활용할 수 있습니다. 이러한 옵션은 공유 장치에서 특정 사용자를 식별하고 연결하는 데 도움이 됩니다. 익명 사용자와 인증된 사용자에 대한 자세한 내용은 [Audience Manager의 방문자 인증 상태](../../reference/visitor-authentication-states.md)를 참조하십시오.

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cross-Device 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 교차 장치 프로필 없음</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에 인증된 사용자로부터 수집된 데이터를 사용하지 않도록 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 현재 인증된 프로필 <b><span class="uicontrol">개</span></b> </p> </td> 
   <td colname="col2"> <p>방문자가 사이트에 로그인한 경우 인증된 프로필에 데이터를 읽고 쓰도록 <span class="keyword"> Audience Manager</span>에 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol">개의 마지막 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>장치에 마지막으로 로그인한 사용자의 인증된 프로필에서 데이터를 읽도록 <span class="keyword"> Audience Manager</span>에 알립니다. </p> <p>선택하면 <span class="keyword"> Audience Manager</span>은(는) 사용자가 익명 상태인 경우 인증된 프로필에 새 특성 데이터를 쓰지 않습니다. 인증되면 새 트레이트 데이터가 사용자의 인증된 프로필에 기록됩니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 모든 교차 장치 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>인증 상태에 관계없이 모든 교차 장치 프로필에서 데이터를 읽도록 Audience Manager에 지시합니다. 이 옵션은 사람 기반 대상 추가 기능을 구입한 Audience Manager 고객에게만 제공됩니다.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options]에 [!UICONTROL cross-device data sources]이(가) 나열됩니다. Source 이러한 옵션은 [!UICONTROL cross-device] [!UICONTROL data source]을(를) 만들 때 제공한 이름을 사용합니다([크로스 디바이스 데이터 만들기](merge-rules-start.md#create-data-source) 참조). 각 프로필 규칙에 사용할 최대 3개의 [!UICONTROL cross-device data sources]을(를) 선택할 수 있습니다. [!UICONTROL Authenticated Profile Options]은(는) **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]**&#x200B;을(를) 선택할 때 사용할 수 있습니다.

## [!UICONTROL Device Options] {#device-options}

[!UICONTROL Device Options]을(를) 사용하면 *`device profile`*&#x200B;에서 사용하는 [!UICONTROL Profile Merge Rule]의 형식을 선택할 수 있습니다. 익명 탐색 활동에서 수집된 [!UICONTROL traits]에서 장치 프로필을 빌드합니다. 최소한 [!UICONTROL profile merge rule]은(는) [!UICONTROL authenticated option] 및 [!UICONTROL device option]을(를) 포함합니다.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 프로필 없음</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에게 세그멘테이션을 위해 익명 프로필에 포함된 특성을 사용하지 않도록 지시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 프로필</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에게 세그멘테이션에 익명 장치 프로필을 사용하도록 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 프로필 링크 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에게 현재 장치와 사용자가 인증한 다른 장치 최대 100개에서 프로필을 읽도록 지시합니다. 이 장치 그래프는 <span class="keyword"> Audience Manager</span>의 고유한 자사 데이터를 기반으로 만들어집니다. 디지털 속성 전반에 걸쳐 높은 수준의 인증을 보유한 고객에게 이상적입니다. <span class="wintitle"> 프로필 링크</span> 장치 그래프가 실시간으로 업데이트됩니다. 이 옵션은 <b><span class="uicontrol">개의 현재 인증된 프로필</span></b> 또는 <b><span class="uicontrol">개의 마지막 인증된 프로필</span></b>을 선택한 경우에 사용할 수 있습니다. 이 옵션을 사용하는 경우 인증된 프로필 하나만 선택할 수 있습니다(<span class="keyword"> Audience Manager</span>은(는) 다른 프로필은 자동으로 회색으로 표시됨). <a href="profile-link-use-case.md"> 프로필 링크 장치 그래프 사용 사례</a>도 참조하세요. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>타사 장치 그래프 옵션</b>(개인 및 세대) </p> </td>
   <td colname="col2"> <p>이러한 옵션을 사용하면 서드파티 공급업체에서 제공하는 장치 그래프 기술을 기반으로 병합 규칙을 작성할 수 있습니다. 타사 장치 그래프는 다음을 제공합니다. </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 확률론적 및/또는 결정론적 데이터. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">개인 또는 가구 수준의 데이터. </li> 
     </ul> </p> <p>이러한 옵션을 사용하려면 <span class="keyword"> Audience Manager</span>과(와) 이미 통합된 Device Graph의 고객이어야 합니다. 자세한 내용을 보거나 시작하려면 계정 관리자에게 문의하십시오. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

[!DNL Experience Cloud] 외부에서 정의된 병합 규칙을 기반으로 다른 [!DNL Audience Manager] 솔루션에서 자동으로 만들어진 대상 세그먼트는 [!UICONTROL External Merge Policy]을(를) 사용하는 것으로 표시됩니다. 예를 들어 [Audience Manager과 Adobe Experience Platform 간의 대상 공유](../../integration/integration-aep/aam-aep-audience-sharing.md)를 참조하십시오.

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)
