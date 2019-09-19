---
description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 요구 사항이나 목표에 따라 특정 대상에 대한 고객 초점을 확장하거나 강화할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다. 현재 프로필 병합 규칙은 실시간 대상에서만 작동합니다.
seo-description: 프로필 병합 규칙 옵션을 사용하면 비즈니스 요구 사항이나 목표에 따라 특정 대상에 대한 고객 초점을 확장하거나 강화할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다. 현재 프로필 병합 규칙은 실시간 대상에서만 작동합니다.
seo-title: 프로필 병합 규칙에 대한 일반 사용 사례
solution: Audience Manager
title: 프로필 병합 규칙에 대한 일반 사용 사례
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 프로필 병합 규칙에 대한 일반 사용 사례 {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] 옵션을 사용하면 비즈니스 요구 사항이나 목표를 기반으로 특정 고객에 초점을 맞추거나 확대할 수 있습니다. 이러한 일반적인 사용 사례에서는 사용 가능한 옵션을 사용하고 개별, 가정 및 크로스 디바이스 타깃팅을 위한 병합 규칙을 만드는 방법을 살펴봅니다. 현재 [!UICONTROL Profile Merge Rules] 실시간 대상만 사용하여 작업할 수 있습니다.

![](assets/merge-rules-options.png)

>[!TIP]
>
>이러한 설정에 대한 정의 및 설명은 [!UICONTROL Merge Rule] 프로필 [병합 규칙 옵션 정의를 참조하십시오](../../features/profile-merge-rules/merge-rule-definitions.md).

## 집중 타깃팅 {#focused-targeting}

웹 사이트에 대한 사용자 인증은 선언된 ID 호출을 트리거해야 [!DNL Audience Manager]합니다. 이 이벤트 후에는 트레이트 데이터를 인증된 프로필에 (및 읽기) 기록합니다. [!DNL Audience Manager] 인증된 프로필에서는 다음을 수행할 수 [!DNL Audience Manager]있습니다.

* 특정 사용자에 대한 인증된 프로필에 트레이트를 작성합니다.
* 세분화를 위해 여러 장치 사용자를 식별하고 차별화합니다.

### 인증된 사용자에게 전달

인증된 프로필 옵션은 오프라인 속성을 기반으로 웹 사이트 또는 앱에 로그인한 사용자를 타깃팅할 수 있는 규칙을 만듭니다. 예를 들어 금융 서비스 업체는 이 옵션을 사용하여 소득 또는 오프라인 활동을 기반으로 하는 특정 서비스 또는 대상 신용 카드 업그레이드 오퍼를 통해 인증된 사용자를 타깃팅합니다. 또 다른 예는 누적된 마일리지 기반 거래를 통해 인증된 단골 고객을 대상으로 하는 항공사입니다.

인증된 사용자에게만 도달하는 규칙을 만들려면 **[!UICONTROL Current Authenticated Profile]** +를 **[!UICONTROL No Device Profile]**&#x200B;선택합니다. 이 옵션은 인증된 프로필 데이터만 사용하여 세그먼트를 평가합니다. 이 규칙은 익명 장치 프로필의 데이터를 무시합니다.

익명 장치 프로필에 데이터를 포함하려면 **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL Current Device Profile]** 규칙을 사용하십시오.

### 이전 인증 상태를 기반으로 사용자에게 전달

이러한 옵션은 검색 중이지만 로그온하지 않은 특정 사용자에게 적용됩니다. 유추된 사용자 수준 타깃팅을 사용하는 옵션을 사용하여 이렇게 할 수 있습니다. 유추된 타깃팅을 사용하면 사이트에 대해 명시적으로 인증되지 않았지만 온라인에서 검색할 수 있는 사람에게 도달할 수 있습니다. 마지막으로 인증된 프로필의 데이터를 읽고 쓰지는 않습니다. 또한 인증된 프로필을 깔끔하게 유지하기 위해 인증된 프로필 대신 장치 프로필에 새로운 트레이트 자격 조건을 [!DNL Audience Manager] 기록합니다. 예를 들어, 사이트나 앱에 로그인하지 않은 기존 고객과 서로 다른 오퍼를 테스트하려는 마케터가 있다고 가정합니다. 마케터는 이러한 광고를 인증되지 않은 현 고객과 테스트하여 가장 많은 응답을 얻을 수 있는 제안을 확인할 수 있습니다.

이전 인증을 기반으로 사용자에게 도달하는 규칙의 예는 다음과 같습니다.

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## 확장된 타깃팅 {#expanded-targeting}

특정 고객에게 도달하는 데 도움이 되는 규칙과 함께 마케터에게는 타깃팅에 사용할 수 있는 데이터 세트의 크기를 늘리는 규칙이 필요합니다. [!UICONTROL Profile Merge Rules] 장치 프로파일 옵션을 사용하여 이 작업을 수행할 수 있습니다. 장치 옵션은 사용자가 하나 또는 여러 장치에서 익명 상태에 있을 때 발생한 트레이트에 따라 그리므로 세그멘테이션에 적합한 데이터 세트를 확장합니다. 이 기능은 개인 장치 그래프를 사용하거나 가정에서 가정 장치 그래프를 사용하는 모든 장치를 사용하여 모든 장치에서 사용자에게 연결하려고 할 때 유용할 수 있습니다. 이 옵션의 사용 사례에는 가족 휴가 상품에 대한 광고가 포함될 수 있습니다. 이 경우, 모든 장치의 사용자가 오퍼에 관심을 보이는 경우 이 혜택을 통해 가정의 모든 디바이스에 도달해야 합니다.

타깃팅 데이터 세트를 확장하는 규칙을 만들려면 **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Graph]** 규칙을 선택합니다.

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

## 장치 그래프 옵션 {#device-graph-options}

규칙에 대한 [!UICONTROL device graph] [!UICONTROL Profile Merge] 옵션을 선택하는 것은 디지털 속성 및 비즈니스 목표에 고유한 조건에 따라 달라집니다. 이러한 일반 지침은 그래프 유형을 사용하는 시기와 사용하는 시기를 이해하는 데 도움이 됩니다. 이러한 옵션을 사용하려면 외부 장치 그래프의 멤버이거나 계약상 [!DNL Adobe Experience Cloud Device Co-op] 관계가 있어야 합니다. 장치 그래프 옵션 선택 시기에 대한 일반적인 지침은 아래 표를 참조하십시오. 특정 사용 사례는 프로필 링크 [장치 그래프 사용 사례](../../features/profile-merge-rules/profile-link-use-case.md) 및 [외부 장치 그래프 사용 사례를 참조하십시오](../../features/profile-merge-rules/external-graph-use-cases.md).

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

>[!MORELIKE_THIS]
>
>* [프로필 링크 장치 그래프 사용 사례](../../features/profile-merge-rules/profile-link-use-case.md)
>* [외부 장치 그래프 사용 사례](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [프로필 병합 규칙 FAQ](../../faq/faq-profile-merge.md)

