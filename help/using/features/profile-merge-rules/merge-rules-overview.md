---
description: 프로필 병합 규칙을 사용하면 세그멘테이션에 사용된 데이터 세트를 제어할 수 있고, 여러 장치에서 사용자를 정확하게 타깃팅할 수 있습니다.
seo-description: 프로필 병합 규칙을 사용하면 세그멘테이션에 사용된 데이터 세트를 제어할 수 있고, 여러 장치에서 사용자를 정확하게 타깃팅할 수 있습니다.
seo-title: 프로필 병합 규칙 개요
solution: Audience Manager
title: 프로필 병합 규칙 개요
uuid: 9 E 7988 CC -9145-432 B -840 A -54 FBD 8657 B 3 B
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you get control over the data sets used for segmentation and can target a person accurately across multiple devices.

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

일반적으로 대상 세그멘테이션 및 타깃팅은 디바이스의 모든 사용자로부터 수집한 데이터를 사용합니다. 장치 수준 데이터를 기반으로 데이터 수집 및 타깃팅은 몇 가지 단점이 있습니다. 예를 들어 장치를 공유하거나 여러 장치에서 사용자를 정확하게 타깃팅하는 여러 사용자를 구별할 수 없습니다. 장치 중심의 데이터 수집은 더 이상 디지털 마케팅 캠페인 또는 크로스 장치 타깃팅에 충분하지 않습니다.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 타깃팅할 데이터 및 세그먼트 [!DNL Audience Manager] 사용자를 수집하는 방법을 기본적으로 변경합니다. 이 플러그인을 사용하면 서로 다른 유형의 프로파일, 디바이스 프로파일 및 인증된 프로파일을 사용할 수 있습니다.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 프로필 유형 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 장치 프로필 </td> 
   <td colname="col2"> <p>장치 프로파일은 쿠키 ID 또는 모바일 장치 ID와 같은 지정된 장치의 ID에 연결되어 있습니다. 이러한 서비스에는 다음이 포함됩니다. </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">규칙 기반의 트레이트는 사용자가 인증되지 않은 경우에 구현됩니다. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">쿠키 기반의 타사 데이터와 같은 장치 ID에 연결된 온보드 트레이트입니다. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 인증된 프로필 </td> 
   <td colname="col2"> <p>인증된 프로필은 사용자가 사이트에 로그인할 때 전달된 사용자 ID에 연결되어 있습니다. 여기에는 </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">사용자가 인증할 때 장치 간에 수집된 규칙 기반 트레이트입니다. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">동일한 사용자 ID에 연결된 오프라인 파일의 온보드 트레이트입니다. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

이러한 프로필은 세그멘테이션에 사용할 수 있는 데이터를 제어합니다. 예를 들어 인증된 프로파일을 사용하면 한 사람에 대해 여러 장치의 데이터를 기반으로 정확한 세그먼트를 작성할 수 있습니다. 즉, 여러 디바이스를 사용하는 고객에게 일관된 브랜드 경험을 제공할 수 있습니다. Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. [!UICONTROL Profile Link Device Graph]이것을 라고도 합니다.

![](assets/authenticated2.png)

## 장점 {#advantages}

With [!UICONTROL Profile Merge Rules] you can:

* 인증된 프로필, 익명 프로파일 또는 둘 다의 조합을 기반으로 사용자를 타깃팅합니다.
* 디바이스에서 특정 고객을 타겟팅할 수 있습니다.
* 결정적인 데이터를 기반으로 장치 그래프를 만듭니다.
* 다양한 프로파일을 기반으로 세그먼트의 데이터를 세부적으로 조정할 수 있습니다.
* 고객에 대한 추가 인사이트 확보

## 시작하기 {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [프로필 병합 규칙 시작하기](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [프로필 병합 규칙 대시보드](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [정의된 프로필 병합 규칙 옵션](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [프로필 병합 규칙에 대한 일반적인 사용 사례](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [프로필 링크 장치 그래프 사용 사례](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [외부 장치 그래프 사용 사례](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [프로필 병합 규칙에 대한 보고서 지표](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [프로필 병합 규칙 및 장치 해제 프로세스](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [즉각적인 장치 간 억제](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [장치 그래프가 있는 프로필 병합 규칙에 대한 중요한 고려 사항](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
