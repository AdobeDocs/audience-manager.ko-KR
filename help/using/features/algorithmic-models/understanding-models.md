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
source-wordcount: '1576'
ht-degree: 1%

---

# 이해 [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 다음을 사용하여 새 사용자 찾기 [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] 는 자동화된 데이터 분석을 통해 새롭고 고유한 대상을 발견할 수 있도록 지원합니다. 을(를) 선택하면 프로세스가 시작됩니다 [!UICONTROL trait] 또는 [!UICONTROL segment], 시간 간격, 자사 및 타사 [!UICONTROL data sources]. 선택 항목은 알고리즘 모델에 대한 입력을 제공합니다. Analytics 프로세스가 실행되면 선택한 모집단의 공유 특성을 기반으로 적합한 사용자를 찾습니다. 완료 시 이 데이터는에서 사용할 수 있습니다. [트레이트 빌더](../../features/traits/about-trait-builder.md) 를 사용하여 를 기반으로 트레이트를 만들 수 있는 위치 [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md). 또한 알고리즘 트레이트를 와 결합하는 세그먼트를 만들 수 있습니다 [!UICONTROL rules-based traits] 및 을 사용하여 기타 자격 요구 사항 추가 [!DNL Boolean] 표현식 및 비교 연산자. [!UICONTROL Look-Alike Modeling] 는 사용 가능한 모든 트레이트 데이터에서 값을 추출하는 동적 방법을 제공합니다.

## 장점 {#advantages}

를 사용할 때의 주요 이점 [!UICONTROL Look-Alike Modeling] 포함:

* **데이터 정확도:** 알고리즘은 정기적으로 실행되므로 결과를 최신 상태로 유지하는 데 도움이 됩니다.
* **자동화:** 대규모 정적 규칙 세트를 관리할 필요는 없습니다. 알고리즘이 사용자를 위한 대상을 찾습니다.
* **시간 절약 및 노력 감소:** 모델링 프로세스를 통해 다음을 추측할 필요가 없습니다. [!UICONTROL traits]/[!UICONTROL segments] 는 캠페인에 리소스를 투입하여 새로운 대상자를 발견할 수 있습니다. 모델이 이 작업을 수행할 수 있습니다.
* **안정성:** 모델링은 사용자 자신의 데이터와 액세스 권한이 있는 선택한 타사 데이터를 평가하는 서버측 검색 및 자격 부여 프로세스와 함께 작동합니다. 즉, 사이트에서 방문자를 보고 트레이트에 대한 자격을 얻을 필요가 없습니다.

## 워크플로 {#workflow}

에서 모델을 관리합니다. **[!UICONTROL Audience Data > Models]**. 높은 수준에서 워크플로 프로세스에는 다음이 포함됩니다.

* 알고리즘에서 평가할 기준 데이터를 선택합니다. 여기에는 다음이 포함됩니다. [!UICONTROL trait] 또는 [!UICONTROL segment], 시간 범위 및 [!UICONTROL data sources] (이미 을 통해 액세스할 수 있는 자체 데이터 및 타사 데이터) [!DNL Audience Manager]). 모델 생성 워크플로우에서 다음을 제외할 수 있습니다. [!UICONTROL traits] 모델을 방해하고 싶지 않다는 뜻입니다.
* 모델을 저장합니다. 저장되면 알고리즘 평가 프로세스가 자동으로 실행됩니다. 단, 이 프로세스가 완료되는 데 최대 7일이 소요될 수 있습니다. [!DNL Audience Manager] 은 알고리즘이 완료되고 다음에 대한 결과를 사용할 수 있을 때 이메일을 보냅니다. [!UICONTROL trait] 생성.
* 알고리즘 빌드 [!UICONTROL traits] 위치: [!UICONTROL Trait Builder].
* 결합 [!UICONTROL traits] 대상 [!UICONTROL segments] 위치: [!UICONTROL Segment Builder].
* 만들기 및 보내기 [!UICONTROL segment] 에 데이터 보내기 [!UICONTROL destination].

