---
description: Audience Manager 내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-description: Audience Manager 내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-title: 데이터 구매자용 Audience Marketplace
solution: Audience Manager
title: 데이터 구매자용 Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 3%

---

# [!UICONTROL Audience Marketplace] 데이터 구매자용  {#audience-marketplace-for-data-buyers}

[!DNL Audience Manager] 내에서 타사 데이터를 구매하려는 데이터 구매자에 대한 개요 및 워크플로우입니다.

>[!NOTE]
>[역할 기반 권한](../../../reporting/reports-dashboard.md)은 [!UICONTROL Audience Marketplace] 기능에 대한 액세스를 제어합니다.
>
>* 관리자는 데이터 피드를 만들고, 구독자를 관리하고, 데이터 피드에 가입할 수 있습니다.
>* 사용자는 피드만 검색하고 볼 수 있습니다.


## [!UICONTROL Marketplace]:{#about-marketplace} 정보

[!UICONTROL Marketplace] 은 구독할 수 있는 데이터 피드를 나열하는 데이터 구매자를 위한 [!DNL Audience Manager] 기능입니다. 플랫 비율, [!DNL CPM] 및 비공개 데이터 피드가 나열됩니다. 이러한 피드는 [!DNL Audience Manager]을 사용하여 데이터를 판매하는 타사 공급업체에서 제공합니다.

[!UICONTROL Marketplace]에서 보고 도구를 사용하여 피드 사용량과 [!UICONTROL traits] 및 구독한 데이터 피드에 있는 피드 간의 겹침을 추적할 수 있습니다. 마지막으로 [!UICONTROL Audience Marketplace] 을 사용하면 [!DNL Adobe]이(가) 송장 및 수수료 지급을 처리합니다(하지만 [!DNL CPM] 피드를 구독할 때 자체 보고서 사용량을 보고해야 함). 이러한 기능을 사용하면 데이터 공급자를 찾는 데 시간을 허비하지 않고 효과적인 데이터 소스를 찾을 수 있습니다.

