---
description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 요구나 목표를 기반으로 특정 대상에 대한 고객의 초점을 확대 또는 강화할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다.
seo-description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 요구나 목표를 기반으로 특정 대상에 대한 고객의 초점을 확대 또는 강화할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다.
seo-title: 프로필 병합 규칙에 대한 일반 사용 사례
solution: Audience Manager
title: 프로필 병합 규칙에 대한 일반 사용 사례
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 4%

---

# 프로필 병합 규칙에 대한 일반 사용 사례 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 옵션을 사용하면 비즈니스 요구 사항이나 목표에 따라 특정 대상에 대한 고객의 초점을 확대 또는 축소할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다. [!UICONTROL Profile Merge Rules] 실시간 및 배치 대상을 사용한 작업

>[!TIP]
>
>이러한 [!UICONTROL Merge Rule] 설정에 대한 정의 및 설명은 [프로필 병합 규칙 옵션 정의](merge-rule-definitions.md)를 참조하십시오.

## 장치 타게팅 {#device-personalization}

이 시나리오는 사용자 인증을 고려하지 않고 장치 ID를 지원하는 대상 플랫폼(DSP, 온사이트 개인화 플랫폼 및 기타 장치 기반 타깃팅 플랫폼)을 사용하여 장치에 일관된 경험을 제공하기 위해 Audience Manager에 정의된 대상 세그먼트에 대해 단일 장치 프로파일을 평가하려는 마케터에게 적용됩니다.

장치 프로파일만을 대상으로 하는 규칙을 만들려면 **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**&#x200B;을 선택합니다.

![장치 전용](assets/device-only.png)

John이 세 대의 스마트폰을 소유하고 있다고 가정합시다. 이 중 2개는 데이터 플랜 A에 관한 아이폰 7s이고, 그 중 하나는 데이터 계획 B에 관한 삼성입니다. 이 세 장치 중 그의 인증 상태를 고려하지 않고, 존의 모바일 회사는 데이터 계획 A에서 실행되는 iPhone 7 장치만 데이터 플랜 업그레이드를 그에게 제공하고 싶어합니다.