## 문제 해결 {#troubleshooting}

모든 항목을 비활성화합니다. [!UICONTROL Look-Alike Model] 3회 연속 실행 시 데이터를 생성하지 못합니다. 이후에 모델의 상태를 다시 활성으로 설정할 수 없습니다. 모델이 데이터를 생성하도록 하려면 충분한 데이터 소스에서 모델을 만드는 것이 좋습니다 [!UICONTROL traits] 의 데이터를 누적합니다.

## 이해 [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] 는 새로운 을 검색하도록 설계된 독점 알고리즘입니다. [!UICONTROL traits] 자동으로 표시됩니다. 비교 [!UICONTROL trait] 현재 데이터 [!UICONTROL traits] 및 [!UICONTROL segments] 를 통해 액세스할 수 있는 다른 모든 자사 및 타사 데이터에 대해 [!DNL Audience Manager]. 다음에 대한 설명은 이 섹션 을 참조하십시오. [!UICONTROL TraitWeight] 알고리즘 검색 프로세스

![](assets/algo_model.png)

다음 단계에서는 [!UICONTROL TraitWeight] 평가 프로세스입니다.

### 1단계: 기준선 만들기 [!UICONTROL Trait] 비교

베이스라인을 작성하려면 [!UICONTROL TraitWeight] 다음을 모두 측정 [!UICONTROL traits] 30일, 60일 또는 90일 간격 동안 대상자와 연결됩니다. 다음으로, 순위 [!UICONTROL traits] 그들의 빈도와 상관관계에 따라서. 빈도 수는 공통성을 측정합니다. 상관 관계는 다음과 같은 가능성을 측정합니다. [!UICONTROL trait] 기준선 대상에만 표시됩니다. [!UICONTROL Traits] 종종 나타나는 것은 높은 공통성을 나타낸다고 하는데, 이는 과 결합할 때 가중 점수를 설정하는 데 사용되는 중요한 특성이다. [!UICONTROL traits] 선택한 항목에서 검색됨 [!UICONTROL data sources].

### 2단계: 동일한 항목 찾기 [!UICONTROL Traits] 다음에서 [!UICONTROL Data Source]

비교를 위해 기준선을 만들면 알고리즘이 동일한 항목을 찾습니다 [!UICONTROL traits] 선택한 항목에서 [!UICONTROL data sources]. 이 단계에서는 [!UICONTROL TraitWeight] 검색된 모든 항목의 빈도 수를 수행합니다. [!UICONTROL traits] 및 를 기준선과 비교합니다. 그러나 기준선과 달리 흔하지 않습니다 [!UICONTROL traits] 는 더 자주 나타나는 순위보다 높은 순위를 갖습니다. 희귀 [!UICONTROL traits] 고도의 특이성을 나타낸다고 합니다. [!UICONTROL TraitWeight] 공통 기준 조합 평가 [!UICONTROL traits] 및 일반적이지 않음(매우 구체적임) [!UICONTROL data source] [!UICONTROL traits] 보다 더 강력하거나 바람직한 [!UICONTROL traits] 두 데이터 세트 모두에 공통됩니다. 사실, 우리 모형은 이러한 크고 공통적인 것들을 인식한다 [!UICONTROL traits] 는 상관 관계가 높은 데이터 세트에 초과 우선 순위를 할당하지 않습니다. 희귀 [!UICONTROL traits] 보다 높은 우선 순위를 얻으십시오. 이는 보다 새롭고 고유한 사용자를 나타낼 가능성이 높기 때문입니다. [!UICONTROL traits] 전반적으로 공통점이 높음.

### 3단계: 가중치 지정

