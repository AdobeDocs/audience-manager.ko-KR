---
description: 일반적인 제품 및 기능 관련 질문 및 문제
keywords: Audience Manager 쿠키
seo-description: 일반적인 제품 및 기능 관련 질문 및 문제
seo-title: 제품 기능 및 기능 FAQ
solution: Audience Manager
title: 제품 기능 및 기능 FAQ
uuid: DA 5 F 5089-24 A 8-4455-88 A 6-EB 62 D 83939 D 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

일반적인 제품 및 기능 관련 질문 및 문제

<br> 

<!-- 

faq_features_functions.xml

 -->

**조직 ID 란 무엇이며 어떻게 찾을 수 있습니까?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

*`Organization ID`* 예를 들어 다음과 같습니다. `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. [관리 - 사용자 관리 FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)를 참조하십시오.

<br> 

**트레이트 또는 대상을 일괄적으로 만들 수 있습니까?**

예. [일괄 관리 도구를 참조하십시오](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] 이 도구는 *에서* 지원되지 [!DNL Audience Manager]않습니다. 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**타사 태그 또는 픽셀의 필요성을[!DNL Audience Manager]줄이고 페이지 로드 시간을 개선할 수 있습니까?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. 따라서 모든 페이지에서 여러 픽셀 호출을 할 필요가 없습니다. 픽셀 호출을 줄이면 페이지 로드 시간이 향상될 수 있습니다.

<br> 

**데이터 피드를 구독했습니다. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**알고리즘 모델과 트레이트 추천의 차이점은 무엇입니까? When should I use each of them?**

**알고리즘 모델**

알고리즘 모델은 가장 영향력 있는 트레이트를 찾을 뿐만 아니라 해당 트레이트를 기반으로 사용자를 점수 지정하며 각 사용자에게 개별 점수를 지정합니다. 그런 다음 사용자를 타깃팅하는 알고리즘 특성을 만듭니다. 특성 빌더에서 정확도 및 도달 제어를 통해 타깃팅하려는 영향력이 있는 트레이트가 있는 모든 사용자를 지정할 수 있습니다.

알고리즘 모델을 사용하면 사용자를 서로 다른 정확도 레벨로 선택할 수 있고 Audience Lab에서 사용자 그룹을 보다 효율적으로 전환할 수 있습니다. See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

알고리즘 모델에서 모델은 8 일마다 실행되며 알고리즘 트레이트에 대한 자격을 갖춘 사용자를 새로 고칩니다.

**트레이트 권장 사항**

특성 Recommendations는 세그먼트에서 사용하는 것과 유사한 다른 트레이트에 대한 통찰력을 얻을 수 있는 빠른 방법입니다.

다음과 같은 경우 트레이트 추천을 사용해야 합니다.

* 세그먼트를 구축하는 동안 빠른 통찰력이 필요합니다.
* 짧은 캠페인에 세그먼트를 사용하거나 전환 대상 고객을 빠르게 표시하지 않으려는 경우
* 고객에 대한 도달 범위를 확대하고 있습니다.

<br> 

**Adobe Analytics와 Audience Manager 세그먼트 간에 차이가 있습니까?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
