---
description: 유사 모델링에 사용된 트레이트 또는 세그먼트를 작성하고 관리할 수 있습니다.
keywords: relative weight, lookalike
seo-description: 유사 모델링에 사용된 트레이트 또는 세그먼트를 작성하고 관리할 수 있습니다.
seo-title: 유사 모델링 정보
solution: Audience Manager
title: 유사 모델링 정보
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 1%

---


# 이해 [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## 새 사용자 찾기 [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] 자동화된 데이터 분석을 통해 고유한 새로운 고객을 발견할 수 있습니다. 프로세스는 [!UICONTROL trait] 또는, 시간 간격, 첫 번째 및 [!UICONTROL segment]제3자를 선택하면 시작됩니다 [!UICONTROL data sources]. 선택 사항은 알고리즘 모델에 대한 입력을 제공합니다. 분석 프로세스가 실행될 때 선택한 모집단에서 공유된 특성을 기반으로 적격한 사용자를 찾습니다. 완료되면 이 데이터를 [특성 빌더에서](../../features/traits/about-trait-builder.md) 사용할 수 있습니다. 여기에서 [정확도와 도달](../../features/traits/trait-accuracy-reach.md)수를 기반으로 트레이트를 만들 수 있습니다. 또한 알고리즘 특성을 결합하는 세그먼트를 만들고 표현식 및 비교 연산자로 기타 자격 요구 사항 [!UICONTROL rules-based traits] 을 추가할 수 [!DNL Boolean] 있습니다. [!UICONTROL Look-Alike Modeling] 사용 가능한 모든 트레이트 데이터에서 값을 추출하는 다이내믹한 방법을 제공합니다.

## 장점 {#advantages}

다음을 사용하여 얻을 수 있는 주요 이점은 다음과 [!UICONTROL Look-Alike Modeling] 같습니다.

* **데이터 정확도:** 알고리즘이 정기적으로 실행되므로 결과를 최신 상태로 유지하고 연관성을 유지할 수 있습니다.
* **자동화:** 대량의 정적 규칙을 관리할 필요가 없습니다. 알고리즘에서 사용자를 찾습니다.
* **시간을 절약하고 노력을 줄일 수 있습니다.** 모델링 프로세스를 통해 어떤 [!UICONTROL traits]/[!UICONTROL segments] 리소스가 효과적인지 추측하거나 새로운 고객을 찾기 위해 캠페인에 시간을 허비하지 않아도 됩니다. 모델이 해줄 수 있습니다.
* **안정성:** 모델링 작업은 사용자 자신의 데이터와 액세스 권한이 있는 타사 데이터를 평가하는 서버측 검색 및 검증 프로세스와 연동됩니다. 즉, 사이트 방문자가 트레이트 자격을 갖추도록 방문자를 확인할 필요가 없습니다.

## 워크플로우 {#workflow}

모델을 관리할 수 있습니다 **[!UICONTROL Audience Data > Models]**. 높은 수준의 워크플로우 프로세스에는 다음이 포함됩니다.

* 알고리즘을 평가할 기준 데이터를 선택합니다. 여기에는 [!UICONTROL trait] 또는 [!UICONTROL segment], 시간 범위 및 [!UICONTROL data sources] (이미 액세스할 수 있는 사용자 자신의 데이터 및 타사 데이터 [!DNL Audience Manager])가 포함됩니다. 모델 생성 워크플로우에서 모델 [!UICONTROL traits] 을 방해하지 않을 항목을 제외할 수 있습니다.
* 모델을 저장합니다. 일단 저장되면 알고리즘 평가 프로세스가 자동으로 실행됩니다. 그러나 이 프로세스를 완료하는 데 최대 7일이 걸릴 수 있습니다. [!DNL Audience Manager] 알고리즘이 완료되고 결과를 만들 수 있을 때 이메일을 [!UICONTROL trait] 보냅니다.
* 알고리즘 [!UICONTROL traits] 구축 [!UICONTROL Trait Builder].
* 여러 구성 요소 [!UICONTROL traits] 를 결합할 수 [!UICONTROL segments] 있습니다 [!UICONTROL Segment Builder].
* 데이터를 만들어 [!UICONTROL segment] A로 보냅니다 [!UICONTROL destination].

## 문제 해결 {#troubleshooting}

