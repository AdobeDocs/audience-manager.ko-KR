---
description: 유사 모델링에 사용된 트레이트 또는 세그먼트를 작성하고 관리합니다.
keywords: 상대적 가중치, 유사
seo-description: 유사 모델링에 사용된 트레이트 또는 세그먼트를 작성하고 관리합니다.
seo-title: 유사 모델링 정보
solution: Audience Manager
title: 유사 모델링 정보
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: 알고리즘 모델
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1595'
ht-degree: 1%

---

# [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models} 이해

## [!UICONTROL Look-Alike Modeling] {#find-new-users}을 사용하여 새 사용자 찾기

[!UICONTROL Look-Alike Modeling] 은 자동화된 데이터 분석을 통해 새롭고 고유한 대상을 찾는 데 도움이 됩니다. 프로세스는 [!UICONTROL trait] 또는 [!UICONTROL segment], 시간 간격, 그리고 첫 번째 및 타사 [!UICONTROL data sources]를 선택하면 시작됩니다. 선택한 사항에서 알고리즘 모델의 입력을 제공합니다. Analytics 프로세스가 실행되면 선택한 모집단의 공유 특성을 기반으로 적합한 사용자를 찾습니다. 완료 시 이 데이터는 [트레이트 빌더](../../features/traits/about-trait-builder.md)에서 사용할 수 있습니다. 여기서 [의 정확도를 기반으로 트레이트를 만들고](../../features/traits/trait-accuracy-reach.md)에 도달합니다. 또한 알고리즘 트레이트를 [!UICONTROL rules-based traits]과 결합하는 세그먼트를 작성하고 [!DNL Boolean] 표현식 및 비교 연산자와 함께 다른 자격 요구 사항을 추가할 수 있습니다. [!UICONTROL Look-Alike Modeling] 는 사용 가능한 모든 트레이트 데이터에서 값을 추출하는 동적 방법을 제공합니다.

## 장점 {#advantages}

[!UICONTROL Look-Alike Modeling]을 사용하면 다음과 같은 주요 이점이 있습니다.

* **데이터 정확도:** 알고리즘이 정기적으로 실행되므로 결과를 최신 및 연관성 있게 유지할 수 있습니다.
* **자동화:** 대량의 정적 규칙을 관리할 필요가 없습니다. 알고리즘에서 대상을 찾을 수 있습니다.
* **시간 절약 및 노력 절약:** 모델링 프로세스를 통해 작업  [!UICONTROL traits]/[!UICONTROL segments] 시간을 추측하거나 새로운 대상을 발견하기 위해 캠페인에서 리소스를 사용할 필요가 없습니다. 모델이 자동으로 이 작업을 수행합니다.
* **안정성:**  모델링은 자체 데이터와 액세스 권한이 있는 선택한 타사 데이터를 평가하는 서버측 검색 및 자격 프로세스와 함께 작동합니다. 즉, 트레이트에 대한 자격을 얻기 위해 사이트 방문자를 볼 필요가 없습니다.

## 워크플로우 {#workflow}

**[!UICONTROL Audience Data > Models]**&#x200B;에서 모델을 관리합니다. 높은 수준에서 워크플로우 프로세스에는 다음이 포함됩니다.

* 알고리즘을 평가할 기준 데이터를 선택합니다. 여기에는 [!UICONTROL trait] 또는 [!UICONTROL segment], 시간 범위 및 [!UICONTROL data sources](사용자 고유의 데이터 및 이미 [!DNL Audience Manager]을 통해 액세스할 수 있는 타사 데이터)가 포함됩니다. 모델 생성 워크플로우에서 모델을 방해하지 않으려는 [!UICONTROL traits]을 제외할 수 있습니다.
* 모델을 저장합니다. 저장하면 알고리즘 평가 프로세스가 자동으로 실행됩니다. 그러나 이 프로세스를 완료하는 데 최대 7일이 걸릴 수 있습니다. [!DNL Audience Manager] 알고리즘이 완료되고 결과를 만들 수 있을 때 이메일을  [!UICONTROL trait] 보냅니다.
* [!UICONTROL Trait Builder]에서 알고리즘 [!UICONTROL traits]을(를) 작성합니다.
* [!UICONTROL traits]을 [!UICONTROL Segment Builder]에 [!UICONTROL segments]에 결합합니다.
* [!UICONTROL segment] 데이터를 만들고 [!UICONTROL destination]에 보냅니다.

