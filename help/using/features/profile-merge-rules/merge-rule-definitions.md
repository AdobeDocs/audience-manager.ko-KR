---
description: 병합 규칙 옵션을 사용하면 세그먼테이션에 사용하는 데이터 Audience Manager 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager과 통합된 타사 장치 그래프 제공자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 4개의 프로필 병합 규칙을 만들 수 있습니다.
seo-description: 병합 규칙 옵션을 사용하면 세그먼테이션에 사용하는 데이터 Audience Manager 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager과 통합된 타사 장치 그래프 제공자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 4개의 프로필 병합 규칙을 만들 수 있습니다.
seo-title: 정의된 프로필 병합 규칙 옵션
solution: Audience Manager
title: 정의된 프로필 병합 규칙 옵션
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: 프로필 병합
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 6%

---

# [!UICONTROL Profile Merge Rules] 정의된 옵션  {#profile-merge-rule-options-defined}

[!UICONTROL profile merge rule] 옵션을 사용하면 세그먼테이션에 사용하는 [!DNL Audience Manager] 데이터의 유형을 제어할 수 있습니다. [!UICONTROL profile merge rule]에는 [!UICONTROL Profile Link] 장치 그래프, [!UICONTROL Adobe Experience Cloud Device Co-op] 및/또는 [!DNL Audience Manager]과 통합된 타사 장치 그래프 공급자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 4개의 [!UICONTROL Profile Merge Rules]을 만들 수 있습니다. 네 번째 [!UICONTROL Profile Merge Rule]은 [!UICONTROL People-Based Destinations] 추가 기능을 구입한 고객에게만 제공됩니다.