Adobe는 연속해서 3회 동안 데이터를 생성하지 [!UICONTROL Look-Alike Model] 못하는 모든 데이터를 비활성화합니다. 이후 모델의 상태를 다시 활성으로 설정할 수는 없습니다. 모델이 데이터를 생성하도록 하기 위해 데이터를 축적할 수 있는 충분한 데이터 소스에서 모델 [!UICONTROL traits] 을 만드는 것이 좋습니다.

## 이해 [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] 는 새로운 기능을 자동으로 검색하도록 설계된 독점 알고리즘입니다 [!UICONTROL traits] . 현재 데이터 [!UICONTROL trait] 및 [!UICONTROL traits] 액세스 권한이 있는 다른 모든 자사 데이터 및 타사 데이터와 [!UICONTROL segments] [!DNL Audience Manager]비교합니다. 알고리즘 검색 프로세스에 대한 설명은 이 섹션을 [!UICONTROL TraitWeight] 참조하십시오.

![](assets/algo_model.png)

다음 단계에서는 [!UICONTROL TraitWeight] 평가 프로세스에 대해 설명합니다.

### 1단계: 비교할 기준 [!UICONTROL Trait] 만들기

기준을 만들려면 30, 60 또는 90일 간격 동안 대상과 [!UICONTROL TraitWeight] [!UICONTROL traits] 연관된 모든 항목을 측정합니다. 그 다음, 그 빈도와 상관 관계 [!UICONTROL traits] 에 따라 순위를 매긴다. 빈도 수는 공통성을 측정합니다. 상관 관계는 기준선 대상자만 [!UICONTROL trait] 존재할 가능성을 측정합니다. [!UICONTROL Traits] 이러한 현상은 종종 선택된 영역에서 발견된 점수와 결합할 때 가중 점수를 설정하는 데 사용되는 중요한 특성인 높은 공통성을 [!UICONTROL traits] 나타낸다고 합니다 [!UICONTROL data sources].

### 2단계: Find the Same [!UICONTROL Traits] in the [!UICONTROL Data Source]

비교할 기준선을 빌드한 후 알고리즘이 선택한 항목 [!UICONTROL traits] 에서 동일하게 보입니다 [!UICONTROL data sources]. 이 단계에서 검색된 모든 항목 [!UICONTROL TraitWeight] 의 주파수 카운트를 수행하고 기준 요소 [!UICONTROL traits] 와 비교합니다. 하지만 기준선과 달리, 일반적이지 않은 [!UICONTROL traits] 것은 더 자주 나타나는 기준보다 높은 순위를 차지합니다. 희귀 [!UICONTROL traits] 는 높은 수준의 특질을 나타낸다고 한다. [!UICONTROL TraitWeight] 두 데이터 세트에 공통으로 사용되는 것보다 [!UICONTROL traits] 는 [!UICONTROL data source] 더 영향력이 [!UICONTROL traits] 많거나 바람직한 것처럼 일반적인 기준 [!UICONTROL traits] 과 일반적이지 않은(매우 특수함) 조합을평가합니다. 실제로 Adobe 모델은 이러한 큰 공통으로 인식하며 상관 관계가 높은 데이터 세트 [!UICONTROL traits] 에 과도한 우선 순위를 할당하지 않습니다. 드물지만 [!UICONTROL traits] 우선순위가 높은 이유는 보드 전반의 공통성이 높은 사용자보다 새롭고 독특한 사용자 [!UICONTROL traits] 를 나타낼 가능성이 높기 때문입니다.

### 3단계: 두께 지정

이 단계에서, 영향력 [!UICONTROL TraitWeight] 과 부적격성 [!UICONTROL traits] 으로 새롭게 발견된 순위를 매긴다. 중량 척도는 0%에서 100%까지 가는 백분율입니다. [!UICONTROL Traits] 순위가 100%에 가까울수록 기준 모집단 내 대상과 더 비슷해집니다. 또한, 기준선 대상과 유사하게 행동할 수 있는 새로운 고유 사용자를 나타내므로 무거운 가중치가 [!UICONTROL traits] 있는 것이 중요합니다. 비교 [!UICONTROL TraitWeight] 데이터 소스 [!UICONTROL traits] 의 기준선 및 높은 규격에서 높은 공통성과 함께 고려해 볼 때 각 데이터 세트에서 [!UICONTROL traits] 공통되는 것보다 더 가치가 높습니다.

