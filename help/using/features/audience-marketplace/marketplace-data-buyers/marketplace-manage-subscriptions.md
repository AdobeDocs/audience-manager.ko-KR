---
description: Marketplace는 데이터 구매자가 조사 및 공개 및 비공개 데이터 피드를 구독하는 곳입니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.
seo-description: Marketplace는 데이터 구매자가 조사 및 공개 및 비공개 데이터 피드를 구독하는 곳입니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.
seo-title: 데이터 피드 가입 관리
solution: Audience Manager
title: 데이터 피드 가입 관리
topic: DIL API
uuid: 7305adb6-cbb8-4430-8204-2243095c0ba5
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '2186'
ht-degree: 2%

---


# 데이터 피드 가입 관리 {#manage-data-feed-subscriptions}

데이터 구매자 [!UICONTROL Marketplace] 가 공개 및 비공개 데이터 피드를 검색하고 구독하는 곳입니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.

## 공개 데이터 피드 구독 {#subscript-public-data-feed}

데이터 구매자 [!UICONTROL Marketplace] 가 공개 및 비공개 데이터 피드를 검색하고 구독하는 곳입니다. 공개 데이터 피드에 가입하려면 다음 단계를 따르십시오.

<!-- t_subscribe_feed.xml -->

공개 데이터 피드에 가입하려면

1. 로 **[!UICONTROL Audience Marketplace > Marketplace]**&#x200B;이동합니다. 검색 기능을 사용하거나 목록을 검색하여 데이터 피드를 찾습니다.

   ![구독](assets/subscribe1.png)

1. 사용할 데이터 피드의 이름을 클릭합니다. 선택한 피드에 대한 [플랜 세부 정보 페이지가](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details) 열립니다.

   ![플랜 세부 사항](assets/plan-details.png)

1. 가입 테이블에서 사용 사례를 선택하고 다음을 수행합니다.
   * 슬라이더를 **[!UICONTROL Subscription]** 다음으로 이동합니다 **[!UICONTROL On]**.
   * 클릭 **[!UICONTROL Review & Subscribe]**. 그러면 [!UICONTROL Terms and Conditions] 창이 열립니다.
   ![구독](assets/subscribe3.png)

1. 창 [!UICONTROL Terms and Conditions] :

   * **중요:** 체크 상자를 **[!UICONTROL ID sync]** 선택된 상태로 두십시오. 이 설정은 데이터 제공자와의 일치 속도를 개선하는 데 도움이 됩니다.
   * 약관 상자를 선택하고 을 클릭하여 구독 프로세스 **[!UICONTROL Accept]** 를 완료합니다.
   ![구독](assets/subscribe4.png)

### 다음 단계

데이터 피드에 가입한 후:

* 폴더를 확인하여 구독을 [!UICONTROL Traits] 확인합니다. 가입된 [데이터 피드 저장소를 참조하십시오](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee).

* 대금 청구 및 지불 설명서를 검토하십시오. 아래 관련 링크를 참조하십시오.

### 우수 사례 {#best-practices}

다음은 작업을 수행할 때 따라야 할 우수 사례 세트입니다 [!UICONTROL Audience Marketplace].

새로운 타사 및 타사 데이터 세트를 탐색할 때 [!UICONTROL Audience Marketplace]는 데이터 피드를 활성화하는 것이 좋습니다 [!UICONTROL Segments & Overlap]. 이를 통해 세그먼트를 만들어 고객 규모를 평가하고 중복 보고서를 실행하여 초기 고객 통찰력을 확보함으로써 데이터를 탐색할 수 있습니다. 대부분의 데이터 제공업체는 이 사용 사례를 무료로 제공하므로 추가 비용 없이 이 분석을 수행할 수 있습니다.

겹치기 보고서를 실행할 때 이러한 우수 사례를 통해 유용한 결과를 얻을 수 있습니다.

