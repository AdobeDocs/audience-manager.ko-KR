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
source-wordcount: '706'
ht-degree: 1%

---

# 최신성 및 빈도 {#recency-and-frequency}

[!UICONTROL Segment Builder]에서 최신성과 빈도를 사용하면 설정된 일별 간격 동안 발생하거나 반복하는 작업에 따라 방문자를 세그먼트화할 수 있습니다.

Audience Manager은 [!DNL recency] 및 [!DNL frequency]을(를) 다음과 같이 정의합니다.

* **[!UICONTROL Recency]:** 사용자가 최근 본 항목 또는 하나 이상의 [!UICONTROL traits] 자격을 얻은 항목.
* **[!UICONTROL Frequency]:** 사용자가 하나 이상의 [!UICONTROL traits]을(를) 열람하거나 자격을 부여하는 비율입니다.

[!UICONTROL Recency] 및 [!UICONTROL Frequency] 설정을 사용하면 사이트, 섹션 또는 특정 크리에이티브에 대한 실제(또는 인지된) 관심 수준에 따라 방문자를 세그먼트화할 수 있습니다. 예를 들어, 최신성/빈도 요구 사항이 높은 세그먼트에 대한 자격이 있는 사용자는 자주 또는 덜 자주 방문하는 사용자보다 사이트 또는 제품에 더 관심이 있을 수 있습니다.

## [!UICONTROL Recency and Frequency] 설정 위치 {#location}

[!UICONTROL Segment Builder]에서 [!UICONTROL Recency] 및 [!UICONTROL Frequency] 설정이 [!UICONTROL Basic View] 패널의 [!UICONTROL Traits] 섹션에 있습니다. 시계 아이콘을 클릭하여 이러한 컨트롤을 표시합니다.

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
   <td colname="col1"> <p> <b>최소값</b> </p> </td> 
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
   <td colname="col2"> <p>빈도 요구 사항을 구성하지 않고 <i>빈도 요구 사항을 구성할 수 있습니다</i>. 빈도 값을 설정하고 최신성 필드를 비워 두면 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>프로필 병합 규칙</b> </p> </td> 
   <td colname="col2"> <p>트레이트 빈도, 외부 장치 그래프 및 프로필 병합 규칙 <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules">을(를) 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 최신성 예 {#recency-examples}

다음은 UI에서 선택한 항목에 따라 최신이 작동하는 방식에 대한 두 가지 예입니다.

### 작거나 같음 연산자 사용(&lt;=)

![다음보다 작음](assets/less-than-equal-to.png)

이 예제에서는 스크린샷에 표시된 대로 &lt;= 연산자를 선택합니다. 이렇게 하면 사용자가 지난 5일 내에 최소 3번 이상 세 개의 [!UICONTROL segment]에 대한 자격이 있는 경우 [!UICONTROL traits]에 대한 자격이 부여됩니다. 아래 타임라인에서는 [!UICONTROL segment]이(가) 만들어지는 시점과 10일 후의 [!UICONTROL segment] 자격을 보여 줍니다.

![마지막 5일](assets/last-5-days.png)

### 보다 크거나 같은 연산자 사용(=>)

![다음보다 큼](assets/greater-than-equal-to.png)

이 예제에서는 스크린샷에 표시된 대로 => 연산자를 선택합니다. 사용자가 Audience Manager 플랫폼에서 첫 번째 자격을 얻은 후 5일 전 컷오프 시간 사이에 최소 3회 이상 세 개의 [!UICONTROL segment]에 대한 자격을 얻은 경우 [!UICONTROL traits]에 대한 자격을 부여합니다. 아래 타임라인에서는 [!UICONTROL segment]이(가) 만들어지는 시점과 10일 후의 [!UICONTROL segment] 자격을 보여 줍니다.

![이전 자격](assets/earlier-qualification.png)


## 빈도 제한 예 {#frequency-capping}

빈도 제한 식에는 [!UICONTROL trait] 실현 수가 원하는 값 미만인 모든 사용자가 포함됩니다. 다음은 몇 가지 옳고 그른 예입니다.

* 잘못됨 - `frequency([1000T]) <= 5` 식에는 ID가 &quot;1000&quot;인 [!UICONTROL trait]을(를) 최대 5번 인식하는 모든 사용자가 포함되지만 [!UICONTROL trait]을(를) 인식하지 못한 사용자도 포함됩니다. 따라서 Audience Manager은 너무 많은 사용자에게 [!UICONTROL segment]의 자격을 부여하므로 성능상의 이유로 이 식의 유효성을 검사하지 않습니다.

* 오른쪽 - ID가 &quot;1000&quot;인 [!UICONTROL trait]을(를) 최대 5번 인식하는 모든 사용자를 포함하려면 표현식에 다른 조건을 추가하여 사용자가 [!UICONTROL trait]에 대해 최소 한 번 이상 자격이 있는지 확인하십시오. `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 오른쪽- 최신성/빈도 요구 사항이 특정 횟수나 일수보다 적어야 하는 경우 [!UICONTROL trait] 연산자로 해당 `AND`을(를) 다른 에 연결하십시오. 첫 번째 글머리 기호의 예제를 사용하면 [!UICONTROL trait]과(와) 같이 다른 `frequency([1000T]) <= 5 AND isSiteVisitorTrait`과(와) 결합할 때 이 식이 유효해집니다.

* 오른쪽 - 광고 빈도 제한 사용 사례의 경우 [!UICONTROL segment]과(와) 유사한 `(frequency([1000T] <= 2D) >= 5)` 규칙을 만들 수 있습니다. 이 식에는 지난 2일 동안 ID가 &quot;1000&quot;인 [!UICONTROL trait]을(를) 최소 5번 이상 구현한 모든 사용자가 포함됩니다. 이 [!UICONTROL segment]을(를) 광고 서버의 `NOT`에 설정된 [!UICONTROL segment]&#x200B;(으)로 광고 서버로 보내 빈도 제한을 설정합니다. 이 방법은 [!DNL Audience Manager]에서 더 높은 성능을 달성하는 동시에 빈도 상한에 동일한 목적을 제공합니다.

>[!MORELIKETHIS]
>
>* [세그먼트 빌더 컨트롤: 트레이트 섹션](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [세그먼트 표현식 편집기에 사용되는 코드 구문](../../features/segments/segment-code-syntax.md)
