---
description: Audience Marketplace 데이터 구매자는 천 개 광고 노출 횟수(CPM) 기준으로 가격이 책정된 데이터 피드에 포함된 트레이트를 사용하여 제공된 모든 광고 노출 횟수를 보고하는 데 동의합니다. CPM 사용량은 매월 5일에 마감되며 이전 달의 데이터를 포함합니다. 정액 요금 가입자는 사용 신고를 하지 않아도 됩니다.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: 데이터 피드 구매자에 대한 청구
keywords: 세그먼트 수준 보고, 세그먼트 수준, 세그먼트 수준
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2029'
ht-degree: 0%

---

# 데이터 피드 구매자에 대한 청구 {#billing-for-data-feed-buyers}

Audience Marketplace 데이터 구매자는 천 개 광고 노출 수([!DNL CPM])당 비용으로 책정된 데이터 피드에 포함된 트레이트를 사용하여 제공된 모든 광고 노출 수를 보고하는 데 동의합니다. [!DNL CPM] 사용은 각 역월의 5일에 만기되며 이전 달의 데이터를 포함합니다. 정액 요금 가입자는 사용 신고를 하지 않아도 됩니다.

<br> 

## CPM 사용을 보고하는 방법 {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 데이터 구매자는 천 개 광고 노출 수([!DNL CPM]) 기준으로 가격이 책정된 데이터 피드에 포함된 트레이트를 사용하여 제공된 모든 광고 노출 수를 보고하는 데 동의합니다. [!DNL CPM] 사용은 각 역월 5일에 만기되며 이전 달의 데이터를 포함합니다. 정액 요금 가입자는 사용 신고를 하지 않아도 됩니다.

[!UICONTROL Audience Marketplace]은(는) [!DNL CPM] 사용량을 보고하는 두 가지 방법을 제공합니다.