### 4단계: 점수 사용자

선택한 각 사용자 [!UICONTROL data sources] 에게 해당 사용자 프로필의 영향력 있는 가중치의 모든 가중치 [!UICONTROL traits] 의 합과 같은 사용자 점수가 부여됩니다. 그런 다음 사용자 점수가 0~100% 사이로 표준화됩니다.

### 5단계: 결과 표시 및 작업

[!DNL Audience Manager] 가중치가 적용된 모델 결과를 표시합니다 [!UICONTROL Trait Builder]. 빌드할 경우 데이터 실행 중 알고리즘에 의해 생성된 가중치가 적용된 점수를 [!UICONTROL algorithmic trait][!UICONTROL Trait Builder] [!UICONTROL traits] 기반으로 만들 수 있습니다. 높은 정확도를 선택하여 사용자 점수가 매우 높으므로 나머지 대상이 아니라 기본 대상자와 매우 비슷한 사용자만 평가할 수 있습니다. 더 많은 고객(도달)에게 도달하려면 정확도를 낮출 수 있습니다.

### 6단계: 전체 처리 주기 [!UICONTROL Trait] 의 중요성 재평가

크기 및 해당 모집단 [!UICONTROL TraitWeight] 의 변화를 [!UICONTROL trait] 기반으로 한 중요도를 주기적으로 재평가합니다 [!UICONTROL trait]. 이렇게 되면 자격을 갖춘 사용자 수가 시간이 지남에 따라 [!UICONTROL trait] 늘어나거나 줄어듭니다. 이러한 행동은 매우 커지는 특성들에서 가장 선명하게 보입니다. 예를 들어 알고리즘이 모델링에 [!UICONTROL trait A] 를 사용한다고 가정합니다. 인구가 증가함에 따라, 그 중요도를 [!UICONTROL trait A] 다시 평가하고 더 낮은 점수를 [!UICONTROL TraitWeight] [!UICONTROL trait] 지정하거나 무시해도 됩니다. 이 경우, 인구 [!UICONTROL trait A] 에 대해 의미 있는 것은 말할 수 없을 정도로 흔하거나 크다. 값 [!UICONTROL TraitWeight] 을 [!UICONTROL trait A] (또는 모델에서 무시)하면 알고리즘 트레이트의 모집단도 줄어듭니다. 영향력 있는 목록의 [!UICONTROL traits] 내용은 기준 인구의 진화를 반영합니다. 이러한 변경 사항이 발생하는 이유를 [!UICONTROL traits] 이해하려면 영향력 있는 사람의 목록을 사용하십시오.

관련 링크:

* [모델 빌더](../../features/algorithmic-models/create-model.md)
* [정확성 및 도달 범위](../../features/traits/trait-accuracy-reach.md)

## 및 [!UICONTROL Look-Alike Models] 에 대한 업데이트 일정 [!UICONTROL Traits] {#update-schedule}

