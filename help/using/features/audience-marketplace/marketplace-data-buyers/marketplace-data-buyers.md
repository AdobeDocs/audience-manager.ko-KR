---
description: Audience Manager 내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: 데이터 구매자용 Audience Marketplace
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# [!UICONTROL Audience Marketplace] 데이터 구매자용 {#audience-marketplace-for-data-buyers}

내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로 [!DNL Audience Manager].

>[!NOTE]
>[역할 기반 권한](../../../reporting/reports-dashboard.md) 액세스 제어 대상: [!UICONTROL Audience Marketplace] 기능.
>
>* 관리자는 데이터 피드를 만들고, 구독자를 관리하며, 데이터 피드에 가입할 수 있습니다.
>* 사용자는 피드를 검색하고 볼 수만 있습니다.


## 다음 [!UICONTROL Marketplace]: 정보 {#about-marketplace}

다음 [!UICONTROL Marketplace] 은(는) [!DNL Audience Manager] 가입할 수 있는 데이터 피드를 나열하는 데이터 구매자를 위한 기능입니다. 정액 요금표입니다 [!DNL CPM], 비공개 데이터 피드 이러한 피드는 를 사용하는 서드파티 공급업체에서 제공합니다. [!DNL Audience Manager] 데이터를 판매합니다.

다음에서 [!UICONTROL Marketplace], 보고 도구를 사용하여 피드 사용 및 다음 항목 간의 겹침을 추적할 수 있습니다. [!UICONTROL traits] 구독 중인 데이터 피드의 사용자를 참조하십시오. 마지막으로 [!UICONTROL Audience Marketplace], [!DNL Adobe] 청구서 및 수수료 지불 처리 ( 를 구독할 때 사용량을 자가 보고해야 함 ) [!DNL CPM] 피드). 이러한 기능을 사용하면 데이터 공급자를 찾는 데 시간을 낭비하지 않고 효과적인 데이터 소스를 찾을 수 있습니다.

