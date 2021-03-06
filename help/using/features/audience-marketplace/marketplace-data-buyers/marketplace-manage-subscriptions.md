---
description: Marketplace에서 데이터 구매자로 이동하여 공개 및 비공개 데이터 피드를 구독합니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.
seo-description: Marketplace에서 데이터 구매자로 이동하여 공개 및 비공개 데이터 피드를 구독합니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.
seo-title: 데이터 피드 가입 관리
solution: Audience Manager
title: 데이터 피드 가입 관리
uuid: 7305adb6-cbb8-4430-8204-2243095c0ba5
feature: Audience Marketplace
exl-id: 171acbbc-88ab-496f-93ea-48956325d8fd
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '2188'
ht-degree: 2%

---

# 데이터 피드 가입 관리 {#manage-data-feed-subscriptions}

[!UICONTROL Marketplace]은 데이터 구매자가 이동하여 공개 및 비공개 데이터 피드를 구독하는 위치입니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.

## 공개 데이터 피드 {#subscript-public-data-feed} 구독

[!UICONTROL Marketplace]은 데이터 구매자가 이동하여 공개 및 비공개 데이터 피드를 구독하는 위치입니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.

<!-- t_subscribe_feed.xml -->

공개 데이터 피드에 가입하려면:

1. **[!UICONTROL Audience Marketplace > Marketplace]**(으)로 이동합니다. 검색 기능을 사용하거나 목록을 검색하여 데이터 피드를 찾습니다.

   ![구독](assets/subscribe1.png)

1. 사용할 데이터 피드의 이름을 클릭합니다. 선택한 피드에 대한 [계획 세부 정보 페이지](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)가 열립니다.

   ![플랜 세부 사항](assets/plan-details.png)

1. 가입 테이블에서 사용 사례를 선택하고
   * **[!UICONTROL Subscription]** 슬라이더를 **[!UICONTROL On]**(으)로 이동합니다.
   * 클릭 **[!UICONTROL Review & Subscribe]**. 그러면 [!UICONTROL Terms and Conditions] 창이 열립니다.

   ![구독](assets/subscribe3.png)

1. [!UICONTROL Terms and Conditions] 창에서 다음을 수행합니다.

   * **중요:**  **[!UICONTROL ID sync]** 확인란을 선택된 상태로 두십시오. 이 설정은 데이터 공급자와의 일치율을 개선하는 데 도움이 됩니다.
   * 조건 상자를 선택하고 **[!UICONTROL Accept]** 을 클릭하여 구독 프로세스를 완료합니다.

   ![구독](assets/subscribe4.png)

### 다음 단계

데이터 피드에 가입한 후:

* [!UICONTROL Traits] 폴더를 확인하여 구독을 확인합니다. [가입한 데이터 피드에 대한 저장소](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee)를 참조하십시오.

* 청구 및 결제 설명서를 검토합니다. 아래의 관련 링크를 참조하십시오.

### 우수 사례 {#best-practices}

다음은 [!UICONTROL Audience Marketplace] 작업 시 따라야 할 모범 사례 세트입니다.

[!UICONTROL Audience Marketplace]을 통해 새로운 제3자 데이터 세트와 제2자 데이터 세트를 탐색할 때 권장되는 첫 번째 단계는 [!UICONTROL Segments & Overlap]에 대한 데이터 피드를 활성화하는 것입니다. 이를 통해 사용자는 세그먼트를 만들어 대상 크기를 평가하고 중복 보고서를 실행하여 초기 대상 통찰력을 얻음으로써 데이터를 탐색할 수 있습니다. 대부분의 데이터 공급자는 이 사용 사례를 무료로 제공하므로 추가 비용 없이 이 분석을 수행할 수 있습니다.

Overlap Reports를 실행할 때 이 모범 사례에 따라 유용한 결과를 얻을 수 있습니다.

