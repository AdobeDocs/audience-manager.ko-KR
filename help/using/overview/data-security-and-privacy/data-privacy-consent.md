---
description: 이 문서에서는 Audience Manager의 동의 관리 작동 방식을 설명합니다.
seo-description: 이 문서에서는 Audience Manager의 동의 관리 작동 방식을 설명합니다.
seo-title: 동의 관리
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: 동의 관리
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# 동의 관리

## 개요 {#overview}

특정 마케팅 활동에 대한 동의가 필요한 경우 Audience Manager 고객은 범위 및 특정 동의 여부를 결정한 후 지속적으로 데이터를 사용할 수 있도록 할지 여부를 결정해야 합니다.

Adobe Audience Manager는 고객의 필수 동의를 얻는 기능을 지원하는 툴을 제공하므로 개인화된 경험을 모든 채널에 제공할 수 있습니다.

>[!IMPORTANT]
>
> 이 문서의 내용은 법률 자문을 위한 것이 아니며, 법률 자문을 대체하기 위한 것이 아니다.
>
> Adobe는 귀하의 데이터 처리자로서 동의 받기에 대한 법적 조언을 제공할 수 없습니다. 또한 Evidon 또는 TrustArc와 같은 동의 관리 솔루션 제공업체와 [함께](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 일하는 것을 고려해 볼 수 있으며, 동의 [](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)구현 설정 시 동의 및 방침에 대한 조언을 구할 수 있습니다.

## Experience Cloud 옵트인 서비스

The [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) lets you set up protocols for the visitor to assist you in determining if you can set a cookie on the individual's device or browser when visiting your site.

이것은 사용자 동의 전에 방문자를 위해 웹 페이지에 쿠키를 배치할 수 있는지 여부와 어떤 Experience Cloud 솔루션이 쿠키를 배치할 수 있는지 여부를 제어할 수 있도록 설계된 확장 기능입니다. [!DNL Experience Cloud ID (ECID) Service]

또한 [Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) 옵트인 서비스를 사용하면 CMP(Consent Management Platform) 및 기존 시스템과 통합되도록 프로토콜을 설정할 수 있습니다.

## 옵트인 관리/동의 받기

Audience Manager 고객은 Audience Manager에서 광고 또는 개인화와 같은 다양한 사용 사례에 대한 사용자 동의를 저장할 수 있습니다. 그런 다음 이러한 트레이트를 사용하여 만드는 세그먼트에는 이러한 각 사용 사례에 대한 각각의 동의를 제공하는 사용자만 포함됩니다. 이 방법을 사용하면 데이터 수집이 중지되지는 않지만 활성화를 위해 세그먼트를 보낼 때만 데이터 사용에 영향을 줍니다. 사용자가 동의를 철회하면 아래 설명에 따라 Audience Manager [인바운드 배치 프로세스](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 또는 Audience Manager 옵트아웃 프로세스를 사용하여 사용자 프로필에서 이러한 트레이트를 제거할 수 있습니다.

## 동의 거부/철회 관리

옵트아웃은 Your Privacy Choices 페이지에서 Adobe Experience [Cloud에 대해 관리할 수](https://www.adobe.com/privacy/opt-out.html#customeruse) 있습니다. 1번의 클릭으로 최종 사용자가 Adobe Experience Cloud 광고 솔루션(Audience Manager 포함)의 데이터 수집을 제어하고 옵트아웃할 수 있습니다. 특히 개인 정보 선택 페이지의 [비즈니스 고객 섹션을](https://www.adobe.com/privacy/opt-out.html#customeruse) 참조하십시오. 타사 쿠키를 지원하지 않는 브라우저의 경우 선언된 [ID 타깃팅을](../../features/declared-ids.md#declared-id-targeting)참조하십시오. 모바일 장치의 경우, 관련 Audience Manager 식별자를 검색하고 선언된 ID 옵트아웃 예제에 [](../../features/declared-ids.md#opt-out-examples)나와 있는 Audience Manager 옵트아웃 API를 호출하십시오. 이후 Mobile SDK에서 옵트아웃 API를 사용하는 사용자에 대한 모든 데이터 수집을 중단할 수 있습니다. Android [장치](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) 및 [iOS 장치를](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)참조하십시오. 옵트아웃에 대한 자세한 내용은 데이터 개인 정보 보호 요청 [문서에서 참조할 수 있습니다](../../overview/data-security-and-privacy/data-privacy-requests.md).

## 제2자 파트너에 대한 동의 관리

또한 제2자 파트너는 일반적으로 데이터 관리자이며, 데이터를 제2자 데이터 파트너와 공유할 데이터 주체의 필요한 동의를 얻기 위한 프로세스를 소유합니다. Audience Manager 고객으로서, 제2자 파트너가 귀하의 사용 사례에 필요한 동의를 받았는지 확인하는 것은 귀하의 책임입니다. 동의에 대한 자세한 내용은 위에 나와 있습니다.

## Audience Marketplace 타사 파트너에 대한 동의 관리

Audience Marketplace 제3자 파트너는 동의 및 액세스/삭제/수정 요청을 관리하는 데이터 관리자입니다. Adobe는 Audience Marketplace 타사 파트너가 Adobe Audience Finder [에서 회사 프로필 정보를 업데이트하여 사용자 데이터](https://www.adobe-audience-finder.com/) 수집에 대한 추가 정보를 제공하도록 적극적으로 요청하고 있습니다. 정보는 Audience Marketplace 제3자 파트너를 통해 제공되며 정기적으로 업데이트됩니다. 그러나 Audience Marketplace 제3자 파트너가 해당 고객의 사용 사례에 필요한 동의를 얻었는지 여부는 각 Audience Manager 고객에게 달려 있습니다. Adobe는 특정 사용 사례에 대해 Audience Marketplace 제3자 파트너가 취득하거나 보고한 동의의 범위 또는 유효성에 대해 진술하지 않습니다.
