---
description: 병합 규칙 옵션을 사용하여 Audience Manager이 세그먼테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 Audience Manager 링크 장치 그래프 및/또는 Profile Link와 통합된 기타 타사 장치 그래프 제공자에 의해 매핑된 장치 프로필이 포함될 수 있습니다. 최대 4개의 프로필 병합 규칙을 만들 수 있습니다.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: 정의된 프로필 병합 규칙 옵션
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 2%

---

# [!UICONTROL Profile Merge Rules] 정의된 옵션 {#profile-merge-rule-options-defined}

다음 [!UICONTROL profile merge rule] 옵션을 사용하면 데이터 유형을 제어할 수 있습니다 [!DNL Audience Manager] 는 세그먼테이션에 을 사용합니다. A [!UICONTROL profile merge rule] 에 의해 매핑된 장치 프로필을 포함할 수 있습니다. [!UICONTROL Profile Link] 와 통합된 Device Graph 및/또는 기타 타사 Device Graph 공급자 [!DNL Audience Manager]. 최대 4개를 만들 수 있습니다. [!UICONTROL Profile Merge Rules]. 네 번째 [!UICONTROL Profile Merge Rule] 는 을(를) 구입한 고객에게만 제공됩니다. [!UICONTROL People-Based Destinations] 추가 기능.