1. 겹치는 데이터 세트가 다음과 같은 데이터 유형 및 수집 방법론과 유사한지 확인합니다.
   * 방문자 지역
   * 쿠키와 모바일 ID 비교
   * 전환 확인 기간
   * 오프라인 활동과 온라인 활동 비교
   * 데이터 공급자가 데이터를 새로 고치는 빈도입니다

1. 겹치는 시간은 약간 늘어날 수 있으므로 겹치기 보고서를 실행하기 전에 최대 30일이 지나도록 허용하여 데이터를 동기화할 수 있도록 하십시오.
1. 여러 마케팅 캠페인에서 데이터 공급자의 데이터를 사용하는 경우 겹침이 늘어날 수 있습니다.
그리고 이니셔티브입니다. 이를 통해 두 데이터 세트의 사용자가 더 많은 동기화 기회를 얻을 수 있습니다.
1. 데이터 세트가 중복될 것이라는 보장는 없습니다. 겹치는 부분이 유효하려면 고객의 데이터 세트의 사용자가 데이터와 연결되어 있어야 합니다
보고 기간 동안 공급자 데이터 세트. 고객의 미디어 데이터가 데이터 공급자 데이터 세트의 사용자에게 제공되지 않은 경우 겹치지 않습니다.
1. 낮은 것이 나쁜 것이라고 생각하지 마라. 잠재 고객과 신규 사용자의 참여를 유도하기 위해 낮은 겹치기 효과를 활용하십시오.

## 비공개 데이터 피드 구독 {#subscript-private-data-feed}

구매자는 **[!UICONTROL Audience Marketplace > Marketplace]**&#x200B;에 있는 비공개 데이터 피드 및 계획에 가입합니다.

<!-- t_private_feed.xml -->

>[!TIP]
>
>경우에 따라 데이터 공급자는 개인 데이터 피드에 대해 할인을 제공할 수 있습니다. 구독 요청을 제출할 때 가능한 할인을 요청할 수 있습니다.

비공개 데이터 피드에 가입하려면:

1. [!UICONTROL Marketplace]에서 데이터 피드 이름을 클릭합니다.
1. 클릭 **[!UICONTROL Request Access]**. 그러면 요청 대화 상자가 열립니다.
1. 요청 대화 상자에서 데이터 피드에 대한 관심사를 나타내는 메모를 제공자에게 작성하여 **[!UICONTROL Send]** 을 클릭합니다. 판매자가 메시지를 검토하고 요청을 승인하거나 거부합니다. 승인을 기다리는 동안 해당 데이터 피드의 [!UICONTROL Marketplace] 목록에 &quot;요청됨&quot;이 나타납니다.

   * **[!UICONTROL Request approved]**:목록의  [!UICONTROL Marketplace] 상태가 &quot;액세스 부여됨&quot;으로 변경되며, 자동 알림을 받게 됩니다. 이때 피드에 가입할 수 있습니다. 지침은 [공개 데이터 피드 가입](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)을 참조하십시오.
   * **[!UICONTROL Request denied]**:피드의 목록에서 &quot;요청된&quot;  [!UICONTROL Marketplace] 텍스트가 제거됩니다. 다시 구독하거나 다른 피드를 선택할 수 있습니다.

## 구매자에 대한 데이터 피드 할인 {#buyer-discount}

[!UICONTROL Audience Marketplace]에서 공급자는 구매자에게 [!DNL CPM] 또는 정액 요금 데이터 피드의 게시된 가격에 할인을 제공할 수 있습니다. 그러나 [!DNL Marketplace] 피드 목록에서 구매자에게 할인 금액이 표시되지 않습니다. 그러나 개인 데이터 피드에 가입하거나 특정 피드에 대한 추가 정보를 요청할 때 할인을 요청할 수도 있습니다.

## 할인 요청 {#request-discount}

<!-- marketplace-buyer-discounts.xml -->

