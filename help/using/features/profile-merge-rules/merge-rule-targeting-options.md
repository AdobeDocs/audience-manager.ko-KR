---
description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 요구 사항이나 목표에 따라 특정 대상에 대한 고객 초점을 확장하거나 강화할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다.
seo-description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 요구 사항이나 목표에 따라 특정 대상에 대한 고객 초점을 확장하거나 강화할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다.
seo-title: 프로필 병합 규칙에 대한 일반 사용 사례
solution: Audience Manager
title: 프로필 병합 규칙에 대한 일반 사용 사례
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# 프로필 병합 규칙에 대한 일반 사용 사례 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 옵션을 사용하면 비즈니스 요구 사항이나 목표를 기반으로 특정 고객에 초점을 맞추거나 확대할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다. [!UICONTROL Profile Merge Rules] 실시간 및 일괄 처리 대상을 사용하여 작업할 수 있습니다.

>[!TIP]
>
>이러한 설정에 대한 정의 및 설명은 [!UICONTROL Merge Rule] 프로필 [병합 규칙 옵션 정의를 참조하십시오](merge-rule-definitions.md).

## 장치 타깃팅 {#device-personalization}

이 시나리오는 사용자 인증을 고려하지 않고 장치 ID(DSP, 온사이트 개인화 플랫폼 및 기타 장치 기반 타깃팅 플랫폼)를 지원하는 타깃팅 플랫폼을 사용하여 장치에 일관된 경험을 제공하기 위해 Audience Manager에 정의된 대상 세그먼트에 대해 단일 장치 프로파일을 평가하려는 마케터에게 적용됩니다.

장치 프로파일만을 대상으로 하는 규칙을 만들려면 **[!UICONTROL No Cross-Device Profile]** +를 **[!UICONTROL Device Profile]**&#x200B;선택합니다.

![장치 전용](assets/device-only.png)

John이 세 대의 스마트폰을 소유하고 있다고 합시다. 데이터 플랜 A에 대한 아이폰 7이 그 중 1개는 삼성 데이터 플랜 B입니다.John의 이동통신사는 세 장치 중 하나에서 John의 인증 상태를 고려하지 않고 데이터 플랜 A에서 실행되는 iPhone 7 장치에서만 데이터 플랜 업그레이드를 제공하려고 합니다.

장치 2는 무시되고, **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** 규칙을 [!DNL Device 1] 사용하고, [!DNL Device 3] 둘 다 세그먼트에 대한 자격이 주어집니다.

![장치 전용](assets/device-management.png)

## 공유 장치 타깃팅 {#target-shared-devices}

존과 그의 아내 제인이 같은 노트북을 이용해 온라인 상점에 가서 다양한 물건을 주문한다고 하자.

존은 여행 티켓과 특별 할인을 예약하기 위해 자신의 계정을 사용하는 반면, 제인은 음악과 영화를 사기 위해 자신의 계정을 사용한다.

스토어의 마케팅 팀은 **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** 규칙을 사용하여 John과 Jane의 인증된 활동에 따라 특정 거래를 타깃팅할 수 있습니다.

![현재 장치 없음](assets/current-no-device.png)

이 규칙을 사용하면 Audience Manager는 장치 프로파일, 세그먼트에 대한 적격한 John의 CRM ID를 완전히 무시하고 Jane의 CRM ID를 적격한 것이 아닙니다.

![shared-device-targeting](assets/shared-device-targeting.png)

## 온라인/오프라인 타깃팅 {#device-household-targeting}

이 사용 사례에서는 가정의 아이덴티티 관리를 다룹니다. 회사는 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** 규칙을 사용하여 해당 장치에서 인증한 마지막 프로필과 단일 장치 프로파일을 병합할 수 있습니다.

![last-device-profile](assets/last-device-profile.png)

연간 $100.000 이상의 소득을 가진 가정으로 이루어진 세그먼트를 고려해 보십시오. 이 중 하나 이상의 장치가 [!DNL iPhone 7] 포함되어 [!DNL Data Plan B]있습니다. 두 개의 가계부 프로파일(크로스 디바이스 프로파일)이 있으며, 각 프로파일(상호 디바이스 프로파일)은 서로 다른 두 개의 디바이스 프로파일에 연결되어 있습니다. 세그먼트에 대한 자격을 얻는 데 필요한 트레이트는 장치 및 장치 간 프로파일에 배포됩니다.

Audience Manager는 모든 장치 + 장치 간 프로필 쌍을 병합하여 병합된 트레이트 세트가 세그먼트에 적합한지 확인합니다. Audience Manager는 병합에 포함된 모든 프로필을 평가하므로 장치 프로파일과 집 프로필 모두 세그먼트화할 수 있습니다.

