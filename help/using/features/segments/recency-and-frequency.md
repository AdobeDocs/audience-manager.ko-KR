---
description: 세그먼트 빌더에서 최신성 및 빈도를 사용하면 지정된 일별 간격 동안 발생하거나 반복되는 작업에 따라 방문자를 세그먼트화할 수 있습니다.
seo-description: 세그먼트 빌더에서 최신성 및 빈도를 사용하면 지정된 일별 간격 동안 발생하거나 반복되는 작업에 따라 방문자를 세그먼트화할 수 있습니다.
seo-title: 최신성 및 빈도
solution: Audience Manager
title: 최신성 및 빈도
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
feature: 세그먼트
exl-id: c00563f0-d270-4d4d-abeb-4b4b81aa68b8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 3%

---

# 최신성 및 빈도 {#recency-and-frequency}

[!UICONTROL Segment Builder]에서 최신성과 빈도를 사용하면 지정된 일별 간격에 따라 발생하거나 반복하는 작업에 따라 방문자를 세그먼트화할 수 있습니다.

Audience Manager은 [!DNL recency] 및 [!DNL frequency]을 다음과 같이 정의합니다.

* **[!UICONTROL Recency]**  : 사용자가 하나 이상의 항목을 보거나 자격이 있는 최근  [!UICONTROL traits]방법입니다.
* **[!UICONTROL Frequency]** : 사용자가 하나 이상의 항목에 대해 보거나 자격을 갖춘  [!UICONTROL traits]비율입니다.

[!UICONTROL Recency] 및  [!UICONTROL Frequency] 설정을 사용하면 사이트, 섹션 또는 특정 크리에이티브에 대한 실제(또는 인식된) 관심 수준에 따라 방문자를 세그먼트화할 수 있습니다. 예를 들어, 최신성/빈도 요구 사항이 높은 세그먼트에 대한 자격이 있는 사용자는 자주 또는 덜 자주 방문하는 사용자보다 사이트 또는 제품에 더 관심이 있을 수 있습니다.

## [!UICONTROL Recency and Frequency] 설정 위치 {#location}

[!UICONTROL Segment Builder]에서 [!UICONTROL Recency] 및 [!UICONTROL Frequency] 설정은 [!UICONTROL Traits] 패널의 [!UICONTROL Basic View] 섹션에 있습니다. 이 컨트롤을 표시하려면 시계 아이콘을 클릭합니다.

![](assets/recency_frequency.png)

## 제한 사항 및 규칙 {#limitations-rules}

