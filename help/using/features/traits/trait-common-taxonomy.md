---
description: 이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.
keywords: DIL
seo-description: 이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.
seo-title: 일반적인 분류법으로 트레이트 분류
solution: Audience Manager
title: 일반적인 분류법으로 트레이트 분류
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: 트레이트
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 5%

---

# 일반적인 분류법으로 트레이트 분류 {#classifying-traits-with-a-common-taxonomy}

이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.

## Audience Manager 분류

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] 분류법은 균일하고 논리적이며 일반적으로 이해되는 명명 규칙을 사용하여 트레이트를 분류하는 선택 기능입니다. 플랫폼 수준에서 작동하므로 [!DNL Audience Manager] 에코시스템 전체에서 이름 지정 일관성을 유지할 수 있습니다. 궁극적으로 일반적인 분류법은 제품을 소비자 개인 정보 보호 및 옵트아웃 프로세스에 대한 업계 표준에 더욱 부합하도록 설계되었습니다.

## 트레이트 분류의 이점

고객이 사용자 지정 세그먼트 및 데이터 모델을 구축할 수 있도록 하는 것은 [!DNL Audience Manager] 모델과 Adobe 플랫폼에서 가치를 캡처할 수 있는 사용자의 핵심 요소입니다. 그러나 세그먼트에 대한 정보를 고객 및 파트너에게 전달할 수 있는 강력하고 확장 가능한 수단도 필요합니다. 또한 이러한 커뮤니케이션을 위해서는 독점 트레이트 및 세그먼트 이름을 보호하면서 세그먼트 정보를 이해하기 쉽고 일반적으로 이해할 수 있는 언어로 공유해야 합니다. [!DNL Audience Manager] 일반 분류법은 이 언어와 기능을 제공합니다.

## 분류법은 업계 표준 분류 카테고리를 사용합니다.

일반적인 분류법은 [!DNL Interactive Advertising Bureau (IAB)]에 의해 생성된 분류를 기반으로 합니다. 네트워크 및 교환에 대한 품질 보증 지침에 대한 자세한 내용은 [!DNL IAB] 의 [웹 사이트](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines)를 참조하십시오.

## 분류 조직

[!DNL Audience Manager] 분류법은 데이터를 계층이라는 중첩된 카테고리로 구성합니다. 각 카테고리는 데이터 분류의 최대 3개의 개별 계층을 포함할 수 있습니다. 가장 높은 수준에서 계층 1 카테고리는 데이터를 가장 일반적인 양식(예: 지역)으로 그룹화합니다. 후속 계층은 더 높은 수준, 일반 카테고리(예: *geography —> 미국 —> New York*)에 더 높은 사양을 제공합니다. 그러나 모든 카테고리에 3개의 계층이 있는 것은 아니며, 일부 카테고리는 2개만 사용합니다.

## 데이터 카테고리의 트레이트 분류

[!UICONTROL Add New Trait Wizard]( * **[!UICONTROL Audience Data > Traits]***에 있음)에서 특성을 만들거나 편집할 때 분류 분류를 지정합니다. 자세한 내용은 특성 만들기](../../features/traits/create-onboarded-rule-based-traits.md)에 대한 [ 설명서를 참조하십시오.

## 분류 체계 작업:추가 고려 사항

일반적인 분류법에 따라 트레이트를 분류하려는 경우 다음을 기억해야 합니다.

* 분류는 *선택 사항*&#x200B;입니다.
* 특성 *은(는) 기본적으로 분류 카테고리에 할당되지 않습니다(즉, 트레이트는 &quot;알 수 없음&quot; 또는 &quot;분류되지 않음&quot; 등으로 분류되지 않음).*
* 트레이트는 *하나의* 분류 카테고리에만 속할 수 있습니다(다중 및 교차 카테고리 분류는 허용되지 않음).
