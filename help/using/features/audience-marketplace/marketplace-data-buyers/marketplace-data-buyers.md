---
description: Audience Manager 내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-description: Audience Manager 내에서 타사 데이터를 구매하려는 데이터 구매자를 위한 개요 및 워크플로우
seo-title: 데이터 구매자를 위한 Audience Marketplace
solution: Audience Manager
title: 데이터 구매자를 위한 Audience Marketplace
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

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

이 [!UICONTROL Marketplace] 기능은 구독할 수 있는 데이터 피드를 나열하는 데이터 구매자를 위한 [!DNL Audience Manager] 기능입니다. 평행 속도, [!DNL CPM]개인 데이터 피드를 나열합니다. 이러한 피드는 데이터를 판매하는 데 사용하는 타사 공급업체에서 [!DNL Audience Manager] 제공합니다.

에서 [!UICONTROL Marketplace]보고 도구를 사용하여 피드 사용을 추적할 수 있으며 트레이트와 구독된 데이터 피드의 트레이트 간 겹침을 추적할 수 있습니다. 마지막으로, [!UICONTROL Audience Marketplace]를 [!DNL Adobe] [!DNL CPM] 사용하면 송장과 수수료 지불을 처리합니다(피드에 가입했을 때 사용량을 자동 보고해야 하지만). 이러한 기능을 사용하면 데이터 제공업체를 찾는 데 시간을 허비하지 않고 효과적인 데이터 소스를 찾을 수 있습니다.

