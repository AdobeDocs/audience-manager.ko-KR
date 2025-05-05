---
description: Model Builder에서 알고리즘 모델을 만들 수 있는 필수 단계 및 선택적 단계에 대해 설명합니다.
keywords: 알고리즘 작동 방식
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: 알고리즘 모델 만들기
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# 유사 모델 만들기 {#create-an-algorithmic-model}

[!UICONTROL Look-Alike Model]을(를) 만들 수 있는 필수 단계 및 선택적 단계를 설명합니다.

## 모델 빌더 섹션

[!UICONTROL Model Builder]은(는) [!UICONTROL Basic Information] 및 [!UICONTROL Configuration] 섹션으로 구성되어 있습니다. 모델을 생성하려면 이 두 섹션의 필수 필드를 작성합니다. 모델을 저장하여 알고리즘을 시작합니다. [!DNL Audience Manager]에서 첫 번째 데이터 실행이 완료된 후 자동 알림을 보냅니다. 전자 메일을 받은 후 [특성 빌더](../../features/traits/about-trait-builder.md)(으)로 이동하여 알고리즘 특성을 만들 수 있습니다.

>[!NOTE]
>
>* 모델을 만들고 이 모델을 사용하여 트레이트를 작성하지 않는 경우 모델링 프로세스는 한 번만 실행됩니다.
>* 의미 있는 양의 정보가 포함된 데이터 소스에서 모델을 구축합니다. 데이터가 충분하지 않은 모델은 실행되지만 결과는 반환되지 않습니다.
>* *다른 알고리즘 특성 또는 세그먼트를 사용하여 모델을 만들지 마십시오*.
>* 자동화된 이메일 알림은 첫 번째 데이터 실행 후 한 번만 전송됩니다.

## 모델 구축

[!UICONTROL Look-Alike Model]을(를) 빌드하려면 아래 단계를 따르십시오.

1. **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**(으)로 이동한 다음 [!UICONTROL Look-Alike Modeling] 섹션에서 **[!UICONTROL Add New]**&#x200B;을(를) 클릭합니다.
   ![유사 항목 추가](assets/look-alike-add.png)
1. [기본 정보](../../features/algorithmic-models/create-model.md#basic-information) 섹션에서
   * 모델 이름을 지정합니다.
   * *(선택 사항)* 모델에 대한 간단한 설명을 제공합니다.
   * 모델의 상태를 **[!UICONTROL Active]** 또는 **[!UICONTROL Inactive]**(으)로 설정합니다. 비활성 모델은 실행되지 않으며 데이터를 생성하지 않습니다.

     ![유사 항목-기본](assets/look-alike-basic.png)
1. [구성](../../features/algorithmic-models/create-model.md#configuration) 섹션에서:
   * 모델링할 트레이트 또는 세그먼트를 선택하려면 **[!UICONTROL Browse All Traits]** 또는 **[!UICONTROL Browse All Segments]**&#x200B;을(를) 클릭하십시오. 이름, ID, 설명 또는 데이터 소스로 트레이트를 검색합니다. 검색 중에 폴더를 클릭하여 해당 폴더 및 그 하위 폴더로 결과를 제한합니다. 트레이트 유형([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] 및 [!UICONTROL Algorithmic]) 또는 모집단 유형([장치 ID](../../reference/ids-in-aam.md) 및 [교차 장치 ID](../../reference/ids-in-aam.md))별로 트레이트를 필터링할 수도 있습니다.

     ![검색 특성](assets/browse-traits.png)
   * 30일, 60일 또는 90일 전환 확인 기간을 선택합니다. 모델의 시간 범위를 설정합니다.
   * 기본적으로 [!UICONTROL TraitWeight] 알고리즘이 선택되어 있습니다.
   * [!UICONTROL Available Data] 목록에서 데이터 원본을 선택하십시오.
   * 완료되면 **[!UICONTROL Save]**&#x200B;을(를) 클릭합니다.

     ![유사 구성](assets/look-alike-configuration.png)

크로스 디바이스 지표가 작동하는 방식에 대한 자세한 내용은 아래 비디오를 시청하십시오.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=ko)

## 알고리즘 모델에 대한 기본 정보 {#basic-information}

<!-- r_model_basic.xml -->

[!UICONTROL Model Builder]에서 [!UICONTROL Basic Information] 설정을 사용하여 새 모델을 만들거나 기존 모델을 편집할 수 있습니다. 새 모델을 만들려면 이름을 입력하고 [!UICONTROL Configuration] 설정으로 이동하세요. 설명 필드는 선택 사항입니다.

| 필드 | 설명 |
|---|---|
| **[!UICONTROL Name]** | 모델의 기능 또는 목적을 설명하는 짧은 논리적 이름을 지정합니다. 약자, 특수 문자 및 악센트 표시를 사용하지 마십시오. |
| **[!UICONTROL Description]** | 모델에 대한 추가 설명 정보를 위한 필드입니다. |
| **[!UICONTROL Status]** | 모델을 활성화하거나 비활성화합니다(기본적으로 활성화됨). |

## 구성 {#configuration}

[!UICONTROL Model Builder]에서 [!UICONTROL Configuration] 섹션을 사용하여 모델에 트레이트 또는 세그먼트를 추가할 수 있습니다. 이 섹션에서는 기준 트레이트 또는 세그먼트, 전환 확인 기간 및 자사 및 타사 데이터 소스의 데이터를 선택합니다.

<!-- r_model_configuration.xml -->

### 전제 조건

먼저 [!UICONTROL Basic Information] 섹션의 필수 필드를 작성합니다.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>기준 트레이트 또는 세그먼트 선택(1)</b> </p> </td> 
   <td colname="col2"> <p>모든 트레이트 또는 세그먼트 목록을 보려면 트레이트 또는 세그먼트 버튼을 클릭합니다. 선택한 세그먼트나 트레이트는 시스템 알고리즘이 모델링에 사용하는 기준선이 됩니다. </p> <p> <p><b>참고</b>: 온보딩된 트레이트, 규칙 기반 트레이트 또는 세그먼트를 기준으로 선택합니다. 그렇지 않으면 모델이 실행되지 않습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>되돌아보기 기간(2) 선택</b> </p> </td> 
   <td colname="col2"> <p>모델의 시간 범위를 설정합니다. 선택한 항목에 따라 알고리즘에서는 이전 30일, 60일 또는 90일의 데이터를 포함하고 평가합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>알고리즘 선택(3)</b> </p> </td> 
   <td colname="col2"> <p>현재 Model Builder는 자체 <span class="keyword"> 트레이트 가중치</span> 알고리즘에서만 작동합니다. <span class="keyword"> Audience Manager</span>은(는) 후속 릴리스에서 다른 알고리즘 함수를 추가할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Data Source에서 모델 데이터 선택(4)</b> </p> </td> 
   <td colname="col2"> <p>모델에서 사용할 자사 및 타사 데이터 소스를 선택할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>제외(5)</b> </p> </td> 
   <td colname="col2"> <p>모델링을 위해 선택한 데이터 소스에서 트레이트를 제외할 수 있습니다. 자세한 내용은 <span class="wintitle"> 제외</span> 목록을 사용하고 <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 알고리즘 모델: 트레이트 제외</a>를 읽어 보십시오. </p> </td>
  </tr> 
 </tbody>
</table>

아래 비디오를 시청하여 자사 유사 모델을 만들어 변환자처럼 보이는 방문자를 더 많이 찾을 수 있는 방법에 대해 알아보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/30933?captions=kor)

>[!MORELIKETHIS]
>
>* [TraitWeight 이해](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
