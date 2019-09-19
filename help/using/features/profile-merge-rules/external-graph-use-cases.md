---
description: 외부 디바이스 그래프로 알 수 없는 사용자를 위한 권장 사항 및 활용 사례 외부 장치 그래프는 Audience Manager와 별도의 장치 그래프로 정의됩니다. 여기에는 Adobe Experience Cloud Device Co-op와 Adobe가 타사 결정적 장치 또는 확률적 장치 그래프 회사와의 통합을 포함합니다.
seo-description: 외부 디바이스 그래프로 알 수 없는 사용자를 위한 권장 사항 및 활용 사례 외부 장치 그래프는 Audience Manager와 별도의 장치 그래프로 정의됩니다. 여기에는 Adobe Experience Cloud Device Co-op와 Adobe가 타사 결정적 장치 또는 확률적 장치 그래프 회사와의 통합을 포함합니다.
seo-title: 외부 장치 그래프 사용 사례
solution: Audience Manager
title: 외부 장치 그래프 사용 사례
uuid: f4bc822d-3 파섹
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 외부 장치 그래프 사용 사례 {#external-device-graph-use-cases}

외부 디바이스 그래프로 알 수 없는 사용자를 위한 권장 사항 및 활용 사례 외부 장치 그래프는 Audience Manager와 별도의 장치 그래프로 정의됩니다. 여기에는 Adobe가 타사 결정적 장치 또는 확률적 장치 그래프 회사와의 [!DNL Adobe Experience Cloud Device Co-op] 및 기타 통합이 포함됩니다.

## 권장 사항 {#recommendations}

다음의 캠페인에 대한 [!DNL Experience Cloud Device Co-op] 및 타사 디바이스 그래프 옵션을 고려하십시오.

* 디지털 속성 전반에 걸쳐 낮은 수준의 인증 인증된 사용자가 [많은 경우 [프로필 링크 장치 그래프] 옵션을](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) 사용합니다.
* 광범위한 고객 타겟팅 타사 [!DNL Experience Cloud Device Co-op] 장치 그래프에는 인증된 데이터와 인증되지 않은 데이터가 포함됩니다.
* 인증된 방문자 및/또는 인증되지 않은 방문자를 개인 및 가정 수준에서 세그먼트화할 수 있습니다.

![](assets/merge-rule-triangle1.png)

## 예상/브랜딩 사용 사례 {#prospecting-branding-use-cases}

브랜딩 캠페인은 가능한 한 많은 사람들에게 전달되도록 설계되었습니다. 세그먼트 자격 조건에 제한이 없습니다. 그러나 이러한 캠페인은 컨텐츠를 여러 번 보고 전환하지 않는 사용자를 지속적으로 타깃팅하여 예산 및 노출 횟수를 낭비할 수 있습니다. 타사 [!UICONTROL Profile Merge] 또는 타사 옵션을 사용하는 [!DNL Device Co-op] 규칙은 효율적인 브랜딩 캠페인을 만드는 데 도움이 될 수 있습니다. 예를 들어, 설정된 빈도 수에 대해 여러 장치에서 확인한 후 이러한 알 수 없는 사용자를 "비시장" 세그먼트에 추가할 수 있습니다.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>조건</b> </p> </td> 
   <td colname="col2">이 사용 사례에서는 다음과 같은 조건을 가정합니다. <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">특정 광고 캠페인에 대해 익명 사용자에게 최대 10개의 노출 횟수를 제공하려는 경우 </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">사용자에게 여러 장치가 있으며 사이트에 대한 인증이 있거나 없을 수 있습니다. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">익명의 사용자는 현재 장치에서 인증되지 않은 상태와 외부 장치 그래프로 연결된 최대 3개의 장치를 탐색하는 동안 광고를 총 10번 봅니다. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">Audience Manager <span class="keyword"> 세그먼트를</span> 정의하여 10개의 노출 횟수를 확인한 후 익명의 사용자를 분류했습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이러한 조건이 주어지면 Audience <span class="keyword"> Manager는 다음과 같습니다</span>. </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">현재 장치에서 수집된 인증되지 않은 익명 활동과 외부 장치 그래프로 연결된 3개의 장치(각 장치의 광고 노출)를 병합합니다. </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">외부 장치 그래프와 현재 장치에 의해 연결된 모든 3개의 장치에서 익명 활동의 조합을 기준으로 인증되지 않은 사용자를 세그먼트 자격 조건에 대해 평가합니다. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">현재 장치에서 억제 세그먼트로 사용할 실시간 대상 및 외부 장치 그래프로 연결된 모든 3개의 장치로 세그먼트를 보냅니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## 재타깃팅 또는 사이트 개인화 사용 사례 {#retargeting-use-case}

이러한 전략은 인증되지 않았거나 알 수 없는 사용자를 사이트로 다시 연결하거나 방문 중에 검색 경험을 개인화하기 위해 고안되었습니다.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>조건</b> </p> </td> 
   <td colname="col2">이 사용 사례에서는 다음과 같은 조건을 가정합니다. <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">인증되지 않은 상태에서 사이트의 활동을 기반으로 개인화된 온사이트 및/또는 오프사이트 경험을 익명의 사용자에게 제공하려는 경우 </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">사용자에게 여러 장치가 있으며 사이트에 대한 인증이 있거나 없을 수 있습니다. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">사용자는 현재 장치에서 인증되지 않은 상태와 외부 장치 그래프로 연결된 최대 3개의 장치를 탐색하는 동안 사이트에서 여러 페이지를 봅니다. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">인증되지 않은 <span class="keyword"> 상태로</span> 탐색하는 동안 사이트에서 여러 페이지를 본 후 사용자를 평가할 수 있도록 Audience Manager 세그먼트를 정의했습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이러한 조건이 주어지면 Audience <span class="wintitle"> Manager는 다음과 같습니다</span>. </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">현재 장치에서 수집된 인증되지 않은 익명 활동과 외부 장치 그래프로 연결된 3개의 장치를 병합합니다(각 장치에서 여러 페이지 보기). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">외부 장치 그래프와 현재 장치에 의해 연결된 모든 3개의 장치에서 익명 활동의 조합을 기준으로 인증되지 않은 사용자를 세그먼트 자격 조건에 대해 평가합니다. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">세그먼트를 실시간 대상에 전송하여 현재 디바이스와 외부 디바이스 그래프로 연결된 모든 3개의 디바이스에 개인화된 온사이트 및/또는 오프사이트 경험을 제공합니다. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## 외부 장치 그래프 사용 사례에 대한 프로필 병합 규칙 옵션 {#profile-merge}

이러한 사용 사례에 대한 병합 규칙 옵션은 아래에 표시된 사용 가능한 옵션과 비슷합니다. 이 [!UICONTROL Authenticated Profile] 옵션은 선택 **[!UICONTROL Current Authenticated Profile]** 또는 **[!UICONTROL Last Authenticated Profile]**&#x200B;사용 가능한 경우에만 사용할 수 있으므로 비활성화됩니다. 사용할 디바이스 그래프 설정의 유형에 따라 [!UICONTROL Device Options] 달라질 수 있습니다.

![](assets/merge-rules-external.png)

이러한 장치 그래프 처리 방법에 대한 자세한 내용을 보려면 PDF, Audience Manager [및 외부 장치 그래프를 다운로드하십시오](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORELIKE_THIS]
>
>* [프로필 링크 장치 그래프 사용 사례](../../features/profile-merge-rules/profile-link-use-case.md)
>* [프로필 병합 규칙에 대한 일반 사용 사례](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

