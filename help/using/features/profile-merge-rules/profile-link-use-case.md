---
description: 프로필 링크 장치 그래프를 사용하여 세그먼트 재타깃팅 및 개인화된 세그먼트 자격 검증을 위한 권장 사항 및 사용 사례
seo-description: 프로필 링크 장치 그래프를 사용하여 세그먼트 재타깃팅 및 개인화된 세그먼트 자격 검증을 위한 권장 사항 및 사용 사례
seo-title: 프로필 링크 장치 그래프 사용 사례
solution: Audience Manager
title: 프로필 링크 장치 그래프 사용 사례
uuid: bd5567fd-fcd5-40ba-b6f1-035d2dbcd3a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 프로필 링크 장치 그래프 사용 사례 {#profile-link-device-graph-use-cases}

장치 그래프를 통한 세그먼트 재타깃팅 및 개인화된 세그먼트 자격 검증을 위한 권장 사항 및 사용 사례 [!UICONTROL Profile Link]

## 권장 사항 {#recommendations}

다음의 캠페인에 대한 [!UICONTROL Profile Link] 장치 그래프를 고려하십시오.

* 디지털 속성 전반에 걸쳐 높은 수준의 인증을 받을 수 있습니다. 인증된 사용자의 수가 적은 경우 [외부 장치 그래프 옵션을](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) 사용합니다.
* 알려진 고객을 정확하게 타깃팅해야 합니다. 이 [!UICONTROL Profile Link device graph] 파일은 인증된 퍼스트 파티 데이터를 사용하여 만들어집니다.
* 인증된 상태와 인증되지 않은 상태에 있는 알려진 고객을 실시간으로 타깃팅합니다.

![](assets/merge-rule-triangle2.png)

## 사용 사례 및 프로필 병합 규칙 구성 다시 타깃팅 {#retargeting-use-cases}

이전에 사이트 내 및/또는 인앱 인증을 획득한 고객을 여러 디바이스에서 리타겟팅할 수 있습니다. 세그먼트는 다음 프로파일로 구성될 수 있습니다.

* 마지막으로 인증된 장치 프로파일.
* 각 장치 프로파일에서 익명 활동

>[!NOTE]
>
>두 프로필 유형의 트레이트 정보를 사용하여 세그먼트를 만들 수 있습니다.

### 재타깃팅 예

샘플 신용 카드 회사에서 어떻게 작동하는지 살펴봅시다. 이 예에서는 3개의 장치 프로파일에서 보이는 익명 활동에서 수집된 트레이트 정보를 사용합니다.

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
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">사용자는 3개의 디바이스를 보유하고 있으며 모든 3개의 디바이스에서 신용 카드 회사 사이트/앱을 마지막으로 인증한 사람입니다. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">첫 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드에 대한 오퍼를 봅니다. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">두 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 혜택 페이지를 봅니다. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">세 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 수수료 및 요금 페이지를 봅니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이러한 조건이 주어지면 Audience <span class="keyword"> Manager는 다음과 같습니다</span>. </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">현재 장치에서 마지막으로 인증된 프로필을 사용하여 모든 3개의 장치에서 수집된 인증되지 않은 익명 활동을 병합합니다. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">다음을 기준으로 익명의 사용자가 세그먼트 자격 조건을 충족하는지 평가합니다. 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">모든 3개 장치에서 익명 활동의 조합입니다. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">현재 장치에서 마지막으로 인증된 프로필입니다. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">모든 3개 장치에서 재타깃팅을 위해 세그먼트를 실시간 대상에 보냅니다. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### 프로필 병합 규칙 다시 타깃팅 예

다음으로 다시 타깃팅을 설정하려면 [!UICONTROL Profile Link]아래 표시된 규칙 구성과 [!UICONTROL Authenticated Options] 같아야 [!UICONTROL Device Options] 합니다. 이 [!UICONTROL Authenticated Profile] 설정은 장치 간 데이터 소스의 이름을 사용하기 때문에 이 예제와 다릅니다.

![프로필 병합 규칙 설정](assets/merge-rules-internal3.png)

## 개인화 사용 사례 및 프로필 병합 규칙 구성 {#personalization-use-case}

인증된 고객을 위해 다양한 디바이스에서 활동을 기반으로 온사이트 및/또는 인앱 경험을 개인화할 수 있습니다. 세그먼트는 다음 프로파일로 구성될 수 있습니다.

* 현재 인증된 장치 프로파일.
* 익명의 디바이스 프로파일

>[!NOTE]
>
>사용자는 인증된 상태여야 세그먼트를 받을 수 있습니다.

### 개인화 예

샘플 신용 카드 회사에서 어떻게 작동하는지 살펴봅시다.

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
   <td colname="col2"> <p>사용 사례에서는 다음과 같은 조건을 가정합니다. </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">사용자는 3개의 디바이스를 보유하고 있으며 모든 3개의 디바이스에서 신용 카드 회사 사이트/앱을 마지막으로 인증한 사람입니다. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">첫 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드에 대한 오퍼를 봅니다. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">두 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 혜택 페이지를 봅니다. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">세 번째 장치에서 인증되지 않은 상태의 사용자는 프리미엄 신용 카드 수수료 및 요금 페이지를 봅니다. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">이러한 장치에서 고객은 자신의 균형을 확인하기 위해 인증(로그인)합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>결과</b> </p> </td> 
   <td colname="col2"> <p>이러한 조건이 주어지면 Audience <span class="keyword"> Manager는 다음과 같습니다</span>. </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">현재 인증된 프로필을 사용하여 모든 3개의 장치에서 수집된 인증되지 않은 익명 활동을 병합합니다. 인증된 프로필은 각 장치에서 일반적인 식별자를 제공합니다. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">다음을 기준으로 인증된 사용자에게 세그먼트 자격 조건을 평가합니다. 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">모든 3개 장치에서 익명 활동의 조합입니다. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">현재 인증된 프로필입니다. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">세그먼트를 실시간 대상으로 전송하여 현재 장치에서 인증되는 동안 사용자에 대한 개인화된 검색 경험을 만듭니다. <p>참고: 이렇게 하면 인증 상태와 관계없이 세그먼트에 대한 3개의 장치가 모두 허용됩니다. 이러한 경우 공유 장치인 경우 개인 정보 보호에 문제가 발생할 수 있습니다. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### 개인화 프로필 병합 규칙 예

개인화를 설정하려면 [!UICONTROL Profile Link]아래 표시된 규칙 구성과 [!UICONTROL Authenticated Options] 같아야 [!UICONTROL Device Options] 합니다. 이 [!UICONTROL Authenticated Profile] 설정은 장치 간 데이터 소스의 이름을 사용하기 때문에 이 예제와 다릅니다.

![](assets/merge-rules-internal4.png)

이러한 장치 그래프 처리 방법에 대한 자세한 내용을 보려면 PDF, Audience Manager [및 외부 장치 그래프를 다운로드하십시오](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORELIKE_THIS]
>
>* [외부 장치 그래프 사용 사례](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [프로필 병합 규칙에 대한 일반 사용 사례](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

