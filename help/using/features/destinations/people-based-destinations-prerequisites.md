---
description: '사용자 기반 대상에 등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요를 알려면 아래 문서를 참조하십시오.  '
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: 사전 요구 사항 및 고려 사항
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# 사전 요구 사항 및 고려 사항 {#prerequisites-considerations}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떤 것도 법률적인 조언이 아닙니다. 법률 자문을 구하시려면 법률 자문을 구하십시오.

등록하기 전에 충족해야 하는 고객 요구 사항에 대한 개요를 알려면 아래 문서를 참조하십시오 [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> 구현 단계로 이동하기 전에 이 문서를 자세히 살펴보십시오.

## 등록 [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] 는 소셜 네트워크에서 사용자 지정된 오퍼로 대상을 타깃팅하거나 이메일 마케팅을 통해 사람 기반 환경에서 자사 대상 세그먼트를 활성화하여 Audience Manager 경험을 향상시키는 프리미엄 기능입니다.

이 프리미엄 기능을 활용하려면 Adobe 담당자에게 문의하십시오.

## 파트너별 사전 요구 사항 {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

를 사용하기 전에 [!UICONTROL People-Based Destinations] 자사 대상을 보내려면 [!UICONTROL segments] to [!DNL Facebook]를 채울 때는 다음 요구 사항을 충족하는지 확인하십시오.

1. 사용자 [!DNL Facebook] 사용자 계정에는 **캠페인 관리** 사용하려는 광고 계정에 대해 사용 권한이 활성화되었습니다.
2. 추가 **Adobe Experience Cloud** 귀사의 광고 파트너로서 비즈니스 계정 [!DNL Facebook Ad Account]. `business ID=206617933627973`를 사용하십시오. 자세한 내용은 [비즈니스 관리자에 파트너 추가](https://www.facebook.com/business/help/1717412048538897) 자세한 내용
   >[!IMPORTANT]
   > Adobe Experience Cloud에 대한 권한을 구성할 때 **캠페인 관리** 권한. 이 단계는 [!UICONTROL People-Based Destinations] 통합에 필요합니다.
3. 읽기 및 서명 [!DNL Facebook Custom Audiences] 서비스 약관. 이렇게 하려면 `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`로 이동하십시오. 여기서 `accountID`는 [!DNL Facebook Ad Account ID]입니다.

### [!DNL LinkedIn] {#linkedin}

를 사용하기 전에 [!UICONTROL People-Based Destinations] 자사 대상 세그먼트를 [!DNL LinkedIn], [!DNL LinkedIn Campaign Manager] 계정에 [!DNL Creative Manager] 또는 더 높은 권한 수준.

편집 방법을 배우려면 [!DNL LinkedIn Campaign Manager] 사용자 권한 [광고 계정에 대한 사용자 권한 추가, 편집 및 제거](https://www.linkedin.com/help/lms/answer/5753) ( LinkedIn 설명서)를 참조하십시오.

자세한 내용은 [LinkedIn 사용자 기반 대상 이해 및 구성](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) 참조하십시오.

### [!DNL Google Customer Match] {#gcm}

를 사용하기 전에 [!UICONTROL People-Based Destinations] 자사 대상 세그먼트를 [!DNL Google Customer Match] 대상을 사용할 때는 Google의 정책을 읽고 따라야 합니다 [!DNL Customer Match]에 요약된 [Google 지원 설명서](https://support.google.com/google-ads/answer/6299717).

다음으로, [!DNL Google] 계정이 [!DNL Standard] 또는 더 높은 권한 수준. 자세한 내용은 [Google 광고 설명서](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) 자세한 내용

준수 계정이 있는 고객은 Google에 의해 자동으로 나열될 수 있습니다.

## 데이터 온보딩 {#data-onboarding}

데이터 수집 [!UICONTROL People-Based Destinations] 현재 은 한 개의 고객 ID( )에 연결된 최대 10개의 해시된 이메일 주소를 지원합니다[!DNL CRM ID]), 배치 전송당. 하나의 고객 ID에 연결된 해시된 이메일 주소를 10개 이상 업로드하면 Audience Manager이 특정 순서로 10개를 섭취하게 됩니다.

여러 배치 전송에서 하나의 고객 ID에 연결된 10개 이상의 해시된 이메일 주소를 업로드하면 Audience Manager이 추가된 가장 최근 10개의 이메일 주소를 유지합니다.

## 데이터 개인 정보 {#data-privacy}

하지만 [!UICONTROL People-Based Destinations] 업로드한 해시된 이메일 주소를 기반으로 대상을 타깃팅할 수 있도록 허용하면, 직접 식별 가능한 방문자 정보를 Audience Manager에 업로드할 수 없습니다. 데이터 온보딩 단계에서 사용하려는 이메일 주소가 과 함께 해시되었는지 확인해야 합니다. [!DNL SHA256] 알고리즘에 대해 설명합니다. 그렇지 않으면 를 사용할 수 없습니다 [!UICONTROL People-Based Destinations].

## 데이터 해싱 및 암호화 {#data-hashing-encryption}

암호화는 양방향 기능입니다. 암호화된 모든 정보는 올바른 암호 해독 키를 사용하여 해독할 수도 있습니다. Audience Manager의 컨텍스트에서 데이터를 암호화하는 것은 개인 식별 정보의 암호화된 형태를 해독할 수도 있으므로 심각한 위험을 발생시킵니다. 암호화와 대조적으로 [!UICONTROL People-Based Destinations] 은 대신 해시된 데이터로 작동하도록 디자인되었습니다.

해싱은 입력을 스크램블하여 고유한 결과를 생성하는 단방향 함수입니다. 과 같은 적절한 해시 알고리즘을 사용하여 [!DNL SHA256]를 설정하는 경우 해싱 함수를 역변환하여 스크램블되지 않은 정보를 표시할 방법이 없습니다. Audience Manager에 온보딩할 이메일 주소는 와 함께 해시해야 합니다. [!DNL SHA256] 알고리즘에 대해 설명합니다. 이렇게 하면 해시되지 않은 이메일 주소가 Audience Manager에 도달하지 않도록 할 수 있습니다.

## 해시 요구 사항 {#hashing-requirements}

이메일 주소를 해싱할 때는 다음 요구 사항을 충족하는지 확인하십시오.

* 전자 메일 문자열에서 선행 및 후행 공백을 모두 잘라냅니다. 예: `johndoe@example.com`, 아님 `<space>johndoe@example.com<space>`;
* 이메일 문자열을 해시할 때는 소문자 문자열을 해시해야 합니다.
   * 예: `example@email.com`, 아님 `EXAMPLE@EMAIL.COM`;
* 해시된 문자열이 모두 소문자로 되어 있는지 확인하십시오
   * 예: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, 아님 `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* 문자열의 소금을 치지 마십시오.

의 해시 요구 사항을 이해하려면 아래 비디오를 시청하십시오. [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud은 다음을 통해 고객 ID를 해시할 수 있는 옵션을 제공합니다. [!DNL Adobe Experience Platform Identity Service (ECID)]. 자세한 내용은 [setCustomerIDs에 대한 SHA256 해시 지원](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) ecid를 사용하여 고객 ID를 해시하는 방법에 대한 자세한 정보.

## 사용자 권한 얻기 {#obtaining-user-permission}

이후 [!UICONTROL People-Based Destinations] 은 사용자 기반 채널에서 자사 대상 데이터를 활성화하는 데 도움이 되며, 광고 또는 기타 용도로 데이터를 사용하는 방법에 대해 고객에게 알리고 필요한 동의를 받아야 합니다.

등록하기 전에 [!UICONTROL People-Based Destinations], 광고 목적으로 해당 정보를 사용하기 전에 고객의 동의를 받아야 합니다.

고객이 광고 캠페인을 옵트아웃하려는 경우 [옵트아웃 관리](../../overview/data-security-and-privacy/data-privacy-requests.md) Audience Manager이 더 이상 데이터를 수집하지 않도록 하는 방법에 대한 자세한 내용을 참조하십시오.

## 자사 데이터 활성화 적용 {#enforcing-first-party-activation}

사용 시 [!UICONTROL People-Based Destinations]에서는 자사 데이터만 사용하여 사용자 기반 채널에서 대상 세그먼트를 활성화할 수 있습니다. 사용자 기반 채널에서 대상 활성화를 위해 제2자 데이터 또는 타사 데이터를 사용할 수 없습니다.

사용 시 [!UICONTROL People-Based Destinations], 사용 [데이터 내보내기 제어](../data-export-controls.md) 레이블을 지정하려면 [!UICONTROL data sources] 및 [!UICONTROL destinations] 대상 플랫폼 및 데이터 공급자의 지침 및 요구 사항에 따라 다음을 수행합니다.

## 선언된 ID 타깃팅을 통해 인증된 해시된 ID 온보딩 {#onboard-authenticated-declared-id}

[!UICONTROL People-Based Destinations]용으로 오프라인 데이터를 Audience Manager에 가져올 수 있는 방법에는 두 가지가 있습니다.

* [배치 데이터 보내기](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) 해시된 이메일 주소를 수집할 Audience Manager. 이 방법을 사용하면 사용자의 [!DNL CRM] 데이터베이스 [!UICONTROL People-Based Destinations]. 또한 이 방법을 사용할 때 해시된 이메일 주소를 [온보드 트레이트](../traits/trait-and-segment-qualification-reference.md).
* 사용 [선언된 ID](../declared-ids.md) 인증된 고객 ID를 전달할 때 해시된 이메일 주소를 선언하려면 . 이 방법을 사용할 때 Audience Manager은 사용자를 대신하여 에만 전송됩니다 [!UICONTROL People-Based Destinations] 온라인에서 인증된 사용자의 해시된 이메일 주소입니다. 사용자 기반 채널을 통해 활성화된 이메일 주소는 선언된 ID 이벤트 호출에 있는 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 전송되지 않습니다.
