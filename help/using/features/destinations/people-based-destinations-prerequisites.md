---
description: 'Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  '
seo-description: 'Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.  '
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Prerequisites and Considerations
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Prerequisites and Considerations {#prerequisites-considerations}

>[!IMPORTANT]
>This article contains product documentation meant to guide you through the setup and usage of this feature. Nothing contained herein is legal advice. Please consult your own legal counsel for legal guidance.

등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 [!DNL People-Based Destinations]참조하십시오.

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 문서를 자세히 읽어 보십시오.

## 사람 기반 대상 등록 {#signing-up}

[!DNL People-Based Destinations] 는 소셜 네트워크나 이메일 마케팅을 통해 고객을 타깃팅하여 사용자 기반 환경에서 자사 고객 세그먼트를 활성화함으로써 Audience Manager 경험을 향상시키는 프리미엄 기능입니다.

이 프리미엄 기능을 활용하려면 Adobe 담당자에게 문의하십시오.

## 파트너별 사전 요구 사항 {#partner-prerequisites}

### [!DNL Facebook]

를 사용하여 퍼스트 파티 고객 세그먼트를 보낼 [!DNL People-Based Destinations] 수 있으려면 먼저 다음 요구 사항을 충족해야 [!DNL Facebook]합니다.

1. 사용자 [!DNL Facebook] 계정에는 사용할 **광고 계정에 대해 캠페인** 관리 권한이 활성화되어 있어야 합니다.
1. Adobe Experience **Cloud** 비즈니스 계정을 광고 파트너에 [!DNL Facebook Ad Account]추가합니다. 활동을 만들려면 `business ID=206617933627973`. 자세한 [내용은 비즈니스 관리자에 파트너](https://www.facebook.com/business/help/708679622611131) 추가를 참조하십시오.
   >[!IMPORTANT]
   > Adobe Experience Cloud에 대한 권한을 구성할 때 캠페인 **관리** 권한을 활성화해야 합니다. 이 작업은 [!DNL People-Based Destinations] 통합에 필요합니다.
1. 서비스 약관을 읽고 [!DNL Facebook Custom Audiences] 서명합니다. 이렇게 하려면, `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`어디로 `accountID` 가십시오 [!DNL Facebook Ad Account ID].

## 데이터 온보딩 {#data-onboarding}

데이터 수집은 [!DNL People-Based Destinations] 현재 일괄 전송당 하나의 고객 ID([!DNL CRM ID])에 연결된 해시된 이메일 주소를 최대 10개까지 지원합니다. 하나의 고객 ID에 연결된 해시된 이메일 주소를 10개 이상 업로드하면 Audience Manager가 10개를 특정 순서 없이 인제스트합니다.

여러 일괄 전송에서 하나의 고객 ID에 연결된 해시된 이메일 주소를 10개 이상 업로드하면 Audience Manager가 추가된 최신 이메일 주소 10개를 유지합니다.

## 데이터 개인 정보{#data-privacy}

사용자가 업로드한 해시된 이메일 주소를 기반으로 대상을 타깃팅할 [!DNL People-Based Destinations] 수 있지만, Audience Manager에 직접 식별 가능한 방문자 정보를 업로드할 수 없는 상태로 남아 있습니다. 데이터 온보딩 단계에서는 사용하려는 이메일 주소가 [!DNL SHA256] 알고리즘과 해시되었는지 확인해야 합니다. 그렇지 않으면, 여러분은 그것을 사용할 수 없을 [!DNL People-Based Destinations]거예요.

## 데이터 해싱 및 암호화 {#data-hashing-encryption}

암호화는 양방향 기능입니다. 또한 올바른 암호 해독 키를 사용하여 암호화된 정보를 해독할 수 있습니다. 암호화된 형식의 개인 식별 정보를 암호화할 수 있으므로 Audience Manager 컨텍스트에서 데이터를 암호화하면 심각한 위험이 발생합니다. 암호화가 아니라 해시된 [!DNL People-Based Destinations] 데이터를 사용하여 작업할 수 있도록 설계되었습니다.

해싱은 고유한 결과를 생성하기 위해 입력을 스크램블하는 단방향 함수입니다. 이와 같이 적절한 해싱 알고리즘을 [!DNL SHA256]사용하면 해싱 기능을 역동적으로 전환하여 스크램블된 정보를 표시할 수 없습니다. Audience Manager에 포함될 이메일 주소는 [!DNL SHA256] 알고리즘으로 해시되어야 합니다. 이렇게 하면 해시되지 않은 이메일 주소가 Audience Manager에 도달하지 않도록 할 수 있습니다.

## Hashing Requirements {#hashing-requirements}

When hashing the email addresses, make sure to comply with the following requirements:

* Trim all leading and trailing spaces from the email string; example: , not ;`johndoe@example.com``<space>johndoe@example.com<space>`
* When hashing the email strings, make sure to hash the lowercase string;
   * Example: , not ;`example@email.com``EXAMPLE@EMAIL.COM`
* Make sure the hashed string is all lowercase
   * Example: , not ;`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149``55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`
* Do not salt the string.

Adobe Experience Cloud gives you the option to hash customer IDs through the Experience Cloud ID Service. See SHA256 Hashing Support for setCustomerIDs for detailed information on how to use ECID to hash customer IDs.[](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)

## Obtaining User Permission {#obtaining-user-permission}

Since  helps you activate first-party audience data in people-based channels, it is your responsibility to inform and obtain any necessary consents from your customers of how you will use their data for advertising or other purposes.[!DNL People-Based Destinations]

Before you sign up for , make sure to obtain your customers' consent before using their information for advertising purposes.[!DNL People-Based Destinations]

In case your customers wish to opt-out of advertising campaigns, see Opt-out Management for details on how to stop Audience Manager from collecting data any further.[](../../overview/data-security-and-privacy/opt-out-management.md)

## 퍼스트 파티 데이터 활성화 적용 {#enforcing-first-party-activation}

사용 [!DNL People-Based Destinations]시 퍼스트 파티 데이터만 사용하여 사람 기반 채널에서 고객 세그먼트를 활성화할 수 있습니다. You cannot use any second- or third-party data for audience activation in people-based channels.

## 선언된 ID 타깃팅을 통해 인증된 해시 ID 온보드 {#onboard-authenticated-declared-id}

두 가지 방법으로 Audience Manager에 오프라인 데이터를 가져올 수 [!DNL People-Based Destinations]있습니다.

* [일괄 처리 데이터를](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager로 보내 해시된 이메일 주소를 인제스트합니다. 이 방법을 사용하면 [!DNL CRM] 데이터베이스에서 해시된 이메일 주소를 사용할 수 [!DNL People-Based Destinations]있습니다. 또한 이 방법을 사용할 때 온보드 트레이트에 대해 해시된 이메일 주소를 [평가할](../traits/trait-qualification-reference.md)수도 있습니다.
* 인증된 [고객 ID를 전달할](../declared-ids.md) 때 선언된 ID를 사용하여 해시된 이메일 주소를 선언합니다. 이 방법을 사용할 때 Audience Manager는 사용자를 대신하여 온라인에서 인증된 사용자의 해시된 이메일 [!DNL People-Based Destinations] 주소에만 전송합니다. 사람 기반 채널을 통해 활성화되는 이메일 주소는 선언된 ID 이벤트 호출의 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 전송되지 않습니다.