장치 및 가계부 프로필 간의 링크를 통해 Audience Manager는 세그먼트를 [!DNL Household 2] 위한 자격을 얻을 수 있지만 [!DNL Household 1]그렇지 않습니다. 부터 [!DNL Household 2]세그먼트에 대한 [!DNL Device 3] 자격이 부여됩니다. 이를 [!UICONTROL Profile Merge Rule] 통해 마케터는 일관성 있는 마케팅 메시지를 개별 디바이스([!DNL Device 3])와 광범위한 가구([!DNL Household 2])에 전달할 수 있습니다.

![가계 관리](assets/household-management.png)

## 사용자 기반 타깃팅 {#all-cross-device}

이 타깃팅 시나리오는 Add-on을 구입한 고객만 사용할 수 [!DNL People-Based Destinations] 있습니다. 이 규칙을 통해 마케터는 인증 데이터를 기반으로 고객에게 도달할 수 있습니다.

온라인 소매업체는 소셜 플랫폼을 통해 기존 고객에게 도달하고 이전 주문에 따라 개인화된 제안을 제공하려고 한다고 가정해 보겠습니다. 또한 [!UICONTROL People-Based Destinations]해시 처리한 이메일 주소를 Audience Manager [!DNL CRM] 로 인제스트하고, 오프라인 데이터에서 세그먼트를 만들고, 이러한 세그먼트를 광고하려는 소셜 플랫폼으로 보내 광고 지출을 최적화할 수 있습니다.

이 옵션에 대한 자세한 내용은 사람 기반 [대상을 참조하십시오](../destinations/people-based-destinations-overview.md).

![전체 장치](assets/all-cross-device.png)

## 장치 그래프 옵션 {#device-graph-options}

규칙에 대한 [!UICONTROL device graph] [!UICONTROL Profile Merge] 옵션을 선택하는 것은 디지털 속성 및 비즈니스 목표에 고유한 조건에 따라 달라집니다. 이러한 일반 지침은 그래프 유형을 사용하는 시기와 사용하는 시기를 이해하는 데 도움이 됩니다. 참고: 이러한 옵션을 사용하려면 Adobe Experience [Cloud](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) Device Co-op의 구성원이거나 외부 장치 그래프와 계약 관계가 있어야 합니다. 장치 그래프 옵션 선택 시기에 대한 일반적인 지침은 아래 표를 참조하십시오. 특정 사용 사례는 프로필 링크 [장치 그래프 사용 사례](profile-link-use-case.md) 및 [외부 장치 그래프 사용 사례를 참조하십시오](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 그래프 유형 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 프로필 링크 장치 그래프</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 프로필 링크</span> 옵션으로 작성된 프로필 <span class="wintitle"> 병합</span> 규칙은 다음 경우에 이상적입니다. </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">고급 고객 인증을 제공하는 디지털 속성 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">집중적인 낮은 도달 캠페인 프로필 <span class="wintitle"> 링크</span> 장치 그래프는 결정 데이터만을 기반으로 합니다. 이 장치 프로파일 풀은 인증되지 않은 사용자 및 장치의 풀에 대해 항상 더 작아집니다. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">고객이 인증된 상태에 있어야 세그먼테이션을 받을 수 있는 사용 사례 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>외부 장치 그래프 옵션 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Experience</span> Cloud Device Co-op <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> 또는 Audience Manager와</a> 통합된 외부 장치 그래프로 작성된 프로필 병합 <span class="keyword"> 규칙은 다음 경우에</span> 이상적입니다. </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">낮은 수준의 고객 인증을 제공하는 디지털 속성 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">광범위한 브랜드 캠페인 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">고객이 세그멘테이션의 자격을 갖추기 위해 인증된 상태에 있을 필요가 없는 경우. </li> 
     </ul> </p> <p> <p>팁:디바이스 <span class="keyword"> Co-op</span> 는 Experience Cloud <span class="keyword"></span> 고객이 낮은 인증과 디바이스 그래프 제공자와의 관계가 없는 경우에 가장 적합한 옵션입니다. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

가능한 사용 사례에 대한 개요는 아래 비디오를 [!UICONTROL Profile Merge Rules]참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/28975/?captions=kor)

>[!MORELIKE_THIS]
>
>* [프로필 링크 장치 그래프 사용 사례](profile-link-use-case.md)
>* [외부 장치 그래프 사용 사례](external-graph-use-cases.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