세그먼트의 트레이트에 최신성과 빈도를 적용하려는 경우 이러한 제한 및 규칙을 검토하고 이해합니다.

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
   <td colname="col2"> <p>최신성 컨트롤을 규칙 기반 및 폴더 트레이트에만 적용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>타사 트레이트</b> </p> </td> 
   <td colname="col2"> <p>타사 트레이트를 포함하는 개별 타사 트레이트 또는 트레이트 그룹에 대해 최신성 규칙을 설정할 수 없습니다. 최신성 및 빈도는 고유한 트레이트에만 적용됩니다. </p> </td> 
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
   <td colname="col2"> <p>타사 트레이트를 포함하는 개별 타사 트레이트 또는 트레이트 그룹에 대해 빈도 규칙을 설정할 수 없습니다. 최신성 및 빈도는 고유한 트레이트에만 적용됩니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>트레이트 유형</b> </p> </td> 
   <td colname="col2"> <p>규칙 기반 및 폴더 트레이트에만 빈도 컨트롤을 적용할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>최신성 요구 사항</b> </p> </td> 
   <td colname="col2"> <p>최신성 요구 사항을 구성하지 않고 <i>빈도 요구 사항을 구성할 수 있습니다. </i> 빈도 값을 설정하고 최신성 필드를 비워 둡니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>프로필 병합 규칙</b> </p> </td> 
   <td colname="col2"> <p><a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> 트레이트 빈도, 외부 장치 그래프 및 프로필 병합 규칙</a>을 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 최신성 예 {#recency-examples}

다음은 UI에서 선택한 항목에 따라 최신성이 작동하는 두 가지 예입니다.

### 보다 작거나 같은 연산자 사용(&lt;=)

![보다 작음](assets/less-than-equal-to.png)

이 예에서는 스크린샷에 표시된 대로 &lt;= 연산자를 선택합니다. 이렇게 하면 사용자가 지난 5일 내에 최소 3회 [!UICONTROL traits] 3개 중 하나에 대한 자격이 있는 경우 [!UICONTROL segment]에 대한 자격이 부여됩니다. 아래 타임라인에는 [!UICONTROL segment] 생성 시, 10월 1일에, 10일 후에 [!UICONTROL segment] 자격이 표시됩니다.

![최근 5일](assets/last-5-days.png)

### 보다 크거나 같은 연산자 사용(=>)

![크거나 같음](assets/greater-than-equal-to.png)

이 예에서는 스크린샷에 표시된 대로 => 연산자를 선택합니다. 이렇게 하면 Audience Manager 플랫폼에서 첫 번째 자격 증명과 5일 전 종료 시간 사이에 언제든지 세 번([!UICONTROL traits]) 중 하나에 해당할 경우 [!UICONTROL segment]에 대한 자격이 사용자에게 생깁니다. 아래 타임라인에는 [!UICONTROL segment] 생성 시, 10월 1일에, 10일 후에 [!UICONTROL segment] 자격이 표시됩니다.

![이전 자격](assets/earlier-qualification.png)


## 빈도 제한 예 {#frequency-capping}

빈도 제한 식에는 [!UICONTROL trait] 실현 수가 원하는 값보다 작은 모든 사용자가 포함됩니다. 다음은 몇 가지 옳고 그른 예입니다.

* 틀림 - `frequency([1000T]) <= 5` 표현식에 ID가 &quot;1000&quot;인 [!UICONTROL trait]을 최대 5회까지 실현했지만 [!UICONTROL trait]를 실현하지 않은 사용자가 모두 포함됩니다. 따라서 Audience Manager은 [!UICONTROL segment]에 대해 너무 많은 사용자에게 자격이 부여되므로 성능상의 이유로 이 표현식의 유효성을 검사하지 않습니다.

* 오른쪽 - ID가 &quot;1000&quot;인 [!UICONTROL trait]을 최대 5회 실현한 모든 사용자를 포함하려면 표현식에 다른 조건을 추가하여 사용자가 [!UICONTROL trait]에 대해 자격이 있는지 최소 한 번 이상 확인합니다. `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* 오른쪽 - 최신성/빈도 요구 사항이 특정 횟수나 일 수보다 작아야 하는 경우 [!UICONTROL trait] 연산자를 사용하여 다른 항목에 연결합니다. `AND` 첫 번째 글머리 기호 포인트에서 이 예제를 사용하면 다음과 같이 다른 [!UICONTROL trait]과 결합할 때 이 식이 유효합니다.`frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* 오른쪽 - 광고 빈도 제한 사용 사례의 경우 다음과 유사한 [!UICONTROL segment] 규칙을 만들 수 있습니다.`(frequency([1000T] <= 2D) >= 5)`. 이 표현식에는 지난 2일 동안 최소 5회 이상 ID가 &quot;1000&quot;인 [!UICONTROL trait]을 실현한 모든 사용자가 포함됩니다. 광고 서버의 [!UICONTROL segment]에 `NOT`이 설정된 상태로 광고 서버에 이 [!UICONTROL segment]을(를) 전송하여 빈도 제한 을 설정합니다. 이 접근 방식은 [!DNL Audience Manager]에서 더 큰 성능을 구현하면서도 빈도 캡핑에 동일한 목적을 제공합니다.

>[!MORELIKETHIS]
>
>* [세그먼트 빌더 컨트롤:트레이트 섹션](../../features/segments/segment-builder.md#segment-builder-controls-traits)
* [세그먼트 표현식 편집기에 사용되는 코드 구문](../../features/segments/segment-code-syntax.md)

