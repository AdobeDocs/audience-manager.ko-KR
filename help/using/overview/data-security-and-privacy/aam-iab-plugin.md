---
description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-title: IAB TCF를 위한 Audience Manager 플러그인
solution: Audience Manager
title: IAB TCF를 위한 Audience Manager 플러그인
translation-type: tm+mt
source-git-commit: 5fff9315558d3088f68268f32681842bb8d5e7d3

---


# IAB TCF를 위한 Audience Manager 플러그인 {#aam-iab-plugin}

## 개요

사용자와 관련된 개인 정보 보호 의무의 중요한 측면은 개인 데이터가 사용되는 방법(즉, &quot;목적&quot;) 및 사용되는 대상(즉, &quot;회사&quot;)에 대한 사용자의 선택을 획득 및 제공하는 것입니다. 

Adobe는 [옵트인 기능](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) 및 [IAB 투명성 및 동의 프레임워크(TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다.

이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다. Audience Manager는 공급업체 ID 565와 함께 IAB TCF에 등록됩니다.

IAB TCF용 Audience Manager 플러그인은 [옵트인 기능을](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)활용하며, 이 기능은 [Adobe ECID(Experience Platform Identity Service) 라이브러리의 일부입니다](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## 범위 및 제한 사항 {#scope-and-limitations}

Audience Manager를 사용하는 게시자 또는 광고주는 IAB TCF에 따라 Audience Manager에 사용자 선택 사항을 전달할 수 있습니다. 이를 통해 모든 파트너에게 사용자 선택 사항을 간편하고 일관되게 전달할 수 있으며 Audience Manager를 통해 사용자의 개인 정보 보호 선택 사항을 준수할 수 있습니다.

이 문서에 설명된 IAB TCF 지원은 IAB 프레임워크에 대한 Audience Manager의 계획된 지원 중 첫 번째 단계를 나타냅니다. 현재 Audience Manager는 다음을 지원하지 않습니다.

* 모바일 디바이스 워크플로우
* 크로스 디바이스 동의 관리
* URL 대상에 [전송된 URL에 동의](../../features/destinations/create-url-destination.md)추가
* 세그먼트에 동의 추가

## 전제 조건 {#prerequisites}

Audience Manager에서 IAB TCF를 사용하려면 다음 전제 조건을 충족해야 합니다.

1. Adobe ECID(Experience Platform Identity Service) 버전 4.1 이상을 사용해야 합니다. [최신 ECID 릴리스를 다운로드하십시오](https://github.com/Adobe-Marketing-Cloud/id-service/releases) .
1. DIL(Audience Manager Data Integration Library) 버전 9.0 이상을 사용해야 하며 [여기에서 다운로드할 수 있습니다](https://github.com/Adobe-Marketing-Cloud/dil/releases). Audience Manager [설명서에서 DIL에 대해 알아봅니다](../..//dil/dil-overview.md).
1. 또는 SSF(서버측 전달)를 사용하여 데이터를 Audience Manager로 가져오는 경우 최신 버전의 AppMeasurement로 업그레이드해야 합니다. Analytics 코드 관리자를 사용하여 [AppMeasurement를 다운로드합니다](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).
1. 귀하는 IAB TCF를 지원하고 IAB TCF에 등록된 CMP(Consent Management Platform) 또는 자체 CMP를 사용하고 있어야 합니다. IAB 프레임워크 [에서 등록된 CMP 목록을 참조하십시오](https://iabeurope.eu/cmp-list/).

## 권장 사항 및 구현 방법 {#recommendations}

Audience Manager에서 IAB TCF 지원을 활성화하려면 옵트인 [을 사용하여 IAB를 설정하는 방법에 대한 설명서를 참조하십시오](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

이는 [Adobe Experience Platform Launch를 사용하여](https://docs.adobelaunch.com/) 속성에서 ECID 옵트인을 계측하여 가장 쉽게 수행됩니다. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## IAB 프레임워크 사용 시 사용자 선택 워크플로우 {#user-choice-workflow}

웹 속성을 방문할 때 사용자는 게시자 및 발행자가 사용하는 타사 공급업체의 데이터 사용 방법에 대한 선택을 제공할 수 있습니다. 사용자는 글로벌 공급업체 목록에 등록된 *타사 업체에* 표준 목적 ** 및 권한 형태로 자신의 선택 사항을 제공합니다. 아래 이미지는 웹 사이트의 처음 방문자에게 표시되는 CMP 대화 상자의 예를 나타냅니다. 고객 구현에 따라 이 대화 상자가 매우 다르게 보일 수 있음을 명심하십시오.

![CMP 대화 상자](assets/cmp.png)

IAB 프레임워크의 표준 목적은 다음과 같습니다.

* 정보 저장 및 액세스
* 개인화
* 광고 선택, 전달 및 보고
* 컨텐츠 선택, 전달 및 보고
* 측정

5가지 표준 용도에 대한 설명은 [IAB 프레임워크 사양 페이지를](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) 참조하십시오.

사용자는 표준 목적과 공급업체의 조합으로 동의하게 될 수 있습니다. 예를 들어, 사용자는 스토리지, 개인화 및 측정에 대해 동의해야 하며 CMP에서 표시하는 모든 타사 공급업체에 동의해야 합니다. 또는, 다른 예로, 그들은 다섯 가지 표준 목적을 위해 그들의 동의를 부여할 수 있지만 CMP가 표시하는 일부 공급업체에 동의만 할 수 있습니다.

사용자가 개인 정보 선택을 선택하면 사용자 선택 사항이 IAB TCF 동의 문자열에 기록됩니다. IAB TCF 동의 문자열은 승인된 목적과 공급업체의 조합과 기타 메타데이터 정보를 저장합니다(자세한 내용은 [IAB 페이지](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) 참조). IAB TCF에 등록된 모든 공급업체는 IAB TCF 동의 문자열을 평가하고 사용자의 개인 정보 선택에 따라 결정을 합니다. 사용자의 개인 정보 보호 선택 사항은 모든 승인된 공급업체에서 유효합니다.

## Audience Manager에 필요한 표준 용도 {#aam-standard-purposes}

Audience Manager는 다음 항목에 대해 IAB TCF 동의 문자열에 저장된 사용자 선택 사항을 평가합니다.

* 정보 저장 및 액세스( [글로벌 공급업체 목록의 목적 ID 1](https://vendorlist.consensu.org/vendorlist.json))
* 개인화(목적 ID 2)
* 측정(목적 ID 5)
* Audience Manager 공급업체는 게시자에 대한 데이터를 저장, 처리 또는 활성화하는 것에 동의합니다.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager 비헤이비어는 사용자가 동의하는지 여부에 따라 달라집니다. {#aam-behavior-consent}

Audience Manager는 Audience Manager가 사용자가 세 가지 목적(저장, 개인화, 측정)에 대한 동의를 제공한 IAB TCF 동의 문자열에서 감지하는지 여부에 따라 다르게 작동합니다.

| 사용자가 *동의를*&#x200B;하면 Audience Manager: | 사용자의 동의 *를* 거부하면 Audience Manager: |
|---|---|
| <ul><li>요청하신 모든 Audience Manager 사용 사례를 실행합니다.</li><li>ID 동기화 시 서드 파티에 대한 동의를 전달하십시오(gdpr = 1을 전달하고 ID 동기화 호출에 대한 gdpr_consent로 동의 문자열 전달).</li><li>광고 서버 픽셀에서 전달된 동의를 평가하고 적용합니다.</li><li>파트너가 시작한 ID 동기화를 수행합니다.</li></ul> | <ul><li>인스턴스에 새 사용자 데이터를 저장하지 않습니다. 여기에는 파트너 ID, 신호, 트레이트 또는 픽셀 데이터가 포함됩니다.</li><li>타사 ID 동기화를 시작하지 않습니다.</li><li>파트너가 시작한 ID 동기화를 준수하지 않습니다.</li></ul> |

## 게시자 사용 사례 {#publisher-use-case}

IAB TCF를 구현함으로써 Adobe 또는 다른 타사 공급업체와의 다른 메커니즘을 통해 웹 속성에서 동의 관리를 위한 사용자 정의 코드를 유지 관리할 필요가 없습니다. 사용 사례는 이미지와 아래 단계에서 설명합니다. 이미지 왼쪽에서 시작:

1. 사용자가 웹 속성 중 하나를 방문합니다. 최신 버전의 ECID 및 DIL 라이브러리(사전 요구 사항 참조)를 사용하는 경우 [옵트인](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)흐름이 트리거됩니다.
2. Audience Manager는 IAB 흐름이 적용되는지(`isIabContext=true`) 확인합니다. 권장 [사항 및 구현 방법을 참조하십시오](aam-iab-plugin.md#recommendations).
3. Audience Manager는 웹 속성에 GDPR이 적용되는지(`gdpr = 1`), IAB에 등록된 CMP가 있는지 여부를 확인합니다. 예를 들어, 유럽 연합 지역에서 방문하는 사용자에게 적용됩니다. 게시자는 GDPR 플래그를 설정해야 합니다.
4. GDPR이 적용되는 경우 Audience Manager는 매개 변수에 전달된 IAB TCF 동의 문자열 `gdpr_consent`을 확인하여 필요한 권한을 확인합니다. Audience Manager는 데이터를 저장, 처리 또는 활성화하기 위해 스토리지, 개인화, 측정, Audience Manager 공급업체의 동의 등에 대한 권한이 필요합니다.
5. IAB TCF 동의 문자열이 존재하며 필요한 권한이 포함되어 있는 경우 Audience Manager는 [데이터 수집 서버](../../reference/system-components/components-data-collection.md) (DCS)에 IAB TCF 동의 문자열을 전달합니다.
6. Audience Manager는 브라우저에서 [demdex 쿠키를](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) 설정하여 응답합니다. 또한 Audience Manager는 타사 ID 동기화를 시작 및 처리합니다.
7. 또는 5단계에서 전달된 IAB TCF 동의 문자열에 필요한 모든 권한이 포함되어 있지 않은 경우 Audience Manager는 데이터를 수집, 처리 또는 활성화하지 않으며 ID 동기화를 해제하거나 시작하지 않습니다.

![게시자 사용 사례](assets/publisher-use-case.png)

## 광고주 사용 사례 {#advertiser-use-case}

Audience Manager는 IAB TCF에 따라 [픽셀 호출](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)시 전달된 동의를 평가하고 이에 대해 승인합니다.

일반적으로 픽셀은 파트너 페이지에 Audience Manager 고객이 배치하거나 광고 응답에 포함할 광고 서버에 배치됩니다. 첫 번째 경우, 파트너는 실행 전에 프로그래밍 방식으로 동의 매개 변수를 검색하고 픽셀에 추가해야 합니다. 두 번째 사례에서는, 아래에서 자세히 설명되고 보다 일반적이며, 광고 서버는 SSP(Supply-Side Platform) 또는 게시자 및 서버로부터 받는 동의 매개 변수를 모든 픽셀에 추가합니다.

Audience Manager는 두 개의 매개 변수를 사용하여 사용자 동의를 픽셀 호출로 전달합니다.

* `gdpr` 0일 수(GDPR이 적용되지 않음) 또는 1(GDPR 적용)일 수 있습니다.
* `gdpr_consent` 은 URL-safe base64로 인코딩된 GDPR 동의 문자열입니다( [사양 참조](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). 두 매개 변수가 있는 노출 픽셀에 대한 샘플 호출은 아래와 같습니다.

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

사용 사례는 이미지와 아래 단계에서 설명합니다. 이미지 왼쪽에서 시작:

1. 사용자는 광고 서버를 통해 노출 횟수를 제공합니다. 이는 DCS(데이터 수집 서버)에 대한 픽셀 호출로 해석됩니다.
2. Audience Manager는 GDPR 플래그가 적용되는지 확인합니다. 그렇지 않으면 Audience Manager는 매크로 변수로 전달된 데이터를 픽셀 호출로 저장합니다.
3. 동의 문자열이 존재하며 필수 권한이 포함되어 있으면 Audience Manager는 매크로 변수로 전달된 데이터를 픽셀 호출로 저장합니다.
4. 동의 문자열이 없거나 필요한 권한이 없는 경우 Audience Manager는 매크로 변수로 전달된 데이터를 픽셀 호출로 삭제합니다.

![광고주 사용 사례](assets/advertiser-use-case.png)

## IAB TCF를 지원하는 정품 인증 파트너 {#aam-activation-partners}

IAB TCF용 Audience Manager 플러그인을 사용하면 사용자의 개인 정보 보호 선택 사항을 준수하면서 활성화 파트너에게 IAB TCF 동의 문자열을 전달할 수 있습니다. IAB TCF를 지원하는 정품 인증 파트너에 대한 자세한 내용은 디바이스 [기반 대상 목록을 참조하십시오](/help/using/features/destinations/device-based-destinations-list.md).

## IAB 구현 테스트 {#test-iab-implementation}

IAB TCF용 Audience Manager 플러그인을 올바르게 구현했는지 테스트하려면 옵트인 및 IAB 구현을 위한 유효성 검사 [방법의 사용 사례 4를 읽어 보십시오](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## Audience Manager의 IAB 및 옵트아웃. 우선 순위. {#iab-and-optout}

사용자가 임의로 선택할 수 있는 또 다른 개인정보 보호 옵션은 모든 데이터 수집을 옵트아웃하는 기능입니다. Adobe는 개인 정보 선택 [페이지 내에서 사용자에게 개인 정보 보호](https://www.adobe.com/privacy/opt-out.html#customeruse) 선택 방법을 제공합니다.

Audience Manager는 설명서의 [별도 문서에서 옵트아웃 요청을 해결합니다](data-privacy-requests.md).

>[!NOTE]
>
>**우선 순위** - 사용자가 위의 링크에 설명된 대로 전역 옵트아웃 도구를 사용하여 데이터 수집을 옵트아웃하는 경우 옵트인 및 IAB 확인보다 우선합니다.

## 추가 리소스 {#additional-resources}

* [Adobe Experience Platform ID 서비스 옵트인](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [IAB 유럽 GDPR 투명성 및 동의 프레임워크](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 유럽 GDPR 투명성 및 동의 프레임워크 기술 사양](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 플러그인 - 비디오 데모](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)