<table id="table_3C6E58F593BA48EC89ACBD9A26E4E74F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 구매자 상태 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>현재 구독자</b> </p> </td> 
   <td colname="col2"> <p>이미 개인 데이터 피드를 구독하고 할인을 요청하려는 경우: </p> 
    <ol id="ol_A58D419EBB9349E9B1225202535130F6"> 
     <li id="li_D0DDC8AC6E9C4675AA4630D63FE8F071"> <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe"> </a> 데이터 피드에서 가입을 취소합니다. </li> 
     <li id="li_05A5379F2A944FB28AB39C196DDE3A1D">데이터 공급자에게 문의하여 할인된 가격으로 요청하십시오. </li> 
     <li id="li_B1B5AA6F6CC64512A02D5E8861A5F266">공급자가 할인을 제공하면 다음 달의 1<sup>st</sup>일에 피드에 다시 가입합니다. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>새 비공개 데이터 피드 구독자</b> </p> </td> 
   <td colname="col2"> <p>구독 요청에서 할인을 요청합니다. <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed"> 개인 데이터 피드 가입</a>을 참조하십시오. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>잠재적 가입자</b> </p> </td> 
   <td colname="col2"> <p><a href="../../../features/audience-marketplace/marketplace-private-feeds.md"> 잠재적 가입자</a>은 개인 데이터 피드에 대한 액세스를 요청했지만 판매자 승인을 받았지만 피드에 가입하지 않은 데이터 구매자입니다. 잠재적인 가입자로 할인을 요청하려면 </p> 
    <ol id="ol_9CECDA92E7894B20AC8A777D78962188"> 
     <li id="li_618B64160CF24549AFCA73E006DCA35A"><b><span class="uicontrol"> Audience Marketplace &gt; Marketplace</span></b>로 이동합니다. </li> 
     <li id="li_FE52A06B30FC4858B48AF81954365FE9">승인된 피드의 이름을 클릭합니다. </li> 
     <li id="li_763C050AC9464BE380D00F6085B6E540"><b><span class="uicontrol"> 추가 세부 정보 요청</span></b>을 클릭합니다. 판매자에게 상세한 요구사항에 대해 할인을 부탁하세요. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## 할인된 피드 검토 {#review-discounted-feeds}

할인된 피드를 검토하려면:

1. **[!UICONTROL Audience Marketplace > Marketplace]**(으)로 이동합니다.
1. 이미 구독한 피드의 이름을 클릭합니다.
1. [!UICONTROL Plan Details] 테이블의 [!UICONTROL Price] 및 [!UICONTROL Your Price] 열을 확인합니다. 피드가 할인되는 경우:

   * 원래 가격은 빨간색으로 표시되어 있습니다
   * [!UICONTROL Your Price] 열의 수수료는 [!UICONTROL Price] 열의 비용보다 낮습니다.

이 예에서는 구매자는 **[!UICONTROL Software Audience Feed]**&#x200B;의 [!UICONTROL Segments and Overlap] 계획에서 10% 할인을 받습니다.

![](assets/buyer-discount.png)

## 구독한 피드 데이터 찾기 {#find-subscribed-data-fee}

데이터 피드에 대한 데이터(트레이트)는 자체 트레이트 저장소 폴더에 표시됩니다. **[!UICONTROL Audience Data > Traits]** 로 이동하고 **[!UICONTROL 3rd-Party Data]** 폴더를 확장하여 구독한 피드에서 트레이트를 보고 작업합니다. 데이터 공급자의 이름을 따라 이름이 지정된 하위 폴더를 찾습니다. 여기에는 개별 데이터 피드의 이름을 딴 폴더와 피드에서 제공한 목록 트레이트가 포함됩니다.

<!-- marketplace-feed-storage.xml -->

![](assets/subscribe5.png)

## 데이터 피드에서 가입 해지 {#unsubscribe}

데이터 구매자는 **[!UICONTROL Audience Marketplace > Marketplace]**&#x200B;에 있는 데이터 피드 및 플랜에서 가입을 해지합니다.

<!-- t_unsubscribe_feed.xml -->

데이터 피드에서 구독을 취소하려면,

