---
description: 유사 모델링에 사용되는 트레이트 또는 세그먼트를 작성하고 관리합니다.
keywords: 상대적 가중치, 유사
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: 유사 모델링 정보
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# [!UICONTROL Look-Alike Modeling] 이해 {#about-algorithmic-models}

## [!UICONTROL Look-Alike Modeling](으)로 새 사용자 찾기 {#find-new-users}

[!UICONTROL Look-Alike Modeling]은(는) 자동화된 데이터 분석을 통해 새롭고 고유한 대상을 찾는 데 도움이 됩니다. [!UICONTROL trait] 또는 [!UICONTROL segment], 시간 간격, 첫 번째 및 타사 [!UICONTROL data sources]을(를) 선택하면 프로세스가 시작됩니다. 선택 항목은 알고리즘 모델에 대한 입력을 제공합니다. Analytics 프로세스가 실행되면 선택한 모집단의 공유 특성을 기반으로 적합한 사용자를 찾습니다. 완료 시 이 데이터는 [트레이트 빌더](../../features/traits/about-trait-builder.md)에서 사용할 수 있습니다. 여기서 [정확도 및 도달](../../features/traits/trait-accuracy-reach.md)을(를) 기준으로 트레이트를 만들 수 있습니다. 또한 알고리즘 트레이트를 [!UICONTROL rules-based traits]과(와) 결합하고 [!DNL Boolean] 표현식 및 비교 연산자와 함께 다른 자격 요구 사항을 추가하는 세그먼트를 만들 수 있습니다. [!UICONTROL Look-Alike Modeling]은(는) 사용 가능한 모든 트레이트 데이터에서 값을 추출하는 동적 방법을 제공합니다.

## 장점 {#advantages}

[!UICONTROL Look-Alike Modeling]을(를) 사용하면 다음과 같은 이점이 있습니다.

* **데이터 정확도:** 알고리즘이 정기적으로 실행되므로 결과를 최신 상태로 유지할 수 있습니다.
* **자동화:** 큰 정적 규칙 집합을 관리할 필요가 없습니다. 알고리즘이 사용자를 위한 대상을 찾습니다.
* **시간을 절약하고 노력을 줄이세요.** 모델링 프로세스를 통해 [!UICONTROL traits]/[!UICONTROL segments]이(가) 작동하거나 새로운 대상을 발견하기 위해 캠페인에 시간 리소스를 사용할 수 있는 방법을 추측할 필요가 없습니다. 모델이 이 작업을 수행할 수 있습니다.
* **안정성:** 모델링은 사용자의 데이터 및 사용자가 액세스할 수 있는 선택한 타사 데이터를 평가하는 서버측 검색 및 자격 부여 프로세스와 함께 작동합니다. 즉, 사이트에서 방문자를 보고 트레이트에 대한 자격을 얻을 필요가 없습니다.

## 워크플로 {#workflow}

**[!UICONTROL Audience Data > Models]**&#x200B;에서 모델을 관리합니다. 높은 수준에서 워크플로 프로세스에는 다음이 포함됩니다.

* 알고리즘에서 평가할 기준 데이터를 선택합니다. 여기에는 [!UICONTROL trait] 또는 [!UICONTROL segment], 시간 범위 및 [!UICONTROL data sources]([!DNL Audience Manager]을(를) 통해 이미 액세스할 수 있는 사용자 데이터 및 타사 데이터)이 포함됩니다. 모델 만들기 워크플로우에서 모델을 방해하지 않을 [!UICONTROL traits]을(를) 제외할 수 있습니다.
* 모델을 저장합니다. 저장되면 알고리즘 평가 프로세스가 자동으로 실행됩니다. 단, 이 프로세스가 완료되는 데 최대 7일이 소요될 수 있습니다. [!DNL Audience Manager]이(가) 알고리즘이 완료되어 [!UICONTROL trait]을(를) 만들 수 있는 결과가 나오면 전자 메일을 보냅니다.
* [!UICONTROL Trait Builder]에서 알고리즘 [!UICONTROL traits]을(를) 빌드합니다.
* [!UICONTROL traits]을(를) [!UICONTROL Segment Builder]의 [!UICONTROL segments](으)로 결합합니다.
* [!UICONTROL segment] 데이터를 만들어 [!UICONTROL destination](으)로 보냅니다.

## 문제 해결 {#troubleshooting}

