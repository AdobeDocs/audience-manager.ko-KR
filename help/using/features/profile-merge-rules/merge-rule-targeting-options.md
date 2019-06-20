---
description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 필요나 목표를 기반으로 특정 대상에 대한 대상자의 범위를 확장하거나 강화할 수 있습니다. 이러한 일반 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가계 및 장치 간 타깃팅을 위한 병합 규칙을 만드는 방법을 알아봅니다. 현재 프로필 병합 규칙은 실시간 대상에서만 작동합니다.
seo-description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 필요나 목표를 기반으로 특정 대상에 대한 대상자의 범위를 확장하거나 강화할 수 있습니다. 이러한 일반 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가계 및 장치 간 타깃팅을 위한 병합 규칙을 만드는 방법을 알아봅니다. 현재 프로필 병합 규칙은 실시간 대상에서만 작동합니다.
seo-title: 프로필 병합 규칙에 대한 일반적인 사용 사례
solution: Audience Manager
title: 프로필 병합 규칙에 대한 일반적인 사용 사례
uuid: c 9 eb 41 c 8-fe 19-45 f 8-9 ff 1-552 c 11 ef 08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# General Use Cases for Profile Merge Rules {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 옵션을 사용하면 비즈니스 요구나 목표를 기반으로 특정 고객에 대한 대상자의 범위를 확장하거나 강화할 수 있습니다. 이러한 일반 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가계 및 장치 간 타깃팅을 위한 병합 규칙을 만드는 방법을 알아봅니다. Currently, [!UICONTROL Profile Merge Rules] work with real-time destinations only.

![](assets/merge-rules-options.png)

>[!TIP]
>
>[!UICONTROL Merge Rule] 이러한 설정에 대한 정의 및 설명은 [정의된 프로필 병합 규칙 옵션을 참조하십시오](../../features/profile-merge-rules/merge-rule-definitions.md).

## Focused targeting {#focused-targeting}

User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. After this event, [!DNL Audience Manager] writes trait data to (and reads from) an authenticated profile. The authenticated profile lets [!DNL Audience Manager]:

* 특정 사용자에 맞는 인증된 프로파일에 트레이트를 작성할 수 있습니다.
* 세분화를 위해 여러 장치 사용자를 식별하고 구별할 수 있습니다.

### 인증된 사용자 도달

인증된 프로필 옵션은 오프라인 속성을 기반으로 웹 사이트 또는 앱에 로그인한 사용자를 타게팅할 수 있는 규칙을 만듭니다. 예를 들어 금융 서비스 회사는 이 옵션을 사용하여 인증된 사용자를 대상으로 하는 신용 카드 업그레이드 제안 또는 소득 또는 오프라인 활동에 따른 전문 서비스 오퍼로 타깃팅합니다. 또 다른 예로 항공사가 인증된 주행거리를 기반으로 하는 거래를 인증한 항공사가 있습니다.

To create a rule that reaches only authenticated users, select **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. 이 옵션은 인증된 프로필 데이터만 사용하여 세그먼트를 평가합니다. 이 규칙은 익명의 장치 프로필에서 데이터를 무시합니다.

To also include data in the anonymous device profile, use the **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** rule.

### 이전 인증 상태에 따라 사용자에게 도달

이러한 옵션은 탐색 중일 때 로그인하지 않은 특정 사용자에게 도달합니다. 추상적인 사용자 수준 타깃팅을 사용하는 옵션을 사용하여 이 작업을 수행할 수 있습니다. 추상적인 타깃팅을 통해 사이트에 명시적으로 인증되지 않았지만 온라인으로 검색할 수 있는 사람에게 도달할 수 있습니다. 마지막으로 인증된 프로필에서 데이터를 읽고 쓸 수 있습니다. And, to help keep the authenticated profile clean, [!DNL Audience Manager] writes new trait qualifications to the device profile instead of the authenticated profile. 예를 들어, 사이트 또는 앱에 로그인하지 않은 기존 고객과 다른 오퍼를 테스트하려는 마케터라고 가정해 봅시다. 마케터는 인증되지 않은 현재 고객에게 이러한 광고를 테스트하여 가장 반응이 높은 오퍼를 확인할 수 있습니다.