## 문제 해결 {#troubleshooting}

세 번의 연속 실행에 대한 데이터를 생성하지 않는 [!UICONTROL Look-Alike Model]을 비활성화합니다. 모델의 상태를 이후에 다시 활성으로 설정할 수 없습니다. 모델이 데이터를 생성하도록 하려면 충분한 [!UICONTROL traits] 데이터를 축적할 수 있는 데이터 소스에서 모델을 만드는 것이 좋습니다.

## [!UICONTROL TraitWeight] {#understanding-traitweight} 이해

[!UICONTROL TraitWeight] 는 새로운 기능을 자동으로 검색하도록 설계된 독점  [!UICONTROL traits] 알고리즘입니다. 또한 현재 [!UICONTROL traits] 및 [!UICONTROL segments]의 [!UICONTROL trait] 데이터를 [!DNL Audience Manager]을 통해 액세스할 수 있는 다른 모든 자사 데이터와 비교합니다. [!UICONTROL TraitWeight] 알고리즘 검색 프로세스에 대한 설명은 이 섹션을 참조하십시오.

![](assets/algo_model.png)

다음 단계에서는 [!UICONTROL TraitWeight] 평가 프로세스를 설명합니다.

### 1단계:[!UICONTROL Trait] 비교를 위한 기준 작성

기준선을 작성하려면 [!UICONTROL TraitWeight]이 30, 60 또는 90일 간격 동안 대상자와 연결된 모든 [!UICONTROL traits]을 측정합니다. 다음으로, 빈도 및 상관 관계에 따라 [!UICONTROL traits]의 등급을 매깁니다. 빈도 수는 공통성을 측정합니다. 상관 관계는 기준 대상에만 [!UICONTROL trait]이 있을 가능성을 측정합니다. [!UICONTROL Traits] 자주 나타나는 현상은 선택한 항목에서  [!UICONTROL traits] 발견된 항목과 결합할 때 가중치가 적용된 점수를 설정하는 데 사용되는 중요한 특성인 높은 공통성을 나타낸다고  [!UICONTROL data sources]합니다.

### 2단계:[!UICONTROL Data Source]에서 동일한 [!UICONTROL Traits]을 찾습니다.

비교를 위해 기준을 빌드하면 알고리즘이 선택한 [!UICONTROL data sources]에서 동일한 [!UICONTROL traits]을 찾습니다. 이 단계에서 [!UICONTROL TraitWeight]은(는) 검색된 모든 [!UICONTROL traits]의 빈도 수를 수행하고 기준 요소와 비교합니다. 그러나 기준선과 달리 일반적이지 않은 [!UICONTROL traits]은(는) 더 자주 나타나는 것보다 더 높게 평가됩니다. 드문 [!UICONTROL traits]은 높은 수준의 특이도를 나타낸다고 합니다. [!UICONTROL TraitWeight] 공통 기준선 [!UICONTROL traits] 과 일반적이지 않은(매우 특정) 조합을 두 데이터 세트 [!UICONTROL data source] [!UICONTROL traits] 에  [!UICONTROL traits] 공통으로 사용할 때보다 더 영향적이거나 바람직한 것으로 평가합니다. 실제로 우리 모델은 이러한 큰 공통 [!UICONTROL traits]을 인식하며 상관 관계가 높은 데이터 세트에 과도한 우선순위를 할당하지 않습니다. 드문 [!UICONTROL traits] 은(는) 보드 전체에서 공통성이 높은 [!UICONTROL traits]보다 새롭고 고유한 사용자를 나타낼 가능성이 높으므로 우선순위가 더 높습니다.

### 3단계:가중치 할당

이 단계에서 [!UICONTROL TraitWeight]은(는) 영향 또는 계획성 순으로 새로 발견된 [!UICONTROL traits]의 등급을 매깁니다. 중량%는 0%에서 100%로 실행되는 백분율입니다. [!UICONTROL Traits] 등급 100%에 근접하면 기준선 모집단의 대상자와 더 비슷해집니다. 또한, 가중치가 높은 [!UICONTROL traits]은(는) 설정한 기본 대상과 유사하게 작동할 수 있는 새롭고 고유한 사용자를 나타내므로 유용합니다. [!UICONTROL TraitWeight]은(는) 비교된 데이터 소스의 기준선 공통성과 높은 특수성이 있는 [!UICONTROL traits]을 각 데이터 세트의 [!UICONTROL traits]보다 더 중요하게 간주합니다.

