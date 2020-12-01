---
description: '사람 기반 대상에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 참조하십시오.  '
seo-description: '사람 기반 대상에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 참조하십시오.  '
seo-title: 사용자 기반 대상 사전 요구 사항 및 고려 사항
solution: Audience Manager
title: 사전 요구 사항 및 고려 사항
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: d3184195d6a51ff013a3d1fc8526ca9afd3386c2
workflow-type: tm+mt
source-wordcount: '1015'
ht-degree: 3%

---


# 사전 요구 사항 및 고려 사항 {#prerequisites-considerations}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 권고사항이다. 법률 자문을 위해 법률 자문을 구할 수 있습니다.

[!UICONTROL People-Based Destinations]에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요는 아래를 참조하십시오.

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 문서를 자세히 읽어 보십시오.

## [!UICONTROL People-Based Destinations] {#signing-up} 등록

[!UICONTROL People-Based Destinations] 는 소셜 네트워크나 이메일 마케팅을 통해 고객을 타깃팅하여 사람 기반 환경에서 자사 고객 세그먼트를 활성화할 수 있도록 함으로써 Audience Manager 경험을 향상시키는 프리미엄 기능입니다.

이 프리미엄 기능을 활용하려면 Adobe 담당자에게 문의하십시오.

## 파트너별 사전 요구 사항 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

[!UICONTROL People-Based Destinations]을(를) 사용하여 자사 대상 [!UICONTROL segments]을(를) [!DNL Facebook]에 보내려면 먼저 다음 요구 사항을 충족해야 합니다.

