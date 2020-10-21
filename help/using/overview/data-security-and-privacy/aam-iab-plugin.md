---
description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-title: IAB TCF를 위한 Audience Manager 플러그인
solution: Audience Manager
title: IAB TCF를 위한 Audience Manager 플러그인
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '2449'
ht-degree: 40%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## 개요

사용자에게 부여할 수 있는 개인정보 보호 의무의 중요한 부분은 개인 데이터가 어떻게 사용될 수 있는지(예를 들어, &quot;목적&quot;) 및 누가 (예를 들어, &quot;회사&quot;)에 대한 사용자 선택 사항을 획득하고 전달하는 것입니다.

Adobe는 [옵트인 기능](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/optin-overview.html) 및 [IAB 투명성 및 동의 프레임워크(TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다.

이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.

>[!IMPORTANT]
>
>Audience Manager is registered in the [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) with the vendor ID 565.

IAB TCF용 Audience Manager 플러그인은 [옵트인 기능](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/iab.html)을 활용하며, 이 기능은 결과적으로 [ ECID(Experience Platform Identity Service)](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html) 라이브러리의 일부입니다.

## 범위 및 제한 사항 {#scope-and-limitations}

Audience Manager를 사용하는 게시자 또는 광고주는 IAB TCF에 따라 Audience Manager에 사용자 선택 사항을 전달할 수 있습니다.

>[!IMPORTANT]
>
>IAB TCF 규정은 유럽 경제 구역에 있는 방문자에게만 적용됩니다.

Audience Manager은 사용자의 개인 정보 보호 선택 사항을 존중하고 함께 일하는 모든 파트너에게 이러한 선택 사항을 쉽게 전달할 수 있는 방법을 제공합니다.

현재 Audience Manager는 다음 사항을 지원하지 않습니다.

* 모바일 장치 워크플로우
* 세그먼트 내보내기에 동의 추가

## Insight [!DNL IAB TCF v2.0] {#upgrading}

구현을 [!DNL Audience Manager Plug-in for IAB TCF] v1.1에서 [!DNL IAB TCF] v2.0으로 업그레이드하거나 [!DNL IAB TCF] [!DNL IAB TCF] v2.0을 처음으로 활성화하는 고객은 아래 설명된 전제 조건 및 구현과 동일한 지침을 따라야 합니다.

## 사전 요구 사항 {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager은 IAB TCF v2.0을 지원합니다.
>
>IAB TCF v1.1 지원은 2020년 8월 15일에 종료됩니다.
>
> 동의 관리를 위해 IAB TCF용 Audience Manager 플러그인을 계속 사용하고자 하는 고객은 지속적인 지원을 위해 최신 버전의 [ECID로](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 업그레이드해야 합니다.
>
> 최신 [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) 버전으로 업그레이드한 후 IAB TCF v1.1 동의 문자열은 더 이상 지원되지 않으므로 최신 ECID 버전으로 업그레이드하기 전에 CMP를 업데이트해야 합니다.

Audience Manager이 있는 IAB TCF용 Audience Manager 플러그인을 사용하려면 다음 사전 요구 사항을 충족해야 합니다.

1. Adobe ECID(Experience Platform Identity Service) 버전 5 이상을 사용해야 합니다. 최신 ECID 릴리스를 [다운로드](https://github.com/Adobe-Marketing-Cloud/id-service/releases)하십시오.
2. You must be using Audience Manager [!DNL Data Integration Library] (DIL) version 9.0 or newer, downloadable from [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). [Audience Manager 설명서에서 DIL](../..//dil/dil-overview.md)에 대해 알아보십시오. Audience Manager에 대한 가장 손쉬운 DIL 구현을 위해 [Adobe](https://docs.adobe.com/content/help/ko-KR/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) 론치를 사용하는 것이 좋습니다.
3. Alternatively, if you use [!DNL Server-Side Forwarding] (SSF) to import data into Audience Manager, you must upgrade to the latest version of AppMeasurement. [Analytics 코드 관리자](https://docs.adobe.com/content/help/ko-KR/analytics/admin/admin-tools/code-manager-admin.html)를 사용하여 AppMeasurement를 다운로드합니다.
4. 귀하는 IAB TCF v2.0과 통합되고 IAB TCF에 등록된 CMP(Consent Management Platform) 또는 자체 CMP를 사용하고 있어야 합니다. [IAB 프레임워크 내에 등록된 CMP](https://iabeurope.eu/cmp-list/) 목록을 참조하십시오.

>[!WARNING]
>
>IAB TCF v.2.0을 지원하지 않는 CMP(Consent Management Platform)를 사용하는 경우, Audience Manager은 방문자가 유럽 연합(EU)에 있더라도 ID 동기화에서 매개 변수를 자동으로 전송합니다. `gdpr=0` GDPR 유효성이 유효한지 확인하려면 CMP(Consent Management Platform)에서 IAB TCF v2.0을 지원하는지 확인하는 것이 좋습니다.

## 권장 사항 및 구현 방법 {#recommendations}

Audience Manager에서 IAB TCF 지원을 활성화하려면 [옵트인으로 IAB를 설정하는 방법](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/iab.html)에 대한 설명서를 참조하십시오.

가장 쉬운 방법은 [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) 를 사용하여 속성에 [!DNL ECID Opt-in] 추가하는 것입니다. Launch 확장을 설정하는 방법을 알려면 [ECID 옵트인 확장](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html)에 대한 설명서를 읽어 보십시오.

## IAB 프레임워크 사용 시 사용자 선택 워크플로우 {#user-choice-workflow}

웹 자산을 방문할 때 사용자는 게시자 및 게시자가 작업에 사용하는 타사 공급업체의 데이터 사용 방법에 대한 선택 사항을 제공할 수 있습니다.

사용자는 글로벌 공급업체 목록에 등록된 *타사 업체에* IAB를 목적으로 ** 동의 *와* 합법적인 관심으로자신의 선택 사항을제공합니다.

아래 이미지는 어떤 웹 사이트를 처음 방문하는 사람에게 표시되는 CMP 대화 상자의 예를 나타냅니다. 고객 구현에 따라 이 대화 상자가 매우 다르게 보일 수 있음을 명심하십시오.

![CMP 대화 상자](assets/cmp-example.png)

IAB TCF v2.0에 포함된 다양한 목적 및 권한에 대한 자세한 내용은 IAB [유럽 투명성 및 동의 프레임워크 정책에 설명되어 있습니다](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

사용자는 목적과 공급업체의 조합을 위해 자신의 동의 또는 합법적인 관심 사항을 부여할 수 있습니다(가능한 경우). 예를 들어, 사용자는 장치에 정보를 저장하고, 제품을 개발 및 개선하며, CMP가 표시하는 모든 타사 공급업체에 동의함을 부여할 수 있습니다.

또는, 다른 예로, 그들은 모든 목적을 위해 그들의 동의 또는 합법적인 이익을 부여할 수 있지만, CMP가 진열한 몇몇 공급업체에게 동의 또는 정당한 이익만을 부여할 수 있습니다.

사용자가 개인 정보 선택을 선택하면 사용자 선택 사항이 IAB TC 문자열에 기록됩니다. The IAB TC string stores the combination of approved purposes and vendors, along with other metadata information (see the [IAB page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) for more information).

IAB TCF에 등록된 모든 공급업체는 IAB TC 문자열을 평가하고 사용자의 개인 정보 선택에 따라 결정을 합니다. 사용자의 개인 정보 보호 선택 사항은 IAB TCF에 등록된 모든 벤더에서 유효합니다.

## Audience Manager에 필요한 목적 {#aam-standard-purposes}

Audience Manager은 IAB 유럽 투명도 및 동의 프레임워크 정책에 정의된 다음 목적을 위해 IAB TC 문자열에 저장된 사용자 선택 사항을 [평가합니다](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes). 또한 [글로벌 공급업체 목록에서 해당 목적을 찾을 수도 있습니다](https://vendorlist.consensu.org/vendorlist.json).

* **목적 1**:장치에 정보 저장 및/또는 액세스
* **목적 10**:제품 개발 및 개선
* **특수 목적 1**:보안, 부정 행위 방지 및 디버그를 보장합니다.

>[!IMPORTANT]
>
>Audience Manager은 쿠키를 배포하고 ID 동기화를 시작 또는 수행하기 위해 목적 1 및 목적 10에 대한 동의와 공급업체의 동의도 필요합니다.
>
>IAB 규정 [에](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)따라, 특별 용도 1(보안, 사기 방지 및 디버그 보장)은 항상 동의하며, 사용자는 이에 반대할 수 없습니다.

## Audience Manager 행동은 사용자가 동의하는지 여부에 따라 달라집니다 {#aam-behavior-consent}

Audience Manager은 IAB TC 문자열에 사용자 동의(장치에 대한 정보 저장 및/또는 액세스, 제품 개발 및 개선)가 포함되는지 여부에 따라 다르게 작동합니다.

Audience Manager에서 근무하는 모든 대상에 대한 사용자 동의도 확인하며, 해당 대상이 IAB TCF에 등록되어 있는 경우 이에 동의합니다.

| 사용자가 *동의하면* Audience Manager는 | 사용자의 동의를 *거부하면* Audience Manager는 |
|---|---|
| <ul><li>요청하신 모든 Audience Manager 사용 사례를 수행합니다.</li><li>Conveys consent to third parties in ID syncs (by passing `gdpr = 1` and the consent string as `gdpr_consent` on ID sync calls).</li><li>광고 서버 픽셀에서 전달된 동의를 평가하고 적용합니다.</li><li>파트너가 시작한 ID 동기화를 수행합니다.</li></ul> | <ul><li>인스턴스에서 새 사용자 데이터를 저장하지 않습니다. 여기에는 파트너 ID, 신호, 트레이트 또는 픽셀 데이터가 포함됩니다.</li><li>타사 ID 동기화를 시작하지 않습니다.</li><li>파트너가 시작한 ID 동기화를 수행하지 않습니다.</li><li>사용자를 추가 데이터 수집에서 옵트아웃합니다.</li></ul> |

## 게시자 사용 사례 {#publisher-use-case}

IAB TCF용 Audience Manager 플러그인을 구현하면, Adobe 또는 다른 타사 공급업체와의 다른 메커니즘을 통해 웹 속성에서 동의 관리를 위한 사용자 정의 코드를 유지 관리할 필요가 없습니다. 사용 사례는 이미지와 아래 단계에 설명되어 있습니다. 이미지의 왼쪽에서 시작하십시오.

1. 사용자가 웹 자산 중 하나를 방문합니다. 최신 버전의 ECID 및 DIL 라이브러리([사전 요구 사항](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites) 참조)를 사용하는 한 옵트인 플로우가 트리거됩니다.
2. Audience Manager가 IAB 플로우가 적용되는지(`isIabContext=true`) 확인합니다. [권장 사항 및 구현 방법](aam-iab-plugin.md#recommendations)을 참조하십시오.
3. Audience Manager checks whether GDPR applies (`gdpr = 1`) and whether there is a CMP, registered with IAB TCF, on your web property. 예를 들어, 유럽 연합에서 방문하는 사용자에게 적용됩니다. 게시자는 GDPR 플래그를 설정해야 합니다.
4. If GDPR applies, Audience Manager checks the IAB TC string, passed in the `gdpr_consent` parameter, for the required consent. Audience Manager은 장치에 정보를 저장 및/또는 액세스하는 행위([IAB TCF 목적 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), 제품 개발 및 개선([IAB TCF 목적 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), 데이터 저장, 처리 또는 활성화에 대한 Audience Manager 공급업체 동의 등이 필요합니다.
5. If the IAB TC string is present and it contains the required consent, Audience Manager passes the IAB TC string on to our [data collection servers](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager은 브라우저에 demdex [쿠키를](https://docs.adobe.com/content/help/ko-KR/core-services/interface/ec-cookies/cookies-am.html) 설정하여 응답하고 타사 ID 동기화를 시작하고 적용합니다.
7. 또는 4단계에서 전달된 IAB TC 문자열에 필요한 모든 권한이 포함되어 있지 않은 경우 Audience Manager은 사용자 데이터를 수집, 처리 또는 활성화하지 않으며 ID 동기화를 해제하거나 시작하지 않습니다. 또한, 사용자가 사용하는 대상에서 사용자를 옵트아웃합니다.

>[!IMPORTANT]
>
>IAB TCF 매개 변수가 필요한 Audience Manager 대상 파트너와 협력하고 있지만 웹 사이트에서 IAB TCF를 지원하는 CMP가 없는 경우 Audience Manager은 ID 동기화 `gdpr=0` 로 전송됩니다. 즉, GDPR은 해당 사용자에게 적용되지 않습니다.
>
> 원하는 경우 Audience Manager에서 IAB TCF 기능을 활성화하여 해당 IAB TC 문자열을 대상 파트너에게 보내야 합니다.



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

1. 사용자는 광고 서버를 통해 광고에 노출됩니다. This translates into a [pixel call](../../integration/media-data-integration/impression-data-pixels.md) to our Data Collection Servers (DCS).
2. Audience Manager가 GDPR 플래그가 적용되는지 확인합니다. If it doesn&#39;t, Audience Manager stores the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.
3. If the IAB TC string is present and it contains the required permissions, Audience Manager stores the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.
4. If the IAB TC string is missing or lacks the required permissions, Audience Manager drops the data passed in the `gdpr` and `gdpr_consent` variables in pixel calls.

![광고주 사용 사례](assets/advertiser-use-case.png)

## IAB TCF를 지원하는 활성화 파트너 {#aam-activation-partners}

IAB TCF용 Audience Manager 플러그인을 사용하면 IAB TC 문자열을 활성화 파트너에게 전달하면서 사용자의 개인 정보 보호 선택을 존중할 수 있습니다. IAB TCF를 지원하는 활성화 파트너에 대한 자세한 내용은 [장치 기반 대상 목록](/help/using/features/destinations/device-based-destinations-list.md)을 참조하십시오.

## URL 대상에 전송된 URL에 동의 추가

IAB TCF v2.0과의 Audience Manager 통합은 IAB TCF v2.0과 통합된 [URL 대상에](../../features/destinations/create-url-destination.md) 전송된 정보에 대한 동의 추가를 지원합니다. 그러나 특정 URL 포맷이 손상되지 않도록 하기 위해 이 프로세스는 Audience Manager에 의해 자동으로 수행되지 않습니다.

전송한 데이터에 동의서를 추가하려는 고객은 URL 형식 [!DNL URL destinations] 에 해당 및 `${GDPR}` `${GDPR_CONSENT_XXXX}` `XXXX` 매크로를 수동으로 추가해야 합니다.

예: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

지원되는 [대상 매크로에 대한 자세한 내용은 정의된](../../features/destinations/destination-macros.md) 대상 매크로를 참조하십시오.

## 상호 장치 동의 관리

IAB TCF용 Audience Manager 플러그인은 사이트 방문자가 적절한 권한을 제공하지 않을 때 요청에 있는 ID를 자동으로 거부합니다. 요청에 [크로스 장치 ID(CRM ID)가 포함되어](../../reference/ids-in-aam.md)있는 경우 Audience Manager은 ID를 해당 [크로스 장치 ID(CRM ID)에 연결된 마지막 장치와 함께 옵트아웃합니다](../../reference/ids-in-aam.md).

## IAB 구현 테스트 {#test-iab-implementation}

To test that you have correctly implemented the Audience Manager Plug-in for IAB TCF, read [Use Case 4 in Validating Opt-in Service](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

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

* [Adobe Experience Platform ID 서비스 옵트인](https://docs.adobe.com/content/help/ko-KR/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 유럽 GDPR 투명성 및 동의 프레임워크](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 유럽 GDPR 투명성 및 동의 프레임워크 기술 사양](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 플러그인 - 비디오 데모](https://helpx.adobe.com/kr/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)