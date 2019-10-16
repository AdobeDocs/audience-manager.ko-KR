---
description: 병합 규칙 옵션을 사용하면 Audience Manager가 세그멘테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager와 통합된 타사 장치 그래프 제공자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 4개의 프로필 병합 규칙을 만들 수 있습니다.
seo-description: 병합 규칙 옵션을 사용하면 Audience Manager가 세그멘테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager와 통합된 타사 장치 그래프 제공자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 4개의 프로필 병합 규칙을 만들 수 있습니다.
seo-title: 프로필 병합 규칙 옵션 정의
solution: Audience Manager
title: 프로필 병합 규칙 옵션 정의
uuid: 225eaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

병합 규칙 옵션을 사용하면 Audience Manager가 세그멘테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 Audience Manager와 통합된 [!UICONTROL Profile Link] 장치 그래프, [!UICONTROL Adobe Experience Cloud Device Co-op]및/또는 기타 타사 장치 그래프 제공자가 매핑하는 장치 프로파일이 포함될 수 있습니다. 최대 4개를 만들 수 [!UICONTROL Profile Merge Rules]있습니다. 네 [!UICONTROL Profile Merge Rule] [!UICONTROL People-Based Destinations] 번째 버전은 Add-On을 구입한 고객에게만 제공됩니다.