사전 인증에 기반한 사용자에게 도달하는 규칙의 예는 다음과 같습니다.

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Expanded targeting {#expanded-targeting}

특정 고객에게 도달하는 데 도움이 되는 규칙과 함께 마케터는 타깃팅에 사용할 수 있는 데이터 세트 크기를 늘리는 규칙을 필요로 합니다. [!UICONTROL Profile Merge Rules] 장치 프로파일 옵션을 사용하여 이 작업을 수행할 수 있습니다. 장치 옵션은 사용자가 하나 이상의 장치에서 익명 상태에 있는 동안 구현된 특성을 그리므로 세그멘테이션에 사용할 수 있는 데이터 세트를 확장합니다. 이 기능은 가족 장치 그래프를 사용하여 모든 장치에서 사용자 장치 그래프나 가정에서의 모든 장치를 사용하여 사용자에게 도달하려고 할 때 유용합니다. 이 옵션에 대한 사용 사례에는 가족 휴가 제안이 포함될 수 있습니다. 이 경우 모든 장치의 사용자가 오퍼에 관심을 보이는 경우 오퍼를 사용하여 가정에서 모든 디바이스에 도달해야 합니다.

To create a rule that expands the targeting data set, select the **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** rule.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Device Graph Options {#device-graph-options}

Choosing a [!UICONTROL device graph] option for a [!UICONTROL Profile Merge] rule depends on conditions unique to your digital properties and business goals. 이러한 일반 지침은 한 유형의 그래프와 다른 유형의 그래프를 언제 사용해야 하는지를 이해하는 데 도움이 됩니다. Note, you must be a member of the [!DNL Adobe Experience Cloud Device Co-op] or have a contractual relationship with an external device graph to use these options. 장치 그래프 옵션을 선택하는 방법에 대한 일반적인 지침은 아래 표를 참조하십시오. For specific use cases, see [Profile Link Device Graph Use Cases](../../features/profile-merge-rules/profile-link-use-case.md) and [External Device Graph Use Cases](../../features/profile-merge-rules/external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 장치 그래프 유형 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 프로필 링크</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 프로필 링크 옵션으로 구축된 프로필 병합</span> <span class="wintitle"> 규칙은 다음과 같은</span> 경우에 이상적입니다. </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">고객 인증을 수준이 높은 디지털 속성 </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">집중적인 집중 캠페인 <span class="wintitle"> 프로필 링크</span> 장치 그래프는 Determinalist 데이터만 기반으로 구축됩니다. 이 장치 프로파일 풀은 인증되지 않은 사용자 및 장치 풀에 항상 상대적으로 작습니다. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">세그멘테이션을 받으려면 고객이 인증된 상태에 있어야 합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>외부 장치 그래프 옵션 </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Experience Cloud Device Co-op를 사용하여 구축된 프로파일 병합</span> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> 규칙</a> 또는 <span class="keyword"> Audience Manager</span> 와 통합된 모든 외부 디바이스 그래프는 다음 사용자에게 이상적입니다. </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">낮은 수준의 고객 인증을 제공하는 디지털 속성 </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">광범위하고 광범위한 브랜드 캠페인 </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">세분화를 위해 고객이 인증된 상태를 유지할 필요는 없는 경우입니다. </li> 
     </ul> </p> <p> <p>Tip: The <span class="keyword"> Device Co-op</span> is your best option if you're a <span class="keyword"> Experience Cloud</span> customer with low authentication and no relationship with any device graph provider. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [프로필 링크 장치 그래프 사용 사례](../../features/profile-merge-rules/profile-link-use-case.md)
>* [외부 장치 그래프 사용 사례](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

