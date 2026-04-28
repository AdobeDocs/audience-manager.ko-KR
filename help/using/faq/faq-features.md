---
description: 일반적인 제품 및 기능 관련 질문 및 문제
keywords: audience manager 쿠키
seo-description: Common product and function-related questions and issues.
seo-title: Product Features and Functions FAQ
solution: Audience Manager
title: 제품 및 기능 FAQ
uuid: da5f5089-24a8-4455-88a6-eb62d83939d2
feature: Overview
exl-id: b5884d26-0be1-4eaa-99a1-7247942bf6c9
TQID: https://experienceleague.adobe.com/gsJ4qXlNDpfWmTq0jjmtjfUWI60yRr7uBTxZjsF-pQE
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: f2fdbb191013b0bcb9bdab0529e3b7f3c872fd54
workflow-type: tm+mt
source-wordcount: 428
ht-degree: 75%

---

# 제품 및 기능 FAQ{#product-features-and-functions-faq}

일반적인 제품 및 기능 관련 질문 및 문제

 

<!-- 

faq_features_functions.xml

 -->

**조직 ID는 무엇이며 어떻게 찾을 수 있습니까?**

*`Organization ID`*&#x200B;는 [!DNL Audience Manager] 및 [!DNL Adobe Experience Cloud]에 조직을 식별하는 고유 ID입니다. 이 ID는 대/소문자를 구분하는 24자의 영숫자 문자열과 그 뒤에 오는 [!UICONTROL @AdobeOrg]로 구성됩니다.

예를 들어 *`Organization ID`*&#x200B;는 `1FD6776A524453CC0A490D44@AdobeOrg`와 같은 모습입니다.

*`Organization ID`*&#x200B;는 Audience Manager의 [DIL](../dil/dil-overview.md) API, [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ko) 및 기타 [!DNL Experience Cloud] 솔루션에서 사용됩니다. 관리자 권한이 있는 사용자는 [!DNL Adobe Admin Console]에서 *`Organization ID`*&#x200B;를 찾을 수 있습니다. [관리 - 사용자 관리 FAQ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ko)를 참조하십시오.

 

**트레이트나 대상을 벌크로 만들 수 있습니까?**

예. [벌크 관리 도구](../reference/bulk-management-tools/bulk-management-intro.md)를 참조하십시오.

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools] 도구는 [!DNL Audience Manager]에서 *지원하지 않습니다*. 편의를 위해 그리고 호의로 제공될 뿐입니다. 벌크 변경의 경우에는 [Audience Manager API](../api/api.md)를 대신 사용하는 것이 좋습니다.

 

**대상으로 일괄 ID 내보내기를 수행할 때 일부 고객 ID가 누락되었습니다. 이유는 무엇입니까?**

장치 ID([AAM UUID](../reference/ids-in-aam.md))가 여러 CRM ID([DPUUID](../reference/ids-in-aam.md))에 연결되어 있으면 최신 매핑만 내보내집니다. 장치 ID를 내보내는 횟수가 예상한 것보다 적을 수 있습니다.

 

**[!DNL Audience Manager]를 사용하면 타사 태그나 픽셀이 덜 필요하고 페이지 로드 시간도 줄어듭니까?**

[!DNL Audience Manager]가 타사 데이터 파트너와 통합되는 경우, 픽셀과 태그를 [!DNL Audience Manager]에 대한 서버 간 ID 호출로 바꿀 수 있습니다. 이 경우 [!DNL Audience Manager]는 처음 사용자를 보고 해당 정보를 타사 파트너와 동기화할 때 단일 ID 호출을 실행합니다. 이렇게 되면 모든 페이지에서 여러 픽셀을 호출할 필요가 없어집니다. 픽셀 호출이 줄어들면 페이지 로드 시간이 향상됩니다.

 

**데이터 피드에 가입했습니다. 그 데이터는 어디에 저장되어 있습니까?**

데이터 피드 및 피드에 포함된 모든 트레이트는 [!DNL Audience Manager]에서 하위 폴더와 트레이트로 표시됩니다. **[!UICONTROL Audience Data > Traits]**&#x200B;로 이동하고 [!UICONTROL 3rd-Party Data] 폴더를 확장하여 트레이트를 보거나 이 데이터를 사용하여 세그먼트와 모델을 만듭니다.

 

**[!UICONTROL Tag Insertion Manager (TIM)]은 무엇입니까?**

Audience Manager는 TIM([!UICONTROL Tag Insertion Manager])을 사용하여 [!UICONTROL data collection code (DIL)]를 만들고 관리했었습니다. 이 기능은 더 이상 사용되지 않으며, [!UICONTROL Dynamic Tag Manager (DTM)]로 대체되었으며, 이후에 [!DNL Adobe Experience Platform Tags]로 대체되었습니다. 자세한 내용은 [Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ko)를 참조하십시오.

 

**Adobe Analytics와 Audience Manager 세그먼트 간에 차이가 있습니까?**

예. 그 차이점에 대한 심도 있는 설명이 필요하면 [Analytics와 Audience Manager의 세그먼트 이해](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html?lang=ko)를 참조하십시오.
