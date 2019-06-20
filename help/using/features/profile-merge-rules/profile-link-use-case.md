---
description: 프로필 링크 장치 그래프를 사용하여 세그먼트 리타겟팅 및 개인화된 세그먼트 자격 조건에 대한 추천 및 사용 사례
seo-description: 프로필 링크 장치 그래프를 사용하여 세그먼트 리타겟팅 및 개인화된 세그먼트 자격 조건에 대한 추천 및 사용 사례
seo-title: 프로필 링크 장치 그래프 사용 사례
solution: Audience Manager
title: 프로필 링크 장치 그래프 사용 사례
uuid: BD 5567 FD-FCD 5-40 BA-B 6 F 1-035 D 2 DDBCD 3 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Link Device Graph Use Cases {#profile-link-device-graph-use-cases}

Recommendations and use cases for segment retargeting and personalized segment qualification with the [!UICONTROL Profile Link] device graph.

## 권장 사항 {#recommendations}

Consider the [!UICONTROL Profile Link] device graph for campaigns that:

* 디지털 자산에서 높은 수준의 인증을 받을 수 있습니다. Use an [external device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a small amount of authenticated users.
* 알려진 고객을 정확하게 타겟팅해야 합니다. The [!UICONTROL Profile Link device graph] is built using first-party, authenticated data.
* 인증된 고객 및 인증되지 않은 상태의 알려진 고객을 실시간으로 타깃팅합니다.

![](assets/merge-rule-triangle2.png)

## Retargeting Use Case and Profile Merge Rule Configuration {#retargeting-use-cases}

이전에 인증된 여러 디바이스에서 사이트 내 및/또는 인앱 경험이 있는 고객을 다시 타깃팅합니다. 세그먼트는 다음 프로필로 구성될 수 있습니다.

* 마지막으로 인증된 장치 프로필입니다.
* 각 장치 프로필에 대한 익명 활동.

>[!NOTE]
>
>특성 유형 프로필 유형을 사용하여 세그먼트를 만들 수 있습니다.

### 리타겟팅 예

샘플 신용 카드 회사와 함께 사용하는 방법을 살펴보겠습니다. 이 예에서는 3 개 장치 프로파일에서만 볼 수 있는 익명 활동에서 수집된 특성 정보를 사용합니다.

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>조건</b> </p> </td> 
   <td colname="col2"> <p>이 사용 사례에서는 다음과 같은 조건을 가정합니다. </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">사용자는 3 개의 장치를 가지고 있으며, 모든 3 개의 장치에서 신용 카드 회사 사이트/앱에서 인증을 받는 마지막 사람입니다. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">첫 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드에 대한 오퍼를 볼 수 있습니다. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">두 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 이점 페이지를 볼 수 있습니다. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">세 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 비용 및 요금 페이지를 볼 수 있습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">모든 3 개의 장치에서 수집된 인증되지 않은 익명 활동을 현재 장치에서 마지막으로 인증된 프로필을 사용하여 병합합니다. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">다음을 기반으로 세그먼트 자격 조건에 대한 익명 사용자를 평가합니다. 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">모든 3 개 장치에서 익명 활동을 결합합니다. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">현재 장치에서 마지막으로 인증된 프로필입니다. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">모든 3 개 장치에서 리타겟팅의 실시간 대상에 세그먼트를 전송합니다. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 프로필 병합 규칙 예 리타겟팅

To set up retargeting with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] 이러한 설정은 크로스 디바이스 데이터 소스의 이름을 사용하기 때문에 옵션은 이 예와 다릅니다.

![프로필 병합 규칙 설정](assets/merge-rules-internal3.png)

## Personalization Use Case and Profile Merge Rule Configuration {#personalization-use-case}

다양한 디바이스에서 활동을 기반으로 인증된 고객 사이트 및/또는 인앱 경험을 개인화할 수 있습니다. 세그먼트는 다음 프로필로 구성될 수 있습니다.

* 현재 인증된 장치 프로필입니다.
* 익명의 디바이스 프로파일.

>[!NOTE]
>
>세그먼트를 적용하려면 사용자가 인증된 상태여야 합니다.

### 개인화 예

샘플 신용 카드 회사와 함께 사용하는 방법을 살펴보겠습니다.

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 사용 사례 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>조건</b> </p> </td> 
   <td colname="col2"> <p>Adobe 사용 사례에서는 다음의 조건을 가정합니다. </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">사용자는 3 개의 장치를 가지고 있으며, 모든 3 개의 장치에서 신용 카드 회사 사이트/앱에서 인증을 받는 마지막 사람입니다. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">첫 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드에 대한 오퍼를 볼 수 있습니다. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">두 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 이점 페이지를 볼 수 있습니다. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">세 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 비용 및 요금 페이지를 볼 수 있습니다. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">이러한 장치에서 고객은 로그인을 통해 인증을 인증합니다 (로그인). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">모든 3 개 장치에서 수집한 인증되지 않은 익명 활동을 현재 인증된 프로필을 사용하여 병합합니다. 인증된 프로필은 각 장치에서 공통 식별자를 제공합니다. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">다음을 기반으로 세그먼트 자격 검증의 인증된 사용자를 평가합니다. 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">모든 3 개 장치에서 익명 활동을 결합합니다. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">현재 인증된 프로필입니다. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">세그먼트를 실시간 대상에 전송하여 현재 장치에서 인증된 동안 사용자에 대한 개인화된 검색 경험을 만듭니다. <p>참고: 인증 상태에 관계없이 세그먼트에 대해 모든 3 개의 장치가 자격 조건을 갖추게 됩니다. 이러한 결과가 공유 장치인 경우 개인 정보 보호에 대한 우려가 발생할 수 있습니다. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### 개인화 프로필 병합 규칙 예

To set up personalization with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] 이러한 설정은 크로스 디바이스 데이터 소스의 이름을 사용하기 때문에 옵션은 이 예와 다릅니다.

![](assets/merge-rules-internal4.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ like_ this]
>
>* [외부 장치 그래프 사용 사례](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [프로필 병합 규칙에 대한 일반적인 사용 사례](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

