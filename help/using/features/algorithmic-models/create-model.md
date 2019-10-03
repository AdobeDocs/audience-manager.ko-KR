---
description: 모델 빌더에서 알고리즘 모델을 만들 수 있는 필수 단계와 선택 단계에 대해 설명합니다.
keywords: 사용 방법
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: 알고리즘 모델 만들기
solution: Audience Manager
title: 알고리즘 모델 만들기
topic: DIL API
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 알고리즘 모델 만들기 {#create-an-algorithmic-model}

에서 알고리즘 모델을 만들 수 있는 필수 단계와 선택 단계에 대해 [!UICONTROL Model Builder]설명합니다.

## 모델 만들기 {#build-model}

<!-- t_model_build.xml -->

### 모델 빌더 섹션

[!UICONTROL Model Builder] 은 [!UICONTROL Basic Information] 및 [!UICONTROL Configuration] 섹션으로 구성됩니다. 모델을 만들려면 이 두 섹션에서 필요한 필드를 완성합니다. Save your model to start the algorithm. [!DNL Audience Manager] sends you an automated notification after the first data run completes. After you receive the email, you can go to Trait Builder and create algorithmic traits.[](../../features/traits/about-trait-builder.md)

>[!NOTE]
>
>* The modeling process runs only once if you create a model and do not build any traits with it.
>* Build models from data sources that contain a meaningful amount of information. Models with insufficient data will run, but they will not return results.
>* *Do not* create models with other algorithmic traits or segments.
>* The automated email notification is sent one time only (after the first data run).


### Build the Model

To build a model, go to the  section and click  and follow the steps below:[!UICONTROL Models]**[!UICONTROL Add New]**

1. In the Basic Information section[](../../features/algorithmic-models/create-model.md#basic-information)
   * Name the model.
   * *(선택 사항)* 모델에 대한 간단한 설명을 제공합니다.
   * 모델의 상태를 **[!UICONTROL Active]** 또는 으로 **[!UICONTROL Inactive]**&#x200B;설정합니다. 비활성 모델은 실행되지 않으며 데이터를 생성하지 않습니다.
1. In the Configuration section:[](../../features/algorithmic-models/create-model.md#configuration)
   * 를 **[!UICONTROL Browse All Traits]** 클릭하거나 **[!UICONTROL Browse All Segments]** 클릭하여 모델링할 트레이트 또는 세그먼트를 선택합니다.  온보드 트레이트, 규칙 기반 트레이트 또는 세그먼트를 기준선으로 선택합니다. 그렇지 않으면 모델이 실행되지 않습니다.
   * 30, 60 또는 90일 룩백 기간을 선택합니다. 그러면 모델의 시간 범위가 설정됩니다.
   * 기본적으로 [!UICONTROL TraitWeight] 알고리즘이 선택됩니다.
   * 목록에서 데이터 소스를 [!UICONTROL Available Data] 선택합니다.
   * Click **[!UICONTROL Save]** when done.

## 알고리즘 모델에 대한 기본 정보 {#basic-information}

<!-- r_model_basic.xml -->

에서 [!UICONTROL Model Builder]설정을 [!UICONTROL Basic Information] 사용하여 새 모델을 만들거나 기존 모델을 편집할 수 있습니다. 새 모델을 만들려면 이름을 입력하고 [!UICONTROL Configuration] 설정으로 이동합니다. 설명 필드는 선택 사항입니다.

| 필드 | 설명 |
|---|---|
| **[!UICONTROL Name]** | 기능이나 목적을 설명하는 짧고 논리적인 이름을 모델에 지정합니다. 약자, 특수 문자 및 강조 표시를 사용하지 마십시오. |
| **[!UICONTROL Description]** | 모델에 대한 추가 설명 정보를 위한 필드입니다. |
| **[!UICONTROL Status]** | Activates or deactivates the model (active by default). |

## 구성 {#configuration}

에서 [!UICONTROL Model Builder]이 [!UICONTROL Configuration] 섹션에서 모델에 트레이트 또는 세그먼트를 추가할 수 있습니다. 이 섹션에서 기준 트레이트 또는 세그먼트, 룩백 기간 및 첫 번째 및 타사 데이터 소스의 데이터를 선택합니다.

<!-- r_model_configuration.xml -->

### 전제 조건

Complete the required fields in the  section first.[!UICONTROL Basic Information]

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
   <td colname="col1"> <p><b>기준 요소 트레이트 또는 세그먼트 선택(1)</b> </p> </td> 
   <td colname="col2"> <p>트레이트 또는 세그먼트 단추를 클릭하여 모든 트레이트 또는 세그먼트 목록을 봅니다. 선택한 세그먼트나 트레이트는 시스템 알고리즘이 모델링에 사용하는 기준이 됩니다. </p> <p> <p><b>참고</b>:온보드 트레이트, 규칙 기반 트레이트 또는 세그먼트를 기준선으로 선택합니다. 그렇지 않으면 모델이 실행되지 않습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>뒤로 보기 기간 선택(2)</b> </p> </td> 
   <td colname="col2"> <p>모델의 시간 범위를 설정합니다. 선택한 항목에 따라 알고리즘은 이전 30일, 60일 또는 90일의 데이터를 포함하고 평가합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>알고리즘 선택(3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary  Trait Weight algorithm only. <span class="keyword"></span> <span class="keyword"> Audience Manager may add other algorithmic functions in subsequent releases.</span> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Select Model Data from Data Source (4)</b> </p> </td> 
   <td colname="col2"> <p>Lets you select the first and third-party data sources you want to use in the model. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>제외(5)</b> </p> </td> 
   <td colname="col2"> <p>You can exclude traits from the data sources you selected for modeling. Use the  Exclusions list and read  Algorithmic Models: Trait Exclusion to learn more.<span class="wintitle"></span><a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"></a> </p> </td>
  </tr> 
 </tbody>
</table>

아래 비디오를 시청하여 퍼스트 파티 유사 모델을 만드는 방법을 살펴보십시오. 그러면 전환자와 비슷한 방문자를 더 많이 찾을 수 있습니다.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?captions=kor)

>[!MORELIKE_THIS]
>
>* [특성 가중치 이해](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