>[!TIP]
>
>Adobe Audience **[Finder를](https://www.adobe-audience-finder.com/)** 사용하여 구독할 수 있는 고품질의 데이터 피드를 찾을 수 있습니다. 그런 다음 Audience Manager UI로 돌아가거나 Audience [Marketplace 구매자 API를](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) 사용하여 찾은 피드에 가입합니다.

![buyer-marketplace-overview](assets/buyer-marketplace-overview.png)

이 [!UICONTROL Marketplace] 목록에는 사용자에게 적합한 데이터 피드를 찾기 위해 정렬 및 검색할 수 있는 정보가 포함되어 있습니다. 구매자 목록의 [!UICONTROL Marketplace] 품목은 다음과 같습니다.

* **[!UICONTROL Search]**:이름이나 텍스트 설명별로 데이터 피드를 찾습니다.
* **[!UICONTROL Similar Traits]**:데이터 피드의 유사한 트레이트 수를 보여줍니다. 이 열은 **[!UICONTROL Similarity To]** 섹션에서 필터링할 트레이트 또는 세그먼트를 입력한 후 표시됩니다.
* **[!UICONTROL Name]**:데이터 피드의 이름입니다.
* **[!UICONTROL Description]**:데이터 피드의 컨텐츠에 대한 정보입니다.
* **[!UICONTROL Provider]**:데이터 공급자의 이름입니다.
* **[!UICONTROL Traits]**:데이터 피드의 트레이트 수입니다.
* **[!UICONTROL 30 Day Provider Unique Users]**:지난 30일 동안 본 고유 사용자 수입니다.
* **[!UICONTROL 30 Day Overlapped Uniques]**:공급자 계정의 사용자와 겹치는 계정의 사용자 수입니다.
* **[!UICONTROL Feed Overlap]**:다음과 같이 계산된 백분율로 표시되는 30일 겹친 고유 값데이터 구매자는 30일 동안 고유 방문자/데이터 구매자 30일 고유 방문자) x 100과 겹칩니다.
* **[!UICONTROL Private Feeds]**:비공개 [데이터 피드를 참조하십시오](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**:데이터 공급자에 대한 구독 수입니다.

요구 사항에 가장 적합한 데이터 피드를 쉽게 찾으려면 [!UICONTROL Marketplace] 페이지 왼쪽에 있는 다음 필터를 사용하십시오.

* **[!UICONTROL Similarity To]**:선택한 특성 또는 세그먼트와 유사성에 따라 데이터 피드를 필터링합니다. 비교할 트레이트 또는 세그먼트를 입력할 때 트레이트 또는 세그먼트 ID 또는 각각의 이름을 사용할 수 있습니다.
* **[!UICONTROL Similarity Cutoff]**:슬라이더를 드래그하여 선택한 트레이트 또는 세그먼트와 비슷한 트레이트를 기준으로 데이터 피드를 필터링합니다.
* **[!UICONTROL Subscription Status]**:구독 상태를 기반으로 데이터 피드를 필터링합니다.
* **[!UICONTROL Plan Use Case]**:지원되는 사용 사례를 기반으로 데이터 피드 필터링: **[!UICONTROL Activation]**&#x200B;및 **[!UICONTROL Segments and Overlap]**&#x200B;를 **[!UICONTROL Modelling]**&#x200B;참조하십시오.
* **[!UICONTROL Plan Unit]**:가격 유형에 따라 데이터 피드를 필터링합니다.

이러한 필터를 사용하는 방법에 대한 개요는 아래 비디오를 참조하십시오.

## 유사한 트레이트 찾기 {#finding-similar-traits}

[!UICONTROL Audience Marketplace] 는 기존 트레이트 또는 세그먼트와 유사성에 따라 다양한 데이터 피드에서 트레이트를 찾을 수 있는 옵션을 제공합니다. 이 작업을 수행하는 방법은 다음과 같습니다.

1. &gt; **[!UICONTROL Audience Marketplace]** 로 **[!UICONTROL Marketplace]**&#x200B;이동합니다.
2. 선택기를 사용하여 트레이트 또는 세그먼트를 기준으로 필터링 중 하나를 선택합니다. **[!UICONTROL Similarity To]** 특성/세그먼트 ID 또는 이름을 기반으로 필터링할 수 있습니다. 검색 상자에 입력한 내용에 따라 관련 제안이 자동으로 표시됩니다.
3. 필터링할 트레이트 또는 세그먼트를 식별한 후 제안 목록에서 클릭합니다.
4. 결과 범위를 좁히려면 **[!UICONTROL Similarity Cutoff]** 슬라이더를 사용하여 비슷한 트레이트에서 비슷한 트레이트로 이동합니다.

필터링이 완료되면 결과 페이지에 새 열이 표시됩니다. **[!UICONTROL Similar Traits]** Adobe 이 열에는 필터링 기준을 충족하는 각 데이터 피드에서 필터링한 트레이트와 유사한 트레이트의 수가 표시됩니다.

유사한 트레이트의 전체 목록을 보려면 **[!UICONTROL Similar Traits]** 열에서 숫자를 클릭합니다.

>[!NOTE]
>
> Audience Marketplace는 데이터 피드에서 상위 500개의 유사한 트레이트 결과를 표시합니다.

유사한 트레이트를 찾는 방법에 대한 전체 개요를 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/29370/?captions=kor)


## 비공개 데이터 피드 {#private-data-feeds}

목록에서 [!UICONTROL Marketplace] 공급자의 이름과 특성 데이터가 비공개로 표시되는 경우가 있습니다. 이는 [비공개 데이터 피드를](../../../features/audience-marketplace/marketplace-private-feeds.md)나타냅니다. 개인 데이터 피드를 사용하면 판매자가 구매자의 데이터 액세스를 제한할 수 있습니다. 판매자는 특별 거래, 할인 또는 개인 정보 및 액세스 제어가 중요한 경우 개인 정보를 비공개로 만들 수 있습니다. 구매자는 개인 피드에 액세스하려면 구매자에게 구독 요청을 보내야 합니다. 자세한 [내용은 비공개 데이터 피드](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) 가입을 참조하십시오.

>[!MORELIKETHIS]
>
>* [Audience Marketplace의 계획 세부 정보 페이지 이해](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [데이터 구매자를 위한 할인](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

