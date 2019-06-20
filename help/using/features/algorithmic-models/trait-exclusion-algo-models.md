---
description: 특성 제외는 모델링 워크플로우에서 추가적인 컨트롤을 제공하므로 도메인 전문 지식 및 규정 요구 사항을 기반으로 필요한 가드 레일을 모델에 추가할 수 있습니다. 하나 이상의 데이터 소스에서 모델을 만들 때 무시할 트레이트를 선택하려면 제외 옵션을 사용합니다.
seo-description: 특성 제외는 모델링 워크플로우에서 추가적인 컨트롤을 제공하므로 도메인 전문 지식 및 규정 요구 사항을 기반으로 필요한 가드 레일을 모델에 추가할 수 있습니다. 하나 이상의 데이터 소스에서 모델을 만들 때 무시할 트레이트를 선택하려면 제외 옵션을 사용합니다.
seo-title: 알고리즘 모델의 특성 제외
title: 알고리즘 모델의 특성 제외
uuid: 1359800 B -6 E 6 C -41 E 1-88 B 4-23 D 31952 ABB 3
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Algorithmic Models: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 모델링 워크플로우에 추가 컨트롤을 제공하므로 도메인 전문 지식 및 규정 요구 사항에 따라 필요한 가드 레일을 모델에 추가할 수 있습니다. [!UICONTROL Exclusions] 하나 이상의 데이터 소스에서 모델을 만들 때 무시할 트레이트를 선택하려면 옵션을 사용합니다.

## 사용 사례 {#use-cases}

Here are some use cases you can address with [!UICONTROL Trait Exclusion]:

* [!UICONTROL Trait Exclusion] 사이트 방문자 트레이트와 같은 특정 캐치 (catch-all) 트레이트를 제외시킬 수 있으므로 모델을 편바이어하지 않고 평평한 결과를 얻을 수 있습니다.
* 잘 모르는 트레이트를 제거하여 영향력이 있는 트레이트를 더 잘 이해할 수 있습니다.
* 인구 통계학적 트레이트와 같은 특정 트레이트를 제외하여 모든 규정 준수 의무에 도움을 줄 수 있습니다.

>[!IMPORTANT]
>
>세 번째 사용 사례에 대한 중요 정보입니다. If the third-party data provider adds a new demographic trait to the data feed *after you created the model*, the trait is automatically picked up by the model. 모델을 만든 후 모델링을 모델링에서 제외할 수 없습니다. [중요한 측면 및 제한](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)사항을 참조하십시오. 이 기능을 사용할 때에는 주의해서 데이터 공급자를 사용하여 피드 구조의 변경 사항을 알려야 합니다.

![](assets/lam_exclude_traits.png)

## How to Use Trait Exclusions {#how-to-use}

Use the [Build a model](../../features/algorithmic-models/create-model.md#build-model) workflow to build new algorithmic models.

1. The [!UICONTROL Exclusions] selection is greyed out until you select one or more data sources for modeling.
2. After selecting one or more data sources for modeling, press **[!UICONTROL Browse All Traits]**.
3. **[!UICONTROL Select Traits to Exclude]** 창에서 이전에 선택한 데이터 소스와 관련된 모든 트레이트를 볼 수 있습니다. 제외할 트레이트를 선택합니다.
4. 트레이트 유형별로 트레이트를 필터링하거나 트레이트 폴더를 검색할 수 있습니다. 특성 폴더에는 선택한 데이터 소스와 관련된 특성만 표시됩니다.
5. **[!UICONTROL Exclude Selected Traits]** 을 누릅니다.

>[!TIP]
>
>폴더에서 트레이트를 하나씩 제외하고 폴더 트레이트를 제외하여 전체 폴더를 제외할 수 있습니다. 예를 들어, 20 개의 트레이트가 있는 폴더에서 모든 트레이트를 하나씩 제외하는 대신 폴더 트레이트를 제외하기만 하면 됩니다.

비디오 자습서를 선호하는 경우 트레이트 제외를 위한 비디오 데모를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12&captions=kor)

## Important Aspects &amp; Limitations {#important-aspects-and-limitations}

Please take note of the following aspects and limitations related to [!UICONTROL Trait Exclusion]:

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 항목 </th> 
   <th colname="col2" class="entry"> 설명 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>모델 요약 보기에서 제외된 트레이트 </p> </td>
   <td colname="col2"> <p>The excluded traits <i>do not show up</i> in the Models Summary view. You can see the excluded traits only in the <b><span class="uicontrol"> Edit Model</span></b> workflow. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>RBAC (역할 기반 액세스 제어) </p> </td>
   <td colname="col2"> <p>Note the following limitations for companies using <a href="../../features/administration/administration-overview.md#administration"> RBAC</a>: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">If you don't have access to view a trait, you <i>cannot</i> select that trait to be excluded from the model. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">If you don't have access to view a trait, you <i>cannot</i> view that trait in the excluded traits list. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>모델을 저장한 후 제외된 트레이트 수정 </p> </td>
   <td colname="col2"> <p>모델을 만들고 저장한 후에는 제외된 트레이트를 수정할 수 없습니다. 결과를 수정하려는 경우 모델을 복제하고 제외된 트레이트를 변경할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>제외할 수 있는 최대 트레이트 수 </p> </td>
   <td colname="col2"> <p>모델에서 제외할 수 있는 최대 트레이트 수는 500 개입니다. 폴더 트레이트를 사용하여 제외를 최대화합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>기준선 특성 제외 </p> </td>
   <td colname="col2"> <p>The baseline trait is excluded by default, so it does not show up in the <b><span class="uicontrol"> Exclusions</span></b> list, when building the model. </p> </td>
  </tr>
 </tbody>
</table>

## 관련 링크

* [알고리즘 특성 정보](/help/using/features/algorithmic-models/understanding-models.md)
* [특성 제외 - 자습서](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)