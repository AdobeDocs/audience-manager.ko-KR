---
description: 트레이트 제외는 모델링 워크플로우에 추가 제어를 제공하여 도메인 전문 지식 및 규정 요구 사항에 따라 필요한 가드 레일을 모델에 추가할 수 있도록 합니다. 하나 이상의 데이터 소스에서 모델을 만들 때 무시할 트레이트를 선택하려면 제외 옵션을 사용합니다.
seo-description: 트레이트 제외는 모델링 워크플로우에 추가 제어를 제공하여 도메인 전문 지식 및 규정 요구 사항에 따라 필요한 가드 레일을 모델에 추가할 수 있도록 합니다. 하나 이상의 데이터 소스에서 모델을 만들 때 무시할 트레이트를 선택하려면 제외 옵션을 사용합니다.
seo-title: 알고리즘 모델 트레이트 제외
title: 알고리즘 모델 트레이트 제외
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: 알고리즘 모델
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# 유사 모델링: 트레이트 제외 {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] 모델링 워크플로우에서 추가 제어를 제공하여 도메인 전문 지식 및 규제 요구 사항에 따라 필요한 가드 레일을 모델에 추가할 수 있습니다. 하나 이상의 데이터 소스에서 모델을 만들 때 무시할 트레이트를 선택하려면 [!UICONTROL Exclusions] 옵션을 사용합니다.

## 사용 사례 {#use-cases}

다음은 [!UICONTROL Trait Exclusion]으로 해결할 수 있는 몇 가지 사용 사례입니다.

* [!UICONTROL Trait Exclusion] 사이트 방문자 트레이트와 같은 특정 다목적 캐치(catch-all) 트레이트를 제외할 수 있으므로 모델을 치우지 않아 결과가 평탄해집니다.
* 모르거나 데이터 소스에서 신뢰하지 않는 트레이트를 제거하여 영향력 있는 트레이트를 더 잘 이해할 수 있습니다.
* 인구 통계 트레이트와 같은 특정 트레이트를 제외하여 보유하고 있는 모든 준수 의무를 지원할 수 있습니다.

>[!IMPORTANT]
>
>세 번째 사용 사례에 대한 중요한 참고 사항입니다. 모델&#x200B;*을 만든 후 타사 데이터 공급자가 데이터 피드*&#x200B;에 새 인구 통계 트레이트를 추가하면 해당 트레이트가 모델에 의해 자동으로 선택됩니다. 모델을 만든 후에는 모델링에서 트레이트를 제외할 수 없습니다. [중요한 측면 및 제한 사항](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations)을 참조하십시오. 이 기능을 사용할 때에는 주의하고 데이터 공급자와 협력하여 피드 구조의 변경 사항에 대해 알려 주십시오.

![](assets/lam_exclude_traits.png)

## 트레이트 제외 사용 방법 {#how-to-use}

[모델](../../features/algorithmic-models/create-model.md#build-model) 워크플로우를 사용하여 새로운 알고리즘 모델을 구축합니다.

1. 모델링할 데이터 소스를 하나 이상 선택할 때까지 [!UICONTROL Exclusions] 선택이 회색으로 표시됩니다.
2. 모델링할 데이터 소스를 하나 이상 선택한 후 **[!UICONTROL Browse All Traits]** 키를 누릅니다.
3. **[!UICONTROL Select Traits to Exclude]** 창에서 이전에 선택한 데이터 소스와 연결된 모든 트레이트를 볼 수 있습니다. 제외할 트레이트를 선택합니다.
4. 트레이트 유형, 트레이트 인구 유형([장치 ID](../../reference/ids-in-aam.md) 및 [교차 장치 ID](../../reference/ids-in-aam.md))별로 트레이트를 필터링하거나 트레이트 폴더를 찾을 수 있습니다. 트레이트 폴더에는 선택한 데이터 소스와 연결된 트레이트만 표시됩니다.
5. **[!UICONTROL Exclude Selected Traits]** 키를 누릅니다.

![트레이트 제외](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>폴더의 트레이트를 하나씩 제외하는 대신 폴더 트레이트를 제외하여 전체 폴더를 제외할 수 있습니다. 예를 들어 20개의 트레이트가 있는 폴더에서 모든 트레이트를 하나씩 제외하는 대신 폴더 트레이트만 제외해야 합니다.

비디오 자습서를 선호하는 경우 트레이트 제외에 대한 비디오 데모를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

또한 장치 간 지표가 작동하는 방식을 자세히 살펴보려면 아래 비디오를 보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## 중요한 측면 및 제한 사항 {#important-aspects-and-limitations}

[!UICONTROL Trait Exclusion]과 관련된 다음 측면 및 제한 사항에 유의하십시오.

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
   <td colname="col2"> <p>제외된 트레이트 <i>은 모델 요약 보기에</i>표시되지 않습니다. 제외된 트레이트는 <b><span class="uicontrol"> 모델 편집</span></b> 워크플로우에서만 볼 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>역할 기반 액세스 제어(RBAC) </p> </td>
   <td colname="col2"> <p><a href="../../features/administration/administration-overview.md#administration"> RBAC</a>을 사용하는 회사에 대해서는 다음 제한 사항을 참고하십시오. </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">트레이트를 볼 수 있는 액세스 권한이 없는 경우 <i>이(가) 모델에서 제외할 트레이트를 선택할 수 없습니다.</i> </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">트레이트를 볼 수 있는 액세스 권한이 없는 경우 <i>에서 제외된 트레이트 목록에서 해당 트레이트를 볼 수 없습니다.</i> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>모델을 저장한 후 제외된 트레이트 수정 </p> </td>
   <td colname="col2"> <p>모델을 만들고 저장한 후에는 제외된 트레이트를 수정할 수 없습니다. 결과를 조정하려는 경우 모델을 복제하고 제외된 트레이트를 변경할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>제외할 수 있는 최대 트레이트 수 </p> </td>
   <td colname="col2"> <p>모델에서 제외할 수 있는 최대 트레이트 수는 500개입니다. 폴더 트레이트를 사용하여 제외를 극대화합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>기준 트레이트 제외 </p> </td>
   <td colname="col2"> <p>기준 트레이트는 기본적으로 제외되므로 모델을 작성할 때 <b><span class="uicontrol"> 제외</span></b> 목록에 표시되지 않습니다. </p> </td>
  </tr>
 </tbody>
</table>

[!UICONTROL Look-Alike Model]에서 특정 트레이트를 제외하는 방법과 이유를 알아보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## 관련 링크

* [알고리즘 트레이트 기본 정보](/help/using/features/algorithmic-models/understanding-models.md)
* [트레이트 제외 - 자습서](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
