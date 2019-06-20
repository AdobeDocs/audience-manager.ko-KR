---
description: 모델 빌더에서 알고리즘 모델을 만들 수 있는 필수 단계와 선택적 단계를 설명합니다.
keywords: Algo How Works
seo-description: 모델 빌더에서 알고리즘 모델을 만들 수 있는 필수 단계와 선택적 단계를 설명합니다.
seo-title: 알고리즘 모델 만들기
solution: Audience Manager
title: 알고리즘 모델 만들기
topic: DIL API
uuid: ccf 4 fc 4 e-cf 92-445 f-b 2 d 9-71 c 3 ca 624 e 26
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create an Algorithmic Model {#create-an-algorithmic-model}

Describes the required and optional steps that let you create an algorithmic model in [!UICONTROL Model Builder].

## Build a Model {#build-model}

<!-- t_model_build.xml -->

### 모델 빌더 섹션

[!UICONTROL Model Builder][!UICONTROL Basic Information] 및 [!UICONTROL Configuration] 섹션으로 구성됩니다. 모델을 만들려면 이 두 섹션의 필수 필드를 완료합니다. 모델을 저장하여 알고리즘을 시작합니다. [!DNL Audience Manager] 첫 번째 데이터 실행이 완료된 후 자동으로 알림을 보냅니다. After you receive the email, you can go to [Trait Builder](../../features/traits/about-trait-builder.md) and create algorithmic traits.

>[!NOTE]
>
>* 모델링 프로세스는 모델을 만들고 어떤 트레이트도 만들지 않는 한 한 번만 실행됩니다.
>* 의미 있는 정보가 들어 있는 데이터 소스에서 모델을 구축합니다. 데이터가 불충분한 모델은 실행되지만 결과를 반환하지 않습니다.
>* *다른 알고리즘 특성 또는 세그먼트로 모델을* 만들지 마십시오.
>* 자동화된 이메일 알림은 첫 번째 데이터 실행 후 한 번만 전송됩니다.


### 모델 구축

To build a model, go to the [!UICONTROL Models] section and click **[!UICONTROL Add New]** and follow the steps below:

1. In the [Basic Information](../../features/algorithmic-models/create-model.md#basic-information) section
   * 모델의 이름을 지정합니다.
   * *(선택 사항)* 모델에 대한 간단한 설명을 제공합니다.
   * Set the status for the model to **[!UICONTROL Active]** or **[!UICONTROL Inactive]**. 비활성 모델은 실행되지 않으며 데이터는 생성되지 않습니다.
1. [구성](../../features/algorithmic-models/create-model.md#configuration) 섹션에서 다음을 수행합니다.
   * Click **[!UICONTROL Browse All Traits]** or **[!UICONTROL Browse All Segments]** to select a trait or segment you want to model against. 온보드 트레이트를 선택하거나 규칙 기반 트레이트 또는 세그먼트를 기준선으로 선택합니다. 그렇지 않으면 모델이 실행되지 않습니다.
   * 30 일, 60 일 또는 90 일 룩백 기간을 선택합니다. 모델에 대한 시간 범위를 설정합니다.
   * [!UICONTROL TraitWeight] 알고리즘이 기본적으로 선택됩니다.
   * Select a data source from the [!UICONTROL Available Data] list.
   * Click **[!UICONTROL Save]** when done.

## Basic Information for Algorithmic Models {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder], the [!UICONTROL Basic Information] settings let you create new or edit existing models. To create a new model, provide a name and move on to the [!UICONTROL Configuration] settings. 설명 필드는 선택 사항입니다.

| 필드 | 설명 |
|---|---|
| **[!UICONTROL Name]** | 모델의 함수 또는 목적을 설명하는 짧은 논리적 이름을 모델에 지정합니다. 약어, 특수 문자 및 악센트 표시를 사용하지 마십시오. |
| **[!UICONTROL Description]** | 모델에 대한 추가 설명 정보를 위한 필드입니다. |
| **[!UICONTROL Status]** | 모델을 활성화 또는 비활성화합니다 (기본적으로 활성). |

## 구성 {#configuration}

In [!UICONTROL Model Builder], the [!UICONTROL Configuration] section lets you add traits or segments to the model. 이 섹션에서 기준 트레이트 또는 세그먼트, 룩백 기간 및 자사 데이터 소스 및 타사 데이터 소스의 데이터를 선택합니다.

<!-- r_model_configuration.xml -->

### 전제 조건

Complete the required fields in the [!UICONTROL Basic Information] section first.

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
   <td colname="col1"> <p><b>기준선 특성 또는 세그먼트 선택 (1)</b> </p> </td> 
   <td colname="col2"> <p>트레이트 또는 세그먼트 단추를 클릭하여 모든 트레이트 또는 세그먼트 목록을 확인합니다. 선택한 세그먼트 또는 트레이트 값이 시스템 알고리즘이 모델링하는 데 사용하는 기준이 됩니다. </p> <p> <p><b></b>참고: 온보드 트레이트를 선택하거나 규칙 기반 트레이트 또는 세그먼트를 기준선으로 선택합니다. 그렇지 않으면 모델이 실행되지 않습니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>뒤로 기간 선택 (2)</b> </p> </td> 
   <td colname="col2"> <p>모델의 시간 범위를 설정합니다. 알고리즘에 따라 이전 30 일, 60 일 또는 90 일의 데이터를 포함하여 평가합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>알고리즘 선택 (3)</b> </p> </td> 
   <td colname="col2"> <p>At this time, Model Builder works with our proprietary <span class="keyword"> Trait Weight</span> algorithm only. <span class="keyword"> Audience Manager</span> 는 후속 릴리스에서 다른 알고리즘 기능을 추가할 수 있습니다. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>데이터 소스에서 모델 데이터 선택 (4)</b> </p> </td> 
   <td colname="col2"> <p>모델에서 사용할 첫 번째 및 타사 데이터 소스를 선택할 수 있습니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>제외 (5)</b> </p> </td> 
   <td colname="col2"> <p>모델링을 위해 선택한 데이터 소스의 트레이트를 제외할 수 있습니다. <span class="wintitle"> 제외</span> 목록을 사용하고 <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> 알고리즘 모델을 읽습니다. 특성 제외를</a> 참조하십시오. </p> </td>
  </tr> 
 </tbody>
</table>

>[!MORE_ like_ this]
>
>* [Traitweight 이해](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

