---
description: 외부 디바이스 그래프로 알 수 없는 사용자를 위한 권장 사항 및 사용 사례 외부 장치 그래프는 Audience Manager과 별개인 장치 그래프로 정의됩니다. 여기에는 Adobe Experience Cloud Device Co-op와 Adobe가 타사 결정 또는 확률적 장치 그래프 회사와 가지는 기타 통합이 포함됩니다.
seo-description: 외부 디바이스 그래프로 알 수 없는 사용자를 위한 권장 사항 및 사용 사례 외부 장치 그래프는 Audience Manager과 별개인 장치 그래프로 정의됩니다. 여기에는 Adobe Experience Cloud Device Co-op와 Adobe가 타사 결정 또는 확률적 장치 그래프 회사와 가지는 기타 통합이 포함됩니다.
seo-title: 외부 장치 그래프 사용 사례
solution: Audience Manager
title: 외부 장치 그래프 사용 사례
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 5%

---


# 외부 장치 그래프 사용 사례 {#external-device-graph-use-cases}

외부 디바이스 그래프로 알 수 없는 사용자를 위한 권장 사항 및 사용 사례 외부 장치 그래프는 Audience Manager과 별개인 장치 그래프로 정의됩니다. 여기에는 Adobe가 제3자 결정 또는 확률적 장치 그래프 회사와 맺은 [!DNL Adobe Experience Cloud Device Co-op] 및 기타 통합이 포함됩니다.

## 권장 사항 {#recommendations}

다음의 캠페인에 대한 [!DNL Experience Cloud Device Co-op] 및 타사 디바이스 그래프 옵션을 고려하십시오.

* 디지털 속성 전반에 걸쳐 낮은 수준의 인증 인증된 사용자가 많은 [!UICONTROL Profile Link Device Graph option] 경우 을 사용합니다.
* 광범위한 고객 Target 타사 장치 그래프 [!DNL Experience Cloud Device Co-op] 는 인증된 데이터와 인증되지 않은 데이터를 포함합니다.
* 인증된 방문자 및/또는 인증되지 않은 방문자를 개인 및 가구 수준에서 세그먼트화합니다.

![](assets/merge-rule-triangle1.png)
<!-- 
## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

A branding campaign is designed to reach as many people as possible. It places few limits on segment qualification. But, these campaigns can waste budget and impressions by constantly targeting people who see your content multiple times and don't convert. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. For example, you can add these unknown users to a "not in-market" segment after seeing them across multiple devices for your set frequency cap.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">You want to deliver a maximum of 10 impressions to an anonymous user for a specific ad campaign. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">A user has 4 devices and may or may not have authenticated on your site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">An anonymous user sees the ad a total of 10 times while browsing in an unauthenticated state on their current device and 3 devices linked to the current device by an external device graph. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Merges the anonymous, unauthenticated activity collected from the current device and the 3 devices linked by the external device graph (the ad impressions from each device). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sends the segment to any real-time destination for use as a suppression segment on the current device and all 3 devices linked by the external device graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

These strategies are designed to bring an unauthenticated or unknown user back to your site or personalize their browsing experience while they're on-site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">You want to deliver a personalized on-site and/or off-site experience to an anonymous user based on their activity on your site while in an unauthenticated state. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">A user has multiple devices and may or may not have authenticated to your site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">A user views multiple pages on your site while browsing in an unauthenticated state on their current device and 3 other devices linked by an external device graph. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state.</li>
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Merges the anonymous, unauthenticated activity collected from the current devices and the 3 devices linked by the external device graph (the multiple page views from each device). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sends the segment to any real-time destination to deliver a personalized on-site and/or off-site experience across the current device and all 3 devices linked by the external device graph. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table> -->

## 확장된 장치 타깃팅 {#audience-expansion}

이 활용 사례는 [!DNL Adobe Co-Op Device Graph] 또는 다른 방법을 통해 정확한 크로스 디바이스 개인화를 통해 어드레서블 대상의 규모를 확장할 수 있는 방법을 보여줍니다 [!DNL External Device Graphs].

Jane이 휴일 패키지 거래를 찾기 위해 정기적으로 사용하는 세 가지 장치를 가지고 있다고 가정해 봅시다. 그녀의 노트북([!DNL Device 1]), 스마트폰([!DNL Device 2]) 및 태블릿([!DNL Device 3])을 제인은 노트북을 사용하는 동안 항공, 호텔, 가이드 투어를 찾아보았다. 김 씨는 스마트폰과 태블릿PC를 사용하면서 여행사 홈페이지만 찾아가 봤다.

여행사는 [!UICONTROL No Cross-Device Profile] + [!UICONTROL Adobe Co-op Device Graph] 규칙을 사용하여 세 가지 장치 프로파일을 모두 병합할 수 있습니다. 이 프로필들은 이 프로파일을 전체 장치 소유자와 연결시키기 때문입니다 [!UICONTROL Adobe Co-op Device Graph].

![audience-expansion-rule](assets/audience-expansion-rule.png)

이 예제에서 세그먼트 자격 조건에 필요한 트레이트가 모두 수집되었습니다 [!DNL Device 1]. Audience Manager은 세그먼트에 대해 프로필 병합에 참여한 모든 장치 프로파일을 검사하므로 이제 Jane의 세 가지 장치 프로필이 모두 세그먼트화됩니다.

이 규칙을 통해 장치 그래프는 이 세그먼트를 1개에서 3개로 분류할 수 있는 장치 프로파일 수를 확장했으며, 여행사를 통해 Jane이 소유한 모든 3개의 디바이스에 일관된 메시지를 전달할 수 있게 되었습니다.

![고객 확대](assets/audience-expansion.png)

## 고급 크로스 디바이스 타깃팅 {#advanced-graph-expansion}

이 사용 사례에서는 외부 장치 그래프나 장치 [!DNL Adobe Co-Op Device Graph]**[!UICONTROL Last Authenticated Profiles]** **[!UICONTROL Adobe Co-Op Device Graph]** 에서 + 규칙을 사용하여 인증된 방문자에 대한 대상 타깃팅을 확장하는 방법을 보여줍니다.

![마지막 장치 그래프](assets/last-device-coop.png)

아래 예에서, Acme Inc. 회사는 가입자를 두고 [!DNL Acme Inc.] [!DNL Data Plan A][!DNL iPhone 7] 장치를 사용하는 100.000달러 이상의 소득을 가진 모든 가구를 목표로 하고 있습니다.

존은 데이터 플랜 A에서 자신의 iPhone 7을 사용하여 Acme Inc. 웹 사이트에서 인증합니다. 동시에 John의 클러스터에는 정기적으로 사용하는 두 개의 추가 장치가 포함되어 있습니다. [!DNL Co-Op Device Graph] 그의 노트북([!DNL Device 1]) 및 보조 스마트폰 [!DNL Device 2] (a [!DNL Samsung S7] on [!DNL Data Plan B])

+ **[!UICONTROL Last Authenticated Profiles]** 를 사용하면 처음 **[!UICONTROL Adobe Co-Op Device Graph]**[!DNL Acme Inc.] 에 한 대만 세그먼트에 해당되는 John의 장치 그래프 클러스터에서 세 개 장치 모두에 개인화된 메시지를 전달할 수 있습니다.

![고급 그래프 확장](assets/advanced-device-graph-expansion.png)

>[!MORELIKETHIS]
>
>* [프로필 링크 장치 그래프 사용 사례](profile-link-use-case.md)
>* [프로필 병합 규칙에 대한 일반 사용 사례](merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

