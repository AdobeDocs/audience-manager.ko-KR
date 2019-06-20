---
description: 외부 장치 그래프를 통해 알 수 없는 사용자에 대한 중재, 리타겟팅 및 개인화를 위한 추천 및 사용 사례 외부 장치 그래프는 Audience Manager와 별개인 장치 그래프로 정의됩니다. 여기에는 Adobe가 타사 Determinalist 또는 Probabilistic 디바이스 그래프 회사와 체결한 Adobe Experience Cloud Device Co-op 및 기타 통합이 포함됩니다.
seo-description: 외부 장치 그래프를 통해 알 수 없는 사용자에 대한 중재, 리타겟팅 및 개인화를 위한 추천 및 사용 사례 외부 장치 그래프는 Audience Manager와 별개인 장치 그래프로 정의됩니다. 여기에는 Adobe가 타사 Determinalist 또는 Probabilistic 디바이스 그래프 회사와 체결한 Adobe Experience Cloud Device Co-op 및 기타 통합이 포함됩니다.
seo-title: 외부 장치 그래프 사용 사례
solution: Audience Manager
title: 외부 장치 그래프 사용 사례
uuid: F 4 BC 822 D -39 D 2-4680-90 ED -7 EE 2 EAD 6 DB 6 F
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 외부 장치 그래프 사용 사례 {#external-device-graph-use-cases}

외부 장치 그래프를 통해 알 수 없는 사용자에 대한 중재, 리타겟팅 및 개인화를 위한 추천 및 사용 사례 외부 장치 그래프는 Audience Manager와 별개인 장치 그래프로 정의됩니다. This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## 권장 사항 {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* 디지털 속성에 대한 인증 수준이 낮습니다. Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* 대규모 고객 타겟팅 [!DNL Experience Cloud Device Co-op] 타사 장치 그래프에는 인증된 데이터와 인증되지 않은 데이터가 포함됩니다.
* 개인 및 가계 수준에서 인증 및/또는 인증되지 않은 방문자를 세그먼트화합니다.

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

브랜딩 캠페인은 최대한 많은 사람들에게 도달하도록 고안되었습니다. 세그먼트 자격 조건은 제한되어 있지 않습니다. 그러나 이러한 캠페인은 컨텐츠를 여러 번 보고 전환하지 않는 사람들을 지속적으로 타겟팅하여 예산과 임프레션을 낭비할 수 있습니다. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. 예를 들어, 이러한 알려지지 않은 사용자를 설정된 주파수 CAP에 대해 여러 장치에서 본 후 &quot;시장 내&quot; 세그먼트에 추가할 수 있습니다.

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
      <li id="li_81AE304924724146A24FAB5B6533AD8E">특정 광고 캠페인에 대해 익명 사용자에게 최대 10 개의 노출 횟수를 전달하려는 경우. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">사용자가 여러 장치를 가지고 있으며, 사이트에 대한 인증을 받지 않았을 수도 있습니다. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">익명의 사용자는 현재 장치 및 외부 장치 그래프로 연결된 최대 3 개의 장치에서 인증되지 않은 상태로 탐색하는 동안 광고를 총 10 번 보게 됩니다. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">현재 장치에서 수집한 인증되지 않은 활동과 외부 장치 그래프로 연결된 3 개의 장치 (각 장치의 광고 노출) 를 병합합니다. </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">외부 장치 그래프와 현재 장치에 의해 연결된 모든 3 개 장치에서 익명 활동의 조합을 기반으로 인증되지 않은 사용자를 세그먼트 자격으로 평가합니다. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">현재 장치에서 억제 세그먼트로 사용할 세그먼트를 실시간 대상에 보내고 외부 장치 그래프로 연결된 모든 3 개의 장치를 전송합니다. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

이러한 전략은 인증되지 않았거나 알려지지 않은 사용자를 사이트로 다시 유도하거나 사이트에 있는 동안 검색 경험을 개인화하기 위해 고안되었습니다.

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
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">인증되지 않은 상태에서 사이트에서의 활동을 기반으로 익명의 사이트 내 및/또는 오프사이트 경험을 익명의 사용자에게 전달하려는 경우 </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">사용자가 여러 장치를 가지고 있으며, 사이트에 대한 인증을 받지 않았을 수도 있습니다. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">사용자는 현재 장치에서 인증되지 않은 상태에서 탐색하는 동안 사이트에서 여러 페이지를 보고 외부 장치 그래프로 연결된 최대 3 개의 장치를 봅니다. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">현재 장치에서 수집한 인증되지 않은 활동 및 외부 장치 그래프로 연결된 3 개의 장치 (각 장치의 여러 페이지 보기) 를 병합합니다. </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">외부 장치 그래프와 현재 장치에 의해 연결된 모든 3 개 장치에서 익명 활동의 조합을 기반으로 인증되지 않은 사용자를 세그먼트 자격으로 평가합니다. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">세그먼트를 실시간 대상으로 전송하여 현재 디바이스 및 외부 디바이스 그래프로 연결된 모든 3 개의 디바이스에 개인화된 사이트 내 경험을 전달합니다. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

이러한 사용 사례에 대한 병합 규칙 옵션은 아래에 표시된 사용 가능한 옵션과 비슷합니다. [!UICONTROL Authenticated Profile] 이러한 설정은 **[!UICONTROL Current Authenticated Profile]** 선택하거나 **[!UICONTROL Last Authenticated Profile]** 선택할 때만 사용할 수 있으므로 옵션이 비활성화됩니다. Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ like_ this]
>
>* [프로필 링크 장치 그래프 사용 사례](../../features/profile-merge-rules/profile-link-use-case.md)
>* [프로필 병합 규칙에 대한 일반적인 사용 사례](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