1. 겹치는 데이터 세트가 다음과 같은 데이터 유형 및 수집 방법론과 유사한지 확인합니다.
   * 방문자 지역
   * 쿠키와 모바일 ID 비교
   * 전환 확인 기간
   * 오프라인 활동과 온라인 활동 비교
   * 데이터 공급자가 데이터를 새로 고치는 빈도

1. 겹치는 시간이 지남에 따라 약간 늘어날 수 있으므로 겹치기 보고서를 실행하기 전에 최대 30일 동안 데이터를 동기화할 수 있도록 해야 합니다.
1. 여러 마케팅 캠페인에서 데이터 공급자의 데이터를 사용하는 경우 겹치기 결과가 발생할 수 있습니다.
프로젝트를 진행할 수 있습니다. 따라서 두 데이터 세트의 사용자가 더 많은 시간을 동기화할 수 있습니다.
1. 데이터 세트 간에 겹칠 것이라는 보장은 없습니다. 겹침이 유효하려면 고객 데이터 세트의 사용자가 보고 기간 동안 데이터 공급자 데이터 세트와 연결해야 합니다. 고객의 미디어 데이터가 데이터 공급자 데이터 세트의 사용자에게 제공되지 않으면 겹치지 않습니다.
1. 낮은 겹치는 것을 나쁜 것으로 생각하지 마라. 낮은 오버랩을 활용하여 잠재 고객을 확보하고 신규 사용자의 참여를 유도할 수 있습니다.

## 개인 데이터 피드 구독 {#subscript-private-data-feed}

구매자는 개인 데이터 피드 및 플랜에 가입합니다 **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_private_feed.xml -->

>[!TIP]
>
>경우에 따라 데이터 제공업체는 개인 데이터 피드에 대해 할인 혜택을 제공할 수 있습니다. 구독 요청을 제출할 때 가능한 할인 혜택을 묻는 메시지가 나타날 수 있습니다.

개인 데이터 피드에 가입하려면

1. 의 데이터 피드 이름을 클릭합니다 [!UICONTROL Marketplace].
1. 클릭 **[!UICONTROL Request Access]**. 그러면 요청 대화 상자가 열립니다.
1. 요청 대화 상자에서 제공자에게 데이터 피드에 대한 귀하의 관심사를 나타내는 메모를 작성하고 을 클릭합니다 **[!UICONTROL Send]**. 판매자는 메시지를 검토하고 요청을 승인하거나 거부합니다. 승인을 기다리는 동안 해당 데이터 피드 목록에 &quot;요청됨&quot;이 [!UICONTROL Marketplace] 나타납니다.

   * **[!UICONTROL Request approved]**: 목록의 상태가 [!UICONTROL Marketplace] &quot;액세스 권한&quot;으로 변경되며 자동 알림을 받게 됩니다. 이제 피드에 가입할 수 있습니다. 자세한 [내용은 공개 데이터 피드](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed) 가입을 참조하십시오.
   * **[!UICONTROL Request denied]**: 피드의 목록에서 &quot;요청됨&quot; 텍스트가 [!UICONTROL Marketplace] 제거됩니다. 다시 구독하거나 다른 피드를 선택할 수 있습니다.

## 구매자를 위한 데이터 피드 할인 {#buyer-discount}

