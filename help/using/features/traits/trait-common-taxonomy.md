---
description: 이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.
keywords: DIL
seo-description: 이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.
seo-title: 일반적인 분류법으로 트레이트 분류
solution: Audience Manager
title: 일반적인 분류법으로 트레이트 분류
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%

---


# 일반적인 분류법으로 트레이트 분류 {#classifying-traits-with-a-common-taxonomy}

이 문서에서는 일반적인 분류법으로 트레이트를 분류하는 방법에 대한 일반적인 개요를 제공합니다.

## Audience Manager 분류

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] 분류 기능은 균일, 논리적, 일반적으로 이해되는 명명 규칙을 사용하여 트레이트를 분류하는 선택 기능입니다. 플랫폼 수준에서 작동하므로 [!DNL Audience Manager] 에코시스템 전체에서 이름 지정 일관성을 유지할 수 있습니다. 궁극적으로 일반적인 분류법은 Adobe 제품을 소비자 개인 정보 및 수신 거부 프로세스와 관련된 업계 표준에 맞게 만들기 위해 고안되었습니다.

## 특성 분류의 이점

고객이 맞춤형 세그먼트와 데이터 모델을 구축할 수 있도록 하는 것은 [!DNL Audience Manager] 모델과 Adobe 플랫폼에서 가치를 캡처하는 기능에 있어 매우 중요합니다. 그러나 고객 및 파트너에게 세그먼트에 대한 정보를 전달하기 위한 강력하고 확장 가능한 수단이기도 합니다. 또한 이러한 커뮤니케이션을 위해서는 세그먼트 정보를 이해하기 쉽고 일반적으로 이해되는 언어로 공유하면서 사용자의 고유한 특성 및 세그먼트 이름을 보호해야 합니다. [!DNL Audience Manager] 일반 분류법은 이 언어와 기능을 제공합니다.

## 분류법은 산업 표준 분류 범주를 사용합니다.

일반적인 분류는 [!DNL Interactive Advertising Bureau (IAB)]에서 만든 분류를 기반으로 합니다. 네트워크 및 교환에 대한 품질 보증 지침에 대한 자세한 내용은 [!DNL IAB]의 [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines)를 참조하십시오.

## 분류 체계

[!DNL Audience Manager] 분류법은 데이터를 계층이라는 중첩 카테고리로 구성합니다. 각 카테고리는 데이터 분류에 대해 최대 3개의 개별 계층을 포함할 수 있습니다. 가장 높은 수준의 계층 1 카테고리는 데이터를 가장 일반적인 양식(예: 지역)으로 그룹화합니다. 이후 계층은 더 높은 수준의 일반 카테고리(예: *지리적 위치 —> 미국 —> 뉴욕*)에 더 높은 사양을 제공합니다. 그러나 모든 카테고리에 3개의 등급이 있는 것은 아니며, 일부 카테고리는 2개의 계층을 사용합니다.

## 데이터 카테고리에서 트레이트 분류

[!UICONTROL Add New Trait Wizard](* **[!UICONTROL Audience Data > Traits]***)에서 트레이트를 만들거나 편집할 때 분류 분류를 할당합니다. 자세한 내용은 traits](../../features/traits/create-onboarded-rule-based-traits.md)를 만드는 방법에 대한 [설명서를 참조하십시오.

## 분류 작업:추가 고려 사항

일반적인 분류법에 따라 특성을 분류하는 경우 다음을 기억해야 합니다.

* 분류는 *선택적*&#x200B;입니다.
* 특성 *은(는) 기본적으로 분류법 범주에 할당된*&#x200B;이(가) 아닙니다(즉, 트레이트는 &quot;알 수 없음&quot; 또는 &quot;분류되지 않음&quot; 등으로 분류되지 않음).
* 트레이트는 *하나* 분류 범주에만 속할 수 있습니다(복수 및 카테고리 간 분류는 허용되지 않음).