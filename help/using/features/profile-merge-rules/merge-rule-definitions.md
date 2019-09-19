---
description: 병합 규칙 옵션을 사용하면 Audience Manager가 세그멘테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager와 통합된 타사 장치 그래프 제공자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 3개의 프로필 병합 규칙을 만들 수 있습니다.
seo-description: 병합 규칙 옵션을 사용하면 Audience Manager가 세그멘테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager와 통합된 타사 장치 그래프 제공자가 매핑하는 장치 프로필이 포함될 수 있습니다. 최대 3개의 프로필 병합 규칙을 만들 수 있습니다.
seo-title: 프로필 병합 규칙 옵션 정의
solution: Audience Manager
title: 프로필 병합 규칙 옵션 정의
uuid: 225eaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

병합 규칙 옵션을 사용하면 Audience Manager가 세그멘테이션에 사용하는 데이터 유형을 제어할 수 있습니다. 병합 규칙에는 Audience Manager와 통합된 [!UICONTROL Profile Link] 장치 그래프, [!UICONTROL Adobe Experience Cloud Device Co-op]및/또는 기타 타사 장치 그래프 제공자가 매핑하는 장치 프로파일이 포함될 수 있습니다. 최대 3개를 만들 수 [!UICONTROL Profile Merge Rules]있습니다.

다음 옵션 중 하나를 선택하여 [!UICONTROL Profile Merge Rule] 만듭니다.

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> 인증된 옵션</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> 인증된 프로필 옵션</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 장치 옵션</a> </li>
</ul>

## 인증된 옵션 {#auth-options}

이 [!UICONTROL Authenticated Options] 옵션을 사용하면 인증되지 않은 사용자와 인증된 사용자를 선택할 수 있으며, 상호 장치 프로파일을 활용하여 세분화할 수 있습니다. 이러한 옵션은 공유 장치에서 특정 사용자를 식별하고 연결하는 데 도움이 됩니다. 익명 사용자와 인증된 사용자에 대한 자세한 내용은 Audience [Manager의 방문자 인증 상태를 참조하십시오](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 인증된 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 인증된 프로필 없음</span></b> </p> </td> 
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
 </tbody>
</table>

## 인증된 프로필 옵션 {#profile-options}

크로스 디바이스 데이터 소스가 [!UICONTROL Authenticated Profile Options] 나열됩니다. 이러한 옵션은 장치 간 데이터 소스를 만들 때 제공한 이름을 사용합니다(장치 간 데이터 소스 [만들기 참조](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). 각 프로필 규칙에 사용할 크로스 장치 데이터 소스를 최대 3개까지 선택할 수 있습니다. 를 [!UICONTROL Authenticated Profile Options] 선택한 경우 **[!UICONTROL Current Authenticated Profile]** 또는 **[!UICONTROL Last Authenticated Profile]**&#x200B;를 사용할 수 있습니다.

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
   <td colname="col1"> <p> <b><span class="uicontrol"> 현재 장치 프로파일</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager에</span> 세그멘테이션에 익명 장치 프로필을 사용하도록 알립니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 프로필 링크 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p>Audience <span class="keyword"> Manager</span> 에 현재 장치 및 사용자가 인증한 마지막 3개 장치에서 프로필을 읽도록 알려줍니다. 이 장치 그래프는 Audience Manager의 자사 데이터를 기반으로 <span class="keyword"> 구축되었습니다</span>. 디지털 자산에서 높은 수준의 인증을 보유한 고객에게 적합합니다. 프로필 <span class="wintitle"> 링크</span> 장치 그래프는 실시간으로 업데이트됩니다. 이 옵션은 [현재 인증된 프로필] 또는 [ <b><span class="uicontrol"> 마지막 인증된 프로필</span></b> ]을 선택할 때 <b><span class="uicontrol"> 사용할 수 있습니다</span></b>. 이 옵션을 사용하는 경우 인증된 단일 프로필만 선택할 수 있습니다(Audience Manager<span class="keyword"> 는</span> 자동으로 다른 프로필을 수집합니다). 프로필 링크 장치 <a href="../../features/profile-merge-rules/profile-link-use-case.md"> 그래프 사용 사례를 참조하십시오</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p>Adobe <span class="keyword"> Experience Cloud</span> Device Co-op에서 제공하는 링크를 사용하여 장치 프로파일을 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> 병합하도록 Audience Manager에 지시합니다</a>. </p> <p><span class="keyword"> Device Co-op</span>는 참여하는 고객이 장치 링크 정보를 공유하는 디지털 협업입니다. Device <span class="keyword"> Co-op</span> 는 이 데이터를 <span class="term"> 장치 그래프로</span>처리합니다. 장치 그래프는 장치 클러스터를 서로 연결합니다. 이러한 링크는 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> 확률적이고 결정적 데이터에서</a>만들어집니다. 클러스터는 알 수 없는 사람이 사용하는 장치 그룹을 나타냅니다. <span class="keyword">Device Co-op</span>는 그 구성원들 간에 이러한 클러스터를 공유하며, 이를 통해 고객에게 가치 있고 일관된 크로스 디바이스 환경을 제공할 수 있습니다. </p> <p> Device Co-op에 대한 <span class="wintitle"> 자세한</span>내용은 다음을 참조하십시오. </p> <p> 
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
     </ul> </p> <p>이러한 옵션을 사용하려면 Audience Manager와 이미 통합된 장치 그래프의 고객이어야 <span class="keyword"> 합니다</span>. 자세한 내용을 살펴보거나 시작하려면 계정 관리자에게 문의하십시오. </p> <p>&lt;a href="../../features/profile-merge-rules/external-graph-use-cases.md)도 참조하십시오. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKE_THIS]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

