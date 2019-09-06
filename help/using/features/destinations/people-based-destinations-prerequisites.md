---
description: '사용자 기반 대상에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 참조하십시오.  '
seo-description: '사용자 기반 대상에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 참조하십시오.  '
seo-title: 인물 기반 대상 사전 요구 사항 및 고려 사항
solution: Audience Manager
title: 사전 요구 사항 및 고려 사항
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 사전 요구 사항 및 고려 사항 {#prerequisites-considerations}

등록 전에 충족해야 하는 고객 요구 사항에 [!DNL People-Based Destinations]대한 개요는 아래를 참조하십시오.

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 문서를 자세히 읽어 보십시오.

## People-based 대상에 등록 {#signing-up}

[!DNL People-Based Destinations] 는 소셜 네트워크나 이메일 마케팅을 통해 사용자 지정된 오퍼로 고객을 타겟팅하여 사용자 기반 환경에서 퍼스트 파티 대상 세그먼트를 활성화할 수 있어 Audience Manager 경험을 향상시키는 프리미엄 기능입니다.

등록 방법에 대한 자세한 내용은 Adobe 세일즈 담당자에게 [!DNL People-Based Destinations]문의하십시오.

## 파트너별 사전 요구 사항 {#partner-prerequisites}

### [!DNL Facebook]

대상 세그먼트를 보낼 수 [!DNL People-Based Destinations] 있으려면 먼저 [!DNL Facebook]다음 요구 사항을 충족해야 합니다.

1. [!DNL Facebook] 사용자 계정은 사용할 광고 계정에 대해 캠페인 **관리** 권한이 활성화되어 있어야 합니다.
1. Adobe **Experience Cloud** 비즈니스 계정을 [!DNL Facebook Ad Account]광고 파트너로 추가합니다. 활동을 만들려면 `business ID=206617933627973`. 자세한 [내용은 비즈니스 관리자에게](https://www.facebook.com/business/help/708679622611131) 파트너 추가를 참조하십시오.
   >[!IMPORTANT]
   > Adobe Experience Cloud에 대한 권한을 구성할 때 캠페인 **관리** 권한을 활성화해야 합니다. 통합을 위해 [!DNL People-Based Destinations] 필요합니다.
1. 서비스 [!DNL Facebook Custom Audiences] 약관을 읽고 서명합니다. 이 작업을 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]``accountID`[!DNL Facebook Ad Account ID]수행하려면 어디에서나 이동하십시오.

## 데이터 온보드 {#data-onboarding}

현재 데이터 수집은 [!DNL People-Based Destinations] 일괄 전송 당 하나의 고객 ID ([!DNL CRM ID]) 에 연결된 최대 10 개의 해시된 이메일 주소를 지원합니다. 고객 ID에 연결된 10 개 이상의 해시된 이메일 주소를 업로드하면 Audience Manager는 특정 순서 없이 이 중 10 개를 인제스트할 수 있습니다.

여러 일괄 전송 시 하나의 고객 ID에 연결된 10 개 이상의 해시된 이메일 주소를 업로드하면 Audience Manager가 추가된 최근 10 개의 이메일 주소를 유지합니다.

## 데이터 개인 정보{#data-privacy}

이메일 주소를 기반으로 대상을 타깃팅할 [!DNL People-Based Destinations] 수 있지만, 직접 식별할 수 있는 방문자 정보는 Audience Manager에 도달하지 않습니다. 데이터 온보드 단계에서 사용하려는 이메일 주소가 [!DNL SHA256] 알고리즘으로 해시되어 있는지 확인해야 합니다. [!DNL People-Based Destinations]그렇지 않으면 사용할 수 없게 됩니다.

## 데이터 해싱 및 암호화 {#data-hashing-encryption}

암호화는 양방향 기능입니다. 암호화된 모든 정보는 올바른 암호 해독 키를 사용하여 해독할 수 있습니다. 모든 암호화된 형태의 개인 정보를 해독하여 민감한 고객 데이터를 공개하므로 Audience Manager의 컨텍스트에서 데이터를 암호화하면 심각한 개인정보 보호 위험이 발생합니다. 암호화와는 달리, 대신 [!DNL People-Based Destinations] 해시된 데이터와 함께 작동하도록 설계되어 타깃팅에 사용하는 고객 데이터를 보호합니다.

해싱은 입력을 스크램블링하여 고유한 결과를 생성하는 단방향 함수입니다. 적절한 해시 알고리즘을 사용하면 [!DNL SHA256]해싱 함수를 반전시키고 스크램블되지 않은 정보를 표시할 방법이 없습니다. Audience Manager에 탑승할 이메일 주소는 [!DNL SHA256] 알고리즘으로 해시해야 합니다. 이렇게 하면 개인 식별이 가능한 정보가 Audience Manager에 도달하지 못하므로 고객 데이터를 안전하게 유지할 수 있습니다.

## 해싱 요구 사항 {#hashing-requirements}

이메일 주소를 해싱할 때 다음 요구 사항을 반드시 준수해야 합니다.

* 이메일 문자열에서 모든 선행 및 후행 공백을 트리밍합니다. 예: `johndoe@example.com`, not `<space>johndoe@example.com<space>`;
* 해시된 문자열이 모두 소문자인지 확인합니다. 예: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, not `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 문자열을 솔로로 만들지 마십시오.

Adobe Experience Cloud는 Experience Cloud ID 서비스를 통해 고객 ID를 해시 처리할 수 있는 옵션을 제공합니다. ECID를 해시 사용 고객 ID에 사용하는 방법에 대한 자세한 내용은 [Setcustomerids에 대한 SHA 256](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 해싱 지원을 참조하십시오.

## 사용자 권한 얻기 {#obtaining-user-permission}

이 기능은 사용자 기반 채널에서 퍼스트 파티 대상 데이터를 활성화하는 [!DNL People-Based Destinations] 데 도움이 되므로, 광고 목적으로 데이터를 어떻게 사용할지 고객에게 알리는 것은 귀하의 책임입니다.

등록을 [!DNL People-Based Destinations]하기 전에 광고 목적으로 고객의 정보를 사용하기 전에 고객의 동의를 얻어야 합니다.

고객이 광고 캠페인을 옵트아웃하려는 경우, Audience Manager에서 데이터 수집을 중단하는 방법에 대한 자세한 내용은 [옵트아웃 관리를](../../overview/data-security-and-privacy/opt-out-management.md) 참조하십시오.

## 자사 데이터 활성화 시행 {#enforcing-first-party-activation}

사용할 [!DNL People-Based Destinations]때는 퍼스트 파티 데이터만 사용하여 사용자 기반 채널에서 대상 세그먼트를 활성화할 수 있습니다. 사용자 기반 채널에서 대상 활성화에는 두 번째 또는 타사 데이터를 사용할 수 없습니다.

## 선언된 ID 타깃팅을 통해 인증된 해시 ID 입수 {#onboard-authenticated-declared-id}

다음 두 가지 방법으로 오프라인 데이터를 Audience Manager로 가져올 [!DNL People-Based Destinations]수 있습니다.

* [일괄 데이터를](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager로 보내 해시된 이메일 주소를 인제스트합니다. 이 방법을 사용하면 [!DNL CRM] 데이터베이스의 해시된 이메일 주소를 모두 사용할 [!DNL People-Based Destinations]수 있습니다. 또한 이 방법을 사용하는 경우 온보드 트레이트에 [대한 해시된 이메일 주소를 자격을 부여할](../traits/trait-qualification-reference.md)수도 있습니다.
* 인증된 고객 ID를 전달할 때 [선언된 ID](../declared-ids.md) 를 사용하여 해시된 이메일 주소를 선언합니다. 이 방법을 사용할 경우 Audience Manager는 온라인으로 인증된 사용자의 해시 이메일 주소만 [!DNL People-Based Destinations] 전송합니다. Facebook를 통해 활성화된 이메일 주소는 선언된 ID 이벤트 호출의 이메일 주소입니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 전송되지 않습니다.
