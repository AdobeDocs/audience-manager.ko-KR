---
description: 세그먼트 빌더에서 최근 및 빈도를 사용하면 설정된 일별 간격에 대해 발생 또는 반복되는 작업을 기준으로 방문자를 세그먼트화할 수 있습니다.
seo-description: 세그먼트 빌더에서 최근 및 빈도를 사용하면 설정된 일별 간격에 대해 발생 또는 반복되는 작업을 기준으로 방문자를 세그먼트화할 수 있습니다.
seo-title: 최신성 및 빈도
solution: Audience Manager
title: 최신성 및 빈도
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 3%

---


# 최신성 및 빈도 {#recency-and-frequency}

[!UICONTROL Segment Builder]에서 최근 및 빈도로 설정된 일별 간격에 대해 발생 또는 반복되는 작업을 기준으로 방문자를 세그먼트화할 수 있습니다.

Audience Manager은 다음과 같이 [!DNL recency] 및 [!DNL frequency]을 정의합니다.

* **[!UICONTROL Recency]:** 사용자가 한 명 이상의 콘텐트를 보고 자격을 갖춘 최근  [!UICONTROL traits]정보입니다.
* **[!UICONTROL Frequency]:** 사용자가 한 명 이상의 사용자에게 열람하거나 자격이 부여된  [!UICONTROL traits]비율입니다.

[!UICONTROL Recency] 및  [!UICONTROL Frequency] 설정을 사용하면 사이트, 섹션 또는 특정 크리에이티브 방문자의 실제(또는 인지) 관심도를 기반으로 방문자를 세그먼트화할 수 있습니다. 예를 들어 최근/빈도 요구 사항이 높은 세그먼트에 적합한 사용자는 방문 빈도가 낮거나 방문 횟수가 적은 사용자보다 사이트 또는 제품에 더 관심을 가질 수 있습니다.

## [!UICONTROL Recency and Frequency] 설정 {#location} 위치

[!UICONTROL Segment Builder]에서 [!UICONTROL Recency] 및 [!UICONTROL Frequency] 설정은 [!UICONTROL Traits] 패널의 [!UICONTROL Basic View] 섹션에 있습니다. 이러한 컨트롤을 표시하려면 시계 아이콘을 클릭합니다.

![](assets/recency_frequency.png)

## 제한 및 규칙 {#limitations-rules}

세그먼트의 트레이트에 최근 및 빈도를 적용하려는 경우 이러한 제한 사항과 규칙을 검토하고 이해합니다.

