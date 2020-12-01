---
description: 특성 제외는 모델링 워크플로우에서 추가적인 컨트롤을 제공하므로 도메인 전문 지식 및 규정 요구 사항에 따라 필요한 가드 레일을 모델에 추가할 수 있습니다. 하나 이상의 데이터 소스에서 모델을 생성할 때 무시할 특성을 선택하려면 제외 옵션을 사용합니다.
seo-description: 특성 제외는 모델링 워크플로우에서 추가적인 컨트롤을 제공하므로 도메인 전문 지식 및 규정 요구 사항에 따라 필요한 가드 레일을 모델에 추가할 수 있습니다. 하나 이상의 데이터 소스에서 모델을 생성할 때 무시할 특성을 선택하려면 제외 옵션을 사용합니다.
seo-title: 알고리즘 모델 특성 제외
title: 알고리즘 모델 특성 제외
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 56f3b605b434f18c07d36196fd6ae21743401294
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 1%

---


# 유사 모델링: 트레이트 제외 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 모델링 워크플로우에서 추가적인 컨트롤을 제공하므로 도메인 전문 지식 및 규정 요구 사항에 따라 필요한 가드 레일을 모델에 추가할 수 있습니다. 하나 이상의 데이터 소스에서 모델을 만들 때 무시할 특성을 선택하려면 [!UICONTROL Exclusions] 옵션을 사용합니다.

## 사용 사례 {#use-cases}

다음은 [!UICONTROL Trait Exclusion]으로 처리할 수 있는 사용 사례입니다.

* [!UICONTROL Trait Exclusion] 에서는 사이트 방문자 트레이트와 같은 특정 catch-all 특성을 제외할 수 있으므로 모델을 편향하지 않고 평탄한 결과를 얻을 수 있습니다.
* 데이터 소스에서 신뢰하지 않거나 알지 못하는 트레이트를 제거하여 영향력 있는 특성을 더 잘 이해할 수 있습니다.
* 인구 통계 특성과 같은 특정 특성을 제외하여 준수 의무를 해결할 수 있습니다.

>[!IMPORTANT]
>
>세 번째 사용 사례에 대한 중요 참고 사항입니다. 타사 데이터 공급자가 모델&#x200B;*을(를) 만든 후 데이터 피드*&#x200B;에 새 인구 통계 트레이트를 추가하면 모델이 트레이트를 자동으로 선택합니다. 모델을 만든 후에는 모델링에서 트레이트를 제외할 수 없습니다. [중요한 측면 및 제한 사항](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)을 참조하십시오. 이 기능을 사용할 때는 주의하고 데이터 제공자와 함께 작업하여 피드 구조의 변경 사항을 알 수 있도록 하십시오.

![](assets/lam_exclude_traits.png)

## 특성 제외 사용 방법 {#how-to-use}

[모델](../../features/algorithmic-models/create-model.md#build-model) 작업 과정을 작성하여 새로운 알고리즘 모델을 작성합니다.

1. 모델링할 데이터 소스를 하나 이상 선택할 때까지 [!UICONTROL Exclusions] 선택 사항이 회색으로 표시됩니다.
2. 모델링할 데이터 소스를 하나 이상 선택한 후 **[!UICONTROL Browse All Traits]**&#x200B;을 누릅니다.
3. **[!UICONTROL Select Traits to Exclude]** 창에서 이전에 선택한 데이터 소스와 연관된 모든 트레이트를 볼 수 있습니다. 제외할 트레이트를 선택합니다.
4. 특성 유형, 특성 인구 유형([장치 ID](../../reference/ids-in-aam.md) 및 [장치 간 ID](../../reference/ids-in-aam.md))별로 트레이트를 필터링하거나 트레이트 폴더를 찾아볼 수 있습니다. 특성 폴더에는 선택한 데이터 소스와 연관된 특성만 표시됩니다.
5. **[!UICONTROL Exclude Selected Traits]**&#x200B;을 누릅니다.

![특성 제외](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>폴더에서 트레이트를 하나씩 제외하는 대신 폴더 트레이트를 제외하여 전체 폴더를 제외할 수 있습니다. 예를 들어 20개의 트레이트가 있는 폴더에서 모든 트레이트를 하나씩 제외하는 대신 폴더 트레이트만 제외해야 합니다.

비디오 자습서를 선호하는 경우 트레이트 제외에 대한 비디오 데모를 확인하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

또한 디바이스 간 지표가 작동하는 방식을 자세히 살펴보려면 아래 비디오를 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## 중요 측면 및 제한 사항 {#important-aspects-and-limitations}

[!UICONTROL Trait Exclusion]과(와) 관련된 다음 측면과 제한 사항을 참고하십시오.

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
   <td colname="col2"> <p>제외된 특성 <i>은 모델 요약 보기에</i>이 표시되지 않습니다. 제외된 트레이트는 <b><span class="uicontrol"> 모델 편집</span></b> 워크플로우에서만 볼 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>RBAC(역할 기반 액세스 제어) </p> </td>
   <td colname="col2"> <p><a href="../../features/administration/administration-overview.md#administration"> RBAC</a>을(를) 사용하는 회사에 대한 다음 제한 사항을 참고하십시오. </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">트레이트를 볼 수 있는 액세스 권한이 없으면 <i>이(가) 모델에서 제외할 트레이트를 선택할 수 없습니다.</i> </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">트레이트를 볼 수 있는 액세스 권한이 없으면 <i>에서 제외된 트레이트 목록에 해당 트레이트를 볼 수 없습니다.</i> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>모델을 저장한 후 제외된 트레이트 수정 </p> </td>
   <td colname="col2"> <p>모델을 만들고 저장한 후에는 제외된 특성을 수정할 수 없습니다. 결과를 수정하려는 경우 모델을 복제하고 제외된 특성을 변경할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>제외할 수 있는 최대 트레이트 수 </p> </td>
   <td colname="col2"> <p>모델에서 제외할 수 있는 최대 트레이트 수는 500개입니다. 폴더 트레이트를 사용하여 제외를 최대화할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>기준 특성 제외 </p> </td>
   <td colname="col2"> <p>기준 특성은 기본적으로 제외되므로 모델을 작성할 때 <b><span class="uicontrol"> 제외</span></b> 목록에 표시되지 않습니다. </p> </td>
  </tr>
 </tbody>
</table>

아래 비디오를 시청하여 [!UICONTROL Look-Alike Model]에서 특정 트레이트를 제외하는 방법과 이유를 알아보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 관련 링크

* [알고리즘 특성 정보](/help/using/features/algorithmic-models/understanding-models.md)
* [특성 제외 - 자습서](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)