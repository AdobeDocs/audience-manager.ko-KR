---
description: 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 받아들여지는 우수 사례와 함께 Audience Manager 통합 및 규정 준수에 대해 설명합니다.
seo-description: Describes Audience Manager integration and compliance with generally accepted best practices related to consumer privacy and opt-out procedures.
seo-title: Data Privacy Overview
solution: Audience Manager
title: 데이터 개인 정보 보호 개요
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
feature: Data Governance & Privacy
exl-id: 051de369-e762-49fb-b65f-6faf94db48a4
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 53%

---

# 데이터 개인 정보 보호 개요 {#data-privacy}

## 개요

데이터 개인 정보 보호 설명서에서는 [!DNL Audience Manager] 소비자 개인 정보 보호 및 옵트아웃 절차와 관련하여 일반적으로 받아들여지는 우수 사례와 통합 및 규정 준수

[!DNL Audience Manager] 는 소비자와 소비자가 상호 작용하는 온라인 브랜드 간 관계의 중요성을 인식합니다. 익명의 데이터 요소를 투명하게 교환하는 것은 양측 모두에게 이득이 됩니다.

* 소비자에게는 개인화된 컨텐츠, 할인된 제품 오퍼 및 간소화된 사용자 환경이 제공됩니다.
* 브랜드에게는 다양한 온라인 비즈니스 모델을 지원하는 중요한 매출원이 생깁니다.

이 모델을 계속 지원하면서 [!DNL Audience Manager] 는 고객을 위해 투명도와 제어력을 제공하는 데 도움이 되는 도구를 제공하는 동시에 [OBA(Online Behavioral Advertising) 자율 규제 원칙](https://www.iab.com/news/self-regulatory-principles-for-online-behavioral-advertising/).

## [!DNL GDPR] {#gdpr}

[GDPR(일반 개인정보보호 규정)](https://gdpr.eu/data-privacy/)에서는 **액세스 권한** 및 **잊혀질 권리** 등 유럽 연합 회원국을 위한 몇 가지 새로운 데이터 개인 정보 보호 권한을 도입했습니다. 이것은 [!DNL EU] 비즈니스에 의해 개인 데이터가 수집된 사용자는 언제든지 자신의 데이터에 대한 액세스나 삭제를 요청할 수 있습니다. 이러한 요청을 준수하지 않으면 귀사에 수백만 달러의 벌금이 부과될 수 있습니다.

을 준수하려면 [!DNL GDPR], [!DNL Audience Manager] 데이터 액세스 및 삭제 지원 [요청](data-privacy-requests.md).

## [!DNL CCPA] {#ccpa}

2020년 1월 1일부터 시행된 [CCPA(캘리포니아 소비자 개인 정보 보호법)](https://www.caprivacy.org/about)은 캘리포니아 주민들에게 개인 정보에 대한 새로운 권리를 제공하고 캘리포니아에서 사업을 하는 특정 업체에 데이터 보호 책임을 부과합니다.

[!DNL CCPA] 개인 데이터를 액세스 및 삭제할 권리, 그리고 이들의 개인 데이터가 판매 또는 공개되었는지 여부(및 공개 대상)를 알 수 있는 권리 등 캘리포니아 거주자에게 새로운 데이터 개인 정보 보호 권한을 제공합니다. 을 준수하려면 [!DNL CCPA], [!DNL Audience Manager] 지원 [!DNL CCPA] 액세스 및 삭제 [요청](data-privacy-requests.md).

자세한 내용은 [Adobe 개인 정보 보호 센터](https://www.adobe.com/privacy/opt-out.html)를 참조하십시오.

## 규정 준수 {#compliance}

[!DNL Audience Manager] 은 다음과 같은 개인 정보 보호 도구를 통해 특정 개인 정보 보호 규정에 따른 귀하의 의무를 준수하도록 도와줍니다 [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) 데이터 액세스 및 삭제 요청

이 서비스는 소비자 데이터 요청을 관리하는 데 도움이 되는 [!DNL RESTful API] 및 사용자 인터페이스를 제공합니다. [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en)를 사용하면 개별 소비자의 요청에 따라 개인 데이터에 대한 액세스 및 삭제 요청을 제출할 수 있으므로, 규정 준수 의무 부분을 자동화하는 데 도움이 됩니다.

데이터 액세스 및 삭제 요청은 Privacy Service을 통해 처리되는 반면, [옵트아웃 요청](data-privacy-requests.md#opt-out-requests) 는 현재 [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md). 자세한 내용은 [데이터 개인 정보 보호 요청](data-privacy-requests.md)을 참조하십시오.

## 관련 개념 {#related-concepts}

* [데이터 개인 정보 보호 요청](data-privacy-requests.md)
* [동의 관리](data-privacy-consent.md)
* [IAB TCF를 위한 Audience Manager 플러그인](aam-iab-plugin.md)
* [Audience Manager 식별자](data-privacy-ids.md)
* [CCPA 용어집](aam-ccpa-glossary.md)
* [GDPR 용어집](aam-gdpr-glossary.md)
* [대상에 대한 GDPR 고려 사항](aam-gdpr-partners.md)
* [Audience Manager 고객을 위한 GDPR 준비 지침](aam-gdpr-readiness.md)
* [데이터 거버넌스](data-governance.md)
* [개인 정보 보호 및 데이터 유지 관련 FAQ](../../faq/faq-privacy.md)
