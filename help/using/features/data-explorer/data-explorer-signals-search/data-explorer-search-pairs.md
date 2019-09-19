---
description: 각각의 키-값 쌍을 기준으로 하나 또는 여러 개의 신호를 검색합니다.
seo-description: 각각의 키-값 쌍을 기준으로 하나 또는 여러 개의 신호를 검색합니다.
seo-title: 키-값 쌍별 검색 신호
title: 키-값 쌍별 검색 신호
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# 키-값 쌍별 검색 신호 {#search-signals-by-key-value-pairs}

각각의 키-값 쌍을 기준으로 하나 또는 여러 개의 신호를 검색합니다.
두 개 이상의 신호를 검색하려면 추가 ![단추를](assets/icon_add.png) 클릭합니다. 검색할 키-값 쌍을 입력한 다음 다음 필터를 사용하여 결과를 좁힙니다.

* **신호 상태**:트레이트, 미사용 신호 또는 둘 다에 포함된 신호를 검색합니다.
* **레코드 보기**:수신한 신호를 검색할 시간 간격을 선택합니다.
* **최소 카운트**:선택한 간격에 지정된 최소 총 카운트를 가진 신호만 표시합니다.

>[!IMPORTANT]
>
>간소화된 사용자 경험을 위해 키-값 쌍의 검색 결과는 데이터 샘플링을 기반으로 합니다. 데이터 [샘플링을 사용하는 방법과](/help/using/reporting/report-sampling.md) [!DNL Audience Manager] 키-값 검색을 일반 검색과 비교할 때 약간의 결과 변형이 표시되는 이유에 대한 자세한 내용은 데이터 샘플링 및 오류 비율을 참조하십시오.

여러 키-값 쌍을 사용하여 신호를 검색할 때 논리 AND [!DNL Audience Manager] 연산자를 사용하여 쌍을 **연결합니다** . 예를 들어 다음 키-값 쌍으로 검색을 수행한다고 가정해 봅시다.

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

이 검색은 동일한 호출에서 세 개의 필터 모두에 해당하는 결과만 반환합니다. `c_creative == "12345"``AND``c_product == "smartphone"``AND``c_location == "europe"`요.

![](assets/signals-search.png)

## 대소문자 구분 및 검색 자동 완성 {#case-insensitivity}

키 및 값 검색 필드는 대/소문자를 구분하지 않습니다. 주요 검색 필드에는 자동 완료된 제안이 포함되어 있습니다.

![](assets/signal-search-suggestions.png)

다음 신호를 [!DNL Audience Manager] 받았다고 가정해 봅시다.

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

키 검색 `product` 필드에 입력하면, `productCategory``newProduct`및 에 대한 자동 완성 제안을 받습니다 `PRODUCT``product`.

마찬가지로 검색할 때 `product == phone`및 [!UICONTROL Data Explorer] 에 대한 결과를 `PRODUCT == phone` 반환합니다 `product == PHONE`.
백채워진 트레이트 실현은 대/소문자를 구분하지 않습니다. 키-값 쌍과 신호가 포함된 트레이트 `PRODUCT == SMARTPHONE` 역시 키-값 쌍으로 신호를 자격을 `product == smartphone`얻습니다.