또한 제공업체 [!UICONTROL Audience Marketplace]는 구매자에게 게시된 요금 데이터 피드 가격 [!DNL CPM] 또는 정액 요금 데이터 피드에 대해 할인 혜택을 제공할 수 있습니다. 하지만, 할인 금액은 [!DNL Marketplace] 피드 목록의 구매자에게 표시되지 않습니다. 그러나 개인 데이터 피드에 가입하거나 특정 피드에 대한 추가 정보를 요청할 때 할인을 요청할 수도 있습니다.

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
   <td colname="col2"> <p>이미 개인 데이터 피드에 가입되어 있고 할인을 요청하려는 경우: </p> 
    <ol id="ol_A58D419EBB9349E9B1225202535130F6"> 
     <li id="li_D0DDC8AC6E9C4675AA4630D63FE8F071"> <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe"> 데이터 피드 구독</a> 취소. </li> 
     <li id="li_05A5379F2A944FB28AB39C196DDE3A1D">데이터 제공업체에 문의하여 할인된 가격으로 요청하십시오. </li> 
     <li id="li_B1B5AA6F6CC64512A02D5E8861A5F266">제공업체가 할인 혜택을 제공하는 경우 다음 달 1일에<sup></sup> 피드에 다시 가입합니다. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>새 개인 데이터 피드 구독자</b> </p> </td> 
   <td colname="col2"> <p>사용료 지불 옵션 구입 시 할인 혜택을 신청하십시오. 비공개 <a href="../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed"> 데이터 피드 가입을 참조하십시오</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>잠재적인 가입자</b> </p> </td> 
   <td colname="col2"> <p>잠재적인 가입자 <a href="../../../features/audience-marketplace/marketplace-private-feeds.md"></a> 는 개인 데이터 피드 액세스를 요청하여 판매자 승인을 받았지만 피드에 가입하지 않은 데이터 구매자입니다. 잠재적인 가입자로 할인을 요청하려면 </p> 
    <ol id="ol_9CECDA92E7894B20AC8A777D78962188"> 
     <li id="li_618B64160CF24549AFCA73E006DCA35A">Audience Marketplace &gt; <b><span class="uicontrol"> 마켓플레이스로 이동합니다</span></b>. </li> 
     <li id="li_FE52A06B30FC4858B48AF81954365FE9">승인된 피드의 이름을 클릭합니다. </li> 
     <li id="li_763C050AC9464BE380D00F6085B6E540">자세한 내용 <b><span class="uicontrol"> 요청을 클릭합니다</span></b>. 자세한 내용은 판매자에게 문의하십시오. </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

## 할인 피드 검토 {#review-discounted-feeds}

할인된 피드를 검토하려면

1. 로 **[!UICONTROL Audience Marketplace > Marketplace]**&#x200B;이동합니다.
1. 이미 가입한 피드의 이름을 클릭합니다.
1. 테이블 [!UICONTROL Price] 의 열과 [!UICONTROL Your Price] 열을 [!UICONTROL Plan Details] 보세요. 피드가 할인되는 경우:

   * 원래 가격은 빨간색으로 표시되어 있습니다
   * 열의 요금은 [!UICONTROL Your Price] 열의 수수료보다 [!UICONTROL Price] 낮을 것입니다.

이 경우 구매자는 해당 [!UICONTROL Segments and Overlap] 플랜에 대해 10% 할인 혜택을 받게 됩니다 **[!UICONTROL Software Audience Feed]**.

![](assets/buyer-discount.png)

## 구독한 피드 데이터 찾기 {#find-subscribed-data-fee}

데이터 피드에 대한 데이터(트레이트)는 고유한 특성 저장소 폴더에 나타납니다. 가입된 피드 **[!UICONTROL Audience Data > Traits]** 에서 트레이트를 보고 사용하려면 폴더로 이동하여 **[!UICONTROL 3rd-Party Data]** 확장합니다. 데이터 공급자의 이름을 딴 하위 폴더를 찾습니다. 여기에는 개별 데이터 피드의 이름을 따서 명명된 폴더와 피드에서 제공하는 트레이트가 포함됩니다.

<!-- marketplace-feed-storage.xml -->

![](assets/subscribe5.png)

## 데이터 피드 구독 취소 {#unsubscribe}

데이터 구매자는 데이터 피드 및 플랜에서 가입을 해지합니다 **[!UICONTROL Audience Marketplace > Marketplace]**.

<!-- t_unsubscribe_feed.xml -->

데이터 피드에서 가입 해지하려면

1. 의 데이터 피드 이름을 클릭합니다 [!UICONTROL Marketplace].
1. 섹션에서 [!UICONTROL Use Case] 사용할 계획을 찾아 슬라이더를 다른 위치로 **[!UICONTROL Subscription]** 이동합니다 **[!UICONTROL Off]**.

