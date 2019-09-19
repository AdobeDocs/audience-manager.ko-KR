---
description: 일반적인 제품 및 기능 관련 질문 및 문제
keywords: 고객 관리자 쿠키
seo-description: 일반적인 제품 및 기능 관련 질문 및 문제
seo-title: ' 제품 기능 FAQ'
solution: Audience Manager
title: 제품 기능 FAQ
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


#  제품 기능 FAQ{#product-features-and-functions-faq}

일반적인 제품 및 기능 관련 질문 및 문제

<br> 

<!-- 

faq_features_functions.xml

 -->

**조직 ID는 무엇이며 어떻게 찾을 수 있습니까?**

이 *`Organization ID`* ID는 조직과 조직을 식별하는 고유한 [!DNL Audience Manager] ID입니다 [!DNL Adobe Experience Cloud]. 대/소문자를 구분하는 24자의 영숫자 문자열 뒤에 오는 [!UICONTROL @AdobeOrg]문자열로 구성됩니다.

예를 들어 다음과 *`Organization ID`* 같습니다. `1FD6776A524453CC0A490D44@AdobeOrg`Adobe

Audience *`Organization ID`* Manager의 DIL [API](../dil/dil-overview.md) , [Experience Cloud ID 서비스](https://marketing.adobe.com/resources/help/en_US/mcvid/)및 기타 [!DNL Experience Cloud] 솔루션에 의해 사용됩니다. 관리자 권한이 있는 사용자는 에서 *`Organization ID`* 을 찾을 수 [!DNL Adobe Admin Console]있습니다. 관리 [- 사용자 관리 FAQ를 참조하십시오](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**트레이트나 대상을 대량으로 만들 수 있습니까?**

예. 일괄 [관리 도구를 참조하십시오](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>이 [!UICONTROL Bulk Management Tools] 도구는 에서 지원되지 *않습니다* [!DNL Audience Manager]. 편의를 위해 그리고 예의상 제공됩니다. 일괄 변경의 경우 Audience Manager API를 [대신 사용하는 것이](../api/api.md) 좋습니다.

<br> 

**타사 태그 또는 픽셀에 대한 필요성을 줄이고 페이지 로드 시간을 향상시킬 수[!DNL Audience Manager]있습니까?**

타사 데이터 파트너와 [!DNL Audience Manager] 통합된 경우 해당 픽셀과 태그를 서버 간 ID 호출로 바꿀 수 [!DNL Audience Manager]있습니다. 이 경우 사용자가 처음 표시되면 단일 ID 호출을 [!DNL Audience Manager] 실행하고 해당 정보를 타사 파트너와 동기화합니다. 따라서 모든 페이지에서 여러 픽셀을 호출할 필요가 없습니다. 픽셀 호출을 줄이면 페이지 로드 시간이 향상됩니다.

<br> 

**데이터 피드에 가입했습니다. 그 데이터는 어디에 저장됩니까?**

데이터 피드와 피드에 포함된 모든 트레이트가 하위 폴더와 트레이트로 표시됩니다 [!DNL Audience Manager]. 이동 **[!UICONTROL Audience Data > Traits]** 및 [!UICONTROL 3rd-Party Data] 폴더를 확장하여 트레이트를 보거나 이 데이터로 세그먼트와 모델을 만듭니다.

<br> 

**[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager [!UICONTROL Tag Insertion Manager] 에서 TIM(생성 및 관리)을 [!UICONTROL data collection code (DIL)]사용했습니다. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. 자세한 내용은 Adobe Launch [및 다이내믹](https://docs.adobelaunch.com/) 태그 [관리를 참조하십시오](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**알고리즘 모델과 트레이트 추천의 차이점은 무엇입니까? 각각 언제 사용해야 합니까?**

**알고리즘 모델**

알고리즘 모델은 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 이러한 트레이트를 기반으로 사용자의 점수를 매기고 각 사용자에게 개별 점수를 지정합니다. 그런 다음 사용자를 타깃팅할 알고리즘 트레이트를 만듭니다. 트레이트 빌더의 정확도 및 도달 범위 제어를 사용하여 타깃팅하려는 영향력 있는 트레이트를 가진 모든 사용자 중에서 어떤 사용자를 지정할 수 있습니다.

알고리즘 모델을 사용하면 다른 정확도 수준에서 사용자를 선택하고 Audience Lab에서 사용자 그룹을 보다 효과적으로 변환할 수 있습니다. Audience Lab의 모델 [비교에서 자세한 사용 사례를 참조하십시오](../features/audience-lab/audience-lab-use-cases.md#compare-models).

알고리즘 모델에서 모델은 8일마다 실행되며 알고리즘 특성에 맞는 사용자를 새로 고칩니다.

**트레이트 권장 사항**

트레이트 추천은 세그먼트에서 사용 중인 트레이트와 유사한 다른 트레이트에 대한 통찰력을 빠르게 얻을 수 있는 방법입니다.

다음과 같은 경우 특성 권장 사항을 사용해야 합니다.

* 세그먼트를 작성하는 동안 빠른 통찰력이 필요합니다.
* 짧은 캠페인에 세그먼트를 사용하거나 전환한 대상자를 빠르게 표시하지 않으려는 경우
* 도달 범위를 최대화하려고 합니다.

<br> 

**Adobe Analytics와 Audience Manager 세그먼트 간에 차이가 있습니까?**

예. Analytics [및 Audience](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) Manager의 세그먼트 이해를 참조하여 차이점에 대한 자세한 설명을 참조하십시오.
