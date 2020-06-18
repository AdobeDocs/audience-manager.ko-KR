---
description: Audience Manager는 자사 데이터, 제2자 데이터, 타사 데이터를 수집하고 관리하는 데 도움이 됩니다.
seo-description: Audience Manager는 자사 데이터, 제2자 데이터, 타사 데이터를 수집하고 관리하는 데 도움이 됩니다.
seo-title: 수집한 데이터 유형
solution: Audience Manager
title: 수집한 데이터 유형
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 69%

---


# 수집한 데이터 유형 {#types-of-data-collected}

[!DNL Audience Manager] 퍼스트 파티, 세컨드 파티 및 서드 파티 데이터를 수집하고 관리하는 데 도움이 됩니다.

여러 사일로에 저장되어 있는 고객 정보 자산에 대한 잠금을 해제하는 것은 오늘날 기업이 직면한 가장 큰 데이터 문제 중 하나입니다. From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] 여러 소스에서 분리된 고객 정보를 파악하고 데이터 수집을 관리하는 데 도움이 됩니다. Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] 는 다음 유형의 데이터를 관리하는 데 도움이 되도록 설계되었습니다.

| 데이터 유형 | 데이터 출처 |
|---|---|
| **자사** | 고객. 데이터는 온라인(웹 사이트의 소비자 상호 작용) 또는 오프라인에서 수집됩니다. |
| **제2자** | 전략적 파트너 및 광고업체 |
| **타사** | 데이터 공급자 및/또는 교환. 데이터에는 의도, 인구 통계학, 소셜/라이프스타일, 사이코그래프 등과 같은 정보가 포함될 수 있습니다. |

## 자사 데이터 수집 {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. 이 핵심 기능은 자산 데이터를 마케팅 프로그램의 초석으로 사용하거나 다른 데이터 소스와 비교하여 타겟팅 및 모델링에 사용하려는 고객(게시자 또는 광고주)의 요구 사항을 해결합니다.

<!-- 

c_1st_party_data.xml

 -->

[!DNL Audience Manager] 고객과 협력하여 데이터 전략을 파악한 다음 이 전략을 사용자 지정 데이터 수집 계획에 매핑합니다. Adobe의 파트너 솔루션팀은 귀사와 협력하여 웹 사이트에서 사이트, 원시 데이터 신호 및 기타 사용자 상호 작용을 평가합니다. Adobe는 이러한 정보를 바탕으로 귀사가 인벤토리의 다양한 페이지에서 사용자 수준 데이터 신호를 캡처하는 맞춤형 데이터 수집 전략을 작성하는 것을 지원하게 됩니다. 캡처된 데이터는 저장되며, 비즈니스 요구 사항이 변경될 때 언제든지 업데이트할 수 있는 사전 정의된 분류법에 다시 매핑됩니다.

다음 예는 샘플 쇼핑 페이지에서 잠재적 데이터 요소를 캡처할 수 있는 방법을 보여줍니다.

![shopping-cart-data](assets/shopping-cart-data.png)

| 항목 | 설명 |
|---|---|
| 1 | **성별**. 쇼핑객의 이름은 보통 쇼핑객의 성별을 나타냅니다. 이 예에서, 쇼핑객의 이름은 Mary이고, 따라서 쇼핑객이 여성이라는 것을 알 수 있습니다. 이름은 Audience Manager가 저장하지 않습니다. |
| 2 | **관심**. 장바구니에 있는 품목들은 다양한 관심사를 나타낼 수 있습니다. 이 예에서, Mary는 운동 장비에 많은 돈을 지출합니다. |
| 3 | **주택 유형**. 배송 및/또는 청구 주소를 기반으로, Mary가 운동 장비를 자신을 위해 구입하는지 아니면 회사를 위해 구입하는지 유추할 수 있습니다. |
| 4 | **위치**. [!DNL ZIP] 위치는 IP 주소보다 안정적입니다. |
| 5 | **프로모션 관련성**. 쇼핑객이 프로모션 코드나 기프트 카드를 사용한다면 이 쇼핑객은 싸고 질 좋은 물건을 찾아다니는 사람일 수 있습니다. |
| 6 | **소비 능력**. Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. 분류법 및 데이터 매핑은 모두 데이터 수집 코드를 변경하지 않고 언제든지 조정할 수 있습니다.

## 제2자 데이터 수집 {#second-party-data}

제2자 데이터는 전략적 비즈니스 파트너로부터 나옵니다(게시자 데이터가 아님). 이 정보는 자사 데이터처럼 수집 및 관리됩니다.

<!-- 

c_2nd_party_data.xml

 -->

제2자 데이터 시나리오에서, 광고주는 자체 데이터 자산을 게시자에게 보내어 해당 정보를 게시자의 데이터와 결합한 다음 더 잘 타겟팅된 광고 프로그램을 실행할 수 있도록 합니다. 뿐만 아니라 게시자는 광고주와 파트너 관계를 맺어 대상 풀을 확장할 수 있습니다. In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

제2자 데이터 수집 및 리마케팅의 한 예에는 의류 소매 업체가 자사 제품에 대한 데이터를 수집한 다음 이 정보를 주요 파트너와 공유하는 것이 있을 수 있습니다. In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## 타사 데이터 수집 {#third-party-data}

타사 데이터는 Audience Manager 외부의 공급업체가 수집하고 공유하는 정보입니다.

<!-- 

c_3rd_party_data.xml

 -->

타사 데이터는 기존 데이터 세그먼트(예: 연령, 가구 소득 등)에 자격을 부여하고, 수요가 있지만 구할 수 없는 데이터를 제공하는 데 사용하거나, 자사 데이터와 제2자 데이터의 알려진 사용자 기반과 비교하는 유사 모델링에 사용할 수 있습니다. [!DNL Audience Manager] 다양한 타사 데이터 제공업체와 협력하여 데이터 제공업체가 수집하는 데이터의 유형을 파악하고 각 제공업체와 적절한 전략적 거래를 할 수 있도록 지원합니다.

>[!NOTE]
>
>[!DNL Audience Manager]가 지원하는 타사 데이터 공급자에 대한 전체 목록이 필요하면 [Adobe Audience Finder](https://www.adobe-audience-finder.com/)를 참조하십시오.

[!DNL Audience Manager] 사용 가능한 데이터 세트 및 데이터 세트를 기반으로 다른 데이터 제공업체와 [!DNL APIs] 통합합니다. 데이터 수집은 사용자가 사이트를 탐색함에 따라 실시간으로, 또는 파트너 간에 ID가 동기화되고 사용자가 사이트를 떠난 후 서버 간에 데이터가 전송되는 대역 외 방법론을 통해 작동합니다. In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. 이것은 도달 범위를 늘리는 데 도움이 되며 페이지의 서버 호출을 줄입니다.

## 파트너 일치 {#match-partners}

많은 클라이언트가 타사 데이터 일치 파트너와 협력하는 것을 선택합니다. 이러한 조직은 등록 요구 사항이 있는 사이트와 관계를 맺고 있으며 등록 네트워크를 기반으로 고객 데이터 파일을 실시간으로 일치시켜 처리할 수 있습니다.

![data-provider-match](assets/data-provider-match.png)