1. [!UICONTROL Marketplace]에서 데이터 피드 이름을 클릭합니다.
1. [!UICONTROL Use Case] 섹션에서 사용할 계획을 찾아 **[!UICONTROL Subscription]** 슬라이더를 **[!UICONTROL Off]**&#x200B;로 이동합니다.

## 데이터 피드 비활성화:발생한 이유 및 응답 방법 {#data-feed-deactivation-reasons}

[!UICONTROL Audience Marketplace]에서 데이터 공급자는 가입한 데이터 피드에 대한 액세스를 취소할 수 있습니다. 이런 일이 생기면 놀라지 마세요. 우리는 당신을 보호했습니다. 데이터 피드 비활성화와 관련된 프로세스 및 절차에 대해서는 이 섹션을 검토하십시오.

## 데이터 피드 비활성화를 위한 일반적인 이유 {#reasons-for-deactivation}

<!-- marketplace-subscriber-deactivated.xml -->

구독하는 피드가 차단되면 황당할 수도 있고 속상할 수도 있습니다. 그러나 데이터 공급자는 다양한 이유로 데이터 피드를 비활성화할 수 있습니다. 몇 가지 일반적인 이유는 다음과 같습니다.

* **청구:** 유료 지불에 일관되게 지연되거나 수수료를 내지 못하는 경우 데이터 공급자는 피드를 비활성화합니다.
* **피드 업데이트:** 데이터 공급자는 피드 분류법 또는 비용 구조를 업데이트할 때 피드를 비활성화해야 합니다.
* **비활성 구매자:** 데이터 제공업체는 구독자가 기간 동안 지출을 표시하지 않는 경우 피드를 비활성화할 권리를 보유합니다.
* **비활성 판매자:** 나가는 데이터 공급자 [!UICONTROL Audience Marketplace] 는 모든 데이터 피드를 비활성화하고 삭제합니다.

>[!TIP]
>
>데이터 피드가 실수로 비활성화되었다고 생각되면 데이터 공급자에게 직접 문의하십시오. [!DNL Adobe] 컨설턴트가 연락처 정보 또는 추가 지원을 제공할 수 있습니다.

## 비활성화 이메일 {#deactivation-email}

데이터 공급자가 데이터 피드 중 하나를 비활성화하면 [!DNL Audience Manager]이 [!UICONTROL Administrator] 권한이 있는 회사에 있는 사용자에게 이메일을 보냅니다. 이메일 필터가 이 메시지를 스팸으로 분류하는 경우가 있습니다. 따라서 이 중요한 알림을 받지 못할 수 있습니다. 비활성화 메시지를 식별하는 데 도움이 되는 이 이메일에는 다음 요소가 포함되어 있습니다.

* **보낸 사람:** 비활성화 이메일은  `aam-noreply@adobe.com`에서 가져옵니다. 팁:이 이메일에 회신하지 마십시오.

* **제목 줄:** 데이터  *피드의 이름 가입* 이 취소되었습니다.

* **첨부 파일:**  전자 메일에 &quot;  `list-of-affected-entities-by-feed-revocation.csv`.&quot;라는 첨부 파일이 포함되어 있습니다. 이는 취소된 피드에 포함된 모든 트레이트를 첨부 파일에 나열하는 복잡한 방법입니다. 데이터 구매자는 이 첨부 파일을 검토해야 합니다. 세그먼트와 [알고리즘 모델](../../../features/algorithmic-models/understanding-models.md)에서 비활성화된 트레이트를 찾고 제거하는 데 도움이 됩니다.

## 비활성화된 트레이트 목록 {#deactivation-trait-list}

비활성화 이메일을 동반하는 목록에는 아래 표시된 필드가 포함되어 있습니다.

<table id="table_5C3800F9D8AA43EFAB4690959A721F63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 필드 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 데이터 피드 ID</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 데이터 피드의 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 데이터 피드 이름</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 데이터 피드의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 트레이트 SID</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 트레이트 이름</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트 이름. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 세그먼트 SID</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트를 포함하는 세그먼트의 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 세그먼트 이름</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트를 포함하는 세그먼트의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo 모델 ID</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트가 포함된 알고리즘 모델의 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 알고리즘 모델 이름</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트가 포함된 알고리즘 모델의 이름입니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 비활성화된 트레이트 제거 {#remove-deactivated-traits}

