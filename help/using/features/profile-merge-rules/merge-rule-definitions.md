---
description: 병합 규칙 옵션을 사용하면 세그멘테이션에 사용되는 데이터 Audience Manager의 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager와 통합된 기타 타사 장치 그래프 제공자에 의해 매핑된 장치 프로파일이 포함될 수 있습니다. 최대 3 개의 프로필 병합 규칙을 만들 수 있습니다.
seo-description: 병합 규칙 옵션을 사용하면 세그멘테이션에 사용되는 데이터 Audience Manager의 유형을 제어할 수 있습니다. 병합 규칙에는 프로필 링크 장치 그래프, Adobe Experience Cloud Device Co-op 및/또는 Audience Manager와 통합된 기타 타사 장치 그래프 제공자에 의해 매핑된 장치 프로파일이 포함될 수 있습니다. 최대 3 개의 프로필 병합 규칙을 만들 수 있습니다.
seo-title: 정의된 프로필 병합 규칙 옵션
solution: Audience Manager
title: 정의된 프로필 병합 규칙 옵션
uuid: 225 EEAF 7-45 E 9-4 F 21-9360-D 80 A 9 F 90520 C
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rule Options Defined {#profile-merge-rule-options-defined}

병합 규칙 옵션을 사용하면 세그멘테이션에 사용되는 데이터 Audience Manager의 유형을 제어할 수 있습니다. A merge rule can include device profiles mapped by the [!UICONTROL Profile Link] device graph, the [!UICONTROL Adobe Experience Cloud Device Co-op], and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 3 [!UICONTROL Profile Merge Rules].

You build a [!UICONTROL Profile Merge Rule] by making a selection from these options:

<ul class="simplelist"> 
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#auth-options"> 인증된 옵션</a> </li>
 <li> <a href="../../features/profile-merge-rules/merge-rule-definitions.md#profile-options"> 인증된 프로필 옵션</a> </li>
 <li><a href="../../features/profile-merge-rules/merge-rule-definitions.md#device-options"> 장치 옵션</a> </li>
</ul>

## Authenticated Options {#auth-options}

The [!UICONTROL Authenticated Options] let you select un-authenticated and authenticated users and leverage their cross-device profile for segmentation. 이러한 옵션은 공유 장치에서 특정 사용자를 식별하고 도달하는 데 도움이 됩니다. For more information on anonymous and authenticated users, see [Visitor Authentication States in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 에게 인증된 사용자로부터 수집한 데이터를 사용하지 않도록 알려줍니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 현재 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p>Tells <span class="keyword"> Audience Manager</span> to read and write data to the authenticated profile if a visitor has logged in to your site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 마지막으로 인증된 프로필</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 에서 장치에 마지막으로 로그인한 사용자의 인증된 프로필에서 데이터를 읽도록 합니다. </p> <p>When selected, <span class="keyword"> Audience Manager</span> will not write new trait data to the authenticated profile if the user is anonymous. 인증이 완료되면 새 트레이트 데이터가 사용자의 인증된 프로필에 기록됩니다. </p> </td>
  </tr> 
 </tbody>
</table>

## Authenticated Profile Options {#profile-options}

The [!UICONTROL Authenticated Profile Options] lists your cross-device data sources. These options use the names you provided when you created a cross-device data source (see [Create a Cross-Device Data Source](../../features/profile-merge-rules/merge-rules-start.md#create-data-source)). 각 프로필 규칙에 사용할 상호 장치 데이터 소스를 최대 3 개까지 선택할 수 있습니다. The [!UICONTROL Authenticated Profile Options] are available when you choose **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**.

## Device Options {#device-options}

The [!UICONTROL Device Options] let you select the type of *`device profile`* used by a [!UICONTROL Profile Merge Rule]. 장치 프로파일은 익명으로 웹을 검색할 때 사용자가 수집한 트레이트로 구성됩니다. 최소한 프로필 병합 규칙에는 인증된 옵션과 장치 옵션이 포함됩니다.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 디바이스 프로파일 없음</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 에서 세그멘테이션에 대한 익명 프로필에 포함된 트레이트를 사용하지 않도록 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 현재 장치 프로파일</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 에서 세그멘테이션에 대해 익명 장치 프로필을 사용하도록 지시합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> 프로필 링크 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 에게 사용자가 인증한 최근 장치 및 최근 3 개의 장치에서 프로필을 읽도록 지시합니다. This device graph is built on your own, first-party data in <span class="keyword"> Audience Manager</span>. 디지털 자산에서 높은 수준의 인증을 보유하고 있는 고객에게 이상적입니다. <span class="wintitle"> 프로필 링크</span> 장치 그래프는 실시간으로 업데이트됩니다. This option is available when you select <b><span class="uicontrol"> Current Authenticated Profile</span></b> or <b><span class="uicontrol"> Last Authenticated Profile</span></b>. When using this option, you can only choose a single authenticated profile (<span class="keyword"> Audience Manager</span> automatically grays out the others). <a href="../../features/profile-merge-rules/profile-link-use-case.md"> 프로필 링크 장치 그래프 사용 사례를 참조하십시오</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op 장치 그래프</span></b> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> 에서 <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op에서 제공하는 링크를 사용하여 장치 프로파일을 병합하도록 합니다</a>. </p> <p><span class="keyword"> Device Co-op</span>는 참여하는 고객이 장치 링크 정보를 공유하는 디지털 협업입니다. <span class="keyword"> 장치 Co-op</span> 는 이 데이터를 <span class="term"> 장치 그래프에 처리합니다</span>. 장치 그래프는 장치 클러스터를 양식 장치 클러스터로 연결합니다. These links are built from <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistic and deterministic data</a>. 클러스터는 알 수 없는 사람이 사용하는 장치 그룹을 나타냅니다. <span class="keyword">Device Co-op</span>는 그 구성원들 간에 이러한 클러스터를 공유하며, 이를 통해 고객에게 가치 있고 일관된 크로스 디바이스 환경을 제공할 수 있습니다. </p> <p> For more information about the <span class="wintitle"> Device Co-op</span>, see the: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> 장치 협력 개요</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> 멤버십 요구 사항</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> 장치 그래프: 내부 프로세스 및 출력</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager 및 외부 디바이스 그래프</a> (PDF 다운로드) </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>타사 장치 그래프 옵션</b> (개인 및 가족) </p> </td>
   <td colname="col2"> <p>이러한 옵션을 사용하면 타사 공급업체에서 제공하는 장치 그래프 기술을 기반으로 병합 규칙을 만들 수 있습니다. 타사 장치 그래프는 다음을 제공합니다. </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> 확률적 및/또는 확정 데이터. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">개인 또는 가계 수준의 데이터. </li> 
     </ul> </p> <p>To use these options, you must be a customer of a device graph provides who is already integrated with <span class="keyword"> Audience Manager</span>. 자세한 내용을 살펴보거나 시작하려면 계정 관리자에게 문의하십시오. </p> <p>&lt; a href = "../../features/profile-merge-rules/external-graph-use-cases. md 참조) </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_ like_ this]
>
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

