---
description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-title: IAB TCF를 위한 Audience Manager 플러그인
solution: Audience Manager
title: IAB TCF를 위한 Audience Manager 플러그인
feature: 데이터 거버넌스 및 개인 정보 보호
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 40%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## 개요

사용자에게 부여할 수 있는 개인정보 보호 책임의 중요한 관점은 개인 데이터를 어떻게 사용할 수 있는지(예를 들어, &quot;목적&quot;) 및 누가(예를 들어, &quot;회사&quot;) 보다 사용자 선택을 누가 취득하고 운반하는 것입니다.

Adobe는 [옵트인 기능](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/optin-overview.html) 및 [IAB 투명성 및 동의 프레임워크(TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다.

이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.

>[!IMPORTANT]
>
>Audience Manager이 공급업체 ID 565와 함께 [IAB TCF](https://iabeurope.eu/tcf-for-vendors/)에 등록되었습니다.

IAB TCF용 Audience Manager 플러그인은 [옵트인 기능](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/iab.html)을 활용하며, 이 기능은 결과적으로 [ ECID(Experience Platform Identity Service)](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html) 라이브러리의 일부입니다.

## 범위 및 제한 사항 {#scope-and-limitations}

Audience Manager를 사용하는 게시자 또는 광고주는 IAB TCF에 따라 Audience Manager에 사용자 선택 사항을 전달할 수 있습니다.

>[!IMPORTANT]
>
>IAB TCF 규정은 유럽 경제 구역에 있는 방문자에게만 적용됩니다.

Audience Manager은 사용자의 개인 정보 보호 선택 사항을 존중하도록 지원하고 사용자가 함께 일하는 모든 파트너에게 이러한 선택 사항을 쉽게 전달할 수 있는 방법을 제공합니다.

현재 Audience Manager는 다음 사항을 지원하지 않습니다.

* 모바일 장치 워크플로우
* 세그먼트 내보내기에 동의 추가

## Insight [!DNL IAB TCF v2.0] {#upgrading}

[!DNL Audience Manager Plug-in for IAB TCF] 구현을 [!DNL IAB TCF] v1.1에서 [!DNL IAB TCF] v2.0으로 업그레이드하거나 처음으로 [!DNL IAB TCF] v2.0을 활성화하는 고객은 아래 설명된 대로 사전 요구 사항 및 구현에 대한 동일한 지침을 따라야 합니다.

## 사전 요구 사항 {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager은 IAB TCF v2.0을 지원합니다.
>
>IAB TCF v1.1 지원은 2020년 8월 15일에 종료됩니다.
>
> 동의 관리를 위해 IAB TCF용 Audience Manager 플러그인을 계속 사용하려면 지속적인 지원을 위해 최신 버전의 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)로 업그레이드해야 합니다.
>
> 최신 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 버전으로 업그레이드한 후 IAB TCF v1.1 동의 문자열은 더 이상 지원되지 않으므로 최신 ECID 버전으로 업그레이드하기 전에 CMP를 업데이트해야 합니다.

Audience Manager이 있는 IAB TCF용 Audience Manager 플러그인을 사용하려면 다음 사전 요구 사항을 충족해야 합니다.

1. Adobe ECID(Experience Platform Identity Service) 버전 5 이상을 사용해야 합니다. 최신 ECID 릴리스를 [다운로드](https://github.com/Adobe-Marketing-Cloud/id-service/releases)하십시오.
2. [여기](https://github.com/Adobe-Marketing-Cloud/dil/releases)에서 다운로드할 수 있는 Audience Manager [!DNL Data Integration Library](DIL) 버전 9.0 이상을 사용해야 합니다. [Audience Manager 설명서에서 DIL](../../dil/dil-overview.md)에 대해 알아보십시오. Audience Manager의 가장 쉬운 DIL 구현은 [Adobe 시작](https://docs.adobe.com/content/help/ko-KR/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html)을 사용하는 것이 좋습니다.
3. 또는 [!DNL Server-Side Forwarding](SSF)을 사용하여 데이터를 Audience Manager으로 가져오는 경우 최신 버전의 AppMeasurement로 업그레이드해야 합니다. [Analytics 코드 관리자](https://docs.adobe.com/content/help/ko-KR/analytics/admin/admin-tools/code-manager-admin.html)를 사용하여 AppMeasurement를 다운로드합니다.
4. IAB TCF v2.0과 통합되고 IAB TCF에 등록되어 있는 CMP(Consent Management Platform) 또는 자체 CMP(Consent Management Platform)를 사용해야 합니다. [IAB 프레임워크 내에 등록된 CMP](https://iabeurope.eu/cmp-list/) 목록을 참조하십시오.

>[!WARNING]
>
>IAB TCF v.2.0을 지원하지 않는 동의 관리 플랫폼(CMP)을 사용하는 경우, Audience Manager은 방문자가 유럽 연합(EU)에 있더라도 ID 동기화에서 `gdpr=0` 매개 변수를 자동으로 전송합니다. GDPR 유효성 검사가 활성 상태인지 확인하려면 CMP(Consent Management Platform)에서 IAB TCF v2.0을 지원하는지 확인하는 것이 좋습니다.

## 권장 사항 및 구현 방법 {#recommendations}

Audience Manager에서 IAB TCF 지원을 활성화하려면 [옵트인으로 IAB를 설정하는 방법](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)에 대한 설명서를 참조하십시오.

이렇게 할 수 있는 가장 쉬운 방법은 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html)을 사용하여 속성에 [!DNL ECID Opt-in]를 추가하는 것입니다. Launch 확장을 설정하는 방법을 알려면 [ECID 옵트인 확장](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)에 대한 설명서를 읽어 보십시오.

## IAB 프레임워크 사용 시 사용자 선택 워크플로우 {#user-choice-workflow}

웹 자산을 방문할 때 사용자는 게시자 및 게시자가 작업에 사용하는 타사 공급업체의 데이터 사용 방법에 대한 선택 사항을 제공할 수 있습니다.

사용자는 글로벌 공급업체 목록에 등록된 *제3자 공급업체*&#x200B;에 IAB를 목적으로 *동의* 및 *합법적인 관심* 형식으로 선택 항목을 제공합니다.

아래 이미지는 어떤 웹 사이트를 처음 방문하는 사람에게 표시되는 CMP 대화 상자의 예를 나타냅니다. 고객 구현에 따라 이 대화 상자가 매우 다르게 보일 수 있음을 명심하십시오.

![CMP 대화 상자](assets/cmp-example.png)

IAB TCF v2.0에 포함된 다양한 목적과 권한에 대한 세부 사항은 [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)에서 다룹니다.

사용자는 목적과 공급업체의 조합을 위해 자신의 동의 또는 정당한 관심 사항을 부여할 수 있습니다(가능한 경우). 예를 들어, 사용자는 장치에 정보를 저장하고, 제품을 개발 및 개선하며, CMP를 통해 표시되는 모든 제3자 업체에 동의한다는 것에 대해 동의해야 합니다.

또는, 다른 예로, 그들은 모든 목적을 위해 그들의 동의 또는 합법적인 이익을 부여할 수 있지만, CMP에 의해 표시된 몇몇 공급업체의 동의 또는 정당한 이익만을 부여할 수 있습니다.

사용자가 개인 정보 선택을 선택하면 사용자 선택 사항이 IAB TC 문자열에 기록됩니다. IAB TC 문자열은 승인된 목적 및 공급업체의 조합과 기타 메타데이터 정보를 저장합니다(자세한 내용은 [IAB 페이지](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) 참조).

IAB TCF에 등록된 모든 공급업체는 IAB TC 문자열을 평가하고 사용자의 개인 정보 보호 선택 사항에 따라 결정을 합니다. 사용자의 개인 정보 보호 선택 사항은 IAB TCF에 등록된 모든 벤더에서 유효합니다.

## Audience Manager {#aam-standard-purposes}에 필요한 목적

Audience Manager은 [IAB 유럽 투명도 및 동의 프레임워크 정책](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions)에 정의된 목적에 따라 IAB TC 문자열에 저장된 사용자 선택을 평가합니다.

* **목적 1**:장치에 정보 저장 및/또는 액세스;
* **목적 10**:제품 개발 및 개선;
* **특수 목적 1**:보안 유지, 사기 방지 및 디버그

>[!IMPORTANT]
>
>쿠키를 배포하고 ID 동기화를 시작 또는 수행하기 위해 Audience Manager은 목적 1 및 목적 10에 대한 동의와 공급업체의 동의도 필요합니다.
>
>[IAB 규정](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)에 따라, 특수 목적 1(보안 보장, 사기 방지 및 디버그)은 항상 동의되며 사용자는 이에 반대할 수 없습니다.

## Audience Manager 행동은 사용자가 동의하는지 여부에 따라 달라집니다 {#aam-behavior-consent}

Audience Manager은 IAB TC 문자열에 사용자 동의(장치에 대한 정보 저장 및/또는 액세스, 제품 개발 및 개선)가 포함되는지 여부에 따라 다르게 작동합니다.

또한 Audience Manager에서 근무하는 모든 대상에 대한 사용자 동의도 확인하며, 해당 대상이 IAB TCF에 등록되어 있는 경우 이에 동의합니다.

| 사용자가 *동의하면* Audience Manager는 | 사용자의 동의를 *거부하면* Audience Manager는 |
|---|---|
| <ul><li>요청하신 모든 Audience Manager 사용 사례를 수행합니다.</li><li>ID 동기화 시 (ID 동기화 호출에서 `gdpr = 1` 및 동의 문자열을 `gdpr_consent` 로 전달하여) 제3자에게 동의를 전달합니다.</li><li>광고 서버 픽셀에서 전달된 동의를 평가하고 적용합니다.</li><li>파트너가 시작한 ID 동기화를 수행합니다.</li></ul> | <ul><li>인스턴스에서 새 사용자 데이터를 저장하지 않습니다. 여기에는 파트너 ID, 신호, 트레이트 또는 픽셀 데이터가 포함됩니다.</li><li>타사 ID 동기화를 시작하지 않습니다.</li><li>파트너가 시작한 ID 동기화를 수행하지 않습니다.</li><li>추가 데이터 수집에서 사용자를 옵트아웃합니다.</li></ul> |

## 게시자 사용 사례 {#publisher-use-case}

IAB TCF용 Audience Manager 플러그인을 구현함으로써, Adobe 또는 다른 제3자 공급업체의 다른 메커니즘을 통해 웹 속성에서 동의 관리를 위한 사용자 정의 코드를 유지 관리할 필요가 없습니다. 사용 사례는 이미지와 아래 단계에 설명되어 있습니다. 이미지의 왼쪽에서 시작하십시오.

1. 사용자가 웹 자산 중 하나를 방문합니다. 최신 버전의 ECID 및 DIL 라이브러리([사전 요구 사항](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites) 참조)를 사용하는 한 옵트인 플로우가 트리거됩니다.
2. Audience Manager가 IAB 플로우가 적용되는지(`isIabContext=true`) 확인합니다. [권장 사항 및 구현 방법](aam-iab-plugin.md#recommendations)을 참조하십시오.
3. Audience Manager은 GDPR이 웹 속성에 적용되는지(`gdpr = 1`) 및 IAB TCF에 등록된 CMP가 있는지 여부를 확인합니다. 예를 들어, 유럽 연합에서 방문하는 사용자에게 적용됩니다. GDPR 플래그를 설정하는 것은 게시자의 책임입니다.
4. GDPR이 적용되는 경우 Audience Manager은 필요한 동의를 위해 `gdpr_consent` 매개 변수에 전달된 IAB TC 문자열을 확인합니다. Audience Manager은 장치에 정보를 저장 및/또는 액세스하는 경우([IAB TCF 목적 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), 제품을 개발 및 개선하는 행위([IAB TCF 목적 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), 데이터를 저장, 처리 또는 활성화하는 Audience Manager 공급업체 동의 등의 동의를 받아야 합니다.
5. IAB TC 문자열이 존재하며 필수 동의가 포함된 경우, Audience Manager은 IAB TC 문자열을 [데이터 수집 서버](../../reference/system-components/components-data-collection.md)(DCS)에 전달합니다.
6. Audience Manager은 브라우저에 [demdex 쿠키](https://docs.adobe.com/content/help/ko-KR/core-services/interface/ec-cookies/cookies-am.html)를 설정하여 응답하고 제3자 ID 동기화를 시작하고 적용합니다.
7. 또는 4단계에서 전달된 IAB TC 문자열에 필요한 모든 권한이 포함되어 있지 않은 경우 Audience Manager은 사용자 데이터를 수집, 처리 또는 활성화하지 않으며 ID 동기화를 해제하거나 시작하지 않습니다. 또한 사용자가 함께 일하는 대상에서 사용자를 옵트아웃합니다.

>[!IMPORTANT]
>
>IAB TCF 매개 변수가 필요한 Audience Manager 대상 파트너와 협력하고 있지만 웹 사이트에서 IAB TCF를 지원하는 CMP가 없는 경우 Audience Manager은 ID 동기화에서 `gdpr=0`을 보냅니다. 따라서 GDPR은 해당 사용자에게는 적용되지 않습니다.
>
> 이 옵션을 원하지 않으면 Audience Manager에서 IAB TCF 기능을 활성화하여 적절한 IAB TC 문자열을 대상 파트너에게 보내야 합니다.



![게시자 사용 사례](assets/publisher-use-case.png)

## 광고주 사용 사례 {#advertiser-use-case}

Audience Manager는 IAB TCF에 따라 [픽셀 호출](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)에서 전달된 동의를 평가하고 수행합니다.

Audience Manager 고객이 파트너 페이지에서 픽셀을 배치하거나 광고 응답에 포함할 광고 서버에 픽셀을 배치할 수 있습니다. 첫 번째 경우, 파트너는 실행 전에 프로그래밍 방식으로 동의 매개 변수를 검색하고 픽셀에 추가해야 합니다. 보다 일반적이며 아래에 자세히 설명되어 있는 두 번째 경우에는 광고 서버가 SSP(공급측 플랫폼)나 게시자 광고 서버로부터 받는 동의 매개 변수를 모든 픽셀에 추가합니다.

Audience Manager는 두 개의 매개 변수를 사용하여 픽셀 호출로 사용자 동의를 전달합니다.

* `gdpr`은 0(GDPR이 적용되지 않음) 또는 1(GDPR이 적용됨)일 수 있습니다.
* `gdpr_consent`는 URL이 안전한 base64로 인코딩된 GDPR 동의 문자열입니다([사양](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) 참조). 두 매개 변수가 있는 노출 픽셀에 대한 샘플 호출의 모습은 다음과 같을 수 있습니다.

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

사용 사례는 이미지와 아래 단계에 설명되어 있습니다. 이미지의 왼쪽에서 시작하십시오.

1. 사용자는 광고 서버를 통해 광고에 노출됩니다. 이는 DCS(데이터 수집 서버)에 대한 [픽셀 호출](../../integration/media-data-integration/impression-data-pixels.md)으로 변환됩니다.
2. Audience Manager가 GDPR 플래그가 적용되는지 확인합니다. 그렇지 않은 경우 Audience Manager은 `gdpr` 및 `gdpr_consent` 변수에 전달된 데이터를 픽셀 호출에 저장합니다.
3. IAB TC 문자열이 있고 필요한 권한이 포함되어 있으면 Audience Manager은 `gdpr` 및 `gdpr_consent` 변수에 전달된 데이터를 픽셀 호출에 저장합니다.
4. IAB TC 문자열이 없거나 필요한 권한이 없는 경우 Audience Manager은 픽셀 호출에서 `gdpr` 및 `gdpr_consent` 변수에 전달된 데이터를 삭제합니다.

![광고주 사용 사례](assets/advertiser-use-case.png)

## IAB TCF를 지원하는 활성화 파트너 {#aam-activation-partners}

IAB TCF용 Audience Manager 플러그인을 사용하면 사용자의 개인 정보 보호 선택 사항을 준수하면서 IAB TC 문자열을 활성화 파트너에게 전달할 수 있습니다. IAB TCF를 지원하는 활성화 파트너에 대한 자세한 내용은 [장치 기반 대상 목록](/help/using/features/destinations/device-based-destinations-list.md)을 참조하십시오.

## URL 대상에 전송된 URL에 동의 추가

IAB TCF v2.0과의 Audience Manager 통합은 IAB TCF v2.0과 통합된 [URL 대상](../../features/destinations/create-url-destination.md)에 전송된 정보에 대한 동의 추가를 지원합니다. 그러나 이 프로세스는 특정 URL 형식이 손상되지 않도록 Audience Manager에 의해 자동으로 수행되지 않습니다.

[!DNL URL destinations]에 전송된 데이터에 동의하기를 원하는 고객은 URL 형식에 `${GDPR}` 및 `${GDPR_CONSENT_XXXX}` 매크로를 수동으로 추가해야 하며 `XXXX`을(를) 대상 파트너 ID로 교체해야 합니다.

예: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

지원되는 대상 매크로에 대한 자세한 내용은 [정의된 대상 매크로](../../features/destinations/destination-macros.md)를 참조하십시오.

## 상호 장치 동의 관리

IAB TCF용 Audience Manager 플러그인은 사이트 방문자가 적절한 권한을 제공하지 않을 때 요청에 있는 ID를 자동으로 거부합니다. 요청에 [상호 장치 ID(CRM ID)](../../reference/ids-in-aam.md)가 포함되어 있는 경우 Audience Manager은 해당 [상호 장치 ID(CRM ID)](../../reference/ids-in-aam.md)에 연결된 마지막 장치와 함께 ID를 옵트아웃합니다.

## IAB 구현 테스트 {#test-iab-implementation}

IAB TCF용 Audience Manager 플러그인을 올바르게 구현했는지 테스트하려면, 옵트인 서비스 유효성 검사 중 [사용 사례 4](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)를 읽어 보십시오.

## Audience Manager의 IAB 및 옵트아웃. 우선순위. {#iab-and-optout}

사용자가 원하는 대로 선택할 수 있는 또 다른 개인 정보 보호 옵션은 모든 데이터 수집을 옵트아웃하는 기능입니다. Adobe에서는 [개인 정보 보호 선택 사항](https://www.adobe.com/kr/privacy/opt-out.html#customeruse) 페이지 내에서 사용자에게 그렇게 하는 방법을 제공합니다.

Audience Manager는 [설명서의 별도 문서](data-privacy-requests.md#opt-out-requests)에서 옵트아웃 요청을 해결합니다.

>[!IMPORTANT]
>
>동의 거부 후 모든 데이터 수집을 옵트아웃한 사용자는 다시 옵트인할 수 없습니다.

>[!NOTE]
>
>**우선순위** - 사용자가 위의 링크에 설명된 대로 글로벌 옵트아웃 도구를 사용하여 데이터 수집을 옵트아웃하는 경우 이것은 옵트인 및 IAB 유효성 확인보다 우선합니다.

## 추가 리소스 {#additional-resources}

* [Adobe Experience Platform ID 서비스 옵트인](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 유럽 GDPR 투명성 및 동의 프레임워크](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 유럽 GDPR 투명성 및 동의 프레임워크 기술 사양](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 플러그인 - 비디오 데모](https://helpx.adobe.com/kr/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)