데이터 구매자는 모든 활성/사용 중 또는 비활성 세그먼트에서 취소된 피드에서 트레이트를 제거할 책임이 있습니다. 제거 옵션은 다음과 같습니다.

* [REST API](../../../api/rest-api-main/rest-api-main.md) 또는 [벌크 관리 도구](../../../reference/bulk-management-tools/bulk-management-intro.md)로 벌크 제거.

* 영향을 받는 세그먼트를 수동으로 검색하고 [!UICONTROL Segment Builder]을 사용하여 비활성화된 트레이트를 제거합니다. [세그먼트에서 트레이트 제거](../../../features/segments/segment-builder.md#segment-builder-controls-traits)를 참조하십시오.

>[!NOTE]
>
>활성 알고리즘 모델 또는 대상에서 트레이트를 제거하면 크기 및 타겟팅 정확도에 영향을 줍니다. 가능하면 해지된 트레이트를 새로운 활성 트레이트로 바꾸십시오.

[계정에서 ](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe) 해지된 모든 트레이트를 제거한 후 비활성화된 데이터 피드에서 가입을 해지합니다. 임시 비활성화인 경우, 데이터 공급자가 필요한 변경을 완료하고 피드를 다시 활성화하면 다시 구독할 수 있습니다. 대부분의 경우와 마찬가지로 파트너(데이터 제공업체 및 [!DNL Adobe])와의 의사 소통은 이 프로세스를 통해 작업하는 데 도움이 될 수 있습니다.

## Audience Marketplace의 계획 세부 정보 페이지 이해 {#marketplace-buyer-details}

[!UICONTROL Marketplace]에서 데이터 계획의 이름을 클릭하면 [!DNL Audience Manager]에서 데이터 피드 가입에 대한 올바른 선택을 할 수 있는 정보를 제공합니다.

<!-- marketplace-buyer-details.xml -->

![](assets/plan-details-numbered.png)

이 페이지에서는 다음 정보를 제공합니다.

1. **기본 계획 정보**. 여기에는 다음과 같은 피드 정보가 포함됩니다.
   * 데이터 피드 이름. 예를 들어 위에 표시된 대로 이 피드의 이름은 &quot;샘플 데이터 피드&quot;입니다.
   * 데이터 공급자의 이름
   * 데이터 피드 ID;
   * 설명;
   * 피드의 트레이트 수

1. 계획 정보 단추.
   * 선택한 데이터 피드의 모든 트레이트에 대한 세부 사항을 보려면 **[!UICONTROL Explore All Traits]** 을 클릭하십시오.
   * **[!UICONTROL Request More Details]** 을 클릭하여 데이터 제공자에게 선택한 데이터 피드에 대해 질문하거나 할인을 요청합니다. 이 기능은 댓글 및 질문을 데이터 공급자에게 직접 전송합니다.

1. 데이터 피드 보고서 지표. 벤 다이어그램(및 관련 지표)에는 지난 30일 동안의 트레이트 겹침 데이터가 표시됩니다. [마켓플레이스 를 참조하십시오.자세한 내용은 ](marketplace-data-buyers.md#about-marketplace) 정보를 참조하십시오.
   * **[!UICONTROL 30 Day Overlapped Uniques]**:공급자 계정의 사용자와 겹치는 계정의 고유 사용자 수입니다. 고유 사용자에 대한 정의는 Audience Manager](/help/using/reference/ids-in-aam.md)의 [ID 색인에서 AAM UUID를 참조하십시오.
   * **[!UICONTROL 30 Day Provider Unique Users]**:공급자 계정에서 들어오는 고유 사용자 수입니다.
   * **[!UICONTROL Your Unique Users]**:계정에서 들어오는 고유 사용자 수입니다.

1. **[!UICONTROL Plan Details]** 표. 이 표는 가격 책정 모델과 용 데이터 피드에 가입할 수 있는 사용 사례를 보여줍니다. [데이터 피드 사용 사례 이해](#use-cases)를 참조하십시오.

1. 계획 작업 단추.
   * **[!UICONTROL Cancel]** 을 클릭하여 변경하지 않고 페이지를 나갑니다.
   * 데이터 피드에 가입하려면 **[!UICONTROL Review & Subscribe]** 을 클릭하십시오. 이 단추는 [!UICONTROL Subscription] 을 [!UICONTROL On] (으)로 전환할 때까지 회색으로 표시됩니다. 또한 [공개 데이터 피드 가입](#subscript-public-data-feed) 및 [개인 데이터 피드 가입](#subscript-private-data-feed)도 참조하십시오.

## 데이터 피드 사용 사례 이해 {#use-cases}

[!UICONTROL Audience Marketplace] 데이터 구매자는 중복, 모델링 및 활성화 사용 사례를 위한 데이터를 구입할 수 있습니다. 각 사용 사례는 특정 목적을 위해 설계되었으며 데이터로 수행할 수 있는 작업을 제한합니다. 이러한 사용 사례 설명을 통해 구매할 데이터 플랜 유형을 올바르게 결정할 수 있습니다.

## 세그먼트 및 Overlap Plan과의 비교 {#comparisons}

<!-- c_use_cases_for_buyers.xml -->

### 세그먼트 및 겹치기

이 사용 사례를 사용하면 [특성-특성 중복 보고서에서 트레이트를 공급자 트레이트와 비교할 수 있습니다.](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) 또한 세그먼트에 공급자 트레이트를 만들거나 추가하고  [세그먼트 간 트레이트 및 세그먼트 간 ](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) 세그먼테이션  [보고서와 추가로 비교할 수 ](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) 있습니다. 겹치기 비교를 통해 다음을 수행할 수 있습니다.

* **대상 도달 범위 확장:**  겹치는 부분이 낮으면 트레이트에 이전에 보지 않은 사용자가 포함되어 있음을 나타냅니다. 이러한 트레이트를 통해 새로운 사용자에게 도달하려고 할 수 있습니다.
* **기존 대상자 향상:** 겹치는 부분이 있으면 트레이트가 데이터 공급자가 소유한 트레이트와 비슷합니다. 이러한 트레이트를 통해 이미 개발된 대상에 타겟팅되고 증분 개선 작업을 수행할 수 있습니다.

### 알고리즘 모델

이 사용 사례를 사용하면 [알고리즘 모델링](../../../features/algorithmic-models/understanding-models.md#understanding-models)을 사용하여 트레이트에 대해 공급자 트레이트를 평가할 수 있습니다. 예를 들어, 알고리즘 모델링 시스템은 공급자 트레이트와 비교하기 위한 기준으로 트레이트 중 하나를 사용합니다. 모델이 실행되면 공급자 트레이트의 대상이 트레이트와 유사한 전환 속성을 공유하는지 여부를 표시할 수 있습니다.

### 활성화

이 사용 사례에서는 [대상](../../../features/destinations/destinations.md)에 데이터를 보낼 수 있습니다. [!DNL Audience Manager]에서 대상은 모든 타사 시스템(광고 서버, [!DNL DSP], [!DNL DMP], 교환 등)입니다. 입니다. 그러나 [!UICONTROL Activation] 사용 사례에서는 중복 보고서를 실행하거나 알고리즘 모델에서 데이터를 테스트할 수 없습니다.

>[!MORELIKETHIS]
>
>* [CPM 데이터 피드에 대한 청구 및 노출 할당](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
* [정액 요금 데이터 피드에 대한 청구 및 노출 할당](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
* [CPM 사용을 보고하는 방법](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
* [공개 데이터 피드 가입](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)
* [데이터 구매자를 위한 할인](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
* [마켓플레이스:정보](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)

