---
description: 데이터 피드를 사용하려면 이름, 설명, 데이터 소스 및 계획 유형이 필요합니다. 피드를 저장하고 활성화하기 전까지 피드가 비활성화됩니다. Audience Marketplace > 내 공유 데이터에 공개 또는 비공개 데이터 피드를 설정합니다. 데이터 판매자만 사용할 수 있습니다.
seo-description: 데이터 피드를 사용하려면 이름, 설명, 데이터 소스 및 계획 유형이 필요합니다. 피드를 저장하고 활성화하기 전까지 피드가 비활성화됩니다. Audience Marketplace > 내 공유 데이터에 공개 또는 비공개 데이터 피드를 설정합니다. 데이터 판매자만 사용할 수 있습니다.
seo-title: 데이터 피드 생성, 가격 및 관리
solution: Audience Manager
title: 데이터 피드 생성, 가격 및 관리
topic: DIL API
uuid: E 28 C 20 B 3-33 FC -4485-8 EE 9-8530 D 126 F 741
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create, Price, and Manage Data Feeds {#create-price-and-manage-data-feeds}

데이터 피드를 사용하려면 이름, 설명, 데이터 소스 및 계획 유형이 필요합니다. 피드를 저장하고 활성화하기 전까지 피드가 비활성화됩니다. [!UICONTROL Audience Marketplace] &gt; [!UICONTROL My Shared Data]에서 공개 또는 비공개 데이터 피드 설정 데이터 판매자만 사용할 수 있습니다.

## Create a Public or Private Data Feed {#create-public-private-data-feed}

데이터 피드를 사용하려면 이름, 설명, 데이터 소스 및 계획 유형이 필요합니다. 피드를 저장하고 활성화하기 전까지 피드가 비활성화됩니다. Set up public or private data feeds in **[!UICONTROL Audience Marketplace > My Shared Data]**. 데이터 판매자만 사용할 수 있습니다.

<!-- t_data_feed.xml -->

공개 또는 비공개 데이터 피드를 만들려면 관리자 권한이 있어야 합니다.
데이터 피드를 만들려면:

1. 클릭 **[!UICONTROL New Data Feed]**.
1. 데이터 피드 이름을 지정합니다. 데이터 구매자는 이름을 기준으로 피드를 검색할 수 있습니다.
1. 간단한 설명을 입력합니다 (최대 255 자).

   좋은 설명은 피드를 정확하게 설명해야 합니다. For example, you could include text for marketing categories, demographics, and geographic coverage (e.g., [!DNL US] or North America). 설명 텍스트는 검색 가능하며 구매자가 피드를 찾거나 평가할 수 있도록 도와줍니다. 데이터 피드에 가입자를 유치하는 것이 좋은 설명입니다.
1. Select a data source from the **[!UICONTROL Data Source]** options.

   >[!IMPORTANT]
   >
   >이 데이터 소스에 속하는 현재 및 향후 모든 트레이트는 이 피드의 일부로서 데이터 구매자와 공유됩니다.

1. In [!UICONTROL Plan Types], select the options you want to use and click **[!UICONTROL Add Plan]**.

   피드에 여러 가지 플랜이 포함될 수 있습니다. 계획에는 여러 가지 사용 사례가 포함될 수 있습니다. For details, see [Plan Types for Data Feeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Click **[!UICONTROL Save]** to save your data fee *without* activating it.
1. 데이터 피드를 저장하고 활성화하려면:
   1. **[!UICONTROL Availability]** 슬라이더를 **[!UICONTROL Active]** 로 이동합니다.
   1. 클릭 **[!UICONTROL Save]**.
   >[!NOTE]
   >
   >* 저장되고 활성화된 데이터 피드는 삭제할 수 없습니다.
   >* 구매자는 활성 피드를 볼 수만 있습니다.


### 옵션: 비공개 데이터 피드 만들기

[!UICONTROL Settings] 섹션에서 슬라이더를 다음 위치로 이동합니다.

* **[!UICONTROL Private]****[!UICONTROL Branded]** And: 구매자의 [!UICONTROL Marketplace] 목록에는 [공급자] 열에 판매자의 이름이 표시되고 다른 모든 데이터는 숨겨집니다.

* **[!UICONTROL Private]****[!UICONTROL Unbranded]** And: 구매자의 [!UICONTROL Marketplace] 목록에는 데이터 피드 이름과 설명만 표시됩니다. The data provider name appears as [!UICONTROL Private Seller].

To see what a private feed looks like to buyers, see the buyers section in [Private Data Feeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

>[!MORE_ like_ this]
>
>* [비공개 데이터 피드](../../../features/audience-marketplace/marketplace-private-feeds.md)


## 가입자의 데이터 피드 비활성화 {#deactivate-data-feed}

[!UICONTROL Audience Marketplace] 데이터 공급자는 가입한 데이터 피드에 대한 구매자 액세스를 취소할 수 있습니다. 유료 지급/비지불 수수료 또는 트레이트 데이터를 잘못 사용하는 경우와 같은 이유로 피드를 피드에서 제거할 수 있습니다.

<!-- marketplace-deactiva4te-subscribers.xml -->

가입자를 해지하려면:

1. In [!UICONTROL My Shared Data], find the feed the subscriber is using.

   >[!NOTE]
   >
   >지연 계정이 있는 데이터 피드는 삼각형/느낌표 아이콘으로 플래그가 지정됩니다.

1. [!UICONTROL Subscribers] 열에서 해당 피드의 가입자를 카운트하는 파란색 숫자를 클릭합니다. 구독 세부 사항 페이지가 열립니다.
1. **[!UICONTROL Subscription]** 슬라이더를 **[!UICONTROL Off]** 로 이동합니다. 확인 대화 상자가 열립니다.
1. [!UICONTROL Confirmation] 팝업을 **[!UICONTROL Yes]** 비활성화하거나 구독을 변경하지 **[!UICONTROL Cancel]** 않고 종료하려면 팝업을 클릭합니다.

### 가입자를 비활성화한 후 발생하는 내용

데이터 피드에 대한 액세스를 취소하면 데이터 구매자의 계정에 있는 모든 관리자 사용자에게 알림 이메일을 보냅니다. 이메일에는 취소된 트레이트가 나열된 첨부 파일이 포함되어 있습니다. 이 목록은 구독자가 세그먼트와 모델에서 비활성화된 트레이트를 찾아 제거하는 데 도움이 됩니다.

### 요금 청구 및 피드 비활성화

데이터 피드에 대한 액세스를 제거한 후, 구독자는 피드를 비활성화한 시기에 따라 이전 또는 현재 달에 대한 비용을 책임집니다.

## Plan Types for Data Feeds {#plan-types}

[!DNL Plan types] 데이터 피드에 필수 구성 [!UICONTROL Audience Marketplace] 요소입니다. 데이터 제공업체에서는 피드에 대해 여러 가지 사용 사례와 가격 옵션을 만들 수 있습니다. 또한 각 데이터 피드에 대한 몇 가지 계획을 만드는 것이 좋은 전략일 수 있습니다. 이를 통해 구매자는 데이터를 모델링하거나 목적지로 전송하는 데이터를 선택할 수 있습니다.

[선택할 데이터 피드를](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) 만듭니다 [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Plan Types and Use Case Options {#plan-types-use-cases}

<!-- c_feed_options.xml -->

[!UICONTROL Use Case] 설정을 통해 판매자가 데이터를 사용하는 방법을 제어할 수 있습니다.

### 세그먼트 및 겹침

A **[!UICONTROL Segments and Overlap]** use case creates a plan that lets buyers compare trait data in a [trait-to-trait overlap report](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Furthermore, buyers can add your data to segments and make comparisons with the [segment-to-trait](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) and [segment-to-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) reports.

Each data feed must include at least one [!UICONTROL Segments and Overlap] use case. Buyers cannot subscribe to other plans in a data feed if the feed does not contain a [!UICONTROL Segments and Overlap] use case, either by itself or in combination with another use case.

겹치기 비교를 통해 구매자에게 도움이 될 수 있습니다.

* **고객 범위 확대:** 겹침 낮음에는 구매자가 이전에 보지 못했던 사용자가 포함됩니다. 따라서 구매자는 이러한 트레이트를 사용하여 새 사용자를 대상 세그먼트에 추가할 수 있습니다.
* **기존 고객 강화:** 오버랩은 사용자의 특성에는 구매자가 이미 알고 있는 것과 유사한 사용자가 포함됩니다. 그 결과 구매자는 이러한 트레이트가 개발된 대상을 대상으로 점진적으로 개선되고 개선되도록 할 수 있습니다.

이 사용 사례를 다음과 같이 가격이 책정됩니다.

* 측정 단위: 정가
* 가격: 무료 ($ 0.00)

### 모델링

A **[!UICONTROL Modeling]** use case creates a plan that lets buyers compare your traits to theirs with [algorithmic modeling](../../../features/algorithmic-models/understanding-models.md#understanding-models). 구매자는 모델 결과를 검토하여 유사한 전환 속성을 자신의 데이터와 공유하는 새로운 고객을 찾습니다. 이 사용 사례를 다음과 같이 가격이 책정됩니다.

* 측정 단위: 정가
* 가격: 할인 또는 시장이자가격

### 활성화

An **[!UICONTROL Activation]** use case lets buyers send data to a [destination](../../../features/destinations/destinations.md). 이 사용 사례에서는 구매자가 중복 보고서나 알고리즘 모델로 데이터를 비교할 수 없습니다. 이 사용 사례를 다음과 같이 가격이 책정됩니다.

* Unit of Measure: [!DNL CPM]
* Price: [!DNL CPM] market rate

## Billing and Price Options {#billing}

요금 청구 및 가격 옵션은 구매자의 데이터 결제 방식을 제어합니다.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 옵션 </th> 
   <th colname="col2" class="entry"> 설명 </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 청구 주기</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> 월정액 옵션은</span></b> 유일한 옵션입니다. 청구 주기는 매월 10 일에 종료됩니다. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 측정 단위</span></b> </td> 
   <td colname="col2">CPM 요금이나 정가로 데이터 구매자 비용 부과 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> CPM 가격을 사용하는 데이터 구매자는 자체 보고서 사용을 해야 합니다. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">정액 요금 요금제는 고정된 요금이 부과되기 때문에 데이터 구매자의 사용을 보고하지 않습니다. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> 가격</span></b> </td>
   <td colname="col2"> 판매자가 구매자에게 CPM 요금이나 정가로 요금을 부과하는 금액. </td>
  </tr> 
 </tbody> 
</table>

## Plan Notes {#plan-notes}

**[!UICONTROL Additional Notes]** 필드에서, 피드의 각 데이터 계획을 설명하는 데 시간이 걸립니다. 유용한 설명은 구매자가 데이터 피드에서 각 계획의 컨텐츠 또는 목적을 이해하는 데 도움이 됩니다. 구매자는 새로운 데이터 소스를 검색하거나 평가할 때 데이터 피드 및 계획 설명을 읽을 수 있습니다.

## Manage Private Data Feed Requests {#manage-private-requests}

구매자의 개인 피드 요청을 관리하기 위한 공급자 워크플로우.

To review, approve, or reject buyer requests, go to [!UICONTROL My Shared Data] and:

<!-- t_private_feed_workflows.xml -->

1. 비공개 데이터 피드의 이름을 클릭합니다.
2. Click **[!UICONTROL Access Requests]** to review all the buyers who want access to your data feed.
3. In the [!UICONTROL Allow Access] section of each request box, click the check mark to approve a request or the X to deny access.
4. 확인 팝업에서 선택한 작업을 확인하거나 취소합니다.

>[!MORE_ like_ this]
>
>* [비공개 데이터 피드](../../../features/audience-marketplace/marketplace-private-feeds.md)


## Discounts for Data Providers {#discounts}

In [!UICONTROL Audience Marketplace], discounts let you reduce the published price of a data feed for individual subscribers. 구독 요청을 제출한 구독자나 데이터 피드 세부 정보를 요청한 가입자에게 할인 혜택을 제공할 수 있습니다. Discounts apply to [!DNL CPM] and flat rate feeds. 신규 고객에 대한 구독 인센티브를 제공하거나 고객 충성도를 보상하기 위해 할인 혜택을 받을 수 있습니다.

## Apply Discounts to a Data Feed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

피드를 할인하려면 할인 필드에 할인 금액을 %로 추가하고 변경 사항을 확인합니다. Data providers can discount a data feeds in [!UICONTROL Audience Marketplace] from either:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In these examples, the seller has added 10% discount to the [!UICONTROL Software Audience] data feed.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Review Discounted Feeds {#review-discounted-feeds}

Data providers can see all of their subscribers and discounted feeds in **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)