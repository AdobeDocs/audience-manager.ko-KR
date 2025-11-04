---
description: 이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: 일반적인 분류법으로 트레이트 분류
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# 일반적인 분류법으로 트레이트 분류 {#classifying-traits-with-a-common-taxonomy}

이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.

## Audience Manager 분류 체계

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] 분류법은 균일하고 논리적이며 일반적으로 이해되는 이름 지정 규칙을 사용하여 트레이트를 분류하는 선택적 기능입니다. 플랫폼 수준에서 작동하여 [!DNL Audience Manager] 에코시스템 전체에서 명명 일관성을 보장합니다. 궁극적으로 일반적인 분류법은 소비자 개인 정보 보호 및 옵트아웃 프로세스와 관련하여 당사 제품을 업계 표준에 맞게 보다 세밀하게 조정하도록 설계되었습니다.

## 트레이트 분류의 장점

고객이 사용자 지정 세그먼트 및 데이터 모델을 만들 수 있도록 하는 것은 [!DNL Audience Manager] 모델 및 플랫폼에서 가치를 포착하는 기능의 핵심입니다. 그러나 세그먼트 관련 정보를 고객 및 파트너에게 전달할 수 있는 강력하고 확장 가능한 수단도 필요합니다. 또한 이러한 커뮤니케이션을 위해서는 사용자의 고유한 트레이트 및 세그먼트 이름을 보호하면서 세그먼트 정보를 이해하기 쉽고 보편적으로 이해할 수 있는 언어로 공유해야 합니다. [!DNL Audience Manager] 일반 분류법은 이 언어와 기능을 제공합니다.

## 분류는 업계 표준 분류 범주를 사용합니다

일반적인 분류법은 [!DNL Interactive Advertising Bureau (IAB)]에서 만든 분류를 기반으로 합니다. 네트워크 및 교환의 품질 보증 지침에 대한 자세한 내용은 [!DNL IAB]의 [웹 사이트](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines)를 참조하십시오.

## 분류 조직

[!DNL Audience Manager] 분류법은 데이터를 계층이라는 중첩된 범주로 구성합니다. 각 카테고리는 데이터 분류를 위해 최대 3개의 개별 계층을 포함할 수 있습니다. 최상위 수준에서 계층 1 범주는 데이터를 가장 일반적인 형식(예: 지역)으로 그룹화합니다. 후속 계층은 더 높은 수준의 일반 범주(예: *geography —> United States —> New York*)에 더 큰 특수성을 제공합니다. 그러나 모든 카테고리에 3개의 계층이 있는 것은 아니며 일부는 2개만 사용합니다.

## 데이터 카테고리에서 트레이트 분류

[!UICONTROL Add New Trait Wizard]&#x200B;([!UICONTROL Audience Data > Traits]에 있음)에서 특성을 만들거나 편집할 때 분류 ***을 &#x200B;***. 자세한 내용은 특성 만들기에 대한 [설명서](../../features/traits/create-onboarded-rule-based-traits.md)를 참조하세요.

## 분류 작업: 추가 고려 사항

일반적인 분류법에 따라 트레이트를 분류하려면 다음을 기억해야 합니다.

* 분류는 *선택 사항*&#x200B;입니다.
* 특성 *은(는) 기본적으로 분류 범주에 할당되지 않습니다*(즉, 특성이 &quot;알 수 없음&quot; 또는 &quot;분류되지 않음&quot; 등으로 분류되지 않음).
* 트레이트는 *one* 분류법 범주에만 속할 수 있습니다(여러 분류 및 교차 분류 허용 안 함).
