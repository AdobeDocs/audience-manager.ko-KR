---
description: 일반적인 제품 및 기능 관련 질문 및 문제
keywords: audience manager 쿠키
seo-description: 일반적인 제품 및 기능 관련 질문 및 문제
seo-title: 제품 및 기능 FAQ
solution: Audience Manager
title: 제품 및 기능 FAQ
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: 개요
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 84%

---

# 제품 및 기능 FAQ{#product-features-and-functions-faq}

일반적인 제품 및 기능 관련 질문 및 문제

 

<!-- 

faq_features_functions.xml

 -->

**조직 ID는 무엇이며 어떻게 찾을 수 있습니까?**

*`Organization ID`*&#x200B;는 [!DNL Audience Manager] 및 [!DNL Adobe Experience Cloud]에 조직을 식별하는 고유 ID입니다. 이 ID는 대/소문자를 구분하는 24자의 영숫자 문자열과 그 뒤에 오는 [!UICONTROL @AdobeOrg]로 구성됩니다.

예를 들어 *`Organization ID`*&#x200B;는 `1FD6776A524453CC0A490D44@AdobeOrg`와 같은 모습입니다.

*`Organization ID`*&#x200B;는 Audience Manager의 [DIL](../dil/dil-overview.md) API, [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html) 및 기타 [!DNL Experience Cloud] 솔루션에서 사용됩니다. 관리자 권한이 있는 사용자는 [!DNL Adobe Admin Console]에서 *`Organization ID`*&#x200B;를 찾을 수 있습니다. [관리 - 사용자 관리 FAQ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html)를 참조하십시오.

 

**트레이트나 대상을 벌크로 만들 수 있습니까?**

예. [벌크 관리 도구](../reference/bulk-management-tools/bulk-management-intro.md)를 참조하십시오.

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] 도구는 [!DNL Audience Manager]에서 *지원하지 않습니다*. 편의를 위해 그리고 호의로 제공될 뿐입니다. 벌크 변경의 경우에는 [Audience Manager API](../api/api.md)를 대신 사용하는 것이 좋습니다.

 

**대상으로 벌크 ID 내보내기를 수행할 때 일부 고객 ID가 누락됩니다. 이유가 무엇입니까?**

장치 ID([AAM UUID](../reference/ids-in-aam.md))가 여러 CRM ID([DPUUIDs](../reference/ids-in-aam.md))에 연결되어 있으면 최신 매핑만 내보냅니다. 내보내는 장치 ID의 예상 수보다 적은 수가 표시될 수 있습니다.

 

**[!DNL Audience Manager]를 사용하면 타사 태그나 픽셀이 덜 필요하고 페이지 로드 시간도 줄어듭니까?**

[!DNL Audience Manager]가 타사 데이터 파트너와 통합되는 경우, 픽셀과 태그를 [!DNL Audience Manager]에 대한 서버 간 ID 호출로 바꿀 수 있습니다. 이 경우 [!DNL Audience Manager]는 처음 사용자를 보고 해당 정보를 타사 파트너와 동기화할 때 단일 ID 호출을 실행합니다. 이렇게 되면 모든 페이지에서 여러 픽셀을 호출할 필요가 없어집니다. 픽셀 호출이 줄어들면 페이지 로드 시간이 향상됩니다.

 

**데이터 피드에 가입했습니다. 그 데이터는 어디에 저장되어 있습니까?**

데이터 피드 및 피드에 포함된 모든 트레이트는 [!DNL Audience Manager]에서 하위 폴더와 트레이트로 표시됩니다. **[!UICONTROL Audience Data > Traits]**&#x200B;로 이동하고 [!UICONTROL 3rd-Party Data] 폴더를 확장하여 트레이트를 보거나 이 데이터를 사용하여 세그먼트와 모델을 만듭니다.

 

**[!UICONTROL Tag Insertion Manager (TIM)]은 무엇입니까?**

Audience Manager는 TIM([!UICONTROL Tag Insertion Manager])을 사용하여 [!UICONTROL data collection code (DIL)]를 만들고 관리했었습니다. 이 기능은 더 이상 사용되지 않으며, [!UICONTROL Dynamic Tag Manager (DTM)]로 대체되었으며, 이후에 [!DNL Adobe Experience Platform Launch]로 대체되었습니다. 자세한 내용은 [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html)을 참조하십시오.

 

**알고리즘 모델과 트레이트 추천 간의 차이점은 무엇입니까? 각각 언제 사용해야 합니까?**

**알고리즘 모델**

알고리즘 모델은 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 이러한 트레이트를 기반으로 사용자에 대한 점수를 매기고 각 사용자에게 개별 점수를 지정합니다.  그런 다음, 사용자를 타겟팅하는 알고리즘 트레이트를 만듭니다. 트레이트 빌더의 정확도와 도달 범위 컨트롤을 사용하면 영향력 있는 트레이트를 가진 모든 사용자 중에서 타겟팅할 사용자를 지정할 수 있습니다.

알고리즘 모델을 사용하면 다양한 정확도 수준에서 사용자를 선택하고 대상 랩에서 어느 사용자 그룹이 더 효과적으로 전환되는지 테스트할 수 있습니다. [대상 랩의 모델 비교](../features/audience-lab/audience-lab-use-cases.md#compare-models)에서 자세한 사용 사례를 확인하십시오.

알고리즘 모델에서 모델은 8일마다 실행되고 알고리즘 트레이트에 맞는 사용자를 새로 고칩니다.

**트레이트 추천**

트레이트 추천은 세그먼트에서 사용 중인 트레이트와 유사한 다른 트레이트에 대한 통찰력을 얻는 빠른 방법입니다.

다음과 같은 경우 트레이트 추천을 사용해야 합니다.

* 세그먼트를 만드는 동안 빠른 통찰력이 필요한 경우
* 짧은 캠페인에 세그먼트를 사용하거나 전환되는 대상을 빠르게 억제하려는 경우
* 도달 범위를 극대화하려는 경우

 

**Adobe Analytics와 Audience Manager 세그먼트 간에 차이가 있습니까?**

예. 그 차이점에 대한 심도 있는 설명이 필요하면 [Analytics와 Audience Manager의 세그먼트 이해](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html)를 참조하십시오.
