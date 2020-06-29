---
description: 각각의 키-값 쌍을 기준으로 하나 또는 여러 개의 신호를 검색합니다.
seo-description: 각각의 키-값 쌍을 기준으로 하나 또는 여러 개의 신호를 검색합니다.
seo-title: 키-값 쌍으로 신호 검색
title: 키-값 쌍으로 신호 검색
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---


# 키-값 쌍으로 신호 검색 {#search-signals-by-key-value-pairs}

각각의 키-값 쌍을 기준으로 하나 또는 여러 개의 신호를 검색합니다.
둘 이상의 신호를 검색하려면 ![추가](assets/icon_add.png) 단추를 클릭합니다. 검색할 키-값 쌍을 입력한 다음 다음 필터를 사용하여 검색 결과를 좁힙니다.

* **신호 상태**: 트레이트, 미사용 신호 또는 둘 다에 포함된 신호를 검색합니다.
* **다음에 대한 레코드**&#x200B;보기: 수신한 신호를 검색할 시간 간격을 선택합니다.
* **최소 카운트**: 선택한 간격에 지정된 최소 합계 개수의 신호만 표시합니다.

>[!IMPORTANT]
>
>간소화된 사용자 경험을 위해 키-값 페어 검색 결과는 데이터 샘플링을 기반으로 합니다. 데이터 샘플링 [을 사용하는 방법과 키-값 검색을 일반 검색과 비교할 때 약간의 결과 변형이 표시되는 이유에 대한 자세한 내용은](/help/using/reporting/report-sampling.md) [!DNL Audience Manager] 데이터 샘플링 및 오류 비율을 참조하십시오.

여러 개의 키-값 쌍을 사용하여 신호를 검색할 때 논리 [!DNL Audience Manager] AND **** 연산자를 사용하여 쌍을 연결합니다. 예를 들어 다음 키-값 쌍으로 검색을 수행한다고 가정해 봅시다.

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

이 검색은 동일한 호출에서 세 개의 필터 모두에 대해 자격을 갖는 결과만 반환합니다. `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## 신호 검색에서 제외된 신호 {#excluded-signals}

Audience Manager에서 사용하고 `d_` 및 `h_` [!UICONTROL Signals Search]접두사가 접두어로 사용한 키 변수는 자세한 내용은 [키 변수의 접두사 요구 사항](../../traits/trait-variable-prefixes.md) 을 참조하십시오.

## 사례 자동 완성 및 검색 {#case-insensitivity}

키 및 값 검색 필드는 대/소문자를 구분하지 않습니다. 주요 검색 필드에는 자동 완료된 제안이 포함됩니다.

![](assets/signal-search-suggestions.png)

다음 신호를 [!DNL Audience Manager] 받았다고 합시다.

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

키 검색 필드 `product` 에 입장하면, `productCategory`, `newProduct`및 `PRODUCT`에 대한 자동 완성 제안을 받게 됩니다 `product`.

마찬가지로 검색할 때 `product == phone`와 [!UICONTROL Data Explorer] 둘 다에 대한 결과 `PRODUCT == phone` 를 `product == PHONE`반환합니다.
백채워진 트레이트 실현은 대/소문자를 구분하지 않습니다. 키-값 쌍이 있는 신호가 포함된 트레이트 `PRODUCT == SMARTPHONE` 는 키-값 쌍으로 신호를 받을 수도 있습니다 `product == smartphone`.