아래 설명된 옵션 중에서 하나를 [!UICONTROL Profile Merge Rule] 선택하여 만듭니다(in) [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

프로필 병합 규칙을 사용하면 여러 규칙 조합을 사용할 수 있으며, 각 조합에서는 특정 사용 사례에 맞게 조정됩니다. 각 규칙 조합 사용 시기에 대한 자세한 내용은 아래 표를 참조하십시오.

| 장치 간 옵션 | 장치 옵션 | 가용성 | 평가 유형 | Audience Lab 지원 | 사용 사례 |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| 크로스 디바이스 프로파일 없음 | 장치 프로파일 | 모든 고객 | 실시간 및 일괄 처리 | 예 | [장치 타깃팅](merge-rule-targeting-options.md#device-personalization) |
| 크로스 디바이스 프로파일 없음 | 외부 장치 그래프(Co-op 장치 그래프 포함) | 모든 고객 | 실시간 및 일괄 처리 | 아니오 | [확장된 장치 타깃팅](external-graph-use-cases.md#audience-expansion) |
| 현재 인증된 프로필 | 장치 프로파일 없음 | 모든 고객 | 실시간 전용 | 아니오 | [공유 장치 타깃팅](merge-rule-targeting-options.md#target-shared-devices) |
| 마지막으로 인증된 프로필 | 장치 프로파일 | 모든 고객 | 실시간 및 일괄 처리 | 예 | [온라인/오프라인 타깃팅](merge-rule-targeting-options.md#device-household-targeting) |
| 마지막으로 인증된 프로필 |  프로필 링크 장치 그래프 | 북미 및 캐나다만 해당 | 실시간 및 일괄 처리 | 예 | [크로스 디바이스 타깃팅](profile-link-use-case.md#cross-device-personalization) |
| 마지막으로 인증된 프로필 | 외부 장치 그래프(Co-op 장치 그래프 포함) | 모든 고객 | 실시간 및 일괄 처리 | 아니오 | [고급 크로스 디바이스 타깃팅](external-graph-use-cases.md#advanced-graph-expansion) |
| 모든 크로스 디바이스 프로파일 | 해당 없음 | 사용자 [기반 대상 고객에게만](../destinations/people-based-destinations-overview.md) 제공 | 일괄 처리만 | 아니오 | [사용자 기반 타깃팅](merge-rule-targeting-options.md#all-cross-device) |

## 프로필 병합 규칙 세그먼트 평가 {#segment-evaluation}

구성에 따라 Audience Manager는 실시간으로, 일괄적으로 또는 둘 다 세그먼트 평가를 수행할 수 있습니다. [!UICONTROL Profile Merge Rules]

* 실시간 세그먼트 평가를 [!DNL DCS] 위해서는 방문자가 실시간으로 디지털 속성에 액세스하여 세그먼트를 확인할 수 있어야 합니다.
* 이전에 자격을 갖춘 트레이트에 대해 일괄 세그먼트 평가가 수행됩니다.
* [!UICONTROL Profile Merge Rules] 실시간 및 일괄 세그먼트 평가를 모두 지원하는 이 기능은 실시간 방문자 활동과 이전에 자격 조건을 갖춘 트레이트를 결합합니다.

## 프로필 병합 규칙 보고 지연 {#reporting-latency}

실시간 세그먼트 평가는 [!UICONTROL Profile Merge Rules] 보고서에 즉시 반영됩니다.

프로필 병합 규칙 보고서에 [](profile-link-metrics.md)반영하려면 일괄 세그먼트 평가가 최대 24시간이 걸릴 수 있습니다.

## 장치 간 옵션 {#auth-options}

를 [!UICONTROL Cross-Device Options] 사용하면 인증된 사용자와 인증되지 않은 사용자를 선택할 수 있으며, 상호 장치 프로파일을 활용하여 세분화할 수 있습니다. 이러한 옵션은 공유 장치에서 특정 사용자를 식별하고 연결하는 데 도움이 됩니다. 익명 사용자와 인증된 사용자에 대한 자세한 내용은 Audience [Manager의 방문자 인증 상태를 참조하십시오](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 간 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 크로스 디바이스 프로파일 없음</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager에</span> 인증된 사용자로부터 수집한 데이터를 사용하지 않도록 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 현재 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>방문자가 <span class="keyword"> 사이트에 로그인한</span> 경우 Audience Manager에 인증된 프로필로 데이터를 읽고 쓰도록 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 마지막으로 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager</span> 에 장치에 마지막으로 로그인한 사용자의 인증된 프로필에서 데이터를 읽도록 알립니다. </p> <p>이 옵션을 선택하면 <span class="keyword"> Audience</span> Manager는 사용자가 익명으로 처리되는 경우 새 특성 데이터를 인증된 프로필에 쓰지 않습니다. 인증 시 새로운 트레이트 데이터가 사용자의 인증된 프로필에 기록됩니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 모든 크로스 디바이스 프로파일</span></b> </p> </td> 
   <td colname="col2"> <p>Audience Manager에 인증 상태에 상관없이 모든 크로스 디바이스 프로파일의 데이터를 읽도록 지시합니다. 이 옵션은 사용자 기반 대상 Add-On을 구입한 Audience Manager 고객에게만 제공됩니다.</p> </td>
  </tr>
 </tbody>
</table>

## 장치 간 프로필 옵션 {#profile-options}

크로스 디바이스 데이터 소스가 [!UICONTROL Cross-Device Profile Options] 나열됩니다. 이러한 옵션은 장치 간 데이터 소스를 만들 때 제공한 이름을 사용합니다(장치 간 데이터 소스 [만들기 참조](merge-rules-start.md#create-data-source)). 각 프로필 규칙에 사용할 크로스 장치 데이터 소스를 최대 3개까지 선택할 수 있습니다. 를 [!UICONTROL Authenticated Profile Options] 선택한 경우 **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]**&#x200B;를 사용할 수 있습니다.

## 장치 옵션 {#device-options}

를 [!UICONTROL Device Options] 사용하면 에서 *`device profile`* 사용하는 유형을 선택할 수 [!UICONTROL Profile Merge Rule]있습니다. 장치 프로파일은 사용자가 익명으로 웹을 탐색할 때 수집한 트레이트로 구성됩니다. 적어도 프로필 병합 규칙에는 인증된 옵션과 장치 옵션이 포함됩니다.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 프로파일 없음</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager에</span> 세그멘테이션에 포함된 트레이트를 사용하지 않도록 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 장치 프로파일</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager에</span> 세그멘테이션에 익명 장치 프로필을 사용하도록 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 프로필 링크 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager</span> 에 현재 장치 및 사용자가 인증한 최대 100개의 다른 장치에서 프로필을 읽도록 알려줍니다. 이 장치 그래프는 Audience Manager의 자사 데이터를 기반으로 <span class="keyword"> 구축되었습니다</span>. 디지털 자산에서 높은 수준의 인증을 보유한 고객에게 적합합니다. 프로필 <span class="wintitle"> 링크</span> 장치 그래프는 실시간으로 업데이트됩니다. 이 옵션은 [현재 인증된 프로필] 또는 [ <b><span class="uicontrol"> 마지막 인증된 프로필</span></b> ]을 선택할 때 <b><span class="uicontrol"> 사용할 수 있습니다</span></b>. 이 옵션을 사용하는 경우 인증된 단일 프로필만 선택할 수 있습니다(Audience Manager<span class="keyword"> 는</span> 자동으로 다른 프로필을 수집합니다). 프로필 링크 장치 <a href="profile-link-use-case.md"> 그래프 사용 사례를 참조하십시오</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager에</span> 현재 장치에서 프로파일을 읽도록 지시하고 Experience Cloud 장치 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Co-op에서 제공하는 링크를 사용하여 최대 100개의 다른 장치에서</a>프로파일을 읽도록 지시합니다. </p> <p><span class="keyword"> Device Co-op</span>는 참여하는 고객이 장치 링크 정보를 공유하는 디지털 협업입니다. Device <span class="keyword"> Co-op</span> 는 이 데이터를 <span class="term"> 장치 그래프로</span>처리합니다. 장치 그래프는 장치 클러스터를 서로 연결합니다. 이러한 링크는 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> 확률적이고 결정적 데이터에서</a>만들어집니다. 클러스터는 알 수 없는 사람이 사용하는 장치 그룹을 나타냅니다. <span class="keyword">Device Co-op</span>는 그 구성원들 간에 이러한 클러스터를 공유하며, 이를 통해 고객에게 가치 있고 일관된 크로스 디바이스 환경을 제공할 수 있습니다. </p> <p> Device Co-op에 대한 <span class="wintitle"> 자세한</span>내용은 다음을 참조하십시오. </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Device Co-op 개요</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> 멤버십 요구 사항</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> 장치 그래프:내부 프로세스 및 출력</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager 및 외부 장치 그래프</a> (PDF 다운로드). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>타사 장치 그래프 옵션</b> (개인 및 가구) </p> </td>
   <td colname="col2"> <p>이러한 옵션을 사용하면 타사 공급업체에서 제공하는 장치 그래프 기술을 기반으로 병합 규칙을 만들 수 있습니다. 타사 장치 그래프는 다음을 제공합니다. </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 확률적 및/또는 결정적 데이터. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">개인 또는 가정 수준의 데이터 </li> 
     </ul> </p> <p>이러한 옵션을 사용하려면 Audience Manager와 이미 통합된 장치 그래프의 고객이어야 <span class="keyword"> 합니다</span>. 자세한 내용을 살펴보거나 시작하려면 계정 관리자에게 문의하십시오. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKE_THIS]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

