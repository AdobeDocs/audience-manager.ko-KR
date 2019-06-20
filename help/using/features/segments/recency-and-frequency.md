---
description: 세그먼트 빌더에서 최근 및 빈도를 사용하면 발생하는 작업에 따라 방문자를 세그먼트화하고 매일 설정된 간격에 대해 반복할 수 있습니다.
seo-description: 세그먼트 빌더에서 최근 및 빈도를 사용하면 발생하는 작업에 따라 방문자를 세그먼트화하고 매일 설정된 간격에 대해 반복할 수 있습니다.
seo-title: 최근 및 빈도
solution: Audience Manager
title: 최근 및 빈도
uuid: Faadd 18 A-BF 27-4 B 73-995 E -9809 F 52 F 5350
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]:** 사용자가 하나 이상의 트레이트에 대해 보거나 자격을 갖춘 일 수입니다.
* **[!UICONTROL Frequency]:** 사용자가 하나 이상의 트레이트에 대해 보거나 자격을 갖춘 비율입니다.

[!UICONTROL Recency][!UICONTROL Frequency] And settings help you segment based on their real (or recognized) level of a site, section, or particular creative. 예를 들어 최근 빈도/빈도 요구 사항이 높은 세그먼트를 자격을 갖춘 사용자는 방문 횟수가 적거나 적게 방문하는 사용자보다 사이트 또는 제품에 더 관심이 있을 수 있습니다.

## Location of Recency and Frequency Settings {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] and [!UICONTROL Frequency] settings are located in the [!UICONTROL Basic View] section of the [!UICONTROL Traits] panel. 이 컨트롤을 표시하려면 시계 아이콘을 클릭합니다.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

세그먼트의 특성에 최근과 빈도를 적용하려는 경우 이러한 제한 사항과 규칙을 검토하고 이해해야 합니다.

### 최근

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
   <td colname="col2"> <p>최근 항목은 0 보다 커야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>서드파티 트레이트레이트</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트나 서드 파티 트레이트가 포함된 특성 그룹에는 최근 규칙을 설정할 수 없습니다. 최근 및 빈도는 고유한 특성에만 적용됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 빈도

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 제한 또는 규칙 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>서드파티 트레이트레이트</b> </p> </td> 
   <td colname="col2"> <p>서드 파티 트레이트가 포함된 개별 서드파티 트레이트나 특성 그룹에는 빈도 규칙을 설정할 수 없습니다. 최근 및 빈도는 고유한 특성에만 적용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>최근 요구 사항</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements <i>without</i> configuring recency requirements. 빈도 값을 설정하고 최근 필드를 비워 두십시오. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>프로필 병합 규칙</b> </p> </td> 
   <td colname="col2"> <p><a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 특성 주파수, 외부 장치 그래프 및 프로필 병합 규칙을 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequency Capping Examples {#frequency-capping}

주파수 탐색 표현식에는 트레이트 실현이 원하는 값 아래 있는 모든 사용자가 포함됩니다. 다음은 몇 가지 예입니다.

* The expression `frequency([1000T]) <= 5` includes all users that have realized the trait with the ID &quot;1000&quot; a maximum of five times, including users who have not realized the trait.
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an `AND` operator. Using the example above, this expression becomes valid when joined with another trait as shown here: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* For advertising frequency-capping use cases, you could create a segment rule similar to this: `(frequency([1000T] <= 2D) >= 5)`. 이 표현식에는 지난 2 일 동안 ID &quot;1000&quot; 를 가진 트레이트를 최소 5 회 구현한 모든 사용자가 포함됩니다. Set frequency capping by sending this segment to the ad server with a `NOT` set on the segment in the ad server. This approach achieves greater performance in [!DNL Audience Manager] while still serving the same purpose for frequency capping.

>[!MORE_ like_ this]
>
>* [세그먼트 빌더 제어: 트레이트 섹션](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [세그먼트 표현식 편집기에서 사용된 코드 구문](../../features/segments/segment-code-syntax.md)