연속 3회 실행에 대한 데이터를 생성하지 못한 [!UICONTROL Look-Alike Model]을(를) 비활성화합니다. 이후에 모델의 상태를 다시 활성으로 설정할 수 없습니다. 모델이 데이터를 생성하도록 하려면 데이터를 누적할 수 있는 [!UICONTROL traits]이(가) 있는 데이터 원본에서 모델을 만드는 것이 좋습니다.

## [!UICONTROL TraitWeight] 이해 {#understanding-traitweight}

[!UICONTROL TraitWeight]은(는) 새 [!UICONTROL traits]을(를) 자동으로 검색하도록 설계된 독점 알고리즘입니다. 현재 [!UICONTROL traits] 및 [!UICONTROL segments]의 [!UICONTROL trait] 데이터를 [!DNL Audience Manager]을(를) 통해 액세스할 수 있는 다른 모든 자사 및 서드파티 데이터와 비교합니다. [!UICONTROL TraitWeight] 알고리즘 검색 프로세스에 대한 설명은 이 섹션을 참조하십시오.

![](assets/algo_model.png)

다음 단계에서는 [!UICONTROL TraitWeight] 평가 프로세스에 대해 설명합니다.

### 1단계: [!UICONTROL Trait] 비교에 대한 기준선 만들기

기준선을 만들려면 [!UICONTROL TraitWeight]은(는) 30일, 60일 또는 90일 간격 동안 대상자와 연결된 모든 [!UICONTROL traits]을(를) 측정합니다. 다음으로, 빈도와 상관 관계에 따라 [!UICONTROL traits]의 순위를 지정합니다. 빈도 수는 공통성을 측정합니다. 상관 관계는 [!UICONTROL trait]이(가) 기준 대상자에만 있을 가능성을 측정합니다. 자주 표시되는 [!UICONTROL Traits]은(는) 선택된 [!UICONTROL data sources]에서 발견된 [!UICONTROL traits]과(와) 결합할 때 가중 점수를 설정하는 데 사용되는 중요한 특징인 높은 공통성을 나타낸다고 합니다.

### 2단계: [!UICONTROL Data Source]에서 동일한 [!UICONTROL Traits] 찾기

비교를 위한 기준선을 만들면 알고리즘이 선택한 [!UICONTROL data sources]에서 동일한 [!UICONTROL traits]을(를) 찾습니다. 이 단계에서 [!UICONTROL TraitWeight]은(는) 검색된 모든 [!UICONTROL traits]의 빈도 수를 수행하고 이를 기준선과 비교합니다. 하지만 기준선과 달리 흔하지 않은 [!UICONTROL traits]은(는) 더 자주 나타나는 순위보다 높은 순위를 갖습니다. 드문 [!UICONTROL traits]은(는) 특이도가 높다고 합니다. [!UICONTROL TraitWeight]은(는) 공통 기준 [!UICONTROL traits]과(와) 비공통(매우 구체적인) [!UICONTROL data source] [!UICONTROL traits]의 조합을 두 데이터 집합에 공통인 [!UICONTROL traits]보다 더 영향력있거나 바람직한 것으로 평가합니다. 실제로 이 모델은 이러한 크고 일반적인 [!UICONTROL traits]을(를) 인식하고 상관 관계가 높은 데이터 집합에 초과 우선 순위를 할당하지 않습니다. 드물게 [!UICONTROL traits]은(는) 게시판에서 공통성이 높은 [!UICONTROL traits]보다 새로운 고유 사용자를 나타낼 가능성이 높으므로 우선 순위가 높습니다.

### 3단계: 가중치 지정

이 단계에서 [!UICONTROL TraitWeight]은(는) 영향 또는 바람직함 순서로 새로 검색된 [!UICONTROL traits]의 등급을 지정합니다. 중량 척도는 0%에서 100%까지 이어지는 백분율이다. [!UICONTROL Traits]이(가) 100%에 가깝게 순위가 매겨졌다는 것은 기준 모집단의 대상자와 더 비슷하다는 의미입니다. 또한 가중치가 높은 [!UICONTROL traits]은(는) 기존의 기본 대상자와 유사하게 작동할 수 있는 새롭고 고유한 사용자를 나타내므로 중요합니다. [!UICONTROL TraitWeight]은(는) 기준선에서 공통성이 높고 비교되는 데이터 원본에서 특이성이 높은 [!UICONTROL traits]을(를) 각 데이터 집합에서 공통적인 [!UICONTROL traits]보다 더 가치 있게 간주한다는 점을 기억하십시오.

