---
description: 이 문서에서는 Audience Manager의 동의 관리 작동 방식을 설명합니다.
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, 개인 정보, 동의
title: 동의 관리
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 98%

---

# 동의 관리

## 개요 {#overview}

특정 마케팅 활동에 대한 동의가 필요한 경우 Audience Manager 고객은 범위를 결정하고, 데이터를 앞으로도 계속 사용할 수 있도록 특정 동의를 갱신해야 할지 여부를 결정해야 합니다.

Audience Manager는 여러 채널을 통해 개인화된 경험을 제공할 수 있도록 사용자로부터 필요한 동의를 얻는 기능을 지원하는 데 도움이 되는 도구를 제공합니다.

>[!IMPORTANT]
>
> 이 문서의 내용은 법률적인 조언이 아니며, 법률적인 조언을 대체하지 않습니다.
>
> 데이터 처리자로서 Adobe는 동의를 얻는 것에 대한 법률 자문을 제공할 수 없습니다. 옵트인 구현을 설정할 때 동의 및 관행에 대한 조언이 필요할 경우 [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/)이나 [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)와 같은 동의 관리 솔루션 공급자와의 협업을 고려하고 회사 법무팀에 문의할 수도 있습니다.

## Experience Cloud 옵트인 서비스

[Experience Cloud 옵트인 서비스](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ko)를 사용하면 방문자가 사용자의 사이트를 방문할 때 개인의 장치 또는 브라우저에서 쿠키를 설정할 수 있는지 확인하는 데 방문자가 도움을 줄 수 있도록 프로토콜을 설정할 수 있습니다.

이것은 사용자의 동의를 얻기 전에 방문자를 위해 웹 페이지에 쿠키를 배치할 수 있는지 여부와 배치할 수 있는 Experience Cloud 솔루션을 제어할 수 있도록 설계된 [!DNL Experience Cloud ID (ECID) Service]의 확장입니다.

또한 [Experience Cloud 옵트인 서비스](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=ko)를 사용하면 더 큰 디자인의 일부로서 CMP(동의 관리 플랫폼) 및 기존 시스템과 통합되는 프로토콜을 설정할 수도 있습니다.

## 옵트인 관리 / 동의 획득

Audience Manager 고객은 Audience Manager에서 트레이트로서 광고 또는 개인화와 같은 다양한 사용 사례에 대한 사용자 동의를 저장할 수 있습니다. 이러한 트레이트로 만든 세그먼트에는 이러한 각 사용 사례에 대해 각각의 동의를 제공하는 사용자만 포함됩니다. 이 접근 방법을 사용하면 데이터 수집은 중지되지 않고 활성화를 위해 세그먼트를 보낼 때 데이터 사용만 영향을 받습니다. 사용자가 동의를 철회하면 Audience Manager [인바운드 배치 프로세스](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 또는 Audience Manager 옵트아웃 프로세스를 아래 자세히 설명된 대로 사용하여 사용자 프로필에서 이러한 트레이트를 제거할 수 있습니다.

## 옵트아웃 관리 / 동의 철회

[귀하의 개인 정보 보호 선택 사항](https://www.adobe.com/kr/privacy/opt-out.html#customeruse) 페이지를 통해 Adobe Experience Cloud에 대한 옵트아웃을 관리할 수 있습니다. 1번의 클릭으로 최종 사용자가 Adobe Experience Cloud 광고 솔루션(Audience Manager 포함)에 의한 데이터 수집을 제어하고 옵트아웃할 수 있습니다. 특히 개인 정보 보호 선택 사항 페이지의 [비즈니스 고객 섹션](https://www.adobe.com/kr/privacy/opt-out.html#customeruse)을 참조하십시오. 타사 쿠키를 지원하지 않는 브라우저의 경우 [선언된 ID 타겟팅](../../features/declared-ids.md#declared-id-targeting)을 참조하십시오. 모바일 장치의 경우, 적절한 Audience Manager 식별자를 검색하고 [선언된 ID 옵트아웃 예](../../features/declared-ids.md#opt-out-examples)에서 언급한 대로 Audience Manager 옵트아웃 API를 호출하십시오. 뒤이어 Mobile SDK에서 옵트아웃 API를 사용하는 해당 사용자에 대한 모든 데이터 수집을 중단할 수 있습니다. [Android 장치](https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html) 및 [iOS 장치](https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html)를 참조하십시오. 옵트아웃에 대한 자세한 내용은 [데이터 개인 정보 보호 요청 문서](../../overview/data-security-and-privacy/data-privacy-requests.md)에 있습니다.

## 제2자 파트너에 대한 동의 관리

제2자 파트너도 일반적으로 데이터 통제자이며, 데이터를 제2자 데이터 파트너와 공유할 수 있도록 데이터 주체로부터 필요한 동의를 받는 프로세스를 소유합니다. Audience Manager 고객으로서 제2자 파트너가 사용 사례에 필요한 동의를 받았는지 확인하는 것은 귀하의 책임입니다. 동의를 받는 데 대한 자세한 내용은 위에 나와 있습니다.

## Audience Marketplace 타사 파트너에 대한 동의 관리

Audience Marketplace 타사 파트너는 데이터 관리자이기도 하며 동의를 받고 액세스/삭제/수정 요청을 관리하는 프로세스를 소유합니다. Adobe에서는 Audience Marketplace 타사 파트너가 사용자 데이터 수집에 대한 추가 정보로 [Adobe Audience Finder](https://www.adobe-audience-finder.com/) 내에서 회사 프로필 정보를 업데이트할 것을 적극적으로 요청하고 있습니다. 정보는 Audience Marketplace 타사 파트너를 통해 공급되며 정기적으로 업데이트됩니다. 그러나 Audience Marketplace 타사 파트너가 해당 고객의 사용 사례에 필요한 동의를 받았음을 확인하는 것은 각 Audience Manager 고객의 책임입니다. Adobe는 주어진 사용 사례에 대해 Audience Marketplace 타사 파트너가 받았거나 보고한 동의의 범위 또는 유효성에 대해 어떠한 표현도 하지 않습니다.