### 4단계:사용자 점수 책정

선택한 [!UICONTROL data sources]의 각 사용자에게는 해당 사용자 프로필에서 영향력 있는 [!UICONTROL traits]의 모든 가중치 합계와 동일한 사용자 점수가 제공됩니다. 그러면 사용자 점수가 0에서 100% 사이에 표준화됩니다.

### 5단계:결과 표시 및 작업

[!DNL Audience Manager] 가중치가 적용된 모델 결과를 로 표시합니다 [!UICONTROL Trait Builder]. [!UICONTROL algorithmic trait]을(를) 만들려면, [!UICONTROL Trait Builder]을(를) 사용하여 데이터 실행 중에 알고리즘에서 생성된 가중치 점수를 기반으로 [!UICONTROL traits]를 만듭니다. 매우 높은 사용자 점수를 가지고 있으므로 나머지 대상이 아니라 기본 대상과 매우 유사한 사용자에게만 자격을 부여하도록 더 높은 정확도를 선택할 수 있습니다. 더 많은 대상(도달)에 도달하려는 경우 정확도를 낮출 수 있습니다.

### 6단계:처리 주기마다 [!UICONTROL Trait] 중요성 재평가

[!UICONTROL TraitWeight]은(는) 정기적으로 [!UICONTROL trait]의 크기 및 모집단의 변경에 따라 [!UICONTROL trait]의 중요성을 다시 평가합니다. 이 문제는 해당 [!UICONTROL trait]에 대해 자격이 있는 사용자 수가 시간이 지남에 따라 증가 또는 감소함에 따라 발생합니다. 이 행동은 매우 크게 보이는 특징에서 가장 잘 보입니다. 예를 들어 알고리즘이 모델링에 [!UICONTROL trait A]을 사용한다고 가정합니다. [!UICONTROL trait A] 모집단이 증가하면 [!UICONTROL TraitWeight]이(가) 해당 [!UICONTROL trait]의 중요성을 다시 평가하고 더 낮은 점수를 할당하거나 무시할 수 있습니다. 이 경우 [!UICONTROL trait A]은(는) 너무 일반적이거나 커서 모집단에서 중요한 것을 말할 수 없습니다. [!UICONTROL TraitWeight] 이 [!UICONTROL trait A] 값을 줄이거나 모델에서 이 값을 무시합니다. 영향력 있는 [!UICONTROL traits] 목록은 베이스라인 모집단의 진화를 반영합니다. 이러한 변경 사항이 발생하는 이유를 이해하려면 영향력 있는 [!UICONTROL traits] 목록을 사용하십시오.

관련 링크:

* [모델 빌더](../../features/algorithmic-models/create-model.md)
* [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md)

## [!UICONTROL Look-Alike Models] 및 [!UICONTROL Traits] {#update-schedule} 일정 업데이트

새 또는 기존 [!UICONTROL algorithmic models] 및 [!UICONTROL traits]에 대한 일정을 만들고 업데이트합니다.