### 4단계: 사용자 점수 지정

선택한 [!UICONTROL data sources]의 각 사용자에게는 해당 사용자의 프로필에서 영향력 있는 [!UICONTROL traits]의 모든 가중치의 합계와 같은 사용자 점수가 제공됩니다. 그런 다음 사용자 점수가 0과 100% 사이에서 표준화됩니다.

### 5단계: 결과 표시 및 작업

[!DNL Audience Manager]이(가) [!UICONTROL Trait Builder]에 가중치가 적용된 모델 결과를 표시합니다. [!UICONTROL algorithmic trait]을(를) 작성하려는 경우 [!UICONTROL Trait Builder]을(를) 사용하면 데이터 실행 중에 알고리즘에서 생성된 가중 점수를 기반으로 [!UICONTROL traits]을(를) 만들 수 있습니다. 높은 정확도를 선택하여 사용자 점수가 매우 높기 때문에 나머지 대상자가 아닌 기준 대상자와 매우 유사한 사용자에게만 자격을 부여할 수 있습니다. 더 많은 대상에 도달하려는 경우(도달) 정확도를 낮출 수 있습니다.

### 6단계: 처리 주기 간 [!UICONTROL Trait]의 중요도 다시 평가

[!UICONTROL TraitWeight]은(는) 해당 [!UICONTROL trait]의 크기 및 모집단 변경을 기반으로 [!UICONTROL trait]의 중요도를 정기적으로 다시 평가합니다. 이 문제는 해당 [!UICONTROL trait]에 대해 자격이 있는 사용자 수가 시간이 지남에 따라 증가하거나 감소할 때 발생합니다. 이러한 행동은 매우 커지게 되는 특성에서 가장 뚜렷하게 나타난다. 예를 들어 알고리즘이 모델링에 [!UICONTROL trait A]을(를) 사용한다고 가정합니다. [!UICONTROL trait A]의 모집단이 증가하면 [!UICONTROL TraitWeight]이(가) 해당 [!UICONTROL trait]의 중요도를 다시 평가하여 낮은 점수를 할당하거나 무시할 수 있습니다. 이 경우 [!UICONTROL trait A]은(는) 너무 일반적이거나 커서 모집단에 대해 중요한 내용을 말할 수 없습니다. [!UICONTROL TraitWeight]이(가) [!UICONTROL trait A]의 값을 줄이면(또는 모델에서 이를 무시하면) 알고리즘 트레이트의 모집단이 줄어듭니다. 영향을 받는 [!UICONTROL traits] 목록은 기준 모집단의 진행 상황을 반영합니다. 영향력 있는 [!UICONTROL traits]의 목록을 사용하여 이러한 변경 내용이 발생하는 이유를 이해하십시오.

관련 링크:

* [모델 빌더](../../features/algorithmic-models/create-model.md)
* [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md)

## [!UICONTROL Look-Alike Models] 및 [!UICONTROL Traits]의 일정 업데이트 {#update-schedule}

신규 또는 기존 [!UICONTROL algorithmic models] 및 [!UICONTROL traits]에 대한 일정을 만들고 업데이트합니다.

