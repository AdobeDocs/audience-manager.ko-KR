---
description: 각각의 키-값 쌍을 기준으로 하나 이상의 신호를 검색합니다.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: 키-값 쌍으로 신호 검색
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# 키-값 쌍으로 신호 검색 {#search-signals-by-key-value-pairs}

각각의 키-값 쌍을 기준으로 하나 이상의 신호를 검색합니다.
두 개 이상의 신호를 검색하려면 ![추가](assets/icon_add.png) 버튼을 클릭합니다. 검색할 키-값 쌍을 입력한 다음 다음 필터를 사용하여 결과 범위를 좁힙니다.

* **신호 상태**: 트레이트, 사용되지 않은 신호 또는 둘 다에 포함된 신호를 검색합니다.
* **레코드 보기**: 수신된 신호를 검색할 시간 간격을 선택합니다.
* **최소 카운트**: 선택한 간격에 지정된 최소 총 개수를 가진 신호만 표시합니다.

>[!IMPORTANT]
>
>간소화된 사용자 환경의 경우 키-값 쌍 검색 결과는 데이터 샘플링을 기반으로 합니다. 자세한 내용은 [데이터 샘플링 및 오류율](/help/using/reporting/report-sampling.md) 자세한 내용은 [!DNL Audience Manager] 에서는 키-값 검색을 일반 검색과 비교할 때 데이터 샘플링 및 작은 결과 변형이 표시되는 이유를 사용합니다.

여러 키-값 쌍을 사용하여 신호를 검색할 때 [!DNL Audience Manager] 논리 를 사용하여 쌍을 연결합니다 **및** 연산자를 사용할 수 있습니다. 예를 들어 다음 키-값 쌍으로 검색을 수행한다고 가정해 보겠습니다.

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

이 검색은 동일한 호출에서 세 개의 필터 모두에 대해 자격이 되는 결과만 반환합니다. `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## 신호 검색에서 제외된 신호 {#excluded-signals}

Audience Manager에서 사용하고 접두사가 있는 주요 변수 `d_` 및 `h_` 접두사는 [!UICONTROL Signals Search]. 자세한 내용은 [주요 변수의 접두사 요구 사항](../../traits/trait-variable-prefixes.md) 자세한 내용

## 대/소문자 구분 및 자동 완성 검색 {#case-insensitivity}

키 및 값 검색 필드는 대/소문자를 구분합니다. 주요 검색 필드에 자동 완성된 제안이 포함되어 있습니다.

![](assets/signal-search-suggestions.png)

예, [!DNL Audience Manager] 다음 신호를 받았습니다.

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

입력 시 `product` 키 검색 필드에서 `productCategory` 및 `product`.

마찬가지로 `product == PHONE`, [!UICONTROL Data Explorer] 에 대해서만 결과 반환 `product == PHONE`.

부족한 트레이트 실현은 대소문자를 구분합니다. 키-값 쌍이 있는 신호가 포함된 트레이트 `PRODUCT == SMARTPHONE` 는 키-값 쌍으로 신호를 분류하지 않습니다 `product == smartphone`.
