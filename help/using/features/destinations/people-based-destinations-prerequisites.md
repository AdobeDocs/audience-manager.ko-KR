---
description: '사람 기반 대상에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 참조하십시오.  '
seo-description: '사람 기반 대상에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 참조하십시오.  '
seo-title: 사용자 기반 대상 사전 요구 사항 및 고려 사항
solution: Audience Manager
title: 전제 조건 및 고려 사항
translation-type: tm+mt
source-git-commit: f3fe6abe913d98549ae6c090a2d5f721485308c2

---


# 전제 조건 및 고려 사항 {#prerequisites-considerations}

등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 [!DNL People-Based Destinations]참조하십시오.

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 문서를 자세히 읽어 보십시오.

## 사람 기반 대상 등록 {#signing-up}

[!DNL People-Based Destinations] 는 소셜 네트워크나 이메일 마케팅을 통해 고객을 타깃팅하여 사용자 기반 환경에서 자사 고객 세그먼트를 활성화함으로써 Audience Manager 경험을 향상시키는 프리미엄 기능입니다.

이 프리미엄 기능을 활용하려면 Adobe 담당자에게 문의하십시오.

## 파트너별 사전 요구 사항 {#partner-prerequisites}

### [!DNL Facebook]

를 사용하여 대상 세그먼트를 [!DNL People-Based Destinations] 보낼 수 [!DNL Facebook]있으려면 먼저 다음 요구 사항을 충족해야 합니다.

