---
description: Audience Marketplace 데이터 구매자는 CPM (천 광고당 노출 횟수) 당 비용으로 데이터 피드에 포함된 트레이트를 사용하여 제공되는 모든 광고 임프레션을 보고하는 것에 동의합니다. CPM 사용 기간은 각 달력 월의 5 일에 결정되며 이전 달에 대한 데이터를 포함합니다. 가입자는 사용료를 보고할 필요가 없습니다.
seo-description: Audience Marketplace 데이터 구매자는 CPM (천 광고당 노출 횟수) 당 비용으로 데이터 피드에 포함된 트레이트를 사용하여 제공되는 모든 광고 임프레션을 보고하는 것에 동의합니다. CPM 사용 기간은 각 달력 월의 5 일에 결정되며 이전 달에 대한 데이터를 포함합니다. 가입자는 사용료를 보고할 필요가 없습니다.
seo-title: 데이터 피드 구매자에 대한 대금 청구
solution: Audience Manager
title: 데이터 피드 구매자에 대한 대금 청구
topic: DIL API
uuid: D 7236667-282 B -4160-9909-579721 AF 4016
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Billing for Data Feed Buyers {#billing-for-data-feed-buyers}

Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions ([!DNL CPM]) basis. [!DNL CPM] 사용량은 각 달력의 5 일에 해당되며 이전 달의 데이터를 포함합니다. 가입자는 사용료를 보고할 필요가 없습니다.

## How to Report CPM Usage {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] 데이터 구매자는 천 개의 광고 노출 횟수 ([!DNL CPM]) 당 비용으로 데이터 피드에 포함된 트레이트를 사용하여 제공되는 모든 광고 임프레션을 보고하는 것에 동의합니다. [!DNL CPM] 사용량은 각 달력의 5 일에 해당되며 이전 달의 데이터를 포함합니다. 가입자는 사용료를 보고할 필요가 없습니다.

[!UICONTROL Audience Marketplace] 에서는 다음 두 가지 방법으로 사용량을 보고할 [!DNL CPM] 수 있습니다.

* **세그먼트 수준 보고**: 권장 [!DNL CPM] 사용량 보고 방법입니다. When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts, based on the algorithms described in [Cost Attribution for CPM Data Feeds](#cost-attribution).
* **데이터 피드 수준 보고**: 이 방법을 사용하려면 CPM 데이터 피드에 대한 비용 [!DNL CPM] 기여도에 [설명된 알고리즘에 따라 각 데이터 피드에 대한 사용량을 개별적으로 보고해야](#cost-attribution)합니다. 하지만 이 방법은 세그먼트 수준 보고보다 더 단조롭고 오류가 발생하기 쉽습니다.

## Report CPM Usage at Segment Level {#segment-level-report}

[!UICONTROL Segment Usage] 이 탭에서는 세그먼트가 매핑되는 대상을 기준으로 그룹화된 세그먼트를 표시하는 동안 세그먼트 수준 사용량을 보고할 수 있습니다.

After reporting [!DNL CPM] usage at segment level, [!UICONTROL Audience Marketplace] automatically assigns the corresponding data feeds the correct usage, based on the [Cost Attribution for CPM Data Feeds](#cost-attribution).

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]** 이동.
2. **[!UICONTROL Segment Usage]** 탭을 선택합니다.
3. 세그먼트에 대한 사용을 채웁니다. You can use the [!UICONTROL Search] box to filter the segments if you only need to report usage for some of them.
4. 클릭 **[!UICONTROL Edit Segments Usage]**.
5. Enter the [!DNL CPM] usage amount in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you&#39;re done and review the confirmation dialog.
   ![세그먼트 사용 확인](assets/confirm-segment-usage.png)
7. 클릭 **[!UICONTROL Confirm]**.

## Report CPM Usage at Data Feed Level {#feed-level-report}

Data feed-level reporting is a more tedious and prone to error process, since you must individually calculate [!DNL CPM] usage for each data feed. We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead.

To report [!DNL CPM] usage at segment level:

1. **[!UICONTROL Audience Marketplace > Payables]** 이동.
2. **[!UICONTROL Feed Usage]** 탭을 선택합니다.
3. [!UICONTROL Search] 이 상자를 사용하여 데이터 피드를 필터링하고 사용량을 보고하는 데 필요한 데이터 피드를 식별합니다.
4. 클릭 **[!UICONTROL Edit Feeds Usage]**.
5. Calculate the [!DNL CPM] usage for each data feed based on the [Cost Attribution for CPM Data Feeds](#cost-attribution), and enter it in the [!UICONTROL Usage] column.
6. Click **[!UICONTROL Save]** when you&#39;re done and review the confirmation dialog.

   ![confirm-feed-usage](assets/confirm-feed-usage.png)

7. 클릭 **[!UICONTROL Confirm]**.

## Bulk reporting

To reduce errors and overhead while reporting [!DNL CPM] usage, you can use the bulk reporting option to download a [!DNL CSV] file containing the data feeds and segments, fill in the usage, and upload it back to [!DNL Audience Manager]. 일괄 보고를 사용하여 피드 및 세그먼트 사용량을 둘 다 보고할 수 있습니다.

[!DNL CPM] 사용량을 일괄 업데이트하려면:

1. **[!UICONTROL Audience Marketplace > Payables]** 이동.
1. Select the **[!UICONTROL Feed Usage]** or **[!UICONTROL Segment Usage]** tab, depending on the type of reporting that you want to update.
1. **[!UICONTROL Edit Feeds Usage]** OR **[!UICONTROL Edit Segments Usage]** 를 클릭합니다.
1. Click **[!UICONTROL download the current usage]** to make sure you use a valid CSV file.
1. 컴퓨터에서 파일을 열고 사용량 보고서를 입력합니다.
1. Click **[!UICONTROL Choose a CSV file]** to upload the updated usage report.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] 파일을 업로드하는 즉시 유효성을 검사하고 파일에 오류가 있는지 여부를 묻는 메시지가 나타납니다.

### 벌크 보고 유효성 검사 오류

| 오류 메시지 | 설명 | 변수 이름이 아니라, 필터링된 보고서의 머리글로 잘못 표시하는 |
| ------------- | -------------| -----|
| 잘못된 입력 | [!DNL Audience Manager] 열 누락 또는 열 제목의 변경 등 [!DNL CSV] 파일 스키마의 변경 사항이 발견되었습니다. | 표 구조를 변경하지 마십시오. |
| 발견되지 않음 | For [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] could not identify the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. | For [!UICONTROL Segment Level Reporting], check the validity of the [!UICONTROL Segment ID] and [!UICONTROL Destination ID] combination. For [!UICONTROL Feed Level Reporting], check the validity of the [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], and [!UICONTROL Use Case] combination. |
| 중복된 레코드 발견 | [!DNL Audience Manager] 노출 값이 다른 중복 레코드가 발견되었습니다. | 보고서를 검토하고 동일한 데이터 피드 또는 세그먼트에 대해 다른 사용 값을 보고하지 않도록 합니다. |
| 지원되지 않는 값 | [!DNL Audience Manager] 열에서 숫자가 아닌 값을 [!DNL Audience Manager] 감지했습니다. | Review the report and make sure you only enter numerical values in the [!DNL Audience Manager] column. |
| 필수 필드용 헤더 누락 | [!DNL Audience Manager] 필수 필드에 대한 누락된 테이블 헤더가 발견되었습니다. For [!UICONTROL Segment Level Reporting], the mandatory fields are: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. For [!UICONTROL Feed Level Reporting], the mandatory fields are: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | 보고서를 검토하고 테이블 헤더가 변경되지 않았는지 확인합니다. |

>[!NOTE]
>[!DNL CSV] 사용량 보고서에서 행을 제거하면 기존 사용량 보고서에 영향을 주지 않습니다. [!DNL Audience Manager] 보고서에 포함된 필드만 처리합니다.

## [!DNL CPM] 보고 우수 사례

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>항상 총 노출 횟수 보고</b> </p> </td> 
   <td colname="col2"> <p>CPM 노출 합계에 대해: </p>
   <p> 소수를 사용하지 않고 총 노출 횟수를 보고합니다. Audience Manager는 사용자가 보고하는 총 수를 기반으로 CPM를 자동으로 계산합니다.</p><p>1,234,567 개의 노출 횟수를 보고해야 하는 경우 이와 정확히 동일하게 보고합니다. CPM를 계산하기 위해 총 노출 횟수를 1,000로 나눌 필요는 없습니다.</p><p>Adobe Target 또는 Analytics 대상과 같은 도구를 사용하여 웹 또는 앱 컨텐츠 (컨텐츠 최적화) 를 최적화하는 데 사용되는 트레이트는 CPM 플랜의 사용량 합계에 기여하지 않습니다. 일반적으로 데이터 공급자는 정액 요금제를 사용하여 컨텐츠 최적화에 대해 보상을 받습니다.</p><p>See <a href="#cost-attribution">Cost Attribution for CPM Data Feeds</a> for more information. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>월별 보고 간격 준수</b> </p> </td> 
   <td colname="col2"> <p>보고서 시스템은 매월 5 일이 지나면 닫힙니다. 그때까지 CPM 사용량을 보고하지 않을 경우 다음 달의 보고서에 해당 금액을 추가해야 합니다. 예를 들어 10 월에 1000 개의 임프레션을 사용하고 10 월의 보고 마감일을 놓치고 11 월에 1000 개의 임프레션을 사용하는 경우를 예로 들 수 있습니다. 이 경우 10 월과 5 월 사이에 10 월 및 11 월 합계 (2000) 를 보고합니다.</p><p><b>팁</b>: 다음 달의 첫 번째 일과 5 번째 날 사이에 이전 달에 대한 CPM 사용을 항상 보고해야 합니다.</p><p>CPM 사용량을 새 달력의 5 번째 달까지 보고할 수 있지만 권장되지 않습니다. 매월 5 일 전에 CPM 사용량을 보고하면 Audience Manager가 데이터를 확인하고 처리할 수 있습니다.</p> </td>
  </tr> 
 </tbody> 
</table>

## Cost Attribution for CPM Data Feeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] you must self-report impression amounts each month, for each of your segments. We recommend reporting [!DNL CPM] usage at segment level, so that cost attribution is done automatically.

<!-- marketplace_cpm_billing.xml -->

### Billing Summary {#billing-summary}

You must submit [!DNL CPM] data feed impression amounts between the 1st and the 5th days of each calendar month. To do this correctly, we recommend that you [Report CPM Usage at Segment Level](#segment-level-report).

>[!TIP]
>When you report [!DNL CPM] usage at segment level, the data feed-level reporting section is automatically filled in with the corresponding usage amounts.

Should you need to [!UICONTROL Report CPM Usage at Data Feed Level], you must individually compile all impressions delivered for each feed in the previous calendar month, and report them according to the billing allocation described in this article.

After you report [!DNL CPM] number for the previous calendar month, [!DNL Adobe] will do the following:

* Create an invoice and bill you based on the [!DNL CPM] rate for each subscribed data feed.
* Pay data providers (sellers) fees owed based on your reported [!DNL CPM] use.

>[!IMPORTANT]
>
>구매자는 보고된 모든 노출 합계는 반드시 유효하고 정확해야 합니다. 노출 합계를 매달 5 일까지 보고하지 못한 경우 다음 달에 보고되지 않은 월의 총계를 포함해야 합니다.

## Assign Impressions at Feed Level Based on Trait Qualification Rules {#assign-impressions}

The [!UICONTROL Activation] use case lets you use traits in the corresponding data feed to create segments in [Segment Builder](../../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74) and map those segments to a destination. The Boolean operators [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT] let you set the conditions for trait and segment qualification.

When you [Report CPM Usage at Data Feed Level](#feed-level-report), you must allocate impressions proportionally for each data feed, according to the [!DNL Boolean] operators used in the trait qualification rules. 다음 표에는 부울 규칙이나 트레이트 유형별로 노출 수를 적절히 할당하는 방법이 나와 있습니다.

>[!TIP]
>[Audience Manager에서 데이터 피드 수준 보고를 자동으로 수행하도록 세그먼트 수준에서](#segment-level-report) CPM 사용을 보고합니다.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 규칙 자격 로직 또는 유형 </th> 
   <th colname="col2" class="entry"> 청구 배포 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> and</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> AND</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 또는</span> </p> </td> 
   <td colname="col2"> <p>부울 또는 조건을 사용하는 규칙 기반 세그먼트의 모든 공급자에게 전달된 노출 수의 가중 할당을 적용할 수 있습니다. 가중 할당은 다음 공식을 사용하여 계산됩니다.</p><p><code>(트레이트 인구/세그먼트 인구) * 노출 횟수 * CPM 비용</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Apply 100% of the delivered impression totals to all the provider traits in a rules-based segment that uses a Boolean <span class="wintitle"> NOT</span> condition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>알고리즘 세그먼트 </p> </td> 
   <td colname="col2"> <p>알고리즘 트레이트가 들어 있는 세그먼트의 모든 공급자 피드에 전달된 노출 수의 100%를 적용합니다. </p> </td> 
  </tr>
 </tbody>
</table>

## Billing Examples {#billing-examples}

The examples below are meant to illustrate how [!DNL CPM] usage allocation is done at data feed level.

>[!MPORTANT]
>We recommend that you [Report CPM Usage at Segment Level](#segment-level-report) instead, to have this process done automatically.

다음 시나리오를 고려해 보겠습니다.

![billing-examples](assets/billing-examples.png)

### 사례 1: 세그먼트 및 자격 규칙이 있는 세그먼트

이 세그먼트에는 별도의 데이터 공급자의 세 가지 특성이 들어 있습니다. Since segment qualification is based on an [!UICONTROL AND] condition, visitors have to realize the traits from all three feeds to qualify for the segment.

![](assets/billing-segment-and.png)

[!UICONTROL AND] 조건으로, 해당 월의 노출 수를 3 개의 데이터 제공자에게 모두 할당해야 합니다. [!UICONTROL Audience Marketplace > Payables] 이 섹션에서는 1,000,000 개의 노출 횟수가 있는 각 공급자를 크레디트합니다.

This example applies to segments that use [!DNL Boolean] [!UICONTROL NOT] operators or for segments that contain algorithmic traits.

### 사례 2: 세그먼트 규칙이 있는 세그먼트

이 세그먼트에는 별도의 데이터 공급자의 세 가지 특성이 들어 있습니다. Since segment qualification is based on an [!UICONTROL OR] condition, visitors have to realize at least one of the three traits to qualify for the segment.

We cannot tell which trait is responsible for an impression because qualification is based on an [!UICONTROL OR] condition. As a result, in the [!UICONTROL Audience Marketplace > Payables] section you credit each provider with a weighted allocation of the total impressions, based on trait population.

![billing-segment-or](assets/billing-segment-or.png)

>[!MORE_ like_ this]
>
>* [정액 요금 데이터 피드에 대한 요금 청구 및 노출 수 할당](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)


## Billing and Impression Allocation for Flat Fee Data Feeds {#billing-flat-fee}

정액 요금 데이터 피드는 구독의 시작 시기 또는 사용 횟수에 관계 없이 매월 고정된 금액을 청구합니다. 요금은 일부 월 사용량 또는 간격에 대해 비례 배분되지 않습니다. CPM 청구와 마찬가지로 Adobe는 송장을 생성하여 구독한 데이터 피드에 대한 월정액 요금제로 청구하게 됩니다.

예를 들어, 한 달 동안 피드에서 특정 트레이트를 켜기로 결정한 경우 사용료 지불 플랜을 시작하거나 특정 트레이트를 활성화한 시기에 상관없이 매월 전체 요금으로 청구됩니다.