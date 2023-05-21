---
description: 세그먼트 빌더에서 최신성과 빈도를 사용하면 설정된 일별 간격 동안 발생하거나 반복되는 작업을 기준으로 방문자를 세그먼트화할 수 있습니다.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: 최신성 및 빈도
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: Segments
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 2%

---

# 최신성 및 빈도 {#recency-and-frequency}

위치 [!UICONTROL Segment Builder], 최신성 및 빈도 를 사용하면 설정된 일별 간격 동안 발생하거나 반복하는 작업에 따라 방문자를 세그먼트화할 수 있습니다.

Audience Manager 정의 [!DNL recency] 및 [!DNL frequency] 다음과 같이:

* **[!UICONTROL Recency]:** 최근 사용자가 조회하거나 한 개(또는 그 이상)에 대한 자격이 있는 시점 [!UICONTROL traits].
* **[!UICONTROL Frequency]:** 사용자가 하나(또는 그 이상)를 보았거나 자격이 있는 비율입니다. [!UICONTROL traits].

[!UICONTROL Recency] 및 [!UICONTROL Frequency] 설정을 사용하면 사이트, 섹션 또는 특정 크리에이티브에 대한 실제(또는 인지된) 관심 수준에 따라 방문자를 세그먼트화할 수 있습니다. 예를 들어, 최신성/빈도 요구 사항이 높은 세그먼트에 대한 자격이 있는 사용자는 자주 또는 덜 자주 방문하는 사용자보다 사이트 또는 제품에 더 관심이 있을 수 있습니다.

## 위치 [!UICONTROL Recency and Frequency] 설정 {#location}

위치 [!UICONTROL Segment Builder], [!UICONTROL Recency] 및 [!UICONTROL Frequency] 설정은 [!UICONTROL Basic View] 의 섹션 [!UICONTROL Traits] 패널. 시계 아이콘을 클릭하여 이러한 컨트롤을 표시합니다.

![](assets/recency_frequency.png)

## 제한 사항 및 규칙 {#limitations-rules}

