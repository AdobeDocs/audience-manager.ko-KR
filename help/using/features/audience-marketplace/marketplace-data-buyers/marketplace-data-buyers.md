---
description: Audience Manager 내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-description: Audience Manager 내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-title: 데이터 구매자를 위한 Audience Marketplace
solution: Audience Manager
title: 데이터 구매자를 위한 Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 12cc02103902a77b8b5967c319f4ac18746a700e

---


# 데이터 구매자를 위한 Audience Marketplace {#audience-marketplace-for-data-buyers}

내부에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 [!DNL Audience Manager]워크플로우

>[!NOTE]
>[역할 기반 권한은](../../../reporting/reports-dashboard.md) 기능에 대한 액세스를 제어합니다 [!UICONTROL Audience Marketplace] .
>
>* 관리자는 데이터 피드를 만들고 구독자를 관리하고 데이터 피드에 가입할 수 있습니다.
>* 사용자는 피드만 검색하고 볼 수 있습니다.


## The Marketplace:정보 {#about-marketplace}

<!-- c_marketplace_about.xml -->

이 [!UICONTROL Marketplace] 기능은 구독할 수 있는 데이터 피드를 나열하는 데이터 구매자를 위한 [!DNL Audience Manager] 기능입니다. 고정 속도 [!DNL CPM]또는 개인 데이터 피드를 나열합니다. 이러한 피드는 데이터를 판매하는 데 사용하는 타사 공급업체에서 [!DNL Audience Manager] 제공합니다. 에서 [!UICONTROL Marketplace]보고 도구를 사용하여 피드 사용을 추적할 수 있으며 트레이트와 구독된 데이터 피드의 트레이트 간 겹침을 추적할 수 있습니다. 마지막으로, [!UICONTROL Audience Marketplace]를 [!DNL Adobe] [!DNL CPM] 사용하면 송장과 수수료 지불을 처리합니다(피드에 가입했을 때 사용량을 자동 보고해야 하지만). 이러한 기능을 사용하면 데이터 제공업체를 찾는 데 시간을 허비하지 않고 효과적인 데이터 소스를 찾을 수 있습니다.

>[!TIP]
> 
>Adobe Audience **[Finder를](https://www.adobe-audience-finder.com/)** 사용하여 구독할 수 있는 고품질의 데이터 피드를 찾을 수 있습니다. 그런 다음 Audience Manager UI로 돌아가거나 Audience [Marketplace 구매자 API를](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) 사용하여 찾은 피드에 가입합니다.

![](assets/buyer_marketplace.png)

이 [!UICONTROL Marketplace] 목록에는 사용자에게 적합한 데이터 피드를 찾기 위해 정렬 및 검색할 수 있는 정보가 포함되어 있습니다. 구매자 목록의 [!UICONTROL Marketplace] 품목은 다음과 같습니다.

* **[!UICONTROL Search]** :이름이나 텍스트 설명별로 데이터 피드를 찾습니다.
* **[!UICONTROL Name]** :데이터 피드의 이름입니다.
* **[!UICONTROL Description]** :데이터 피드의 컨텐츠에 대한 정보입니다.
* **[!UICONTROL Provider]** :데이터 공급자의 이름입니다.
* **[!UICONTROL Traits]** :데이터 피드의 트레이트 수입니다.
* **[!UICONTROL 30 Day Provider Unique Users]** :지난 30일 동안 본 고유 사용자 수입니다.
* **[!UICONTROL 30 Day Overlapped Uniques]** :공급자 계정의 사용자와 겹치는 계정의 사용자 수입니다.
* **[!UICONTROL Feed Overlap]** :다음과 같이 계산된 백분율로 표시되는 30일 겹친 고유 값데이터 구매자는 30일 동안 고유 방문자/데이터 구매자 30일 고유 방문자) x 100과 겹칩니다.
* **[!UICONTROL Private Feeds]** :비공개 [데이터 피드를 참조하십시오](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]** :데이터 공급자에 대한 구독 수입니다.

## 비공개 데이터 피드 {#private-data-feeds}

목록에서 [!UICONTROL Marketplace] 공급자의 이름과 특성 데이터가 비공개로 표시되는 경우가 있습니다. 이는 [비공개 데이터 피드를](../../../features/audience-marketplace/marketplace-private-feeds.md)나타냅니다. 개인 데이터 피드를 사용하면 판매자가 구매자의 데이터 액세스를 제한할 수 있습니다. 판매자는 특별 거래, 할인 또는 개인 정보 및 액세스 제어가 중요한 경우 개인 정보를 비공개로 만들 수 있습니다. 구매자는 개인 피드에 액세스하려면 구매자에게 구독 요청을 보내야 합니다. 자세한 [내용은 비공개 데이터 피드](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 가입을 참조하십시오.

>[!MORELIKE_THIS]
>
>* [Audience Marketplace의 계획 세부 정보 페이지 이해](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [데이터 구매자를 위한 할인](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