1. 사용자 [!DNL Facebook] 계정에는 사용할 **광고 계정에 대해 캠페인** 관리 권한이 활성화되어 있어야 합니다.
1. Adobe Experience **Cloud** 비즈니스 계정을 광고 파트너에 [!DNL Facebook Ad Account]추가합니다. 활동을 만들려면 `business ID=206617933627973`. 자세한 [내용은 비즈니스 관리자에 파트너](https://www.facebook.com/business/help/708679622611131) 추가를 참조하십시오.
   >[!IMPORTANT]
   > Adobe Experience Cloud에 대한 권한을 구성할 때 캠페인 **관리** 권한을 활성화해야 합니다. 이 작업은 [!DNL People-Based Destinations] 통합에 필요합니다.
1. 서비스 약관을 읽고 [!DNL Facebook Custom Audiences] 서명합니다. 이렇게 하려면, `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`어디로 `accountID` 가십시오 [!DNL Facebook Ad Account ID].

## 데이터 온보딩 {#data-onboarding}

데이터 수집은 [!DNL People-Based Destinations] 현재 일괄 전송당 하나의 고객 ID([!DNL CRM ID])에 연결된 해시된 이메일 주소를 최대 10개까지 지원합니다. 하나의 고객 ID에 연결된 해시된 이메일 주소를 10개 이상 업로드하면 Audience Manager가 10개를 특정 순서 없이 인제스트합니다.

여러 일괄 전송에서 하나의 고객 ID에 연결된 해시된 이메일 주소를 10개 이상 업로드하면 Audience Manager가 추가된 최신 이메일 주소 10개를 유지합니다.

## 데이터 개인 정보{#data-privacy}

이메일 주소를 기반으로 고객을 타깃팅할 [!DNL People-Based Destinations] 수 있지만 직접 식별할 수 있는 방문자 정보는 Audience Manager에 도달하지 않습니다. 데이터 온보딩 단계에서는 사용하려는 이메일 주소가 [!DNL SHA256] 알고리즘과 해시되었는지 확인해야 합니다. 그렇지 않으면, 여러분은 그것을 사용할 수 없을 [!DNL People-Based Destinations]거예요.

## 데이터 해싱 및 암호화 {#data-hashing-encryption}

암호화는 양방향 기능입니다. 또한 올바른 암호 해독 키를 사용하여 암호화된 정보를 해독할 수 있습니다. 암호화된 개인 식별 정보를 암호화하여 민감한 고객 데이터를 노출할 수 있으므로 Audience Manager의 컨텍스트에서 데이터를 암호화하면 심각한 개인정보 보호 위험이 발생합니다. 암호화와 [!DNL People-Based Destinations] 달리 해시된 데이터를 사용하여 작업할 수 있도록 설계되어 있으므로 타깃팅에 사용하는 고객 데이터를 보호할 수 있습니다.

해싱은 고유한 결과를 생성하기 위해 입력을 스크램블하는 단방향 함수입니다. 이와 같이 적절한 해싱 알고리즘을 [!DNL SHA256]사용하면 해싱 기능을 역동적으로 전환하여 스크램블된 정보를 표시할 수 없습니다. Audience Manager에 포함될 이메일 주소는 [!DNL SHA256] 알고리즘으로 해시되어야 합니다. 이렇게 하면 개인 식별이 가능한 정보가 Audience Manager에 전달되지 않으므로 고객 데이터를 안전하게 유지할 수 있습니다.

## 해싱 요구 사항 {#hashing-requirements}

이메일 주소를 해싱할 때는 다음 요구 사항을 준수해야 합니다.

* 이메일 문자열에서 모든 선행 및 후행 공백을 트리밍합니다.예: `johndoe@example.com`그렇지 `<space>johndoe@example.com<space>`않음
* 해시된 문자열이 모두 소문자인지 확인하십시오.예: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`그렇지 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`않음
* 문자열의 소금을 치지 마십시오.

Adobe Experience Cloud ID 서비스를 통해 고객 ID를 해시할 수 있는 옵션이 제공됩니다. ECID를 [사용하여 고객 ID를](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) 해시하는 방법에 대한 자세한 내용은 setCustomerID에 대한 SHA256 해싱 지원을 참조하십시오.

## 사용자 권한 얻기 {#obtaining-user-permission}

사람 기반 채널에서 자사 고객 데이터를 활성화하는 [!DNL People-Based Destinations] 데 도움이 되므로 고객에게 광고 용도로 자사 데이터를 사용하는 방법을 알려야 합니다.

가입하기 전에 [!DNL People-Based Destinations]광고 목적으로 고객의 정보를 사용하기 전에 고객의 동의를 받아야 합니다.

고객이 광고 캠페인을 옵트아웃하려는 경우 Audience Manager [의](../../overview/data-security-and-privacy/opt-out-management.md) 데이터 수집을 중지하는 방법에 대한 자세한 내용은 옵트아웃 관리를 참조하십시오.

## 퍼스트 파티 데이터 활성화 적용 {#enforcing-first-party-activation}

사용 [!DNL People-Based Destinations]시 퍼스트 파티 데이터만 사용하여 사람 기반 채널에서 고객 세그먼트를 활성화할 수 있습니다. 사람 기반 채널에서 고객 활성화를 위해 제휴 데이터 또는 타사 데이터를 사용할 수 없습니다.

## 선언된 ID 타깃팅을 통해 인증된 해시 ID 온보드 {#onboard-authenticated-declared-id}

두 가지 방법으로 Audience Manager에 오프라인 데이터를 가져올 수 [!DNL People-Based Destinations]있습니다.

* [일괄 처리 데이터를](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager로 보내 해시된 이메일 주소를 인제스트합니다. 이 방법을 사용하면 에서 [!DNL CRM] 데이터베이스의 해시된 이메일 주소를 모두 사용할 수 [!DNL People-Based Destinations]있습니다. 또한 이 방법을 사용할 때 온보드 트레이트에 대해 해시된 이메일 주소를 [평가할](../traits/trait-qualification-reference.md)수도 있습니다.
* 인증된 [고객 ID를 전달할](../declared-ids.md) 때 선언된 ID를 사용하여 해시된 이메일 주소를 선언합니다. 이 방법을 사용하는 경우 Audience Manager는 [!DNL People-Based Destinations] 온라인에서 인증된 사용자의 해시된 이메일 주소로만 전송합니다. Facebook을 통해 활성화된 이메일 주소는 선언된 ID 이벤트 호출에 있는 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 전송되지 않습니다.