### [!UICONTROL Look-Alike Model] 만들기 및 업데이트 일정

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
   <td colname="col2"> <p>새 [!UICONTROL Look-Alike Models] 또는 복제된 의 경우 만들기 프로세스가 매일 한 번씩 실행됩니다. 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> EST 오후 5시 (11월 - 3월) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 오후 6시 EDT(3월~11월) </li> 
     </ul> </p> <p>생성 기한 이후에 빌드되거나 복제된 모델은 다음 날 처리됩니다. </p> <p>모델의 첫 번째 실행에서 데이터가 생성되지 않으면 다음 날 두 번째로 실행됩니다. 두 번째 시도에서도 데이터가 생성되지 않으면 다음 날인 세 번째 시도가 있습니다. 세 번째 시도에서도 데이터가 생성되지 않으면 모델 실행이 중지됩니다. 이 경우 모델을 비활성화합니다. <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 유사 모델 문제 해결</a>에서 자세히 알아보세요. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>모델 업데이트</b> </td> 
   <td colname="col2"> <p>이상적인 조건에서 기존 모델은 최소 7일에 한 번, 평일에 실행됩니다. 예를 들어 월요일에 모델을 만드는 경우(기한까지) 늦어도 다음 월요일에는 업데이트됩니다. </p> <p>다음 조건 중 하나를 충족하면 모델이 다시 실행됩니다. </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">마지막 실행이 실패했습니다. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">이전에 성공적으로 실행되었으며 지난 7일 동안 전혀 실행되지 않았으며 모델에 하나 이상의 활성 트레이트가 연결되어 있습니다. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] 만들기 및 업데이트 일정

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
   <td colname="col2"> <p>트레이트 만들기 프로세스는 월요일부터 금요일까지 매일 실행됩니다. 일반적으로 새로운 알고리즘 트레이트는 48시간 이내에 UI에 표시됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>트레이트 업데이트</b> </td> 
   <td colname="col2"> <p>기존 트레이트는 7일에 한 번 이상 업데이트되며 모델 업데이트 일정을 따릅니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 모델 목록 보기 {#models-list-view}

목록 보기는 모델을 생성, 검토 및 관리하는 데 도움이 되는 중앙 작업 영역입니다.

[!UICONTROL Models] 목록 페이지에는 다음 작업을 수행하는 데 도움이 되는 기능과 도구가 포함되어 있습니다.

* 새 모델을 만듭니다.
* 기존 모델을 관리합니다(편집, 일시 중지, 삭제 또는 복제).
* 이름으로 모델을 검색합니다.
* 지정된 모델을 사용하여 [!UICONTROL algorithmic traits]을(를) 만듭니다.

## 모델 요약 보기 {#models-summary-view}

요약 페이지에는 모델에서 만든 이름, 도달/정확도, 처리 기록 및 [!UICONTROL traits] 등 모델 세부 정보가 표시됩니다. 이 페이지에는 모델을 만들고 관리할 수 있는 설정도 포함되어 있습니다. 요약 목록에서 모델 이름을 클릭하여 세부 정보를 확인합니다.

모델 요약 페이지에는 다음 섹션이 포함되어 있습니다.

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
   <td colname="col2"> <p>모델 이름, 마지막으로 실행된 시간 등 모델에 대한 기본 정보가 포함됩니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 도달 및 정확도</span> </p> </td> 
   <td colname="col2"> <p>마지막 모델 실행에 대해 <a href="../../features/traits/trait-accuracy-reach.md"> 정확도와 도달</a> 데이터를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 처리 기록</span> </p> </td> 
   <td colname="col2"> <p>최근 10번의 실행에 대한 처리 날짜 및 시간과 해당 실행에 데이터가 생성되었는지 여부를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle">개의 영향력 있는 트레이트</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">개의 영향력 있는 특성</span> 테이블: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 모델의 기준선 모집단에서 가장 잘 나타나는 영향력 있는 상위 50개 트레이트를 나열합니다. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">각 트레이트의 <span class="wintitle"> 상대 가중치</span> 순위 순서대로 순위를 지정합니다. <span class="wintitle"> 상대 가중치</span>은(는) 영향 또는 원하는 순서로 새로 검색된 트레이트를 정렬합니다. 중량 척도는 0%에서 100%까지 이어지는 백분율이다. 100%에 가까운 트레이트는 기준 모집단의 대상자와 더 비슷하다는 의미입니다. <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> TraitWeight 이해</a>를 참조하십시오. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">각 트레이트에 대한 30일 고유 수 및 총 트레이트 인구를 표시합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 모델을 사용하는 트레이트 <span class="wintitle">개</span> </p> </td>
   <td colname="col2"> <p>선택한 모델을 기반으로 알고리즘 트레이트 목록을 표시합니다. 트레이트에 대한 자세한 내용을 보려면 트레이트 이름 또는 트레이트 ID를 클릭하십시오. 알고리즘 특성 생성 프로세스로 이동하려면 <b><span class="uicontrol"> </span></b>(으)로 새 특성 만들기 를 선택합니다. </p> <p>섹션 레이블은 모델 이름에 따라 변경됩니다. 예를 들어 모델을 만들고 이름을 모델 A로 지정한다고 가정해 보겠습니다. 요약 페이지를 로드하면 이 섹션의 이름이 모델 A</span>을(를) 사용하는 트레이트 <span class="wintitle">개로 변경됩니다. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [대상](../../features/destinations/destinations.md)
>* [트레이트](../../features/traits/trait-details-page.md)
>* [세그먼트](../../features/segments/segments-purpose.md)