이 단계에서는 [!UICONTROL TraitWeight] 새로 발견된 순위 [!UICONTROL traits] 영향력 또는 바람직성의 순서로. 중량 척도는 0%에서 100%까지 이어지는 백분율이다. [!UICONTROL Traits] 100%에 가까운 순위는 기준 모집단의 대상자와 더 비슷하다는 것을 의미합니다. 또한 가중치가 매우 높음 [!UICONTROL traits] 는 기존의 기본 대상자와 유사하게 작동할 수 있는 새롭고 고유한 사용자를 나타내므로 중요합니다. 기억해, [!UICONTROL TraitWeight] 고려 사항 [!UICONTROL traits] 기준에서 높은 공통성과 비교된 데이터 소스에서 높은 특수성을 가지고보다 가치 있음 [!UICONTROL traits] 각 데이터 세트에 공통으로 사용됩니다.

### 4단계: 사용자 점수 지정

선택한 의 각 사용자 [!UICONTROL data sources] 은 영향력 있는 사용자의 모든 가중치의 합과 같은 사용자 점수를 부여합니다 [!UICONTROL traits] 사용자 프로필에 게시합니다. 그런 다음 사용자 점수가 0과 100% 사이에서 표준화됩니다.

### 5단계: 결과 표시 및 작업

[!DNL Audience Manager] 가중치가 적용된 모델의 결과를 [!UICONTROL Trait Builder]. 을(를) 빌드하려는 경우 [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] 을(를) 만들 수 있습니다. [!UICONTROL traits] 데이터 실행 중에 알고리즘에서 생성된 가중 점수를 기반으로 합니다. 높은 정확도를 선택하여 사용자 점수가 매우 높기 때문에 나머지 대상자가 아닌 기준 대상자와 매우 유사한 사용자에게만 자격을 부여할 수 있습니다. 더 많은 대상에 도달하려는 경우(도달) 정확도를 낮출 수 있습니다.

### 6단계: 의 중요도 재평가 [!UICONTROL Trait] 처리 주기 간

정기적으로, [!UICONTROL TraitWeight] 의 중요도 재평가 [!UICONTROL trait] 그 규모와 인구의 변화를 토대로 [!UICONTROL trait]. 해당 항목에 대해 자격이 있는 사용자 수로 발생합니다 [!UICONTROL trait] 시간이 지남에 따라 증가 또는 감소합니다. 이러한 행동은 매우 커지게 되는 특성에서 가장 뚜렷하게 나타난다. 예를 들어 알고리즘이 [!UICONTROL trait A] 모델링용입니다. 의 모집단으로 [!UICONTROL trait A] 증가, [!UICONTROL TraitWeight] 의 중요성 재평가 [!UICONTROL trait] 낮은 점수를 할당하거나 무시할 수 있습니다. 이 경우, [!UICONTROL trait A] 은 너무 흔하거나 커서 인구수에 대해 중요한 것을 말할 수 없습니다. 다음 이후 [!UICONTROL TraitWeight] 의 가치 감소 [!UICONTROL trait A] (또는 모델에서 이를 무시함) 알고리즘 트레이트의 모집단은 감소합니다. 영향력 있는 목록 [!UICONTROL traits] 기준선 모집단의 진화를 반영합니다. 영향력 있는 사용자 목록 사용 [!UICONTROL traits] 이러한 변경 사항이 발생하는 이유를 이해할 수 있습니다.

관련 링크:

* [모델 빌더](../../features/algorithmic-models/create-model.md)
* [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md)

## 다음에 대한 일정 업데이트 [!UICONTROL Look-Alike Models] 및 [!UICONTROL Traits] {#update-schedule}

