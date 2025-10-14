---
description: 해당 키-값 쌍을 기반으로 하나 이상의 신호를 검색합니다.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: 키-값 쌍으로 신호 검색
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# 키-값 쌍으로 신호 검색 {#search-signals-by-key-value-pairs}

해당 키-값 쌍을 기반으로 하나 이상의 신호를 검색합니다.
두 개 이상의 신호를 검색하려면 ![추가](assets/icon_add.png) 단추를 클릭하십시오. 검색할 키-값 쌍을 입력한 다음 다음 다음 필터를 사용하여 결과 범위를 좁힙니다.

* **신호 상태**: 트레이트에 포함된 신호, 사용되지 않은 신호 또는 둘 다를 검색합니다.
* **다음에 대한 레코드 보기**: 수신된 신호를 검색할 시간 간격을 선택하십시오.
* **최소 개수**: 선택한 간격에 최소 총 개수가 지정된 신호만 표시합니다.

>[!IMPORTANT]
>
>간소화된 사용자 경험을 위해 키-값 쌍 검색 결과는 데이터 샘플링을 기반으로 합니다. [에서 데이터 샘플링을 사용하는 방법과 키-값 검색을 일반 검색과 비교할 때 약간의 결과 변형이 나타나는 이유에 대한 자세한 내용은 &#x200B;](/help/using/reporting/report-sampling.md)데이터 샘플링 및 오류율[!DNL Audience Manager]을 참조하십시오.

여러 키-값 쌍을 사용하여 신호를 검색할 때 [!DNL Audience Manager]은(는) 논리 **AND** 연산자를 사용하여 쌍을 연결합니다. 예를 들어 다음 키-값 쌍으로 검색을 수행하고 있다고 가정해 보겠습니다.

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

이 검색은 동일한 호출에서 세 개 필터 모두에 적합한 결과만 반환합니다. `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## 신호 검색에서 제외된 신호 {#excluded-signals}

Audience Manager에서 사용하고 접두사 `d_` 및 `h_`이(가) 접두사로 사용하는 키 변수는 [!UICONTROL Signals Search]에서 표시되지 않습니다. 자세한 내용은 [주요 변수의 접두사 요구 사항](../../traits/trait-variable-prefixes.md)을 참조하십시오.

## 대소문자 구분 및 검색 자동 완성 {#case-insensitivity}

키 및 값 검색 필드는 대/소문자를 구분합니다. 주요 검색 필드에는 자동 완성된 제안이 포함됩니다.

![](assets/signal-search-suggestions.png)

[!DNL Audience Manager]이(가) 다음 신호를 수신했다고 가정해 보겠습니다.

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

키 검색 필드에 `product`을(를) 입력하면 `productCategory` 및 `product`에 대해 자동 완성된 제안을 받게 됩니다.

마찬가지로 `product == PHONE`을(를) 검색할 때 [!UICONTROL Data Explorer]은(는) `product == PHONE`에 대한 결과만 반환합니다.

채워진 트레이트 실현도 대소문자를 구분합니다. 키-값 쌍이 `PRODUCT == SMARTPHONE`인 신호가 포함된 트레이트가 키-값 쌍이 `product == smartphone`인 신호를 한정하지 않습니다.