* **세그먼트 수준 보고**: 권장되는 [!DNL CPM] 사용 보고 방법입니다. 세그먼트 수준에서 [!DNL CPM] 사용을 보고할 때 데이터 피드 수준 보고 섹션은 [CPM 데이터 피드에 대한 비용 속성](#cost-attribution)에 설명된 알고리즘을 기반으로 해당 사용 금액으로 자동으로 채워집니다.
* **데이터 피드 수준 보고**: 이 메서드를 사용하려면 [!DNL CPM]CPM 데이터 피드에 대한 비용 속성[에 설명된 알고리즘을 기반으로 각 데이터 피드에 대한 ](#cost-attribution) 사용량을 개별적으로 보고해야 합니다. 그러나 이 방법은 세그먼트 수준 보고보다 지루하고 오류가 발생하기 쉽습니다.

<br> 

## 세그먼트 수준에서 CPM 사용 보고 {#segment-level-report}

[!UICONTROL Segment Usage] 탭에서는 세그먼트 수준 사용을 보고할 수 있으며 매핑된 대상별로 그룹화된 세그먼트를 표시할 수 있습니다.

세그먼트 수준에서 [!DNL CPM] 사용을 보고하면 [!UICONTROL Audience Marketplace]이(가) CPM 데이터 피드에 대한 [비용 속성](#cost-attribution)을(를) 기반으로 해당 데이터 피드에 올바른 사용을 자동으로 할당합니다.

세그먼트 수준에서 [!DNL CPM] 사용을 보고하려면:

1. **[!UICONTROL Audience Marketplace > Payables]**(으)로 이동합니다.
1. **[!UICONTROL Segment Usage]** 탭을 선택합니다.
1. 세그먼트에 대한 사용을 입력합니다. 일부 세그먼트에 대한 사용량만 보고하면 되는 경우 [!UICONTROL Search] 상자를 사용하여 세그먼트를 필터링할 수 있습니다.
1. **[!UICONTROL Edit Segments Usage]** 아이콘을 클릭합니다.
1. [!DNL CPM] 열에 [!UICONTROL Usage] 사용량을 입력하십시오.
1. 완료되면 **[!UICONTROL Save]**&#x200B;을(를) 클릭하고 확인 대화 상자를 검토합니다.

   ![confirm-segment-usage](assets/confirm-segment-usage.png)

1. **[!UICONTROL Confirm]** 아이콘을 클릭합니다.

세그먼트 수준 사용을 보고할 수 있는 방법에 대한 비디오 데모도 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## 데이터 피드 수준에서 CPM 사용 보고 {#feed-level-report}

각 데이터 피드에 대해 개별적으로 [!DNL CPM] 사용량을 계산해야 하므로 데이터 피드 수준 보고는 더 지루하고 오류 프로세스가 발생하기 쉽습니다. 대신 [세그먼트 수준에서 CPM 사용량을 보고](#segment-level-report)하는 것이 좋습니다.

세그먼트 수준에서 [!DNL CPM] 사용을 보고하려면:

1. **[!UICONTROL Audience Marketplace > Payables]**(으)로 이동합니다.
2. **[!UICONTROL Feed Usage]** 탭을 선택합니다.
3. [!UICONTROL Search] 상자를 사용하여 데이터 피드를 필터링하고 사용량을 보고해야 하는 데이터 피드를 식별합니다.
4. **[!UICONTROL Edit Feeds Usage]** 아이콘을 클릭합니다.
5. CPM 데이터 피드에 대한 [!DNL CPM]비용 속성[을(를) 기반으로 각 데이터 피드에 대한 ](#cost-attribution) 사용량을 계산하고 [!UICONTROL Usage] 열에 입력하십시오.
6. 완료되면 **[!UICONTROL Save]**&#x200B;을(를) 클릭하고 확인 대화 상자를 검토합니다.

   ![피드 사용량 확인](assets/confirm-feed-usage.png)

7. **[!UICONTROL Confirm]** 아이콘을 클릭합니다.

<br> 

## 벌크 보고

[!DNL CPM] 사용량을 보고하는 동안 오류 및 오버헤드를 줄이기 위해 일괄 보고 옵션을 사용하여 데이터 피드 및 세그먼트가 포함된 [!DNL CSV] 파일을 다운로드하고, 사용량을 입력한 다음 [!DNL Audience Manager]에 다시 업로드할 수 있습니다. 대량 보고를 사용하여 피드 및 세그먼트 사용을 모두 보고할 수 있습니다.

[!DNL CPM] 사용량을 일괄적으로 업데이트하려면:

1. **[!UICONTROL Audience Marketplace > Payables]**(으)로 이동합니다.
1. 업데이트하려는 보고 유형에 따라 **[!UICONTROL Feed Usage]** 또는 **[!UICONTROL Segment Usage]** 탭을 선택합니다.
1. **[!UICONTROL Edit Feeds Usage]** 또는 **[!UICONTROL Edit Segments Usage]**&#x200B;을(를) 클릭합니다.
1. 올바른 CSV 파일을 사용하는지 확인하려면 **[!UICONTROL download the current usage]**&#x200B;을(를) 클릭하십시오.
1. 컴퓨터에서 파일을 열고 사용 보고서를 입력합니다.
1. 업데이트된 사용 현황 보고서를 업로드하려면 **[!UICONTROL Choose a CSV file]**&#x200B;을(를) 클릭하십시오.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager]은(는) 업로드하는 즉시 파일의 유효성을 검사하고 파일에서 오류가 검색되는지 확인합니다.

<br> 

### 유효성 검사 오류 일괄 보고

| 오류 메시지 | 설명 | 변수 이름이 아니라, 필터링된 보고서의 머리글로 잘못 표시하는 |
| ------------- | -------------| -----|
| 잘못된 입력 | [!DNL Audience Manager]이(가) 열 누락 또는 열 제목 변경과 같은 [!DNL CSV] 파일 스키마의 변경 내용을 발견했습니다. | 테이블 구조를 변경하지 마십시오. |
| 발견되지 않음 | [!UICONTROL Segment Level Reporting]의 경우 [!DNL Audience Manager]이(가) [!UICONTROL Segment ID] 및 [!UICONTROL Destination ID] 조합을 식별할 수 없습니다. [!UICONTROL Feed Level Reporting]의 경우 [!DNL Audience Manager]이(가) [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] 및 [!UICONTROL Use Case] 조합을 식별할 수 없습니다. | [!UICONTROL Segment Level Reporting]의 경우 [!UICONTROL Segment ID] 및 [!UICONTROL Destination ID] 조합의 유효성을 검사하십시오. [!UICONTROL Feed Level Reporting]의 경우 [!UICONTROL Data Provider Name], [!UICONTROL Feed Name] 및 [!UICONTROL Use Case] 조합의 유효성을 검사하십시오. |
| 중복 레코드 발견 | [!DNL Audience Manager]이(가) 다른 노출 값을 가진 중복 레코드를 발견했습니다. | 보고서를 검토하고 동일한 데이터 피드 또는 세그먼트에 대해 서로 다른 사용 값을 보고하지 않도록 하십시오. |
| 지원되지 않는 값 | [!DNL Audience Manager]이(가) [!DNL Audience Manager] 열에서 숫자가 아닌 값을 검색했습니다. | 보고서를 검토하고 [!DNL Audience Manager] 열에 숫자 값만 입력해야 합니다. |
| 필수 필드의 헤더 누락 | [!DNL Audience Manager]에서 필수 필드에 누락된 테이블 헤더를 검색했습니다. [!UICONTROL Segment Level Reporting]의 필수 필드는 [!UICONTROL Segment ID], [!UICONTROL Destination ID]입니다. [!UICONTROL Feed Level Reporting]의 필수 필드는 [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name], [!UICONTROL Use Case]입니다. | 보고서를 검토하고 표 머리글이 변경되지 않았는지 확인하십시오. |

>[!NOTE]
>[!DNL CSV] 사용 보고서에서 행을 제거해도 기존 사용 보고서에는 영향을 주지 않습니다. [!DNL Audience Manager]은(는) 보고서에 포함된 필드만 처리합니다.

<br> 

## [!DNL CPM] 보고 모범 사례

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>항상 총 노출 횟수를 보고하세요</b> </p> </td> 
   <td colname="col2"> <p>CPM 노출 총계의 경우: </p>
   <p> 소수를 사용하지 않고 총 노출 횟수를 보고합니다. Audience Manager은 보고하는 총 수를 기반으로 CPM을 자동으로 계산합니다.</p><p>1,234,567회 노출 횟수를 보고해야 하는 경우 이와 정확히 동일하게 보고하십시오. CPM을 계산하기 위해 총 노출 횟수를 1,000으로 나눌 필요가 없습니다.</p><p>Adobe Target 또는 Analytics 대상과 같은 도구를 사용하여 웹 또는 앱 컨텐츠를 최적화(컨텐츠 최적화)하는 데 사용되는 트레이트는 CPM 플랜의 사용 총계에 기여하지 않습니다. 데이터 제공업체는 일반적으로 정액 요금 플랜을 사용하여 콘텐츠 최적화에 대해 보상을 받습니다.</p><p>자세한 내용은 <a href="#cost-attribution">CPM 데이터 피드의 비용 속성</a>을 참조하십시오. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>월별 보고 간격 유지</b> </p> </td> 
   <td colname="col2"> <p>보고서 시스템은 매월 5일 이후에 닫힙니다. 그때까지 CPM 사용을 보고하지 않으면 다음 달의 보고서에 해당 금액을 추가해야 합니다. 예를 들어, 10월에 1000개의 노출을 사용하고, 10월 보고 기한을 놓치고, 11월에 1000개의 노출을 사용한다고 가정해 보겠습니다. 이 경우 1일과 5일 사이에 10월과 11월 합계(2000년)를 12월에 보고합니다.</p><p><b>팁</b>: 항상 다음 달 1일에서 5일 사이에 이전 달의 CPM 사용을 보고해 보십시오.</p><p>늦어도 새 역월 5일까지는 CPM 사용을 보고할 수 있지만 권장되지 않습니다. 매월 5일 전에 CPM 사용을 보고하면 Audience Manager에서 데이터를 확인하고 처리할 수 있는 시간이 제공됩니다.</p> </td>
  </tr> 
 </tbody> 
</table>

<br> 

## CPM 데이터 피드에 대한 비용 속성 {#cost-attribution}

[!UICONTROL Audience Marketplace]에서는 각 세그먼트에 대해 매월 노출 금액을 자체 보고해야 합니다. 비용 속성이 자동으로 수행되도록 세그먼트 수준에서 [!DNL CPM] 사용을 보고하는 것이 좋습니다.

<!-- marketplace_cpm_billing.xml -->

### 청구 요약 {#billing-summary}

[!DNL CPM]개의 데이터 피드 노출 금액을 매월 1일과 5일 사이에 제출해야 합니다. 이 작업을 올바르게 수행하려면 [세그먼트 수준에서 CPM 사용을 보고](#segment-level-report)하는 것이 좋습니다.

>[!TIP]
>세그먼트 수준에서 [!DNL CPM] 사용을 보고하면 데이터 피드 수준 보고 섹션이 해당 사용 금액으로 자동으로 채워집니다.

[!UICONTROL Report CPM Usage at Data Feed Level]해야 하는 경우 이전 달력의 각 피드에 대해 배달된 모든 노출 횟수를 개별적으로 컴파일하고 이 문서에 설명된 청구 할당에 따라 보고해야 합니다.

이전 달력의 [!DNL CPM] 번호를 보고하면 [!DNL Adobe]에서 다음을 수행합니다.

* 청구서를 만들고 구독한 각 데이터 피드의 [!DNL CPM] 요금을 기준으로 청구하세요.
* 보고된 [!DNL CPM] 사용에 따라 지불해야 하는 데이터 공급자(판매자) 요금을 지불하십시오.

>[!IMPORTANT]
>
>구매자는 보고된 모든 노출 합계가 참이고 정확해야 합니다. 노출 합계를 매월 5일까지 보고하지 않으면 다음 달에 보고되지 않은 달의 합계를 포함해야 합니다.

<br> 

## 트레이트 자격 규칙에 따라 피드 수준에서 노출 횟수 할당 {#assign-impressions}

[!UICONTROL Activation] 사용 사례를 사용하면 해당 데이터 피드의 특성을 사용하여 [세그먼트 빌더](../../../features/segments/segment-builder.md)에서 세그먼트를 만들고 해당 세그먼트를 대상에 매핑할 수 있습니다. 부울 연산자 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]을(를) 사용하면 트레이트 및 세그먼트 자격에 대한 조건을 설정할 수 있습니다.

[데이터 피드 수준에서 CPM 사용을 보고](#feed-level-report)할 때 트레이트 자격 규칙에 사용된 [!DNL Boolean] 연산자에 따라 각 데이터 피드에 비례하여 노출을 할당해야 합니다. 다음 표에는 부울 규칙 또는 트레이트 유형별로 노출을 적절하게 할당하는 방법이 나와 있습니다.

>[!TIP]
>[세그먼트 수준에서 CPM 사용량 보고](#segment-level-report) Audience Manager에서 데이터 피드 수준 보고를 자동으로 수행합니다.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 규칙 자격 논리 또는 유형 </th> 
   <th colname="col2" class="entry"> 청구 분배 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 및</span> </p> </td> 
   <td colname="col2"> <p>부울 <span class="wintitle"> AND</span> 조건을 사용하는 규칙 기반 세그먼트의 모든 공급자 트레이트에 전달된 노출 합계의 100%를 적용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 또는</span> </p> </td> 
   <td colname="col2"> <p>부울 OR 조건을 사용하는 규칙 기반 세그먼트의 모든 공급자 트레이트에 게재된 노출 합계의 가중 할당을 적용합니다. 가중 할당은 다음 공식을 사용하여 계산됩니다.</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle">이(가) </span> 아님 </p> </td> 
   <td colname="col2"> <p>부울 <span class="wintitle"> NOT</span> 조건을 사용하는 규칙 기반 세그먼트의 모든 공급자 트레이트에 전달된 노출 합계의 100%를 적용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>알고리즘 세그먼트 </p> </td> 
   <td colname="col2"> <p>알고리즘 트레이트가 포함된 세그먼트의 모든 공급자 피드에 게재된 노출 합계의 100%를 적용합니다. </p> </td> 
  </tr>
 </tbody>
</table>

<br> 

## 청구 예 {#billing-examples}

아래 예제는 데이터 피드 수준에서 [!DNL CPM] 사용 할당이 수행되는 방식을 보여 주기 위한 것입니다.

>[!IMPORTANT]
>이 프로세스를 자동으로 완료하려면 대신 [세그먼트 수준에서 CPM 사용을 보고](#segment-level-report)하는 것이 좋습니다.

다음 시나리오를 살펴보겠습니다.

![청구 예](assets/billing-examples.png)

<br> 

### 사례 1: AND 자격 규칙이 있는 세그먼트

이 세그먼트에는 별도의 데이터 공급자의 트레이트 3개가 포함되어 있습니다. 세그먼트 자격은 [!UICONTROL AND] 조건을 기반으로 하므로 방문자는 세 피드 모두에서 특성을 인식해야 세그먼트를 사용할 수 있습니다.

![](assets/billing-segment-and.png)

[!UICONTROL AND] 조건을 사용하면 세 데이터 공급자 모두에 해당 달 동안 받은 노출 횟수의 100%를 할당해야 합니다. [!UICONTROL Audience Marketplace > Payables] 섹션에서 각 공급자에게 1,000,000개의 노출 횟수를 크레딧합니다.

이 예제는 [!DNL Boolean] [!UICONTROL NOT] 연산자를 사용하는 세그먼트나 알고리즘 트레이트가 포함된 세그먼트에 적용됩니다.

<br> 

### 사례 2: OR 자격 규칙이 있는 세그먼트

이 세그먼트에는 별도의 데이터 공급자의 트레이트 3개가 포함되어 있습니다. 세그먼트 자격은 [!UICONTROL OR] 조건을 기반으로 하므로 방문자는 세 가지 트레이트 중 하나 이상을 실현해야 세그먼트 자격을 얻을 수 있습니다.

자격은 [!UICONTROL OR] 조건을 기반으로 하므로 노출의 원인이 되는 특성을 알 수 없습니다. 그 결과, [!UICONTROL Audience Marketplace > Payables] 섹션에서 트레이트 모집단을 기준으로 총 노출 횟수에 대한 가중 할당으로 각 공급자의 크레딧을 제공합니다.

![billing-segment-or](assets/billing-segment-or.png)

<br> 

### 사례 3: 모델링 및 활성화 사용 사례가 있는 세그먼트

이 예에서는 모델링 및 활성화라는 두 가지 데이터 피드 사용 사례를 기반으로 한 속성에 대해 설명합니다. 예제에서는 다음 정보가 포함된 두 개의 데이터 공급자를 살펴봅니다.

![데이터 피드](assets/feed-use-cases.png)

추가 아래 표에서 세그먼트 X는 세그먼트 규칙 T1 또는 T2가 있는 두 개의 트레이트 T1 및 T2를 포함하며, 여기서

* T1은 데이터 피드 A의 트레이트입니다.
* T2는 데이터 피드 A 및 데이터 피드 B의 타사 트레이트를 모델로 한 알고리즘 트레이트입니다.

세그먼트는 대상에 매핑되고 [세그먼트 수준 보고](#segment-level-report)를 사용하여 한 달 동안 이 세그먼트에 대해 1,000,000개의 노출이 입력됩니다.

이 1,000,000회 노출 중:

* T1은 세그먼트 인구의 40%를 차지하며, 피드 A의 노출 횟수는 40만 회입니다.
* T2는 세그먼트 인구의 60%를 차지하며, 피드 A와 피드 B에 대해 600,000개의 노출로 해석됩니다.

데이터 피드 수준에서 노출이 할당되는 방식은 다음과 같습니다.

* 데이터 피드 A는 트레이트 T2(데이터 피드 A와 데이터 피드 B의 트레이트에 모델링되어 모두 노출됨)에서 600,000개의 노출을 수신하고 트레이트 T1(데이터 피드 A의 트레이트인)에서 400,000개의 노출을 수신하며 총 1,000,000개의 노출을 수신합니다.
* 데이터 피드 B는 트레이트 T2(위의 설명 참조)에서 600,000개의 노출을 받고 트레이트 T1에서 0개의 노출을 받습니다.

데이터 피드 및 사용 사례별로 한눈에 파악할 수 있는 분류는 다음과 같습니다.

![피드 분류](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>모델링 사용 사례의 경우 활성화 시에만 CPM 사용을 보고해야 합니다. 모델을 실행만 하고 활성화하지 않는 경우 사용 보고가 필요하지 않습니다.

<br> 

## 정액 요금 데이터 피드에 대한 청구 및 노출 할당 {#billing-flat-fee}

정액 요금 데이터 피드에서는 구독이 시작되는 시기 또는 사용하는 노출 횟수에 관계없이 매월 고정 금액을 청구합니다. 일부 월 사용량 또는 간격에 대해서는 요금이 비례배부되지 않습니다. CPM 청구와 마찬가지로 Adobe은 송장을 생성하고 구독한 데이터 피드에 대해 월별 고정 요금 방식으로 청구합니다.

예를 들어, 이달 중순에 피드의 특정 트레이트를 켜기로 결정했다고 가정해 보겠습니다. 구독을 시작한 시기 또는 특정 트레이트를 활성화한 시기에 상관없이 여전히 전체 월별 요금으로 청구됩니다.