>[!TIP]
>
>**[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**&#x200B;를 사용하여 구독할 수 있는 고품질 데이터 피드를 찾으십시오. 그런 다음 [!DNL Audience Manager] 사용자 인터페이스로 돌아가거나 [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)를 사용하여 찾은 피드에 가입합니다.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

[!UICONTROL Marketplace] 목록에는 정렬 및 검색하여 자신에게 적합한 데이터 피드를 찾을 수 있는 정보가 포함되어 있습니다. [!UICONTROL Marketplace] 구매자 목록의 품목은 다음과 같습니다.

* **[!UICONTROL Search]**:이름 또는 텍스트 설명별로 데이터 피드를 찾습니다.
* **[!UICONTROL Similar Traits]**:데이터 피드 [!UICONTROL traits] 의 유사한 수를 보여줍니다. 이 열은 **[!UICONTROL Similarity To]** 섹션에서 필터링할 [!UICONTROL trait] 또는 [!UICONTROL segment]을 입력한 후에 표시됩니다.
* **[!UICONTROL Name]**:데이터 피드의 이름입니다.
* **[!UICONTROL Description]**:데이터 피드의 컨텐츠에 대한 정보입니다.
* **[!UICONTROL Provider]**:데이터 공급자의 이름입니다.
* **[!UICONTROL Traits]**:데이터 피드 [!UICONTROL traits] 의 수입니다.
* **[!UICONTROL 30 Day Provider Unique Users]**:지난 30일 동안 본 고유한 사용자 수입니다.
* **[!UICONTROL 30 Day Overlapped Uniques]**:계정의 사용자 수가 공급자 계정의 사용자와 겹칩니다.
* **[!UICONTROL Feed Overlap]**:다음과 같이 계산된 백분율로 표시되는 30일 겹친 고유 값:데이터 구매자 30일 고유 사항 / 데이터 구매자 30일 고유 사항) x 100과 겹쳤습니다.
* **[!UICONTROL Private Feeds]**:비공개  [데이터 피드 를 참조하십시오](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**:데이터 공급자에 있는 구독 수입니다.

 

필요에 가장 적합한 데이터 피드를 쉽게 찾으려면 [!UICONTROL Marketplace] 페이지 왼쪽에서 사용할 수 있는 다음 필터를 사용하십시오.

* **[!UICONTROL Similarity To]**:선택한 또는  [!UICONTROL trait] 중 하나의 유사성에 따라 데이터  [!UICONTROL segment] 피드를 필터링합니다. 비교할 [!UICONTROL trait] 또는 세그먼트를 입력할 때 [!UICONTROL trait] 또는 [!UICONTROL segment] ID 또는 해당 이름을 사용할 수 있습니다.
* **[!UICONTROL Similarity Cutoff]**:슬라이더를 드래그하여 데이터 피드가 선택한 또는 과 얼마나 유사한지 [!UICONTROL traits] 에 따라  [!UICONTROL trait] 데이터 피드를 필터링합니다 [!UICONTROL segment]. [!UICONTROL trait] 유사성 점수에 대한 자세한 내용은 [트레이트 유사성 점수](../../segments/trait-recommendations.md#trait-similarity-score)를 참조하십시오
* **[!UICONTROL Subscription Status]**:구독 상태에 따라 데이터 피드를 필터링합니다.
* **[!UICONTROL Plan Use Case]**:지원되는 사용 사례를 기반으로 데이터 피드를 필터링합니다. **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** 및  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**:가격 유형에 따라 데이터 피드를 필터링합니다.

## 비슷한 [!UICONTROL Traits] {#finding-similar-traits} 찾기

[!UICONTROL Audience Marketplace] 기존 또는 세그먼트와 유사성 [!UICONTROL traits] 에 따라 다양한 데이터 피드에서 찾을 수 있는 옵션 [!UICONTROL traits] 을 제공합니다. 방법은 다음과 같습니다.

1. **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**(으)로 이동합니다.
2. **[!UICONTROL Similarity To]** 선택기를 사용하여 [!UICONTROL trait] 또는 [!UICONTROL segment]를 기준으로 필터링 중에서 선택합니다. [!UICONTROL trait]/[!UICONTROL segment] ID 또는 이름을 기준으로 필터링할 수 있습니다. 검색 상자는 입력에 따라 관련 제안을 자동으로 표시합니다.
3. 필터링할 트레이트 또는 세그먼트를 식별했으면 추천 목록에서 클릭합니다.
4. 결과 범위를 좁히려면 **[!UICONTROL Similarity Cutoff]** 슬라이더를 사용하여 덜 유사한 [!UICONTROL traits]에서 더 유사한 것으로 이동합니다.

필터링이 완료되면 결과 페이지에 새 열이 표시됩니다.**[!UICONTROL Similar Traits]** 이 열에는 필터링 기준을 충족하는 각 데이터 피드에서 필터링한 값과 유사한 [!UICONTROL traits] 수가 표시됩니다.

유사한 트레이트의 전체 목록을 보려면 **[!UICONTROL Similar Traits]** 열에서 숫자를 클릭합니다.

>[!NOTE]
>
> Audience Marketplace은 데이터 피드에 걸친 상위 500개의 유사한 [!UICONTROL trait] 결과를 표시합니다.

유사한 [!UICONTROL traits]을 찾는 방법에 대한 전체 개요를 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 비공개 데이터 피드 {#private-data-feeds}

[!UICONTROL Marketplace] 목록에서 경우에 따라 공급자의 이름과 [!UICONTROL trait] 데이터가 비공개로 표시됩니다. 이는 [개인 데이터 피드](../../../features/audience-marketplace/marketplace-private-feeds.md)를 나타냅니다. 비공개 데이터 피드를 통해 판매자는 구매자의 데이터 액세스를 제한할 수 있습니다. 판매자는 특별 거래, 할인 또는 개인 정보 및 액세스 제어가 중요한 경우 비공개 피드를 만들 수 있습니다. 구매자는 개인 피드에 액세스하려면 판매자에게 구독 요청을 보내야 합니다. 자세한 내용은 [개인 데이터 피드 가입](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 을 참조하십시오.

>[!MORELIKETHIS]
>
>* [Audience Marketplace의 계획 세부 정보 페이지 이해](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
* [데이터 구매자를 위한 할인](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