[!UICONTROL Profile Merge Rule]을(를) 만들려면 아래 설명된 선택 사항에서 [!UICONTROL Profile Merge Rule Setup]을(를) 선택합니다.

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 옵션 개요 {#overview}

[!UICONTROL Profile Merge Rules] 각각 특정 사용 사례에 맞게 조정된 많은 규칙 조합을 사용할 수 있습니다. 각 규칙 조합을 사용할 시기에 대한 자세한 내용은 아래 표를 참조하십시오.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 가용성 | 평가 유형 | [!UICONTROL Audience Lab] 지원 | 사용 사례 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 모든 고객 | 실시간 및 배치 | 예 | [장치 타깃팅](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (포함  [!UICONTROL Co-op Device Graph]) | 모든 고객 | 실시간 및 배치 | 아니요 | [확장된 장치 타깃팅](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 모든 고객 | 실시간 전용 | 아니요 | [공유 장치 타깃팅](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 모든 고객 | 실시간 및 배치 | 예 | [온라인/오프라인 타깃팅](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 모든 고객 | 실시간 및 배치 | 예 | [교차 장치 타깃팅](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (포함  [!UICONTROL Co-op Device Graph]) | 모든 고객 | 실시간 및 배치 | 아니요 | [고급 교차 장치 타깃팅](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 해당 없음 | [사용자 기반 대상](../destinations/people-based-destinations-overview.md) 고객에게만 제공 | 배치만 | 아니요 | [사용자 기반 대상 타겟팅](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 평가  {#segment-evaluation}

[!UICONTROL Profile Merge Rules] 구성에 따라 [!DNL Audience Manager] 은 실시간으로, 일괄적으로 또는 두 가지 모두에서 [!UICONTROL segment] 평가를 수행할 수 있습니다.

* 실시간 [!UICONTROL segment] 평가를 수행하려면 [!UICONTROL segment] 자격이 부여되도록 방문자가 실시간으로 디지털 속성에 액세스하는 것을 보려면 [!DNL DCS] 가 필요합니다.
* 배치 [!UICONTROL segment] 평가가 이전에 자격이 있는 [!UICONTROL traits]에 대해 수행됩니다.
* [!UICONTROL Profile Merge Rules] 실시간 및 배치 평가 [!UICONTROL segment] 를 모두 지원하는 에서는 실시간 방문자 활동을 이전에 자격을 갖춘 활동과 결합할 수  [!UICONTROL traits]있습니다.

## [!UICONTROL Profile Merge Rules] 보고 지연  {#reporting-latency}

실시간 [!UICONTROL segment] 평가는 [!UICONTROL Profile Merge Rules] 보고서에 즉시 반영됩니다.

일괄 처리 [!UICONTROL segment] 평가는 [프로필 병합 규칙 보고서](profile-link-metrics.md)에 반영하는 데 최대 24시간이 걸릴 수 있습니다.

## [!UICONTROL Cross-Device Options] {#auth-options}

[!UICONTROL Cross-Device Options] 을(를) 사용하면 인증된 사용자와 인증되지 않은 사용자를 선택하고 교차 장치 프로필을 활용하여 세그멘테이션을 수행할 수 있습니다. 이러한 옵션은 공유 장치의 특정 사용자를 식별하고 연결하는 데 도움이 됩니다. 익명 및 인증된 사용자에 대한 자세한 내용은 Audience Manager](../../reference/visitor-authentication-states.md)의 [방문자 인증 상태 를 참조하십시오.

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 교차 장치 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 교차 장치 프로필 없음</span></b> </p> </td> 
   <td colname="col2"> <p>인증된 사용자로부터 수집된 데이터를 사용하지 않도록 <span class="keyword"> Audience Manager</span>에 지시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 현재 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>방문자가 사이트에 로그인한 경우 <span class="keyword"> Audience Manager</span>에 데이터를 읽고 쓰도록 지시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 마지막으로 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>장치에 마지막으로 로그인한 사용자의 인증된 프로필에서 데이터를 읽도록 <span class="keyword"> Audience Manager</span>에 지시합니다. </p> <p>이 옵션을 선택하면 사용자가 익명 상태인 경우 <span class="keyword"> Audience Manager</span>이 인증된 프로필에 새 트레이트 데이터를 기록하지 않습니다. 인증되면 새 트레이트 데이터가 사용자의 인증된 프로필에 기록됩니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 모든 교차 장치 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>인증 상태에 관계없이 모든 교차 장치 프로필에서 데이터를 읽도록 Audience Manager에게 알려줍니다. 이 옵션은 사용자 기반 대상 추가 기능을 구입한 Audience Manager 고객에게만 제공됩니다.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options]에 [!UICONTROL cross-device data sources]이 나열됩니다. 이러한 옵션은 [!UICONTROL cross-device] [!UICONTROL data source]([교차 장치 데이터 소스 만들기](merge-rules-start.md#create-data-source) 참조)를 만들 때 제공한 이름을 사용합니다. 각 프로필 규칙에 사용할 최대 3개의 [!UICONTROL cross-device data sources]을 선택할 수 있습니다. [!UICONTROL Authenticated Profile Options] 은 **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]**&#x200B;를 선택하는 경우 사용할 수 있습니다.

## [!UICONTROL Device Options] {#device-options}

[!UICONTROL Device Options]을 사용하면 [!UICONTROL Profile Merge Rule]에 사용되는 *`device profile`* 유형을 선택할 수 있습니다. 장치 프로필은 익명 브라우징 활동에서 수집한 [!UICONTROL traits]에서 빌드됩니다. 최소한 [!UICONTROL profile merge rule]에는 [!UICONTROL authenticated option] 및 [!UICONTROL device option]가 포함됩니다.

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
   <td colname="col2"> <p>세그먼테이션을 위해 익명 프로필에 포함된 트레이트를 사용하지 않도록 <span class="keyword"> Audience Manager</span>에 지시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>세그먼테이션에 익명 장치 프로필을 사용하도록 <span class="keyword"> Audience Manager</span>에 지시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 프로필 링크 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에게 현재 장치와 사용자가 인증한 최대 100개의 다른 장치에서 프로필을 읽도록 지시합니다. 이 장치 그래프는 <span class="keyword"> Audience Manager</span>에 있는 고유한 자사 데이터를 기반으로 합니다. 디지털 속성에서 높은 수준의 인증을 받는 고객에게 이상적입니다. <span class="wintitle"> 프로필 링크</span> 장치 그래프가 실시간으로 업데이트됩니다. 이 옵션은 <b><span class="uicontrol"> 현재 인증된 프로필</span></b> 또는 <b><span class="uicontrol"> 마지막 인증된 프로필</span></b>을 선택하는 경우 사용할 수 있습니다. 이 옵션을 사용하는 경우 인증된 단일 프로필(<span class="keyword"> Audience Manager</span>은(는) 자동으로 다른 프로필을 그룹화하는 경우에만 선택할 수 있습니다. 또한, <a href="profile-link-use-case.md"> 프로필 링크 장치 그래프 사용 사례</a>도 참조하십시오. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span>에게 현재 장치에서 프로필을 읽고 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>에서 제공하는 링크를 사용하는 최대 100개의 다른 장치를 알려줍니다. </p> <p><span class="keyword"> Device Co-op</span>는 참여하는 고객이 장치 링크 정보를 공유하는 디지털 협업입니다. <span class="keyword"> Device Co-op</span>은 <span class="term"> 장치 그래프</span>에서 이 데이터를 처리합니다. 장치 그래프는 장치를 장치 클러스터로 함께 연결합니다. 이러한 링크는 <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> 확률적 및 결정론적 데이터</a>에서 빌드됩니다. 클러스터는 알 수 없는 사람이 사용하는 장치 그룹을 나타냅니다. <span class="keyword">Device Co-op</span>는 그 구성원들 간에 이러한 클러스터를 공유하며, 이를 통해 고객에게 가치 있고 일관된 크로스 디바이스 환경을 제공할 수 있습니다. </p> <p> <span class="wintitle"> Device Co-op</span>에 대한 자세한 내용은 다음을 참조하십시오. </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Device Co-op 개요</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> 멤버십 요구 사항</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> 장치 그래프:내부 프로세스 및 출력</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>타사 장치 그래프 옵션</b> (개인 및 가구) </p> </td>
   <td colname="col2"> <p>이러한 옵션을 사용하면 타사 공급업체에서 제공하는 장치 그래프 기술을 기반으로 병합 규칙을 작성할 수 있습니다. 타사 장치 그래프는 다음을 제공합니다. </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 확률론적 데이터 및/또는 결정론적 데이터. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">개인 또는 가구 수준의 데이터. </li> 
     </ul> </p> <p>이러한 옵션을 사용하려면 장치 그래프의 고객이어야 합니다. 이 고객은 이미 <span class="keyword"> Audience Manager</span>과 통합되었습니다. 자세한 내용을 살펴보거나 시작하려면 계정 관리자에게 문의하십시오. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

[!DNL Audience Manager] 외부에 정의된 병합 규칙을 기반으로 다른 [!DNL Experience Cloud] 솔루션에서 자동으로 생성된 대상 세그먼트는 [!UICONTROL External Merge Policy] 를 사용하는 것으로 표시됩니다. 예를 들어 [Audience Manager과 Adobe Experience Platform 간 대상 공유](../../integration/integration-aep/aam-aep-audience-sharing.md)를 참조하십시오.

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