>[!TIP]
>
>사용 **[Adobe 대상 파인더](https://www.adobe-audience-finder.com/)** 구독할 수 있는 고품질 데이터 피드를 찾으십시오. 그런 다음 로 돌아갑니다. [!DNL Audience Manager] 사용자 인터페이스 또는 사용 [Audience Marketplace 구매자 API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) 를 클릭하여 찾은 피드에 가입합니다.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

다음 [!UICONTROL Marketplace] 목록에는 정렬하고 검색하여 본인에게 적합한 데이터 피드를 찾을 수 있는 정보가 포함되어 있습니다. 의 항목 [!UICONTROL Marketplace] 구매자 목록에는 다음이 포함됩니다.

* **[!UICONTROL Search]**: 이름 또는 텍스트 설명별로 데이터 피드를 찾습니다.
* **[!UICONTROL Similar Traits]**: 유사한 항목의 수를 보여줍니다. [!UICONTROL traits] 데이터 피드에서. 이 열은 을(를) 입력한 후에 표시됩니다. [!UICONTROL trait] 또는 [!UICONTROL segment] 에서 필터링 기준: **[!UICONTROL Similarity To]** 섹션.
* **[!UICONTROL Name]**: 데이터 피드의 이름.
* **[!UICONTROL Description]**: 데이터 피드의 콘텐츠에 대한 정보입니다.
* **[!UICONTROL Provider]**: 데이터 공급자의 이름입니다.
* **[!UICONTROL Traits]**: 의 수 [!UICONTROL traits] 데이터 피드에서.
* **[!UICONTROL 30 Day Provider Unique Users]**: 지난 30일 동안 표시된 고유 사용자 수입니다.
* **[!UICONTROL 30 Day Overlapped Uniques]**: 공급자 계정의 사용자와 겹치는 계정의 사용자 수입니다.
* **[!UICONTROL Feed Overlap]**: 30일 겹친 고유 값, 백분율로 표시됨: 데이터 구매자 30일 겹친 고유/데이터 구매자 30일 고유) x 100으로 계산된 값.
* **[!UICONTROL Private Feeds]**: 를 참조하십시오 [비공개 데이터 피드](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: 데이터 공급자에 대한 구독 수입니다.

 

요구 사항에 가장 적합한 데이터 피드를 쉽게 찾으려면 의 왼쪽에 있는 다음 필터를 사용하십시오. [!UICONTROL Marketplace] 페이지:

* **[!UICONTROL Similarity To]**: 다음 중 하나와의 유사성을 기준으로 데이터 피드 필터링 [!UICONTROL trait] 또는 [!UICONTROL segment] 선택하셨을 때 을(를) 입력할 때 [!UICONTROL trait] 또는 비교할 세그먼트를 만들 때 [!UICONTROL trait] 또는 [!UICONTROL segment] ID 또는 해당 이름.
* **[!UICONTROL Similarity Cutoff]**: 슬라이더를 드래그하여 데이터 피드가 얼마나 유사한지에 따라 데이터 피드를 필터링합니다 [!UICONTROL traits] 은(는) 선택한 항목에 해당합니다. [!UICONTROL trait] 또는 [!UICONTROL segment]. 에 대해 자세히 알아보기 [!UICONTROL trait] 유사성 점수, 참조 [트레이트 유사성 점수](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: 구독 상태를 기반으로 데이터 피드를 필터링합니다.
* **[!UICONTROL Plan Use Case]**: 지원되는 사용 사례를 기반으로 데이터 피드를 필터링합니다. **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]**, 및 **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: 가격 유형에 따라 데이터 피드를 필터링합니다.

## 유사 항목 찾기 [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 을(를) 찾는 옵션을 제공합니다. [!UICONTROL traits] 기존 피드와의 유사성을 기반으로 다양한 데이터 피드에서 [!UICONTROL traits] 또는 세그먼트. 방법은 다음과 같습니다.

1. 다음으로 이동 **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. 사용 **[!UICONTROL Similarity To]** 을(를) 기반으로 필터링 중에서 선택하는 선택기 [!UICONTROL trait] 또는 [!UICONTROL segment]. 다음을 기준으로 필터링할 수 있습니다. [!UICONTROL trait]/[!UICONTROL segment] ID 또는 이름. 검색 상자는 입력에 따라 관련 제안을 자동으로 표시합니다.
3. 필터링할 트레이트 또는 세그먼트를 식별했으면 제안 목록에서 해당 트레이트를 클릭합니다.
4. 결과 범위를 좁히려면 **[!UICONTROL Similarity Cutoff]** 더 유사하지 않은 항목에서 이동하는 슬라이더 [!UICONTROL traits]을 클릭하여 더 유사한 항목으로 변경합니다.

필터링이 완료되면 결과 페이지에 새 열이 표시됩니다. **[!UICONTROL Similar Traits]**. 이 열에는 유사한 항목의 수가 표시됩니다 [!UICONTROL traits] 필터링 기준을 충족하는 각 데이터 피드에서 필터링 기준으로 사용할 수 있습니다.

유사한 트레이트의 전체 목록을 보려면 **[!UICONTROL Similar Traits]** 열.

>[!NOTE]
>
> Audience Marketplace에 상위 500개가 유사하게 표시됨 [!UICONTROL trait] 데이터 피드에 있는 의 결과입니다.

유사한 항목을 찾는 방법에 대한 전체 개요는 아래 비디오를 참조하십시오 [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## 비공개 데이터 피드 {#private-data-feeds}

다음에서 [!UICONTROL Marketplace] list, sometimes때때로 제공자 이름 및 [!UICONTROL trait] 데이터는 비공개로 표시됩니다. 이는 다음을 나타냅니다. [비공개 데이터 피드](../../../features/audience-marketplace/marketplace-private-feeds.md). 비공개 데이터 피드를 통해 판매자는 자신의 데이터에 대한 구매자 액세스를 제한할 수 있습니다. 판매자는 특별 할인, 할인 또는 개인 정보 보호 및 액세스 제어가 중요한 경우 피드를 비공개로 만들 수 있습니다. 구매자가 프라이빗 피드에 접속하려면 판매자에게 가입 요청을 보내야 한다. 다음을 참조하십시오 [개인 데이터 피드 구독](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 을 참조하십시오.

>[!MORELIKETHIS]
>
>* [Audience Marketplace의 계획 세부 정보 페이지 이해](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [데이터 구매자를 위한 할인](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

