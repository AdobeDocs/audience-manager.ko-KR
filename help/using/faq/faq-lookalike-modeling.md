---
description: 유사 모델링은 자동화된 데이터 분석을 통해 새롭고 고유한 대상을 발견하는 데 도움이 됩니다. 이 문서에서는 가장 자주 묻는 질문에 대한 답변을 제공합니다.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: 유사 모델링 FAQ
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 0%

---

# 유사 모델링 FAQ

## 개요 {#overview}

이 문서에서는 [!UICONTROL Look-Alike Modeling]에 대해 가장 자주 묻는 질문에 대한 답변을 제공합니다.

## 질문 {#questions}

**왜 고정된 [!UICONTROL Accuracy & Reach] 그래프를 얻는 것입니까?**

플랫 [!UICONTROL Accuracy & Reach] 그래프는 거의 모든 사용자가 모델에서 동일한 점수를 받았음을 의미합니다. 이 문제는 모델을 실행한 데이터 소스에 사이트 방문자 트레이트를 포함할 때 발생할 수 있습니다. 이를 방지하려면 [!UICONTROL Exclusions] 필드를 사용하여 모델 만들기 단계 동안 모델 입력에서 일반 트레이트를 제거하십시오.

 

**가장 영향력 있는 트레이트 중 일부에 매우 적은 수의 대상이 있는 이유는 무엇입니까?**

알고리즘에서는 기준선 트레이트와 상관 관계가 높은 트레이트를 선택합니다. 예를 들어, 주어진 트레이트가 기준선 트레이트와 100% 겹치면 해당 트레이트의 사용자 수가 적더라도 가중치가 매우 높습니다.

 

**내 모델이 실행/다시 실행되지 않는 이유는 무엇입니까?**

결과가 생성된 모델은 하나 이상의 활성 알고리즘 트레이트를 생성하고 활성 세그먼트와 대상에 매핑한 경우에만 계속 실행됩니다.

 

**내 모델이 결과를 내지 못한 이유는 무엇입니까?**

이는 일반적으로 기준 모집단과 선택한 데이터 소스의 모집단 간에 상당한 트레이트 겹침이 없기 때문에 발생합니다.

 

**기준 트레이트 또는 세그먼트 크기에 대한 권장 사항이 있습니까?**

선택한 데이터 소스의 기본 모집단과 모집단 간에 상당한 트레이트 겹침이 있는 경우, 몇 천명의 사용자만 이 모델을 실행하기에 충분해야 합니다. [!UICONTROL Look-Alike Modeling]은(는) 더 정확한 결과를 생성합니다. 기준선은 더 커집니다.

 

**모델에 대해 어떤 타사 데이터 원본을 선택해야 합니까?**

기준 트레이트/세그먼트와 적어도 일부가 겹치지만 동시에 추가 사용자를 가져오는 데이터 소스를 사용하십시오. 각 데이터 피드와 관련된 비용도 고려해야 합니다. 비용 및 가격 모델은 [!UICONTROL Audience Marketplace]의 데이터 공급자에 따라 다릅니다.

 

**모델링에 타사 데이터를 사용하는 데 비용이 듭니까?**

선택한 데이터 피드의 가격 모델에 따라 다릅니다. 일부 피드는 비용 없이 모델링을 허용하는 반면 다른 피드는 수수료를 부과합니다. 자세한 내용은 [데이터 피드 구매자에 대한 청구](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)를 참조하십시오.

 

**모델/특성을 만들 수 있습니까?**

현재 최대 20개의 알고리즘 모델과 50개의 알고리즘 트레이트를 만들 수 있습니다.

 

**모델 교육 및 알고리즘 트레이트 모집단의 새로 고침 빈도는 얼마입니까?**

이 모델은 알고리즘 트레이트 모집단을 새로 고침하면서 8일에 한 번 재교육합니다.