## 데이터 피드 비활성화: 발생하는 이유와 대응 방법 {#data-feed-deactivation-reasons}

에서 [!UICONTROL Audience Marketplace]데이터 공급자는 가입된 데이터 피드에 대한 액세스를 취소할 수 있습니다. 이런 일이 일어나면 놀라지 마라. 우리는 당신을 덮었습니다. 데이터 피드 비활성화와 관련된 프로세스 및 절차는 이 섹션을 검토하십시오.

## 데이터 피드 비활성화를 위한 일반적인 이유 {#reasons-for-deactivation}

<!-- marketplace-subscriber-deactivated.xml -->

사용료 지불 옵션을 신청한 피드가 중단되면 황급히 또는 속지 않게 될 수도 있습니다. 하지만 데이터 공급자는 다양한 이유로 데이터 피드를 비활성화할 수 있습니다. 다음과 같은 일반적인 이유가 있습니다.

* **청구:** 요금 지불에 일관되게 지연되거나 수수료를 지불하지 못하는 경우 데이터 제공자는 피드를 비활성화합니다.
* **피드 업데이트:** 데이터 제공자는 피드 분류 또는 비용 구조를 업데이트할 때 피드를 비활성화해야 합니다.
* **비활성 구매자:** 가입자에게 긴 기간 동안 지출이 표시되지 않는 경우 데이터 제공자는 피드를 비활성화할 수 있는 권리를 보유합니다.
* **비활성 판매자:** 이탈한 데이터 제공자는 해당 데이터 피드를 모두 비활성화하고 [!UICONTROL Audience Marketplace] 삭제합니다.

>[!TIP]
>
>데이터 피드가 실수로 비활성화되었다고 생각되면 데이터 공급자에게 직접 문의하십시오. 컨설턴트가 연락처 정보 또는 추가 지원을 도와줄 수 있습니다. [!DNL Adobe]

## 비활성화 이메일 {#deactivation-email}

데이터 공급자가 데이터 피드 중 하나를 비활성화하면 [!DNL Audience Manager] 권한이 있는 회사에 있는 사용자에게 이메일을 [!UICONTROL Administrator] 보냅니다. 이메일 필터는 이 메시지를 스팸으로 분류하는 경우가 있습니다. 따라서 이 중요한 알림을 놓칠 수 있습니다. 비활성화 메시지를 식별하는 데 도움이 되는 이 이메일에는 다음 요소가 포함되어 있습니다.

* **보낸 사람:** 비활성화 이메일은 에서 발송됩니다 `aam-noreply@adobe.com`. 팁: 이 이메일에 회신하지 마십시오.

* **제목:** 여기에서 데이터 피드 *이름* 구독이 취소되었습니다.

* **첨부 파일:** 이메일에는 &quot;.&quot;라는 이름의 첨부 파일이 `list-of-affected-entities-by-feed-revocation.csv`포함됩니다. 이렇게 하면 첨부 파일에 취소된 피드에 포함된 모든 트레이트가 나열됩니다. 데이터 구매자는 이 첨부를 검토해야 합니다. 세그먼트와 알고리즘 모델에서 비활성화된 트레이트를 찾고 [제거하는 데 도움이 됩니다](../../../features/algorithmic-models/understanding-models.md).

## 비활성화된 특성 목록 {#deactivation-trait-list}