신규 또는 기존 및 기존 [!UICONTROL algorithmic models] 에 대한 스케줄 생성 및 갱신 [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] 작성 및 업데이트 일정

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
   <td colname="col2"> <p>새 모델 또는 복제된 [!UICONTROL 유사 모델]의 경우 작성 프로세스는 다음 위치에서 하루에 한 번 실행됩니다. 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 오후 5시 EST (11월 - 3월) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> PM EDT(3월 - 11월) </li> 
     </ul> </p> <p>작성 마감 시간 이후에 빌드되거나 복제된 모델은 다음 날에 처리됩니다. </p> <p>모델의 첫 번째 실행에서 데이터가 생성되지 않으면 두 번째 실행, 그 다음 날. 두 번째 시도에서도 데이터가 생성되지 않으면 다음 날 세 번째 시도가 발생합니다. 세 번째 시도에서도 데이터가 생성되지 않으면 모델이 실행되지 않습니다. 이 경우 모델을 비활성화합니다. 유사 모델 문제 <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> 해결에서 자세한 내용을 참조하십시오</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>모델 업데이트</b> </td> 
   <td colname="col2"> <p>이상적인 조건 하에서, 기존 모델은 7일에 한 번 이상 주중에 실행됩니다. 예를 들어, 월요일에 모델(마감 시간)을 만들면 다음 월요일이 최신 상태로 업데이트됩니다. </p> <p>모델이 다음 조건을 충족하면 다시 실행됩니다. </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">마지막 출장이 안 되었다. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">이 속성은 IT 이전에 성공적으로 실행되었으며 지난 7일 동안 전혀 실행되지 않았습니다. 이 모델에 하나 이상의 활성 특성이 연결되어 있습니다. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] 작성 및 업데이트 일정

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
   <td colname="col2"> <p>특성 생성 프로세스는 매일, 월요일부터 금요일까지 실행됩니다. 일반적으로 새로운 알고리즘 특성이 48시간 이내에 UI에 나타납니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>특성 업데이트</b> </td> 
   <td colname="col2"> <p>기존 트레이트는 7일에 한 번 이상 업데이트되며 모델 업데이트 일정을 따릅니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 모델 목록 보기 {#models-list-view}

목록 보기는 모델을 생성, 검토 및 관리하는 데 도움이 되는 중앙 작업 공간입니다.

목록 [!UICONTROL Models] 페이지에는 다음과 같은 유용한 기능과 도구가 포함되어 있습니다.

* 새로운 모델 제작
* 기존 모델 관리(편집, 일시 중지, 삭제 또는 복제)
* 이름별로 모델을 검색합니다.
* 주어진 모델을 [!UICONTROL algorithmic traits] 사용하여 작성합니다.

## 모델 요약 보기 {#models-summary-view}

요약 페이지에는 이름, 도달/정확도, 처리 내역 및 모델에서 생성된 모델 세부 사항 [!UICONTROL traits] 이 표시됩니다. 또한 이 페이지에는 모델을 만들고 관리할 수 있는 설정도 포함되어 있습니다. 요약 목록에서 모델 이름을 클릭하여 세부 사항을 확인합니다.

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
   <td colname="col2"> <p>모델의 이름 및 마지막으로 실행된 시간과 같은 기본 정보를 포함합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 도달 및 정확도</span> </p> </td> 
   <td colname="col2"> <p>마지막 모델 실행에 대한 <a href="../../features/traits/trait-accuracy-reach.md"> 정확도와 도달</a> 데이터를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델 처리 내역</span> </p> </td> 
   <td colname="col2"> <p>마지막 10개 실행에 대한 처리 날짜 및 시간과 해당 실행에 데이터가 생성되었는지 여부를 표시합니다. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 영향력 있는 특성</span> </p> </td> 
   <td colname="col2"> <p>영향력 있는 <span class="wintitle"> 특성</span> 표: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> 모델의 기준선 모집단에서 가장 잘 나타내는 상위 50개의 영향력 있는 트레이트가 나열됩니다. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">각 트레이트의 <span class="wintitle"> 상대적 무게</span> 등급 순서로 등급을 지정합니다. 상대적 무게 <span class="wintitle"> 는</span> 영향이나 designment 순으로 새롭게 발견된 특성을 정렬합니다. 중량 척도는 0%에서 100%까지 가는 백분율입니다. 트레이트가 100%에 가까울수록 기준선 모집단 내 대상과 더 비슷하다는 것을 의미합니다. 트레이트 가중치 <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> 이해를 참조하십시오</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">각 트레이트에 대한 총 30일 고유 수와 총 특성 인구를 보여줍니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> 모델을 사용한 트레이트</span> </p> </td>
   <td colname="col2"> <p>선택한 모델을 기반으로 알고리즘 트레이트 목록을 표시합니다. 트레이트에 대한 자세한 내용을 보려면 트레이트 이름이나 트레이트 ID를 클릭합니다. 모델을 사용하여 <b><span class="uicontrol"> 새 특성</span></b> 만들기를 선택하여 알고리즘 특성 생성 프로세스로 이동합니다. </p> <p>단면 레이블은 모델 이름을 기준으로 변경됩니다. 예를 들어 모델을 만들고 모델 A로 이름을 지정합니다. 요약 페이지를 로드할 때 이 섹션의 이름이 모델 A를 사용하여 <span class="wintitle"> 트레이트로 변경됩니다</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [대상](../../features/destinations/destinations.md)
>* [트레이트](../../features/traits/trait-details-page.md)
>* [세그먼트](../../features/segments/segments-purpose.md)