### [!UICONTROL Recency] {#recency}

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 제한 또는 규칙 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>최소 값</b> </p> </td> 
   <td colname="col2"> <p>최근 값은 0보다 커야 합니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>특성 유형</b> </p> </td> 
   <td colname="col2"> <p>최근 컨트롤을 규칙 기반 및 폴더 특성에만 적용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>타사 트레이트</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트를 포함하는 개별 타사 트레이트 또는 트레이트 그룹에 대해 최근 규칙을 설정할 수 없습니다. 최근 및 빈도는 고유한 특성에만 적용됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL Frequency] {#frequency}

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 제한 또는 규칙 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>타사 트레이트</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트를 포함하는 개별 타사 트레이트 또는 트레이트 그룹에 대해 빈도 규칙을 설정할 수 없습니다. 최근 및 빈도는 고유한 특성에만 적용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>특성 유형</b> </p> </td> 
   <td colname="col2"> <p>빈도 컨트롤을 규칙 기반 및 폴더 특성에만 적용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>최근 요구 사항</b> </p> </td> 
   <td colname="col2"> <p>최근 요구 사항을 구성하지 않고 빈도 요구 사항 <i>을 구성할 수 있습니다. </i> 주파수 값을 설정하고 최근 필드를 비워 두면 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>프로필 병합 규칙</b> </p> </td> 
   <td colname="col2"> <p><a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 특성 빈도, 외부 장치 그래프 및 프로필 병합 규칙</a>을 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 최근 예 {#recency-examples}

다음은 UI에서 선택한 내용에 따라 최근 기능이 작동하는 두 가지 예입니다.

### 보다 작거나 같음 연산자(&lt;=) 사용

![작거나 같음](assets/less-than-equal-to.png)

이 예에서는 스크린샷에 표시된 것처럼 &lt;= 연산자를 선택합니다. 사용자가 지난 5일 이내에 최소 3회 [!UICONTROL traits] 중 하나를 받을 수 있는 경우 이 자격 조건은 사용자가 [!UICONTROL segment]에 가입해야 합니다. 아래 타임라인에는 [!UICONTROL segment]이(가) 생성될 때의 [!UICONTROL segment] 자격, 10월 1일, 그 후 10일이 표시됩니다.

![지난 5일](assets/last-5-days.png)

### 보다 크거나 같은 연산자(=>) 사용

![크거나 같음](assets/greater-than-equal-to.png)

이 예에서는 스크린샷에 표시된 대로 => 연산자를 선택합니다. 사용자가 Audience Manager 플랫폼에서 첫 번째 자격 조건과 5일 전 잘라내기 시간 사이에 언제든지 최소 3회의 [!UICONTROL traits] 중 하나를 받을 수 있는 경우 이 자격 조건은 사용자가 [!UICONTROL segment]에 참여할 수 있는 자격이 됩니다. 아래 타임라인에는 [!UICONTROL segment]이(가) 생성될 때의 [!UICONTROL segment] 자격, 10월 1일, 그 후 10일이 표시됩니다.

![이전 자격 조건](assets/earlier-qualification.png)


## 주파수 매핑 예 {#frequency-capping}

빈도 매핑 식에는 [!UICONTROL trait] 재지정 수가 원하는 값 미만인 모든 사용자가 포함됩니다. 다음은 몇 가지 옳고 그른 예입니다.

* 틀림 - `frequency([1000T]) <= 5` 식에는 ID가 &quot;1000&quot;인 [!UICONTROL trait]을(를) 최대 5회까지 인식했지만 [!UICONTROL trait]을(를) 깨닫지 못한 사용자가 모두 포함됩니다. 따라서 Audience Manager은 [!UICONTROL segment]에 너무 많은 사용자를 사용할 수 있기 때문에 성능상의 이유로 이 식의 유효성을 검사하지 않습니다.

* 오른쪽 - ID가 &quot;1000&quot;인 [!UICONTROL trait]을 최대 5회까지 실현한 모든 사용자를 포함하려면 표현식에 다른 조건을 추가하여 사용자가 [!UICONTROL trait]에 대해 적어도 한 번 이상 자격이 있는지 확인합니다. `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 오른쪽 - 최근/빈도 요구 사항이 특정 횟수나 일수 보다 작아야 하는 경우 [!UICONTROL trait]을 `AND` 연산자로 다른 항목에 연결합니다. 첫 번째 글머리 기호 예제에서 이 표현식은 다음과 같이 다른 [!UICONTROL trait]과 결합하면 유효합니다.`frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 오른쪽 - 광고 빈도-매핑 사용 사례의 경우 이와 유사한 [!UICONTROL segment] 규칙을 만들 수 있습니다.`(frequency([1000T] <= 2D) >= 5)`. 이 표현식에는 지난 2일 동안 최소 5회 동안 ID가 &quot;1000&quot;인 [!UICONTROL trait]을(를) 실현한 모든 사용자가 포함됩니다. 광고 서버의 [!UICONTROL segment]에 `NOT`이 설정된 광고 서버로 이 [!UICONTROL segment]을(를) 전송하여 빈도 매핑을 설정합니다. 이 접근 방식은 주파수 캡핑을 위해 동일한 용도로 제공하면서 [!DNL Audience Manager]에서 더 큰 성능을 얻습니다.

>[!MORELIKETHIS]
>
>* [세그먼트 빌더 컨트롤:트레이트 섹션](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [세그먼트 표현식 편집기에 사용되는 코드 구문](../../features/segments/segment-code-syntax.md)

