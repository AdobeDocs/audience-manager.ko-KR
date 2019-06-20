---
description: Audience Manager 내에서 서드 파티 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-description: Audience Manager 내에서 서드 파티 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-title: 데이터 구매자를 위한 Audience Marketplace
solution: Audience Manager
title: 데이터 구매자를 위한 Audience Marketplace
topic: DIL API
uuid: F 505 B 5 F 4-4231-4 E 84-993 A-CD 64128 B 540 F
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# Audience Marketplace for Data Buyers {#audience-marketplace-for-data-buyers}

Overview and workflow for data buyers who want to purchase third-party data from within [!DNL Audience Manager].

>[!NOTE]
>[역할 기반 권한은](../../../reporting/reports-dashboard.md) [!UICONTROL Audience Marketplace] 기능에 대한 액세스를 제어합니다.
>
>* 관리자는 데이터 피드를 만들고, 가입자를 관리하며, 데이터 피드를 구독할 수 있습니다.
>* 사용자는 피드를 검색하고 볼 수만 있습니다.


## The Marketplace: About {#about-marketplace}

<!-- c_marketplace_about.xml -->

The [!UICONTROL Marketplace] is an [!DNL Audience Manager] feature for data buyers that lists data feeds you can subscribe to. It lists flat rate, [!DNL CPM], or private data feeds. These feeds are provided by third-party vendors that use [!DNL Audience Manager] to sell data. In the [!UICONTROL Marketplace], reporting tools let you track feed usage and the overlap between your traits and those in a subscribed data feed. Finally, with [!UICONTROL Audience Marketplace], [!DNL Adobe] takes care of invoices and fee payments (though you do have to self-report usage when subscribed to a [!DNL CPM] feed). 이러한 기능을 사용하면 데이터 공급자를 찾는 데 시간을 허비하지 않고도 효과적인 데이터 소스를 찾을 수 있습니다.

>[!TIP]
> 
>**[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** 를 사용하여 구독할 수 있는 고품질 데이터 피드를 찾으십시오. Then, go back into the Audience Manager UI or use the [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) to subscribe to the feeds you found.

![](assets/buyer_marketplace.png)

[!UICONTROL Marketplace] 목록에는 정렬 및 검색을 통해 귀하에게 딱 맞는 데이터 피드를 찾을 수 있는 정보가 포함되어 있습니다. [!UICONTROL Marketplace] 구매자의 목록에 있는 항목은 다음과 같습니다.

* **[!UICONTROL Search]:** 이름이나 텍스트 설명으로 데이터 피드를 찾습니다.
* **[!UICONTROL Name]:** 데이터 피드 이름.
* **[!UICONTROL Description]:** 데이터 피드의 콘텐트에 대한 정보입니다.
* **[!UICONTROL Provider]:** 데이터 공급자의 이름입니다.
* **[!UICONTROL Traits]:** 데이터 피드의 트레이트 수입니다.
* **[!UICONTROL 30 Day Provider Unique Users]:** 지난 30 일 동안 본 고유 사용자의 수입니다.
* **[!UICONTROL 30 Day Overlapped Uniques]:** 공급자의 계정에서 사용자와 겹치는 계정의 사용자 수입니다.
* **[!UICONTROL Feed Overlap]:** 30 일의 중첩된 고유 값 값으로, 백분율로 표시된 후 다음과 같이 계산됩니다. 데이터 구매자 30 일 중첩 고유 방문자 수/데이터 구매자 30 일 고유 방문자) x 100.
* **[!UICONTROL Private Feeds]:** [비공개 데이터 피드를 참조하십시오](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]:** 데이터 공급자와 보유한 구독의 수입니다.

## 비공개 데이터 피드 {#private-data-feeds}

[!UICONTROL Marketplace] 목록에서 공급자의 이름과 특성 데이터가 비공개로 표시되는 경우가 있습니다. This indicates a [private data feed](../../../features/audience-marketplace/marketplace-private-feeds.md). 판매자는 비공개 데이터 피드를 사용하여 구매자의 데이터에 대한 액세스를 제한할 수 있습니다. 판매자는 특별 할인, 할인 또는 개인 정보 및 액세스 제어 기능이 중요한 경우 피드를 비공개 상태로 만들 수 있습니다. 비공개 피드에 액세스하려면 구매자에게 구독 요청을 보내야 합니다. See [Subscribe to a Private Data Feed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) for details.

>[!MORE_ like_ this]
>
>* [Audience Marketplace의 계획 세부 정보 페이지 이해](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [데이터 구매자를 위한 할인 혜택](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

