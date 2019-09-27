---
description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-description: In Segment Builder, recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.
seo-title: 최근 및 빈도
solution: Audience Manager
title: 최근 및 빈도
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: 1cbff10b9e978755e139e7d5b996249de5ebb5bd

---


# Recency and Frequency {#recency-and-frequency}

In , recency and frequency let you segment visitors based on actions that occur or repeat over a set daily interval.[!UICONTROL Segment Builder]

Audience Manager defines  and  as follows:[!DNL recency][!DNL frequency]

* **[!UICONTROL Recency]** :사용자가 하나 이상의 트레이트를 조회하거나 자격을 얻은 최근 정보입니다.
* **[!UICONTROL Frequency]** :사용자가 하나 이상의 트레이트에 대해 열람하거나 자격이 부여된 비율입니다.

[!UICONTROL Recency] 및 [!UICONTROL Frequency] 설정을 사용하면 사이트, 섹션 또는 특정 크리에이티브의 실제(또는 인지) 관심도를 기반으로 방문자를 세그먼트화할 수 있습니다. 예를 들어 최근/빈도 요구 사항이 높은 세그먼트에 대한 자격이 있는 사용자는 방문 빈도가 낮거나 적은 사용자보다 사이트 또는 제품에 더 관심이 있을 수 있습니다.

## 최근 및 빈도 설정의 위치 {#location}

에서 [!UICONTROL Segment Builder]및 [!UICONTROL Recency] 설정은 [!UICONTROL Frequency] 패널의 [!UICONTROL Basic View] 섹션에 있습니다 [!UICONTROL Traits] . 시계 아이콘을 클릭하여 이러한 컨트롤을 표시합니다.

![](assets/recency_frequency.png)

## 제한 및 규칙 {#limitations-rules}

세그먼트의 트레이트에 최근 및 빈도를 적용하려는 경우 이러한 제한 사항과 규칙을 검토하고 이해합니다.

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
   <td colname="col2"> <p>최근 값은 0보다 커야 합니다. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>특성 유형</b> </p> </td> 
   <td colname="col2"> <p>최근 컨트롤을 규칙 기반 및 폴더 특성에만 적용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>타사 트레이트</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트가 포함된 개별 타사 트레이트나 트레이트 그룹에 대해 최근 규칙을 설정할 수 없습니다. 최근 및 빈도는 고유한 특성에만 적용됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 빈도

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limit or Rule </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Third-Party Traits</b> </p> </td> 
   <td colname="col2"> <p>You cannot set frequency rules on individual third-party traits or trait groups that contain third-party traits. Recency and frequency applies to your own traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Trait Types</b> </p> </td> 
   <td colname="col2"> <p>You can apply frequency controls to rule-based and folder traits only. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Recency Requirements</b> </p> </td> 
   <td colname="col2"> <p>You can configure frequency requirements without configuring recency requirements. <i></i> 주파수 값을 설정하고 최근 필드를 비워 두면 됩니다. </p> </td> 
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

Frequency-capping expressions include all the users whose number of trait realizations is below a desired value. Here are a few Right and Wrong examples:

* Wrong - The expression  includes all users that have realized the trait with the ID "1000" a maximum of five times but also includes users who have not realized the trait. `frequency([1000T]) <= 5` Therefore, Audience Manager does not validate this expression for performance reasons, as it would qualify too many users for the segment.

* Right - If you want to include all users that have realized the trait with the ID "1000" a maximum of five times, add another condition to the expression, to make sure the users have qualified for the trait at least once:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Right- When you need recency/frequency requirements to be less than a specific number of times or days, join that trait to another with an  operator. `AND` 첫 번째 글머리 기호 예제에서 이 표현식은 다음과 같이 다른 트레이트와 연결되면 유효합니다. `frequency([1000T]) <= 5 AND isSiteVisitorTrait`Adobe

* Right - For advertising frequency-capping use cases, you could create a segment rule similar to this: . `(frequency([1000T] <= 2D) >= 5)` This expression includes all users that have realized the trait with the ID "1000" in the past 2 days at least five times. 광고 서버의 세그먼트에 `NOT` 설정된 상태로 이 세그먼트를 광고 서버로 전송하여 빈도 매핑을 설정합니다. 이러한 접근 방식은 주파수 캡핑을 위해 동일한 용도로 제공하면서 [!DNL Audience Manager] 더욱 높은 성능을 제공합니다.

>[!MORELIKE_THIS]
>
>* [세그먼트 빌더 컨트롤:트레이트 섹션](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [세그먼트 표현식 편집기에서 사용되는 코드 구문](../../features/segments/segment-code-syntax.md)