### [!UICONTROL Look-Alike Model] 생성 및 업데이트 일정

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> 활동 유형 </th>
   <th colname="col2" class="entry"> 설명 </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>모델 생성 또는 복제</b> </td>
   <td colname="col2"> <p>새 모델 또는 복제된 [!UICONTROL 유사 모델]의 경우 작성 프로세스는 하루에 한 번 실행됩니다. 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 오후 5시 EST (11월 - 3월) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 오후 6시 EDT(3월 - 11월) </li> 
     </ul> </p> <p>생성 기한 이후에 만들거나 복제된 모델은 다음 날 처리됩니다. </p> <p>모델의 첫 번째 실행에서 데이터가 생성되지 않으면 두 번째 실행에서 다음 날 실행됩니다. 두 번째 시도에서도 데이터를 생성하지 않으면 다음 날 세 번째 시도가 발생합니다. 세 번째 시도에서도 데이터가 생성되지 않으면 모델의 실행이 중지됩니다. 이 경우 모델을 비활성화합니다. 자세한 내용은 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 유사 모델 문제 해결</a>을 참조하십시오. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>모델 업데이트</b> </td> 
   <td colname="col2"> <p>이상적인 조건에서, 기존 모델은 7일에 한 번 이상 주중에 실행됩니다. 예를 들어 월요일(마감일)에 모델을 만드는 경우, 늦어도 다음 월요일에는 업데이트됩니다. </p> <p>다음 조건을 충족하면 모델이 재실행됩니다. </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">마지막 실행이 성공하지 못했습니다. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">이 모델은 성공적으로 실행되었으며 지난 7일 동안 전혀 실행되지 않았습니다. 이 모델에 하나 이상의 활성 트레이트가 연결되어 있습니다. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] 생성 및 업데이트 일정

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 활동 유형 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>트레이트 만들기</b> </td> 
   <td colname="col2"> <p>트레이트 생성 프로세스는 매일, 월요일부터 금요일까지 실행됩니다. 일반적으로 새로운 알고리즘 트레이트는 48시간 이내에 UI에 나타납니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>트레이트 업데이트</b> </td> 
   <td colname="col2"> <p>기존 트레이트는 7일에 한 번 이상 업데이트되고 모델 업데이트 일정을 따릅니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 모델 목록 보기 {#models-list-view}

목록 보기는 모델을 만들고, 검토하고, 관리하는 데 도움이 되는 중앙 작업 공간입니다.

[!UICONTROL Models] 목록 페이지에는 다음과 같은 기능을 제공하는 기능과 도구가 포함되어 있습니다.

* 새 모델을 만듭니다.
* 기존 모델(편집, 일시 중지, 삭제 또는 복제)을 관리합니다.
* 이름별로 모델을 검색합니다.
* 지정된 모델을 사용하여 [!UICONTROL algorithmic traits] 을 만듭니다.

## 모델 요약 보기 {#models-summary-view}

요약 페이지에는 이름, 도달/정확도, 처리 내역 및 모델에서 생성된 [!UICONTROL traits] 등의 모델 세부 정보가 표시됩니다. 또한 페이지에 모델을 만들고 관리할 수 있는 설정이 포함되어 있습니다. 요약 목록에서 모델 이름을 클릭하여 해당 세부 정보를 확인합니다.

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
   <td colname="col2"> <p>모델 이름 및 마지막으로 실행된 시점과 같은 기본 정보를 포함합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 도달 및 정확도</span> </p> </td> 
   <td colname="col2"> <p>마지막 모델 실행에 대한 <a href="../../features/traits/trait-accuracy-reach.md"> 정확도와 도달</a> 데이터를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 처리 내역</span> </p> </td> 
   <td colname="col2"> <p>최근 10개의 실행에 대한 처리 날짜 및 시간과 해당 실행에서 데이터가 생성되었는지 여부를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 영향력 있는 트레이트</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 영향력 있는 트레이트</span> 테이블: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 모델의 기준선 모집단에 가장 잘 표현되는 상위 50개의 영향력 있는 트레이트를 나열합니다. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E"><span class="wintitle"> 상대 가중치</span> 등급 순서로 각 트레이트의 등급을 매깁니다. <span class="wintitle"> 상대적 가중치</span> 는 영향이나 계획성 순서로 새로 발견된 트레이트를 정렬합니다. 중량%는 0%에서 100%로 실행되는 백분율입니다. 트레이트가 100%에 가까운 등급 지정은 기본 모집단의 대상자와 더 비슷하다는 것을 의미합니다. <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> TraitWeight</a> 이해 를 참조하십시오. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">각 트레이트에 대한 30일 고유 정보와 총 트레이트 모집단을 보여줍니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델을 사용한 트레이트</span> </p> </td>
   <td colname="col2"> <p>선택한 모델을 기반으로 알고리즘 트레이트의 목록을 표시합니다. 트레이트에 대한 자세한 내용을 보려면 트레이트 이름 또는 트레이트 ID를 클릭하십시오. <b><span class="uicontrol"> 모델</span></b>으로 새 트레이트 만들기 를 선택하여 알고리즘 트레이트 생성 프로세스로 이동합니다. </p> <p>모델 이름에 따라 단면 레이블이 변경됩니다. 예를 들어 모델을 만들고 모델 A로 이름을 지정한다고 가정합니다.요약 페이지를 로드할 때 이 섹션의 이름이 <span class="wintitle"> 모델 A</span>을 사용하여 트레이트로 변경됩니다. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [대상](../../features/destinations/destinations.md)
* [트레이트](../../features/traits/trait-details-page.md)
* [세그먼트](../../features/segments/segments-purpose.md)