1. 사용할 광고 계정에 대해 [!DNL Facebook] 사용자 계정에 **캠페인 관리 권한이 활성화되어 있어야 합니다.**
2. **Adobe Experience Cloud** 비즈니스 계정을 광고 파트너로 추가합니다. [!DNL Facebook Ad Account] `business ID=206617933627973`를 사용하십시오. 자세한 내용은 [비즈니스 관리자에 파트너 추가](https://www.facebook.com/business/help/1717412048538897)를 참조하십시오.
   >[!IMPORTANT]
   > Adobe Experience Cloud에 대한 권한을 구성할 때 **캠페인 관리 권한** 권한을 활성화해야 합니다. 이 단계는 [!UICONTROL People-Based Destinations] 통합에 필요합니다.
3. [!DNL Facebook Custom Audiences] 서비스 약관을 읽고 서명합니다. 이렇게 하려면 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`로 이동하십시오. 여기서 `accountID`는 [!DNL Facebook Ad Account ID]입니다.

### [!DNL LinkedIn] {#linkedin}

[!UICONTROL People-Based Destinations]을(를) 사용하여 자사 대상 세그먼트를 [!DNL LinkedIn]에 보내려면 먼저 [!DNL LinkedIn Campaign Manager] 계정에 [!DNL Creative Manager] 이상의 권한 수준이 있는지 확인하십시오.

[!DNL LinkedIn Campaign Manager] 사용자 권한을 편집하는 방법에 대한 자세한 내용은 LinkedIn 설명서의 [광고 계정에 대한 사용자 권한 추가, 편집 및 제거를 참조하십시오.](https://www.linkedin.com/help/lms/answer/5753)

비디오 지침은 [LinkedIn 사용자 기반 대상 이해 및 구성](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html)을 참조하십시오.

### [!DNL Google Customer Match] {#gcm}

[!UICONTROL People-Based Destinations]을(를) 사용하여 자사 대상 세그먼트를 [!DNL Google Customer Match] 대상으로 보내려면 먼저 [!DNL Google]이(가) 사용자를 해당 허용 목록에 추가해야 합니다.

[!DNL Google] 담당자에게 문의하고 [고객 일치 파트너 사용 설명서에 설명된 허용 목록 지침을 따라 데이터](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google] 문서를 업로드합니다.

이 프로세스가 완료되면 [!UICONTROL People-Based Destination]을(를) 만들 수 있습니다.

## 데이터 온보딩 {#data-onboarding}

현재 [!UICONTROL People-Based Destinations]에 대한 데이터 수집은 일괄 전송당 하나의 고객 ID([!DNL CRM ID])에 연결된 최대 10개의 해시된 이메일 주소를 지원합니다. 하나의 고객 ID에 연결된 해시된 이메일 주소를 10개 이상 업로드하면 Audience Manager이 10개의 이메일 주소를 특정 순서대로 인제스트합니다.

여러 일괄 전송에서 하나의 고객 ID에 연결된 10개 이상의 해시된 이메일 주소를 업로드하면 Audience Manager이 최근에 추가된 10개의 이메일 주소를 유지합니다.

## 데이터 개인 정보{#data-privacy}

[!UICONTROL People-Based Destinations]을(를) 사용하면 사용자가 업로드한 해시된 이메일 주소를 기반으로 대상을 타게팅할 수 있지만, 직접 식별 가능한 방문자 정보를 Audience Manager에 업로드할 수 없는 상태로 남아 있습니다. 데이터 온보딩 단계에서 사용하려는 이메일 주소가 [!DNL SHA256] 알고리즘으로 해시되었는지 확인해야 합니다. 그렇지 않으면 [!UICONTROL People-Based Destinations]에서 사용할 수 없습니다.

## 데이터 해싱 대 암호화 {#data-hashing-encryption}

암호화는 양방향 함수입니다. 또한 올바른 암호 해독 키를 사용하여 암호화된 정보를 해독할 수 있습니다. 암호화된 형식의 개인 식별 정보가 해독될 수 있으므로 Audience Manager의 컨텍스트에서 데이터를 암호화하면 심각한 위험이 발생합니다. 암호화에 비해 [!UICONTROL People-Based Destinations]은 해시된 데이터를 대신 사용하도록 설계되었습니다.

해싱은 고유한 결과를 만들기 위해 입력을 스크램빙하는 단방향 함수입니다. [!DNL SHA256]와 같은 적절한 해싱 알고리즘을 사용하면 해싱 기능을 역동적으로 수행하고 스크램블되지 않은 정보를 표시할 방법이 없습니다. Audience Manager에 내장할 이메일 주소는 [!DNL SHA256] 알고리즘으로 해시되어야 합니다. 이렇게 하면 해시되지 않은 이메일 주소가 Audience Manager에 도달하지 않도록 할 수 있습니다.

## 해싱 요구 사항 {#hashing-requirements}

이메일 주소를 붙여넣을 때는 다음 요구 사항을 준수해야 합니다.

* 이메일 문자열에서 모든 선행 및 후행 공백을 트리밍합니다.예:`johndoe@example.com`;`<space>johndoe@example.com<space>`
* 이메일 문자열을 해싱할 때는 소문자 문자열을 해시해야 합니다.
   * 예:`example@email.com`;`EXAMPLE@EMAIL.COM`
* 해시된 문자열이 모두 소문자인지 확인하십시오.
   * 예:`55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`;`55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`
* 끈에 소금을 치지 마라.

[!UICONTROL People-Based Destinations]의 해싱 요구 사항을 이해하려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud은 [!DNL Adobe Experience Platform Identity Service (ECID)]을 통해 고객 ID를 해시할 수 있는 옵션을 제공합니다. ECID를 사용하여 고객 ID를 해시하는 방법에 대한 자세한 내용은 [SHA256 setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html)에 대한 해싱 지원을 참조하십시오.

## 사용자 권한 얻기 {#obtaining-user-permission}

[!UICONTROL People-Based Destinations]은(는) 사람 기반 채널에서 자사 고객 데이터를 활성화하는 데 도움이 되므로, 광고 또는 기타 목적으로 자사 데이터를 어떻게 사용할지를 고객에게 알리고 필요한 동의를 얻어야 합니다.

[!UICONTROL People-Based Destinations]에 등록하기 전에 광고 목적으로 고객의 정보를 사용하기 전에 고객의 동의를 받아야 합니다.

고객이 광고 캠페인 수신을 거부하려는 경우 Audience Manager의 데이터 수집을 중지하는 방법에 대한 자세한 내용은 [옵트아웃 관리](../../overview/data-security-and-privacy/data-privacy-requests.md)를 참조하십시오.

## 퍼스트 파티 데이터 활성화 구현 {#enforcing-first-party-activation}

[!UICONTROL People-Based Destinations]을(를) 사용하는 경우 자사 데이터만 사용하여 사람 기반 채널에서 대상 세그먼트를 활성화할 수 있습니다. 사람 기반 채널에서 고객 활성화를 위해 제2자 또는 제3자 데이터를 사용할 수 없습니다.

[!UICONTROL People-Based Destinations]을(를) 사용하는 경우 대상 플랫폼 및 데이터 공급자의 지침 및 요구 사항에 따라 [데이터 내보내기 컨트롤](../data-export-controls.md)을 사용하여 [!UICONTROL data sources] 및 [!UICONTROL destinations]에 레이블을 지정합니다.

## 선언된 ID 타게팅 {#onboard-authenticated-declared-id}을(를) 통해 인증된 해시 ID 온딩

[!UICONTROL People-Based Destinations]용으로 오프라인 데이터를 Audience Manager에 가져올 수 있는 방법에는 두 가지가 있습니다.

* [해시된 이메일 ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 주소를 인제스트하는 배치 데이터 Audience Manager을 전송합니다. 이 방법을 사용하면 [!UICONTROL People-Based Destinations]의 [!DNL CRM] 데이터베이스에서 해시된 이메일 주소를 사용하도록 선택할 수 있습니다. 또한 이 방법을 사용할 때 [온보드 tries](../traits/trait-and-segment-qualification-reference.md)에 대해 해시된 이메일 주소를 사용할 수도 있습니다.
* 인증된 고객 ID를 전달할 때 [선언된 ID](../declared-ids.md)를 사용하여 해시된 이메일 주소를 선언합니다. 이 방법을 사용할 때 Audience Manager은 사용자를 대신하여 온라인으로 인증된 사용자의 해시된 이메일 주소만 [!UICONTROL People-Based Destinations]에게 보냅니다. 사람 기반 채널을 통해 활성화되는 이메일 주소는 선언된 ID 이벤트 호출의 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 전송되지 않습니다.