다음을 빌드합니다. [!UICONTROL Profile Merge Rule] 아래에 설명된 옵션에서 선택하여 [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] 옵션 개요 {#overview}

[!UICONTROL Profile Merge Rules] 각각 특정 사용 사례에 초점을 맞춘 다양한 규칙 조합을 사용할 수 있습니다. 각 규칙 조합을 사용할 시기에 대한 자세한 내용은 아래 표를 참조하십시오.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | 가용성 | 평가 유형 | [!UICONTROL Audience Lab] 지원 | 사용 사례 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | 모든 고객 | 실시간 및 일괄 처리 | 예 | [장치 타기팅](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | 모든 고객 | 실시간 및 일괄 처리 | 아니요 | [확장된 장치 타깃팅](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | 모든 고객 | 실시간 전용 | 아니요 | [공유 장치 타깃팅](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | 모든 고객 | 실시간 및 일괄 처리 | 예 | [온라인/오프라인 타기팅](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | 모든 고객 | 실시간 및 일괄 처리 | 예 | [크로스 디바이스 타기팅](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | 모든 고객 | 실시간 및 일괄 처리 | 아니요 | [고급 크로스 디바이스 타기팅](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | 해당 없음 | 제외 대상 [사용자 기반 대상](../destinations/people-based-destinations-overview.md) 고객 | 일괄 처리만 | 아니요 | [사용자 기반 대상에 대한 타깃팅](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] 평가 {#segment-evaluation}

다음에 따라 [!UICONTROL Profile Merge Rules] 구성, [!DNL Audience Manager] 다음을 수행할 수 있습니다. [!UICONTROL segment] 실시간, 일괄 처리 또는 두 가지 모두로 평가합니다.

* 실시간 [!UICONTROL segment] 평가를 수행하려면 [!DNL DCS] 방문자가 실시간으로 디지털 속성에 액세스하여 다음을 수행할 수 있는 권한을 얻습니다. [!UICONTROL segment].
* 일괄 처리 [!UICONTROL segment] 평가는 이전에 자격을 부여한 사람에 대해 수행됩니다. [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] 실시간 및 일괄 처리 모두 지원 [!UICONTROL segment] 평가는 실시간 방문자 활동과 이전에 자격을 갖춘 활동을 결합합니다 [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] 보고 지연 {#reporting-latency}

실시간 [!UICONTROL segment] 평가는 다음에 즉시 반영됩니다. [!UICONTROL Profile Merge Rules] 보고서.

일괄 처리 [!UICONTROL segment] 평가에 반영하는 데 최대 24시간이 소요될 수 있습니다. [프로필 병합 규칙 보고서](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

다음 [!UICONTROL Cross-Device Options] 인증된 사용자와 인증되지 않은 사용자를 선택하고 세그멘테이션을 위해 해당 크로스 디바이스 프로필을 활용할 수 있습니다. 이러한 옵션은 공유 장치에서 특정 사용자를 식별하고 연결하는 데 도움이 됩니다. 익명 및 인증된 사용자에 대한 자세한 내용은 [Audience Manager의 방문자 인증 상태](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>전달 <span class="keyword"> Audience Manager</span> 인증된 사용자로부터 수집된 데이터를 사용하지 마십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 현재 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>전달 <span class="keyword"> Audience Manager</span> 방문자가 사이트에 로그인한 경우 인증된 프로필에 데이터를 읽고 씁니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 마지막으로 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>전달 <span class="keyword"> Audience Manager</span> 장치에 마지막으로 로그인한 사용자의 인증된 프로필에서 데이터를 읽습니다. </p> <p>선택한 경우 <span class="keyword"> Audience Manager</span> 사용자가 익명 상태인 경우 인증된 프로필에 새 트레이트 데이터를 쓰지 않습니다. 인증되면 새 트레이트 데이터가 사용자의 인증된 프로필에 기록됩니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 모든 교차 장치 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>인증 상태에 관계없이 모든 교차 장치 프로필에서 데이터를 읽도록 Audience Manager에 알립니다. 이 옵션은 사람 기반 대상 추가 기능을 구입한 Audience Manager 고객에게만 제공됩니다.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

다음 [!UICONTROL Cross-Device Profile Options] 다음을 나열합니다. [!UICONTROL cross-device data sources]. 이러한 옵션은 다음을 만들 때 제공한 이름을 사용합니다. [!UICONTROL cross-device] [!UICONTROL data source] (참조 [크로스 디바이스 데이터 소스 만들기](merge-rules-start.md#create-data-source)). 최대 3개를 선택할 수 있습니다. [!UICONTROL cross-device data sources] 를 사용하여 각 프로필 규칙에 사용할 수 있습니다. 다음 [!UICONTROL Authenticated Profile Options] 을(를) 선택할 때 사용할 수 있습니다. **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

다음 [!UICONTROL Device Options] 의 유형을 선택할 수 있도록 해줍니다. *`device profile`* 다음에 의해 사용됨 [!UICONTROL Profile Merge Rule]. 장치 프로필은에서 빌드됩니다. [!UICONTROL traits] 익명 검색 활동에서 수집됩니다. 최소한 [!UICONTROL profile merge rule] 다음 포함: [!UICONTROL authenticated option] 및 a [!UICONTROL device option].

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
   <td colname="col2"> <p>전달 <span class="keyword"> Audience Manager</span> 세그먼테이션을 위해 익명 프로필에 포함된 트레이트를 사용하지 마십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>전달 <span class="keyword"> Audience Manager</span> 세그먼테이션에 익명 장치 프로필을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 프로필 링크 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p>전달 <span class="keyword"> Audience Manager</span> 현재 장치 및 사용자가 인증한 최대 100개의 다른 장치에서 프로필을 읽습니다. 이 장치 그래프는 의 고유한 자사 데이터를 기반으로 구축됩니다. <span class="keyword"> Audience Manager</span>. 디지털 속성 전반에 걸쳐 높은 수준의 인증을 보유한 고객에게 이상적입니다. 다음 <span class="wintitle"> 프로필 링크</span> device graph가 실시간으로 업데이트됩니다. 이 옵션은 다음을 선택할 때 사용할 수 있습니다. <b><span class="uicontrol"> 현재 인증된 프로필</span></b> 또는 <b><span class="uicontrol"> 마지막으로 인증된 프로필</span></b>. 이 옵션을 사용하는 경우 인증된 단일 프로필 만 선택할 수 있습니다(<span class="keyword"> Audience Manager</span> 다른 항목은 자동으로 회색으로 표시됩니다. 다음을 참조하십시오. <a href="profile-link-use-case.md"> 프로필 링크 장치 그래프 사용 사례</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>타사 장치 그래프 옵션</b> (개인 및 세대) </p> </td>
   <td colname="col2"> <p>이러한 옵션을 사용하면 서드파티 공급업체에서 제공하는 장치 그래프 기술을 기반으로 병합 규칙을 작성할 수 있습니다. 타사 장치 그래프는 다음을 제공합니다. </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 확률론적 및/또는 결정론적 데이터. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">개인 또는 가구 수준의 데이터. </li> 
     </ul> </p> <p>이러한 옵션을 사용하려면 이미 와 통합된 Device Graph를 제공하는 고객이어야 합니다 <span class="keyword"> Audience Manager</span>. 자세한 내용을 보거나 시작하려면 계정 관리자에게 문의하십시오. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

다른 세그먼트에서 자동으로 생성된 대상 세그먼트 [!DNL Experience Cloud] 솔루션, 외부에 정의된 병합 규칙 기반 [!DNL Audience Manager], 는 을 사용하는 것으로 표시됩니다. [!UICONTROL External Merge Policy]. 예를 들어 다음을 참조하십시오. [Audience Manager과 Adobe Experience Platform 간의 대상 공유](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