비활성화 이메일에 동봉된 목록에는 아래와 같은 필드가 포함되어 있습니다.

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
   <td colname="col1"> <p><b><span class="uicontrol"> 특성 SID</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 특성 이름</span></b> </p> </td> 
   <td colname="col2"> <p>특성 이름이 비활성화되었습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 세그먼트 SID</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트가 포함된 세그먼트의 ID입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> 세그먼트 이름</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트가 포함된 세그먼트의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo 모델 ID</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트가 포함된 알고리즘 모델의 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Algo 모델 이름</span></b> </p> </td> 
   <td colname="col2"> <p>비활성화된 트레이트가 포함된 알고리즘 모델의 이름. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 비활성화된 트레이트 제거 {#remove-deactivated-traits}

데이터 구매자는 모든 활성/사용 중 또는 비활성 세그먼트에서 취소된 피드의 트레이트를 제거할 책임이 있습니다. 제거 옵션은 다음과 같습니다.

* REST API [또는 벌크 관리 도구](../../../api/rest-api-main/rest-api-main.md) 를 사용하여 벌크 [제거](../../../reference/bulk-management-tools/bulk-management-intro.md).

* 영향을 받는 세그먼트를 수동으로 검색하고 비활성화된 트레이트를 제거할 수 있습니다 [!UICONTROL Segment Builder]. 세그먼트에서 [트레이트 제거를 참조하십시오](../../../features/segments/segment-builder.md#segment-builder-controls-traits).

>[!NOTE]
>
>활성 알고리즘 모델 또는 대상에서 트레이트를 제거하면 비율 및 타깃팅 정확성에 영향을 줍니다. 가능한 경우 취소된 트레이트를 새롭고 활동적인 트레이트로 교체해 보십시오.

[계정에서 해지된 트레이트를 모두 제거한](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#unsubscribe) 후 비활성화된 데이터 피드 가입을 해지합니다. 임시 비정품 인증인 경우 데이터 공급자가 필요한 변경 작업을 완료하고 피드를 다시 활성화하면 다시 가입할 수 있습니다. 대부분의 경우와 마찬가지로 파트너(데이터 제공업체 및)와의 효과적인 커뮤니케이션을 통해 이러한 프로세스를 진행할 수 [!DNL Adobe]있습니다.

## Audience Marketplace의 계획 세부 정보 페이지 이해 {#marketplace-buyer-details}

에서 데이터 플랜 이름을 클릭하면 데이터 피드 가입에 대한 [!UICONTROL Marketplace]정보를 선택할 수 [!DNL Audience Manager] 있는 정보를 제공합니다.

<!-- marketplace-buyer-details.xml -->

![](assets/plan-details-numbered.png)

이 페이지에서는 다음 정보를 제공합니다.

1. **기본 플랜 정보**. 여기에는 다음과 같은 피드 정보가 포함됩니다.
   * 데이터 피드 이름. 예를 들어, 위와 같이 이 피드의 이름은 &quot;샘플 데이터 피드&quot;입니다.
   * 데이터 공급자의 이름
   * 데이터 피드 ID;
   * 설명;
   * 피드의 트레이트 수;

1. 계획 정보 단추를 참조하십시오.
   * 선택한 데이터 피드 **[!UICONTROL Explore All Traits]** 의 모든 트레이트에 대한 세부 사항을 보려면 클릭하십시오.
   * 데이터 제공업체 **[!UICONTROL Request More Details]** 에 선택한 데이터 피드에 대해 질문하거나 할인을 요청하려면 을 클릭합니다. 이 기능은 의견 및 질문을 데이터 제공자에게 직접 보냅니다.

1. 데이터 피드 보고서 지표를 참조하십시오. 벤 다이어그램(및 관련 지표)은 지난 30일 동안 트레이트 겹침 데이터를 보여줍니다. Marketplace [를 참조하십시오. 자세한](marketplace-data-buyers.md#about-marketplace) 내용
   * **[!UICONTROL 30 Day Overlapped Uniques]**: 공급자 계정의 사용자와 겹치는 계정의 고유 사용자 수입니다. 고유 사용자 정의에 대해서는 Audience Manager의 ID [인덱스에서 AAM UUID를 참조하십시오](/help/using/reference/ids-in-aam.md).
   * **[!UICONTROL 30 Day Provider Unique Users]**: 공급자 계정에서 나오는 고유 사용자 수입니다.
   * **[!UICONTROL Your Unique Users]**: 계정에서 들어오는 고유 사용자 수입니다.

1. **[!UICONTROL Plan Details]** 표. 이 표에서는 가격 모델에 대해 데이터 피드에 가입할 수 있는 사용 사례를 보여줍니다. 데이터 피드 [사용 사례 이해를 참조하십시오](#use-cases).

1. 계획 작업 단추를 참조하십시오.
   * 페이지 **[!UICONTROL Cancel]** 를 변경하지 않고 나가려면 을 클릭합니다.
   * 데이터 피드 **[!UICONTROL Review & Subscribe]** 에 가입하려면 을 클릭합니다. 전환을 전환할 때까지 이 단추는 회색으로 [!UICONTROL Subscription] 표시됩니다 [!UICONTROL On]. 공개 데이터 피드 [구독](#subscript-public-data-feed) 및 개인 데이터 피드 [가입을 참조하십시오](#subscript-private-data-feed).

## 데이터 피드 사용 사례 이해 {#use-cases}

데이터 구매자는 [!UICONTROL Audience Marketplace] 중복, 모델링 및 활성화 사용 사례를 위한 데이터를 구입할 수 있습니다. 각 사용 사례는 특정 목적에 맞게 설계되었으며 데이터를 사용하여 수행할 수 있는 작업을 제한합니다. 이러한 사용 사례 설명을 통해 구매할 데이터 플랜 유형을 정확하게 결정할 수 있습니다.

## 세그먼트 및 겹침 계획을 사용한 비교 {#comparisons}

<!-- c_use_cases_for_buyers.xml -->

### 세그먼트 및 겹치기

이 사용 사례를 사용하면 트레이트를 트레이트와 트레이트 대 트레이트 겹침 [보고서에서 공급자 트레이트와 비교할 수 있습니다.](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report) 또한 세그먼트에 공급자 트레이트를 만들거나 추가할 수 있으며 [세그먼트별 특성](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) 및 [세그먼트별 세그먼트 간](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) 보고서를 사용하여 추가적인 비교를 만들 수 있습니다. 겹치는 비교를 통해 다음을 수행할 수 있습니다.

* **고객 범위 확장:** 낮은 겹치는 트레이트에 이전에 보지 못한 사용자가 포함되어 있음을 나타냅니다. 이러한 트레이트를 통해 신규 사용자에게 도달할 수 있습니다.
* **기존 고객 강화:** 겹치기 비율이 높으면 데이터 공급자가 소유한 트레이트와 비슷합니다. 이러한 트레이트를 통해 이미 개발된 대상에 대한 타깃팅되고 증가분을 향상시킬 수 있습니다.

### 알고리즘 모델

이 사용 사례를 사용하면 알고리즘 모델링을 통해 사용자 트레이트와 공급자 트레이트를 [평가할 수 있습니다](../../../features/algorithmic-models/understanding-models.md#understanding-models). 예를 들어, Adobe의 알고리즘 모델링 시스템은 공급자 트레이트와 비교하기 위해 사용자 특성 중 하나를 사용합니다. 모델이 실행되면 공급자 트레이트의 대상이 트레이트와 유사한 전환 속성을 공유하는지 여부를 표시할 수 있습니다.

### 활성화

이 사용 사례에서는 데이터를 [대상으로 보낼 수 있습니다](../../../features/destinations/destinations.md). 즉, 대상 [!DNL Audience Manager]은 모든 타사 시스템(광고 서버, [!DNL DSP][!DNL DMP], 교환 등)입니다. 입니다. 그러나 [!UICONTROL Activation] 사용 사례에서는 중복 보고서를 실행하거나 알고리즘 모델에서 데이터를 테스트할 수 없습니다.

>[!MORELIKETHIS]
>
>* [CPM 데이터 피드에 대한 청구 및 노출 할당](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [고정 요금 데이터 피드에 대한 청구 및 노출 할당](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [CPM 사용을 보고하는 방법](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
>* [공개 데이터 피드 구독](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-public-data-feed)
>* [데이터 구매자를 위한 할인](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
>* [The Marketplace: 정보](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace)