**[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** 규칙, [!DNL Device 1] 및 [!DNL Device 3]을(를) 모두 사용하여 세그먼트 자격이 적절하고 장치 2는 무시됩니다.

![장치 전용](assets/device-management.png)

## 공유 장치 타게팅 {#target-shared-devices}

존과 그의 아내 제인이 같은 노트북을 사용하여 온라인 상점에 가서 다양한 물건을 주문한다고 하자.

존은 여행 티켓과 특별 할인을 예약하기 위해 자신의 계좌를 사용하지만, 제인은 음악과 영화를 사기 위해 자신의 계정을 사용한다.

스토어의 마케팅 팀은 **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** 규칙을 사용하여 순전히 인증된 활동에 따라 특정 거래를 John과 Jane에 타깃팅할 수 있습니다.

![현재 장치 없음](assets/current-no-device.png)

이 규칙을 사용하면 Audience Manager은 장치 프로파일, 세그먼트에 대한 John의 CRM ID를 확인하지만 Jane의 CRM ID를 검증하지 않은 채 완전히 무시됩니다.

![shared-device-targeting](assets/shared-device-targeting.png)

## 온라인/오프라인 타깃팅 {#device-household-targeting}

이 사용 사례는 가계 ID 관리에 적용됩니다. 회사는 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** 규칙을 사용하여 해당 장치에서 인증한 마지막 프로필과 단일 장치 프로파일을 병합할 수 있습니다.

![last-device-profile](assets/last-device-profile.png)

$100.000/년 이상의 소득을 가진 가정으로 구성된 세그먼트가 [!DNL Data Plan B]에 [!DNL iPhone 7]이(가) 있는 하나 이상의 장치를 포함하고 있다고 가정합니다. 2개의 가계부 프로파일(크로스 디바이스 프로파일)이 있으며, 각각 서로 다른 2개의 디바이스 프로파일에 연결됩니다. 세그먼트의 자격에 필요한 트레이트는 장치 및 장치 간 프로파일에 배포됩니다.

Audience Manager은 모든 장치 + 장치 간 프로파일 쌍을 병합하여 병합된 트레이트 세트가 세그먼트에 적합한지를 확인합니다. Audience Manager은 병합에 포함된 모든 프로파일을 평가하므로 장치 프로파일과 가구 프로파일 모두 세그먼트화할 수 있습니다.

장치와 일반 프로파일 간의 링크를 통해 Audience Manager은 [!DNL Household 2]을(를) 세그먼트로 사용할 수 있지만 [!DNL Household 1]은(는) 사용할 수 없습니다. [!DNL Household 2]에서 [!DNL Device 3]만 세그먼트에 자격이 있습니다. 이 [!UICONTROL Profile Merge Rule]은(는) 마케터가 개별 장치([!DNL Device 3]) 및 더 넓은 가구([!DNL Household 2])에 일관된 마케팅 메시지를 전달할 수 있도록 했습니다.

![가계 관리](assets/household-management.png)

## 사람 기반 대상에 대한 타깃팅 {#all-cross-device}

>[!IMPORTANT]
>
>이 문서에는 이 기능의 설정 및 사용을 안내하기 위한 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 충고이다. 법률 자문을 위해 법률 자문을 구할 수 있는 법률 자문을 구할 수 있다.

이 타깃팅 시나리오는 [!DNL People-Based Destinations] Add-on을 구입한 고객만 사용할 수 있습니다. 이 규칙을 통해 마케터는 인증 데이터를 기반으로 고객에게 도달할 수 있습니다.

온라인 소매업체는 소셜 플랫폼을 통해 기존 고객에게 접근하고 이전 주문에 따라 개인화된 제안을 제공하고자 한다고 가정합니다. [!UICONTROL People-Based Destinations]을 사용하면 자신의 [!DNL CRM]에서 해시된 이메일 주소를 Audience Manager으로 인제스트하고, 오프라인 데이터에서 세그먼트를 작성하고, 해시된 식별자를 사용하여 광고 지출을 최적화하는 등 보급하려는 소셜 플랫폼에 이러한 세그먼트를 보낼 수 있습니다.

이 옵션에 대한 자세한 내용은 [사용자 기반 대상](../destinations/people-based-destinations-overview.md)을 참조하십시오.

![전체 장치](assets/all-cross-device.png)

## 장치 그래프 옵션 {#device-graph-options}

[!UICONTROL Profile Merge] 규칙에 대해 [!UICONTROL device graph] 옵션을 선택하는 것은 디지털 속성 및 비즈니스 목표에 고유한 조건에 따라 달라집니다. 이러한 일반 지침은 그래프 유형을 사용하는 시기와 사용하는 시기를 이해하는 데 도움이 됩니다. 이러한 옵션을 사용하려면 [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/ko-KR/device-co-op/using/home.html)의 구성원이거나 외부 장치 그래프와 계약 관계를 가져야 합니다. 장치 그래프 옵션 선택 시기에 대한 일반적인 지침은 아래 표를 참조하십시오. 특정 사용 사례에 대해서는 [프로필 링크 장치 그래프 사용 사례](profile-link-use-case.md) 및 [외부 장치 그래프 사용 사례](external-graph-use-cases.md)를 참조하십시오.

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
   <td colname="col2"> <p><span class="wintitle"> 프로필 </span> 링크 옵션을 사용하여 만든 프로필  <span class="wintitle"> 지표</span> 는 다음 경우에 적합합니다. </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">높은 수준의 고객 인증을 제공하는 디지털 속성 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">집중적인 낮은 도달 캠페인 <span class="wintitle"> 프로필 링크</span> 장치 그래프는 결정적 데이터만을 기반으로 합니다. 이 장치 프로파일 풀은 항상 인증되지 않은 사용자 및 장치 풀을 기준으로 더 작아집니다. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">고객이 세그멘테이션을 적용받기 위해 인증된 상태에 있어야 하는 경우. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>외부 장치 그래프 옵션 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 프로파일 </span> 병합은  <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud 장치 </a> 조합 또는 Audience Manager와 통합된 외부 장치 그래프로  <span class="keyword"> 만들어지며, 다음</span> 과 같은 작업을 수행하는 데적합합니다. </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">낮은 수준의 고객 인증을 제공하는 디지털 속성입니다. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">광범위한 도달 브랜드 캠페인 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">고객이 세그멘테이션을 적용받기 위해 인증된 상태에 있을 필요가 없는 경우. </li> 
     </ul> </p> <p> <p>팁:<span class="keyword"> 장치 Co-op</span>은(는) 인증이 적고 장치 그래프 공급자와 관계가 없는 <span class="keyword"> Experience Cloud</span> 고객인 경우에 가장 좋은 옵션입니다. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Profile Merge Rules]에 대한 가능한 사용 사례에 대한 개요는 아래 비디오를 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [프로필 링크 장치 그래프 사용 사례](profile-link-use-case.md)
>* [외부 장치 그래프 사용 사례](external-graph-use-cases.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