세그먼트의 트레이트에 최신성과 빈도를 적용하려는 경우 이러한 제한 사항과 규칙을 검토하고 이해합니다.

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
   <td colname="col2"> <p>최신성은 0보다 커야 합니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>트레이트 유형</b> </p> </td> 
   <td colname="col2"> <p>규칙 기반 및 폴더 트레이트에만 최신성 제어를 적용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>타사 트레이트</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트가 포함된 개별 타사 트레이트 또는 트레이트 그룹에 대해 최신성 규칙을 설정할 수 없습니다. 최신성과 빈도는 고유한 트레이트에만 적용됩니다. </p> </td> 
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
   <td colname="col2"> <p>개별 타사 트레이트 또는 타사 트레이트가 포함된 트레이트 그룹에 대해 빈도 규칙을 설정할 수 없습니다. 최신성과 빈도는 고유한 트레이트에만 적용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>트레이트 유형</b> </p> </td> 
   <td colname="col2"> <p>규칙 기반 및 폴더 트레이트에만 빈도 컨트롤을 적용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>최신성 요구 사항</b> </p> </td> 
   <td colname="col2"> <p>빈도 요구 사항을 구성할 수 있습니다 <i>없이</i> 최신성 요구 사항 구성. 빈도 값을 설정하고 최신성 필드를 비워 두면 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>프로필 병합 규칙</b> </p> </td> 
   <td colname="col2"> <p>다음을 참조하십시오 <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 트레이트 빈도, 외부 장치 그래프 및 프로필 병합 규칙</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 최신성 예 {#recency-examples}

다음은 UI에서 선택한 항목에 따라 최신이 작동하는 방식에 대한 두 가지 예입니다.

### 작거나 같음 연산자 사용(&lt;=)

![보다 작음](assets/less-than-equal-to.png)

이 예제에서는 스크린샷에 표시된 대로 &lt;= 연산자를 선택합니다. 이렇게 하면 사용자에게 다음 자격이 부여됩니다. [!UICONTROL segment] 셋중 어느 하나라도 해당될 때에는 [!UICONTROL traits] 지난 5일 동안 최소 3번. 아래 타임라인에는 다음 항목이 표시됩니다. [!UICONTROL segment] 다음 시점의 자격 요건 [!UICONTROL segment] 는 10월 1일에 만들어지고 10일 후에 만들어집니다.

![최근 5일](assets/last-5-days.png)

### 보다 크거나 같은 연산자 사용(=>)

![크거나 같음](assets/greater-than-equal-to.png)

이 예제에서는 스크린샷에 표시된 대로 => 연산자를 선택합니다. 이렇게 하면 사용자에게 다음 자격이 부여됩니다. [!UICONTROL segment] 셋중 어느 하나라도 해당될 때에는 [!UICONTROL traits] Audience Manager 플랫폼에서의 첫 자격과 5일 전 마감 시간 사이에 최소 3번. 아래 타임라인에는 다음 항목이 표시됩니다. [!UICONTROL segment] 다음 시점의 자격 요건 [!UICONTROL segment] 는 10월 1일에 만들어지고 10일 후에 만들어집니다.

![이전 선별](assets/earlier-qualification.png)


## 빈도 제한 예 {#frequency-capping}

빈도 제한 표현식에는 다음 수를 가진 모든 사용자가 포함됩니다. [!UICONTROL trait] 구현이 원하는 값 미만입니다. 다음은 몇 가지 옳고 그른 예입니다.

* 틀림 - 표현식 `frequency([1000T]) <= 5` 을(를) 실현한 모든 사용자 포함 [!UICONTROL trait] id가 &quot;1000&quot;인 경우 최대 5번이지만 를 실현하지 않은 사용자도 포함합니다. [!UICONTROL trait]. 따라서 Audience Manager은 너무 많은 사용자에게 자격을 부여하므로 성능상의 이유로 이 표현식의 유효성을 검사하지 않습니다. [!UICONTROL segment].

* 오른쪽 - 를 실현한 모든 사용자를 포함하려는 경우 [!UICONTROL trait] id가 최대 5배인 &quot;1000&quot;을 사용하여 다른 조건을 표현식에 추가하여 사용자가 다음 조건에 대한 자격이 있는지 확인합니다. [!UICONTROL trait] 최소 한 번:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 오른쪽- 최신성/빈도 요구 사항이 특정 횟수나 일수보다 적어야 하는 경우 해당 요구 사항에 참여합니다. [!UICONTROL trait] 을(를) 가진 다른 사람에게 `AND` 연산자. 첫 번째 글머리 기호의 예제를 사용하면 이 표현식을 다른 글머리 기호와 결합할 때 사용할 수 있습니다 [!UICONTROL trait] 아래와 같이 표시됩니다. `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 오른쪽 - 광고 빈도 제한 사용 사례의 경우 [!UICONTROL segment] 다음과 유사한 규칙: `(frequency([1000T] <= 2D) >= 5)`. 이 표현식에는 다음을 실현한 모든 사용자가 포함됩니다. [!UICONTROL trait] 지난 2일 동안 ID가 &quot;1000&quot;인 경우 최소 5번 이상. 이 메시지를 전송하여 빈도 제한 설정 [!UICONTROL segment] 을 사용하여 광고 서버에 `NOT` 다음에 설정 [!UICONTROL segment] 광고 서버에서 다음을 수행합니다. 이 방법은에서 더 나은 성능을 제공합니다. [!DNL Audience Manager] 빈도 설정을 위해 여전히 동일한 목적을 수행하는 동안.

>[!MORELIKETHIS]
>
>* [세그먼트 빌더 컨트롤: 트레이트 섹션](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [세그먼트 표현식 편집기에 사용되는 코드 구문](../../features/segments/segment-code-syntax.md)