신규 또는 기존 일정 생성 및 업데이트 [!UICONTROL algorithmic models] 및 [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] 일정 만들기 및 업데이트

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
   <td colname="col2"> <p>신규 또는 복제의 경우 [!UICONTROL Look-Alike Models], 만들기 프로세스는 하루에 한 번 실행됩니다. 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> EST 오후 5시 (11월 - 3월) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 오후 6시 EDT(3월~11월) </li> 
     </ul> </p> <p>생성 기한 이후에 빌드되거나 복제된 모델은 다음 날 처리됩니다. </p> <p>모델의 첫 번째 실행에서 데이터가 생성되지 않으면 다음 날 두 번째로 실행됩니다. 두 번째 시도에서도 데이터가 생성되지 않으면 다음 날인 세 번째 시도가 있습니다. 세 번째 시도에서도 데이터가 생성되지 않으면 모델 실행이 중지됩니다. 이 경우 모델을 비활성화합니다. 다음에서 자세히 보기 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 유사 모델 문제 해결</a>. </p> </td>
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

### [!UICONTROL Look-Alike Trait] 일정 만들기 및 업데이트

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

다음 [!UICONTROL Models] 목록 페이지에는 다음 작업을 수행하는 데 도움이 되는 기능 및 도구가 포함되어 있습니다.

* 새 모델을 만듭니다.
* 기존 모델을 관리합니다(편집, 일시 중지, 삭제 또는 복제).
* 이름으로 모델을 검색합니다.
* 만들기 [!UICONTROL algorithmic traits] 주어진 모델을 사용합니다.

## 모델 요약 보기 {#models-summary-view}

요약 페이지에는 이름, 도달/정확도, 처리 내역 및 [!UICONTROL traits] 모델에서 생성됨. 이 페이지에는 모델을 만들고 관리할 수 있는 설정도 포함되어 있습니다. 요약 목록에서 모델 이름을 클릭하여 세부 정보를 확인합니다.

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
   <td colname="col1"> <p> <span class="wintitle"> 모델 도달 범위 및 정확도</span> </p> </td> 
   <td colname="col2"> <p>표시 <a href="../../features/traits/trait-accuracy-reach.md"> 정확성 및 도달 범위</a> 마지막 모델 실행에 대한 데이터입니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 처리 기록</span> </p> </td> 
   <td colname="col2"> <p>최근 10번의 실행에 대한 처리 날짜 및 시간과 해당 실행에 데이터가 생성되었는지 여부를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 영향력 있는 트레이트</span> </p> </td> 
   <td colname="col2"> <p>다음 <span class="wintitle"> 영향력 있는 트레이트</span> 표: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 모델의 기준선 모집단에서 가장 잘 나타나는 영향력 있는 상위 50개 트레이트를 나열합니다. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">각 트레이트의 순위를 순서대로 매깁니다. <span class="wintitle"> 상대 가중치</span> 등급. 다음 <span class="wintitle"> 상대 가중치</span> 영향 또는 바람직성의 순서로 새로 검색된 트레이트를 정렬합니다. 중량 척도는 0%에서 100%까지 이어지는 백분율이다. 100%에 가까운 트레이트는 기준 모집단의 대상자와 더 비슷하다는 의미입니다. 다음을 참조하십시오 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> TraitWeight 이해</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">각 트레이트에 대한 30일 고유 수 및 총 트레이트 인구를 표시합니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델을 사용한 트레이트</span> </p> </td>
   <td colname="col2"> <p>선택한 모델을 기반으로 알고리즘 트레이트 목록을 표시합니다. 트레이트에 대한 자세한 내용을 보려면 트레이트 이름 또는 트레이트 ID를 클릭하십시오. 선택 <b><span class="uicontrol"> 모델을 사용하여 새 트레이트 만들기</span></b> 알고리즘 트레이트 만들기 프로세스로 이동합니다. </p> <p>섹션 레이블은 모델 이름에 따라 변경됩니다. 예를 들어 모델을 만들고 이름을 모델 A로 지정한다고 가정해 보겠습니다. 요약 페이지를 로드하면 이 섹션의 이름이 로 변경됩니다. <span class="wintitle"> 모델 A를 사용한 트레이트</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [대상](../../features/destinations/destinations.md)
>* [트레이트](../../features/traits/trait-details-page.md)
>* [세그먼트](../../features/segments/segments-purpose.md)

