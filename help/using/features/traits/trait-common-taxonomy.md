---
description: 이 문서에서는 일반적인 분류로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.
keywords: DIL
seo-description: 이 문서에서는 일반적인 분류로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.
seo-title: 일반적인 분류 방식을 사용하여 트레이트화 분류
solution: Audience Manager
title: 일반적인 분류 방식을 사용하여 트레이트화 분류
uuid: 2 E 177344-07 D 9-40 A 7-8 C 99-C 6 C 6518 B 9 D 97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

이 문서에서는 일반적인 분류로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.

## Audience Manager 분류

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] 분류법은 균일, 논리적 및 일반적으로 이름 지정 규칙을 사용하여 트레이트를 분류하는 선택 기능입니다. It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. 궁극적으로, 일반적인 분류법은 우리의 제품을 소비자 개인 정보 보호 및 옵트아웃 프로세스와 관련된 업계 표준과 더욱 잘 하도록 고안되었습니다.

## 트레이트 분류의 이점

Enabling our customers to build custom segments and data models is core to the [!DNL Audience Manager] model and to your ability to capture value from our platform. 또한, 고객 및 파트너에게 세그먼트에 대한 정보를 전달하는 강력하고 확장 가능한 수단이기도 합니다. 또한 이 커뮤니케이션을 사용하려면 세그먼트 정보를 이해하기 쉽고 보편적으로 이해할 수 있는 언어로 공유해야 하며 독점 특성 및 세그먼트 이름을 보호해야 합니다. [!DNL Audience Manager] 일반적인 분류법은 이 언어와 기능을 제공합니다.

## 분류법은 업계 표준 분류 카테고리를 사용합니다.

The common taxonomy is based on the classifications created by the [!DNL Interactive Advertising Bureau (IAB)]. Refer to the [!DNL IAB]'s [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) for more information about quality assurance guidelines for networks and exchanges.

## 분류 체계 구성

[!DNL Audience Manager] 분류법은 데이터를 계층이라는 중첩 카테고리로 구성합니다. 각 카테고리에는 데이터 분류에 대해 최대 3 개의 별도 계층을 포함할 수 있습니다. 최상위 수준에서 계층 1 카테고리는 데이터를 가장 일반적인 양식 (예: 지역) 로 그룹화합니다. Subsequent tiers provide greater specificity to the higher level, general category (e.g., *geography --&gt; United States --&gt; New York*). 하지만 모든 카테고리가 3 개의 계층을 가지는 것은 아닙니다. 일부 카테고리는 2 개만 사용합니다.

## 데이터 카테고리의 트레이트를 분류합니다.

You assign taxonomic classifications when creating or editing traits in the [!UICONTROL Add New Trait Wizard] (located in * **[!UICONTROL Audience Data > Traits]***). Refer to the [documentation on creating traits](../../features/traits/create-onboarded-rule-based-traits.md) for more information.

## 분류법을 사용한 작업: 추가 고려 사항

일반적인 분류에 따라 트레이트를 분류하기로 결정하는 경우 기억해야 합니다.

* Classification is *optional*.
* Traits *are not* assigned to a taxonomic category by default (i.e., traits are not classified as "unknown" or "uncategorized" etc.).
* *트레이트는* 하나의 분류 카테고리에 속할 수 있습니다 (다중 및 교차 카테고리 분류는 허용되지 않음).