---
description: 유사 모델링을 통해 알고리즘 모델링을 통해 사용되는 트레이트 또는 세그먼트를 제작 및 관리할 수 있습니다. 모델 기능은 대상 데이터 > 모델에 있습니다.
keywords: 상대적 가중치
seo-description: 유사 모델링을 통해 알고리즘 모델링을 통해 사용되는 트레이트 또는 세그먼트를 제작 및 관리할 수 있습니다. 모델 기능은 대상 데이터 > 모델에 있습니다.
seo-title: 알고리즘 모델 정보
solution: Audience Manager
title: 알고리즘 모델 정보
topic: DIL API
uuid: 39441 e 72-5316-453 d -9 aff -0 e 0 b 633 aabcd
translation-type: tm+mt
source-git-commit: 157e70906b80bd0a23ba6e7721d2c456d378ffb5

---


# About Algorithmic Models {#about-algorithmic-models}

유사 모델링을 통해 알고리즘 모델링을 통해 사용되는 트레이트 또는 세그먼트를 제작 및 관리할 수 있습니다. Model features are located in **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Understanding Algorithmic Models {#understanding-models}

The sections below represent a review of algorithmic modeling in [!DNL Audience Manager]. 모델링 작업, 이점 및 워크플로우에 대해 설명합니다.

<!-- understanding-models.xml -->

## Find New Users with Algorithmic Modeling {#find-new-users}

알고리즘 모델링을 사용하면 자동화된 데이터 분석을 통해 고유한 신규 고객을 발견할 수 있습니다. 특성 또는 세그먼트, 시간 간격, 첫 번째 및 타사 데이터 소스를 선택하면 프로세스가 시작됩니다. 선택 사항은 알고리즘 모델에 대한 입력을 제공합니다. 분석 프로세스가 실행되면 선택한 모집단의 공유 특성을 기반으로 자격 조건을 갖춘 사용자를 찾습니다. Upon completion, this data is available in [Trait Builder](../../features/traits/about-trait-builder.md) where you can use it to create traits based on [accuracy and reach](../../features/traits/trait-accuracy-reach.md). 또한 알고리즘 트레이트와 규칙 기반의 트레이트를 결합하고 부울 표현식 및 비교 연산자로 다른 자격 조건을 추가하는 세그먼트를 작성할 수 있습니다. 알고리즘 모델링을 사용하면 사용 가능한 모든 트레이트 데이터에서 값을 추출할 수 있습니다.

## 장점 {#advantages}

The major benefits of using [!DNL Audience Manager] modeling include:

* **데이터 정확도:** 알고리즘이 정기적으로 실행되므로 결과를 최신 상태로 유지할 수 있습니다.
* **자동화:** 대량의 정적 규칙을 관리할 필요가 없습니다. 알고리즘은 사용자를 위한 대상을 찾습니다.
* **작업 시간을 단축하고 노력을 줄일 수 있습니다.** 모델링 프로세스를 통해 새로운 고객을 파악하기 위해 어떤 특성/세그먼트가 효과적인지 또는 캠페인에 리소스를 할애할 수 있는지 추측할 필요가 없습니다. 모델이 자동으로 만들어줍니다.
* **안정성:** 모델링은 사용자가 액세스할 수 있는 자체 데이터와 선택된 타사 데이터를 평가하는 서버측 탐색 및 검증 프로세스와 함께 작동합니다. 이것은 사이트에서 방문자가 트레이트를 위해 자격을 부여하지 않아도 된다는 것을 의미합니다.

## 워크플로우 {#workflow}

You manage models in **[!UICONTROL Audience Data > Models]**. 높은 수준에서 워크플로우 프로세스는 다음과 관련되어 있습니다.

* 알고리즘을 평가할 기준 데이터를 선택합니다. This includes a trait or segment, time range, and data sources (your own data and third-party data you already have access to through [!DNL Audience Manager]). 모델 제작 워크플로우에서는 모델에 방해하지 않을 트레이트를 제외할 수 있습니다.
* 모델을 저장합니다. 일단 저장된 알고리즘 평가 프로세스는 자동으로 실행됩니다. 그러나 이 프로세스가 완료되는 데 최대 7 일이 걸릴 수 있습니다. [!DNL Audience Manager] 알고리즘이 완료되고 트레이트 작성을 위해 결과를 사용할 수 있을 때 이메일을 전송합니다.
* Build algorithmic traits in [!UICONTROL Trait Builder].
* Combine traits into segments in [!UICONTROL Segment Builder].
* 세그먼트 데이터를 만들어 대상에 보냅니다.

## 문제 해결 {#troubleshooting}

연속 3 회 실행에 대한 데이터를 생성하지 못하는 알고리즘 모델을 비활성화합니다. 나중에 다시 활성 상태로는 모델의 상태를 설정할 수 없습니다. 모델이 데이터를 생성하도록 하려면 데이터를 축적하기 위한 충분한 트레이트가 포함된 데이터 소스에서 모델을 빌드하는 것이 좋습니다.

>[!MORE_ like_ this]
>
>* [대상](../../features/destinations/destinations.md)
>* [트레이트](../../features/traits/trait-details-page.md)
>* [세그먼트](../../features/segments/segments-purpose.md)


## Understanding TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] 은 새로운 트레이트를 자동으로 발견하기 위해 고안된 독점 알고리즘입니다. It compares trait data from your current traits and segments against all other first and third-party data that you have access to through [!DNL Audience Manager]. Refer to this section for a description of the [!UICONTROL TraitWeight] algorithmic discovery process.

<!-- traitweight.xml -->

![](assets/algo_model.png)

The following steps describe the [!UICONTROL TraitWeight] evaluation process.

### 1 단계: 트레이트 비교를 위한 기준 구축

To build a baseline, [!UICONTROL TraitWeight] measures all the traits associated with an audience for a 30, 60, or 90 day interval. 다음으로 주파수와 상관관계에 따라 트레이트등급을 평가합니다. 빈도 수는 공통성을 측정합니다. 상관 관계는 기준선 대상자만 트레이트 제공 가능성을 측정합니다. 흔히 나타나는 트레이트는 높은 공통성을 보여주며, 선택한 데이터 소스에서 검색된 트레이트와 결합할 때 가중치가 적용된 점수를 설정하는 데 사용되는 중요한 특성이라고 할 수 있습니다.

### 2 단계: 데이터 소스에서 동일한 특성 찾기

비교를 위한 기준선을 만든 후 알고리즘은 선택한 데이터 소스에서 동일한 트레이트를 찾습니다. In this step, [!UICONTROL TraitWeight] performs a frequency count of all discovered traits and compares them to the baseline. 하지만 기준선과 달리 일반적이지 않은 특징은 더 자주 나타나는 것보다 순위가 높습니다. 드문 특징은 높은 수준의 특이성을 나타낸다는 것입니다. [!UICONTROL TraitWeight] 공통적인 기준선 트레이트와 일반적이지 않은 (매우 구체적인) 데이터 소스 트레이트의 조합을 두 데이터 세트에 공통되는 특성보다 더 영향력이 있거나 바람직한 것으로 평가합니다. 실제로 모델은 이러한 크고 공통적인 특성을 인식하며 높은 상관 관계를 갖는 데이터 세트에 과도한 우선 순위를 할당하지 않습니다. 드문 특징은 보드 전체에서 공통되는 특성보다 새로운 고유 사용자를 나타낼 가능성이 더 많기 때문에 우선 순위가 높습니다.

### 3 단계: 가중치 지정

In this step, [!UICONTROL TraitWeight] ranks newly discovered traits in order of influence or desirability. 가중치 비율은 0%에서 100%로 실행하는 백분율입니다. 트레이트가 100%에 가까울수록 기준선 모집단의 대상과 더 비슷하다는 의미입니다. 또한 가중치가 크게 가중치가 적용된 트레이트는 설정된 기준선 대상자와 유사하게 행동할 수 있는 새로운 고유 사용자를 나타내기 때문에 중요합니다. Remember, [!UICONTROL TraitWeight] considers traits with high commonality in the baseline and high specificity in the compared data sources to be more valuable than traits common in each data set.

### 4 단계: 점수 사용자

선택한 Data Sources의 각 사용자에게는 사용자 프로필에 있는 영향력 있는 트레이트의 모든 가중치 합계와 동일한 사용자 점수가 주어집니다. 그러면 사용자 점수가 0 ~ 100% 사이에서 표준화됩니다.

### 5 단계: 결과 표시 및 작업

Audience Manager displays your weighted model results in [!UICONTROL Trait Builder]. When you want to build an algorithmic trait, [!UICONTROL Trait Builder] lets you create traits based on the weighted score generated by the algorithm during a data run. 높은 정확도를 선택하여 매우 높은 사용자 점수를 보유하고 따라서 나머지 대상이 아닌 기준선 대상과 매우 유사한 사용자를 분류할 수 있습니다. 더 많은 고객 (도달) 에 도달하려면 정확도를 낮춰야 합니다.

### 6 단계: 처리 주기 전체에서 트레이트의 중요성 평가

Periodically, [!UICONTROL TraitWeight] re-evaluates the importance of a trait based on the size and change in the population of that trait. 이것은 시간이 지남에 따라 해당 트레이트 수가 늘어나거나 감소하는 사용자 수로 발생합니다. 이 동작은 매우 큰 트레이트에 가장 분명하게 표시됩니다. 예를 들어 알고리즘에서 모델링을 위해 트레이트 A를 사용한다고 가정합니다. As the population of trait A increases, [!UICONTROL TraitWeight] re-evaluates the importance of that trait and may assign a lower score or ignore it. 이 경우 트레이트 A는 너무 일반적이거나 크므로 해당 인구에 대해 아무 것도 말하지 않습니다. After [!UICONTROL TraitWeight] reduces the value of Trait A (or ignores it in the model), the population of the algorithmic trait decreases. 영향력 있는 특성 목록은 기준선 모집단 진화를 반영합니다. 영향력이 있는 특성 목록을 사용하여 이러한 변경 사항이 발생하는 이유를 이해합니다.

관련 링크:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [정확성 및 전달 범위](../../features/traits/trait-accuracy-reach.md)

## Update Schedule for Algorithmic Models and Traits {#update-schedule}

새로운 알고리즘 및 기존 알고리즘 모델 및 트레이트에 대한 일정을 작성하고 업데이트합니다.

<!-- c_model_update_schedule.xml -->

### 알고리즘 모델 제작 및 업데이트 일정

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> 활동 유형 </th>
   <th colname="col2" class="entry"> 설명 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>모델 만들기 또는 복제</b> </td>
   <td colname="col2"> <p>새로운 알고리즘 또는 복제된 알고리즘 모델의 경우 제작 프로세스가 하루에 한 번 실행됩니다. 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (11 월 ~ 3 월) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (3 월 ~ 11 월) </li> 
     </ul> </p> <p>제작 기한 이후에 구축 또는 복제된 모델은 다음 날 처리됩니다. </p> <p>모델의 첫 번째 실행이 데이터를 생성하지 않으면 다음 날 두 번째로 실행됩니다. 두 번째 시도가 데이터를 생성하지 않으면 다음 날 세 번째 시도가 발생합니다. 세 번째 시도가 데이터를 생성하지 않으면 모델은 실행되지 않습니다. 이 경우 모델이 비활성화됩니다. See more in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Troubleshooting Algorithmic Models</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>모델 업데이트</b> </td> 
   <td colname="col2"> <p>이상적인 조건에서 기존 모델은 최소 7 일에 한 번씩 실행됩니다. 예를 들어 월요일에는 모델 (마감일까지) 를 만드는 경우 최신 월요일 월요일이 업데이트됩니다. </p> <p>모델은 다음 조건 중 하나라도 충족하면 다시 실행됩니다. </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">마지막 실행이 실패했습니다. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">이전에 성공적으로 실행되었으며 지난 7 일 동안 전혀 실행되지 않았으며 모델에 최소 1 개의 활성 트레이트가 연결되어 있습니다. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### 알고리즘 특성 제작 및 업데이트 일정

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 활동 유형 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>특성 만들기</b> </td> 
   <td colname="col2"> <p>트레이트 제작 프로세스는 월요일부터 금요일까지 실행됩니다. 일반적으로 새 알고리즘 특성이 48 시간 내에 UI에 나타납니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>특성 업데이트</b> </td> 
   <td colname="col2"> <p>기존 트레이트는 최소 7 일에 한 번씩 업데이트되며 모델 업데이트 일정을 따릅니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Models List View {#models-list-view}

목록 보기는 모델을 생성, 검토 및 관리하는 데 도움이 되는 중앙 작업 공간입니다.

<!-- c_models_list_view.xml -->

모델 목록 페이지에는 다음과 같은 기능이 포함되어 있습니다.

* 새로운 모델 제작
* 기존 모델 관리 (편집, 일시 중지, 삭제 또는 복제)
* 이름별로 모델을 검색합니다.
* 주어진 모델을 사용하여 알고리즘 트레이트를 만들 수 있습니다.

## Models Summary View {#models-summary-view}

요약 페이지에는 모델에서 만든 이름, 도달/정확도, 처리 내역 및 트레이트 등의 모델 세부 사항이 표시됩니다. 이 페이지에는 모델을 만들고 관리할 수 있는 설정도 포함되어 있습니다. 요약 목록에서 모델 이름을 클릭하여 세부 정보를 확인합니다.

<!-- c_models_summary.xml -->

모델 요약 페이지에는 다음 섹션이 포함됩니다.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 섹션 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> 기본 정보</span> </p> </td>
   <td colname="col2"> <p>모델의 이름과 마지막 실행 시기 등 모델에 대한 기본 정보를 포함합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 도달 및 정확도</span> </p> </td> 
   <td colname="col2"> <p>Shows <a href="../../features/traits/trait-accuracy-reach.md"> accuracy and reach</a> data for the last model run. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 처리 내역</span> </p> </td> 
   <td colname="col2"> <p>마지막 10 개 실행의 처리 날짜 및 시간 및 해당 실행에 데이터가 생성되었는지 여부를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 영향력 있는 특징</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 영향력 있는 트레이트</span> 표: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 모델의 기준선 모집단 내에서 가장 잘 표현되는 상위 50 개의 영향력이 있는 트레이트를 나열합니다. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ranks each trait in order of its <span class="wintitle"> Relative Weight</span> rank. <span class="wintitle"> 상대적 가중치는</span> 새롭게 검색된 트레이트를 영향 또는 선호도로 정렬합니다. 가중치 비율은 0%에서 100%로 실행하는 백분율입니다. 트레이트가 100%에 가까울수록 기준선 모집단의 대상과 더 비슷하다는 의미입니다. See <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Understanding TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">각 트레이트에 대한 30 일 고유 값과 총 특성 모집단을 보여줍니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델을 사용하는 트레이트</span> </p> </td>
   <td colname="col2"> <p>선택한 모델을 기반으로 하는 알고리즘 특성 목록을 표시합니다. 트레이트 이름 또는 트레이트 ID를 클릭하여 트레이트에 대한 자세한 내용을 참조하십시오. Select <b><span class="uicontrol"> Create New Trait with Model</span></b> to go to the algorithmic trait creation process. </p> <p>섹션 레이블은 모델의 이름에 따라 변경됩니다. For example, say you create a model and name it Model A. When you load the summary page, the name of this section gets changed to <span class="wintitle"> Traits Using Model A</span>. </p> </td>
  </tr>
 </tbody>
</table>