---
description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-description: Adobe는 옵트인 기능 및 IAB 투명성 및 동의 프레임워크(TCF) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다. 이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다.
seo-title: IAB TCF를 위한 Audience Manager 플러그인
solution: Audience Manager
title: IAB TCF를 위한 Audience Manager 플러그인
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# IAB TCF를 위한 Audience Manager 플러그인 {#aam-iab-plugin}

## 개요

사용자와 관련된 개인 정보 보호 의무의 중요한 측면은 개인 데이터가 사용되는 방법(즉, &quot;목적&quot;) 및 사용되는 대상(즉, &quot;회사&quot;)에 대한 사용자의 선택을 획득 및 제공하는 것입니다. 

Adobe는 [옵트인 기능](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) 및 [IAB 투명성 및 동의 프레임워크(TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/) 지원을 통해 사용자의 개인 정보 보호 선택을 관리 및 소통할 수 있는 수단을 제공합니다.

이 문서에서는 IAB TCF를 지원하는 Audience Manager 사용 사례 및 Audience Manager에서 IAB TCF 지원을 구현하는 방법에 대해 설명합니다. Audience Manager는 공급업체 ID 565와 함께 IAB TCF에 등록됩니다.

IAB TCF용 Audience Manager 플러그인은 [옵트인 기능을](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)활용하며, 이 기능은 [Adobe ECID(Experience Platform Identity Service)](https://marketing.adobe.com/resources/help/en_US/mcvid/) 라이브러리의 일부입니다.

## 범위 및 제한 사항 {#scope-and-limitations}

Audience Manager를 사용하는 게시자 또는 광고주는 IAB TCF에 따라 Audience Manager에 사용자 선택 사항을 전달할 수 있습니다. 이를 통해 모든 파트너에게 사용자 선택 사항을 간편하고 일관되게 전달할 수 있고 Audience Manager를 통해 사용자의 개인 정보 보호 선택 사항을 준수할 수 있습니다.

이 문서에 설명된 IAB TCF 지원은 Audience Manager의 IAB 프레임워크 지원 계획 중 첫 번째 단계입니다. 현재 Audience Manager는 다음을 지원하지 않습니다.

* 모바일 디바이스 워크플로우;
* 크로스 디바이스 동의 관리
* URL 대상에 [](../../features/destinations/create-url-destination.md)전송된 URL에 동의 추가
* 세그먼트에 동의 추가

## 전제 조건 {#prerequisites}

Audience Manager에서 IAB TCF를 사용하려면 다음 전제 조건을 충족해야 합니다.

1. Adobe Experience Platform ECID 파섹 버전 4.1 이상을 사용해야 합니다. [최신 ECID 릴리스를 다운로드하십시오](https://github.com/Adobe-Marketing-Cloud/id-service/releases) .
1. 여기에서 다운로드할 수 있는 DIL(Audience Manager Data Integration Library) 버전 9.0 이상을 사용해야 [합니다](https://github.com/Adobe-Marketing-Cloud/dil/releases). Audience Manager [설명서에서](../..//dil/dil-overview.md)DIL에 대해 알아보십시오.
1. 또는 SSF(서버측 전달)를 사용하여 데이터를 Audience Manager로 가져오는 경우 최신 버전의 AppMeasurement로 업그레이드해야 합니다. Analytics 코드 관리자를 사용하여 [AppMeasurement를 다운로드합니다](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
1. 귀하는 IAB TCF를 지원하고 IAB TCF에 등록된 CMP(Consent Management Platform) 또는 자체 CMP를 사용하고 있어야 합니다. IAB 프레임워크에 [등록된 CMP 목록을 참조하십시오](https://advertisingconsent.eu/cmp-list/).

## 권장 사항 및 구현 방법 {#recommendations}

Audience Manager에서 IAB TCF 지원을 활성화하려면 Opt-in을 사용하여 IAB를 설정하는 [방법에 대한 설명서를 참조하십시오](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

이 작업은 Adobe Experience Platform Launch [를 사용하여](https://docs.adobelaunch.com/) 속성에서 ECID 옵트인을 계측하여 수행하는 것이 가장 쉽습니다. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## IAB 프레임워크 사용 시 사용자 선택 워크플로우 {#user-choice-workflow}

웹 속성을 방문할 때 사용자는 자신의 데이터가 게시자와 발행자가 사용하는 타사 공급업체에서 어떻게 사용되는지 선택할 수 있습니다. 사용자는 글로벌 공급업체 목록에 등록된 *타사 업체에* 표준 목적과 사용 권한을 ** 제공합니다. 아래 이미지는 웹 사이트의 처음 방문자에게 표시되는 CMP 대화 상자의 예를 나타냅니다. 고객 구현에 따라 이 대화 상자가 매우 다르게 보일 수 있다는 점을 명심하십시오.

![CMP 대화 상자](assets/cmp.png)

IAB 프레임워크의 표준 목적은 다음과 같습니다.

* 정보 저장 및 액세스
* 개인화
* 광고 선택, 전달 및 보고
* 컨텐츠 선택, 전달 및 보고
* 측정

5가지 표준 [용도에 대한 설명은 IAB 프레임워크 사양 페이지를](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) 참조하십시오.

사용자는 표준 목적과 공급업체의 조합에 대해 동의를 할 수 있습니다. 예를 들어, 사용자는 스토리지, 개인화 및 측정에 대해 동의하거나 CMP가 표시하는 모든 타사 공급업체에 동의해야 합니다. 또는, 다른 예로, 그들은 다섯 가지 표준 목적을 위해 동의를 할 수 있지만, CMP에 의해 표시된 몇 개의 벤더에게 동의만 할 수 있습니다.

사용자가 개인 정보 선택을 선택하면 사용자 선택 사항이 IAB TCF 동의 문자열에 기록됩니다. IAB TCF 동의 문자열은 승인된 목적과 벤더의 조합을 다른 메타데이터 정보와 함께 저장합니다(자세한 내용은 [IAB 페이지](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) 참조). IAB TCF에 등록된 모든 공급업체는 IAB TCF 동의 문자열을 평가하고 사용자의 개인 정보 보호 선택 사항에 따라 결정합니다. 사용자의 개인 정보 보호 선택 사항은 모든 승인된 공급업체에서 유효함을 염두에 두십시오.

## Audience Manager에 필요한 표준 용도 {#aam-standard-purposes}

Audience Manager는 IAB TFC 동의 문자열에 저장된 사용자 선택 사항을 다음과 같이 평가합니다.

* 정보 저장 및 액세스( [글로벌 공급업체 목록의](https://vendorlist.consensu.org/vendorlist.json)목적 ID 1)
* 개인화(목적 ID 2)
* 측정(목적 ID 5)
* Audience Manager 공급업체는 게시자에 대한 데이터를 저장, 처리 또는 활성화하는 것에 동의합니다.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager 비헤이비어는 사용자가 동의하는지 여부에 따라 달라집니다. {#aam-behavior-consent}

Audience Manager는 Audience Manager가 IAB TCF 동의 문자열에서 사용자가 세 가지 용도(스토리지, 개인화, 측정)에 대한 동의를 제공하는지 여부에 따라 다르게 작동합니다.

| 사용자가 *동의를*&#x200B;하면 Audience Manager: | 사용자가 동의를 *거부하면* Audience Manager: |
|---|---|
| <ul><li>요청한 Audience Manager의 모든 활용 사례를 실행합니다.</li><li>ID 동기화에서 제3자에게 동의를 전달합니다(gdpr = 1을 전달하고 ID 동기화 호출에서 동의 문자열을 gdpr_consent로 전달).</li><li>광고 서버 픽셀에서 전달된 동의를 평가하고 처리합니다.</li><li>파트너가 시작한 ID 동기화를 적용합니다.</li></ul> | <ul><li>인스턴스에 새 사용자 데이터를 저장하지 않습니다. 여기에는 파트너 ID, 신호, 트레이트 또는 픽셀 데이터가 포함됩니다.</li><li>타사 ID 동기화를 시작하지 않습니다.</li><li>파트너가 시작한 ID 동기화를 준수하지 않습니다.</li></ul> |

## 게시자 사용 사례 {#publisher-use-case}

IAB TCF를 구현하면 Adobe 또는 다른 타사 공급업체와의 다른 메커니즘을 통해 웹 속성에서 동의 관리를 위한 사용자 지정 코드를 유지 관리할 필요가 없습니다. 사용 사례는 이미지와 아래 단계에서 설명합니다. 이미지 왼쪽에서 시작:

1. 사용자가 웹 속성 중 하나를 방문합니다. 최신 버전의 ECID 및 DIL 라이브러리를 사용하는 경우(사전 요구 사항 참조 [](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)) 옵트인 흐름이 트리거됩니다.
2. Audience Manager는 IAB 흐름이 적용되는지(`isIabContext=true`) 확인합니다. 권장 [사항 및 구현](aam-iab-plugin.md#recommendations)방법을 참조하십시오.
3. Audience Manager는 웹 속성에 GDPR이 적용되는지(`gdpr = 1`) 및 IAB에 등록된 CMP가 있는지 여부를 확인합니다. 예를 들어 유럽 연합(EU) 지역에서 방문하는 사용자에게 적용됩니다. 게시자는 GDPR 플래그를 설정해야 합니다.
4. GDPR이 적용되는 경우 Audience Manager는 매개 변수에 전달된 IAB TCF 동의 문자열을 확인하여 필요한 권한을 `gdpr_consent`확인합니다. Audience Manager는 데이터를 저장, 처리 또는 활성화하기 위해 스토리지, 개인화, 측정, Audience Manager 공급업체의 동의 등에 대한 권한이 필요합니다.
5. IAB TCF 동의 문자열이 존재하고 필요한 권한이 포함되어 있는 경우 Audience Manager는 IAB TCF 동의 문자열을 [데이터 수집 서버](../../reference/system-components/components-data-collection.md) (DCS)에 전달합니다.
6. Audience Manager는 브라우저에서 [demdex 쿠키를](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) 설정하여 응답합니다. 또한 Audience Manager는 타사 ID 동기화를 시작 및 처리합니다.
7. 또는 5단계에서 전달된 IAB TCF 동의 문자열에 필요한 모든 권한이 포함되어 있지 않은 경우 Audience Manager는 데이터를 수집, 처리 또는 활성화하지 않으며 ID 동기화를 유지하거나 시작하지 않습니다.

![게시자 사용 사례](assets/publisher-use-case.png)

## 광고주 사용 사례 {#advertiser-use-case}

Audience Manager는 IAB TCF에 따라 [픽셀 호출로](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)전달된 동의를 평가하고 처리합니다.

픽셀은 일반적으로 Audience Manager 고객이 파트너 페이지에 배치하거나 광고 응답에 포함할 광고 서버에 배치됩니다. 첫 번째 경우, 파트너가 프로그램 방식으로 동의 매개 변수를 검색하고 시작하기 전에 픽셀에 추가해야 합니다. 두 번째 사례에서는, 아래에 자세히 설명된 바와 같이, 광고 서버는 SSP(Supply-Side Platform) 또는 게시자 광고 서버로부터 받는 동의 매개 변수를 모든 픽셀에 추가합니다.

Audience Manager는 두 개의 매개 변수를 사용하여 픽셀 호출에서 사용자 동의를 전달합니다.

* `gdpr` can be 0 (GDPR not apply) or 1 (GDPR applies);
* `gdpr_consent` 는 URL-safe base64 인코딩된 GDPR 동의 문자열입니다( [사양](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)참조). 두 매개 변수가 있는 노출 픽셀에 대한 샘플 호출은 아래와 같습니다.

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

사용 사례는 이미지와 아래 단계에서 설명합니다. 이미지 왼쪽에서 시작:

1. 사용자는 광고 서버를 통해 임프레션이 제공됩니다. 이는 DCS(데이터 수집 서버)에 대한 픽셀 호출로 해석됩니다.
2. Audience Manager는 GDPR 플래그가 적용되는지 확인합니다. 그렇지 않으면 Audience Manager는 매크로 변수로 전달된 데이터를 픽셀 호출에 저장합니다.
3. 동의 문자열이 존재하고 필요한 권한이 포함되어 있으면 Audience Manager는 매크로 변수로 전달된 데이터를 픽셀 호출에 저장합니다.
4. 동의 문자열이 없거나 필요한 권한이 없는 경우 Audience Manager는 매크로 변수에 전달된 데이터를 픽셀 호출에서 삭제합니다.

![광고주 사용 사례](assets/advertiser-use-case.png)

## IAB TCF를 지원하는 정품 인증 파트너 {#aam-activation-partners}

IAB TCF용 Audience Manager 플러그인을 사용하면 IAB TCF 동의 문자열을 활성화 파트너에게 전달하면서 사용자의 개인 정보 보호 선택 사항을 준수할 수 있습니다. IAB TCF를 지원하는 정품 인증 파트너에 대한 자세한 내용은 디바이스 기반의 대상 [목록을 참조하십시오](/help/using/features/destinations/device-based-destinations-list.md).

## IAB 구현 테스트 {#test-iab-implementation}

IAB TCF용 Audience Manager 플러그인을 올바르게 구현했는지 테스트하려면 옵트인 및 IAB 구현의 [유효성 검사 방법에서 사용 사례 4를 읽어 보십시오](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## Audience Manager의 IAB 및 옵트아웃. 우선 순위. {#iab-and-optout}

사용자가 자유롭게 이용할 수 있는 또 다른 개인정보 보호 옵션은 모든 데이터 수집을 거부할 수 있는 기능입니다. Adobe는 사용자에게 개인 정보 보호 선택 [페이지에서 이를 수행할 수 있는 방법을 제공합니다](https://www.adobe.com/privacy/opt-out.html#customeruse) .

Audience Manager는 설명서의 [별도의 아티클에서](data-privacy-requests.md)옵트아웃 요청을 처리합니다.

>[!NOTE]
>
>**우선 순위** - 사용자가 위의 링크에 설명된 대로 전역 옵트아웃 도구를 사용하여 데이터 수집을 옵트아웃하는 경우 옵트인 및 IAB 확인보다 우선합니다.

## 추가 리소스 {#additional-resources}

* [Adobe Experience Platform Identity Service 옵트인](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR 투명성 및 동의 프레임워크](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB 유럽 GDPR 투명성 및 동의 프레임워크 기술 사양](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF 플러그인 - 비디오 데모](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)