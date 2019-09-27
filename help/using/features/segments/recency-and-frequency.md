---
description: 세그먼트 빌더에서 최근 및 빈도는 설정된 일별 간격 동안 발생하거나 반복되는 작업을 기준으로 방문자를 세그먼트화할 수 있도록 해줍니다.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: Recency and Frequency
solution: Audience Manager
title: 최근 및 빈도
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: c7e8b67ccad4479487b471668462937c5be6be34

---


# Recency and Frequency {#recency-and-frequency}

In [!UICONTROL Segment Builder], recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.

Audience Manager defines [!DNL recency] and [!DNL frequency] as follows:

* **[!UICONTROL Recency]** : How recently a user viewed or qualified for one (or more) traits.
* **[!UICONTROL Frequency]:** The rate at which a user viewed or qualified for one (or more) traits.

[!UICONTROL Recency] and  settings help you segment visitors based on their real (or perceived) level of interest in a site, section, or particular creative. [!UICONTROL Frequency] For example, users who qualify for a segment with high recency/frequency requirements may be more interested in a site or product than users who visit less often or less frequently.

## Location of Recency and Frequency Settings {#location}

In ,  and  settings are located in the  section of the  panel. [!UICONTROL Segment Builder][!UICONTROL Recency][!UICONTROL Frequency][!UICONTROL Basic View][!UICONTROL Traits] Click the clock icon to expose these controls.

![](assets/recency_frequency.png)

## Limitations and Rules {#limitations-rules}

세그먼트의 트레이트에 최근 및 빈도를 적용하려는 경우 이러한 제한 사항과 규칙을 검토하고 이해합니다.

### 최근

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>최소 값</b> </p> </td> 
   <td colname="col2"> <p>Recency must be greater than 0. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트가 포함된 개별 타사 트레이트나 트레이트 그룹에 대해 최근 규칙을 설정할 수 없습니다. 최근 및 빈도는 고유한 특성에만 적용됩니다. </p> </td> 
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
   <td colname="col1"> <p> <b>타사 트레이트</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트를 포함하는 개별 타사 트레이트 또는 트레이트 그룹에 대해 주파수 규칙을 설정할 수 없습니다. 최근 및 빈도는 고유한 특성에만 적용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>최근 요구 사항</b> </p> </td> 
   <td colname="col2"> <p>최근 요구 사항을 구성하지 <i>않고</i> 주파수 요구 사항을 구성할 수 있습니다. 주파수 값을 설정하고 최근 필드를 비워 두면 됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>프로필 병합 규칙</b> </p> </td> 
   <td colname="col2"> <p>트레이트 <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 빈도, 외부 장치 그래프 및 프로필 병합 규칙을 참조하십시오</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 최근 예 {#recency-examples}

다음은 UI에서 선택한 내용에 따라 최근 기능의 두 가지 예입니다.

### 보다 작거나 같음 연산자(&lt;=) 사용

![작거나 같음](assets/less-than-equal-to.png)

이 예에서는 스크린샷과 같이 &lt;= 연산자를 선택합니다. 이 경우 사용자가 지난 5일 동안 세 가지 트레이트 중 하나를 최소 3회 받을 수 있는 자격이 주어집니다. 아래 타임라인에는 세그먼트 작성 시, 10월 1일 및 10일 이후의 세그먼트 자격 조건이 표시됩니다.

![지난 5일](assets/last-5-days.png)

### 보다 크거나 같은 연산자(=&gt;) 사용

![크거나 같음](assets/greater-than-equal-to.png)

이 예에서는 스크린샷에 표시된 대로 =&gt; 연산자를 선택합니다. 이렇게 하면 사용자가 Audience Manager 플랫폼에서 첫 번째 자격 조건과 5일 전 단축 시간 사이에 언제든지 세 가지 트레이트 중 한 트레이트를 최소 3번 받을 수 있는 자격이 되는 것입니다. 아래 타임라인에는 세그먼트 작성 시, 10월 1일 및 10일 이후의 세그먼트 자격 조건이 표시됩니다.

![이전 자격 조건](assets/earlier-qualification.png)


## 주파수 매핑 예 {#frequency-capping}

주파수 매핑 식에는 트레이트 실현의 수가 원하는 값보다 작은 모든 사용자가 포함됩니다. 다음은 몇 가지 예입니다.

* The expression  includes all users that have realized the trait with the ID "1000" a maximum of five times, including users who have not realized the trait.`frequency([1000T]) <= 5`
* When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an  operator. `AND` 위의 예를 사용하면 다음과 같이 다른 트레이트와 연결되면 이 표현식이 유효합니다. `frequency([1000T]) <= 5 AND isSiteVisitorTrait`Adobe

* For advertising frequency-capping use cases, you could create a segment rule similar to this: . `(frequency([1000T] <= 2D) >= 5)` This expression includes all users that have realized the trait with the ID "1000" in the past 2 days at least five times. Set frequency capping by sending this segment to the ad server with a  set on the segment in the ad server. `NOT` This approach achieves greater performance in  while still serving the same purpose for frequency capping.[!DNL Audience Manager]

>[!MORE_LIKE_THIS]
>
>* [Segment Builder Controls: Traits Section](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Code Syntax Used in the Segment Expression Editor](../../features/segments/segment-code-syntax.md)

