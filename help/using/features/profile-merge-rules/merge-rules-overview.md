---
description: 프로필 병합 규칙을 사용하면 세그멘테이션에 사용되는 데이터 세트를 제어할 수 있고 여러 장치에서 사람을 정확하게 타깃팅할 수 있습니다.
seo-description: 프로필 병합 규칙을 사용하면 세그멘테이션에 사용되는 데이터 세트를 제어할 수 있고 여러 장치에서 사람을 정확하게 타깃팅할 수 있습니다.
seo-title: 프로필 병합 규칙 개요
solution: Audience Manager
title: 프로필 병합 규칙 개요
uuid: 9e7988cc-9145-43 파섹
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# 프로필 병합 규칙 개요 {#profile-merge-rules-overview}

세그멘테이션에 사용되는 데이터 세트를 제어할 [!UICONTROL Profile Merge Rules] 수 있고 여러 디바이스에서 인물을 정확하게 타깃팅할 수 있습니다.

## 익명 및 인증된 프로필로 데이터 수집 및 타깃팅 {#data-collection-targeting}

일반적으로 고객 세분화 및 타깃팅은 디바이스의 모든 사용자가 수집한 데이터를 기반으로 합니다. 디바이스 수준 데이터를 기반으로 데이터 수집 및 타깃팅에 몇 가지 단점이 있습니다. 예를 들어 장치를 공유하거나 여러 장치에서 사용자를 정확하게 타게팅하는 여러 사용자를 구별할 수 없습니다. 디바이스 중심의 데이터 수집으로 디지털 마케팅 캠페인이나 크로스 디바이스 타깃팅이 충분하지 않습니다.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] 기본적으로 타깃팅을 위해 데이터 및 세그먼트를 수집하는 방법을 [!DNL Audience Manager] 변경합니다. 이 플러그인을 사용하면 서로 다른 2가지 유형의 프로파일, 장치 프로파일 및 인증된 프로파일을 사용하여 작업할 수 있습니다.

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
   <td colname="col2"> <p>장치 프로파일은 쿠키 ID 또는 모바일 장치 ID와 같은 해당 장치의 ID에 연결되어 있습니다. 이러한 서비스에는 다음이 포함됩니다. </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">사용자가 인증되지 않을 때 발생하는 규칙 기반 트레이트입니다. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">쿠키 기반, 타사 데이터와 같은 장치 ID에 연결된 트레이트입니다. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> 인증된 프로필 </td> 
   <td colname="col2"> <p>인증된 프로필은 사용자가 사이트에 로그인할 때 전달된 사용자 ID에 연결되어 있습니다. 여기에는 다음이 포함됩니다. </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">사용자가 인증될 때 장치 간에 수집된 규칙 기반 트레이트입니다. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">동일한 사용자 ID에 연결된 오프라인 파일에서 온보드 트레이트입니다. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

이러한 다양한 프로필은 세그멘테이션에 사용할 수 있는 데이터를 제어합니다. 예를 들어 인증된 프로파일을 사용하면 한 사람에 대해 여러 장치의 데이터를 기반으로 정확한 세그먼트를 만들 수 있습니다. 즉, 여러 디바이스에서 고객에게 일관된 브랜드 경험을 제공할 수 있습니다. 또한 크로스 디바이스 인증을 통해 사용자가 온라인 활동에 사용하는 서로 다른 플랫폼을 [!DNL Audience Manager] 매핑할 수 있습니다. 이것을 "The"라고 [!UICONTROL Profile Link Device Graph]합니다.

![](assets/authenticated2.png)

## 장점 {#advantages}

다음을 [!UICONTROL Profile Merge Rules] 수행할 수 있습니다.

* 인증된 프로필, 익명 프로파일 또는 두 가지 조합을 기반으로 사용자를 타깃팅합니다.
* 모든 디바이스에서 특정 고객을 타깃팅합니다.
* 결정 데이터를 기반으로 디바이스 그래프를 만듭니다.
* 다양한 프로파일을 기반으로 세그먼트의 데이터를 세밀하게 조정할 수 있습니다.
* 고객에 대한 통찰력을 얻을 수 있습니다.

## 시작하기 {#getting-started}

자세한 내용은 다음 섹션 및 [FAQ를](../../faq/faq-profile-merge.md) 참조하십시오 [!UICONTROL Profile Merge Rules].

* [프로필 병합 규칙 시작](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [프로필 병합 규칙 대시보드](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [프로필 병합 규칙 옵션 정의](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [프로필 병합 규칙에 대한 일반 사용 사례](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [프로필 링크 장치 그래프 사용 사례](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [외부 장치 그래프 사용 사례](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [프로필 병합 규칙에 대한 보고서 지표](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [프로필 병합 규칙 및 장치 분리 프로세스](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [즉각적인 장치 간 억제](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [장치 그래프와 프로필 병합 규칙에 대한 중요 고려 사항](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
