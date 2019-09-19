---
description: 이 자료에는 유럽 개인 정보 보호 규정(GDPR)과 관련하여 당사 고객 및 파트너가 요청하는 몇 가지 일반적인 질문과 데이터 프로세서로서 Adobe Audience Manager가 다양한 GDPR 요구 사항을 해결하는 방법이 포함되어 있습니다.
seo-description: 이 자료에는 유럽 개인 정보 보호 규정(GDPR)과 관련하여 당사 고객 및 파트너가 요청하는 몇 가지 일반적인 질문과 데이터 프로세서로서 Adobe Audience Manager가 다양한 GDPR 요구 사항을 해결하는 방법이 포함되어 있습니다.
seo-title: GDPR FAQ
solution: Audience Manager
title: GDPR FAQ
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# GDPR FAQ{#gdpr-faq}

이 자료에는 유럽 개인 정보 보호 규정(GDPR)과 관련하여 당사 고객 및 파트너가 요청하는 몇 가지 일반적인 질문과 데이터 프로세서로서 Adobe Audience Manager가 다양한 GDPR 요구 사항을 해결하는 방법이 포함되어 있습니다.

이 문서에서는 Audience Manager의 GDPR 준비성에 대한 질문을 다룹니다. Experience Cloud GDPR FAQ도 [참조하십시오.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

GDPR은 2018년 5월 25일부터 EU(Data Subject)의 개인 사용자에게 개인 정보를 보다 효과적으로 제어하고 EU 내의 규제를 더욱 강화하여 국제 비즈니스를 위한 규정 환경을 단순화하는 것을 주된 목적으로 실시되었습니다. Adobe의 GDPR 준비 과정의 일부로 Adobe Audience Manager 팀은 데이터 주체의 요청 액세스 및 삭제를 지원하기 위해 필요한 서비스 및 프로세스를 개선했습니다.

## GDPR 용어집 {#gdpr-glossay}

GDPR과 관련하여 사용되는 주요 용어에 대해 잘 알고 있습니다. 아래에서 가장 일반적으로 사용되는 용어 중 일부를 강조 표시했습니다.

<br> 

**** 데이터 컨트롤러:GDPR은 "재무 책임자"를 "법적 담당자"로 정의하고 있으며, 개인 정보의 처리 목적과 방법을 단독으로 또는 다른 사용자와 공동으로 결정합니다. Audience Manager 고객은 데이터 관리자입니다. 고객은 Audience Manager에서 데이터를 관리하는 방법을 제어합니다.

<br> 

**** 데이터 프로세서:"프로세서"는 "관리자를 대신하여 개인 데이터를 처리하는 법률 담당자"입니다. Adobe는 Audience Manager(Adobe의 데이터 관리 플랫폼 또는 DMP)의 맥락에서 DMP를 통해 처리 및 저장 및 서비스를 처리하는 모든 개인 데이터에 대해 "데이터 프로세서"를 수행합니다. Adobe는 데이터 관리자의 권한 및 지침에 따라 개인 데이터만 처리합니다(예: 고객과의 계약에 명시된 경우).

<br> 

**** 데이터 주체:개인 데이터와 관련된 개인 Audience Manager에서 데이터 주체는 Audience Manager 고객 또는 최종 사용자입니다. Audience Manager가 데이터 주체로부터 직접 요청을 받는 경우 이러한 요청은 해당 Adobe 고객에게 전달됩니다.

<br> 

**** 동의:동의란 "진술이나 명확한 적극적 조치에 의해 데이터 주체의 바램에 대해 자유롭게 주어진, 구체적이고, 정보에 근거한 그리고 모호하지 않은 표시를 의미하며, 그와 관련된 개인 데이터의 처리에 동의함을 의미한다"는 것을 의미합니다. 동의는 Audience Manager를 통한 Adobe가 아니라 데이터 관리자의 책임입니다.

<br> 

**** 액세스:데이터 주체는 데이터 관리자가 개인 데이터를 처리하는지 여부를 확인하도록 요구할 권리가 있습니다. 데이터 관리자가 데이터 주체의 개인 데이터를 처리하는 경우 개인 데이터에 대한 액세스 및 사본을 제공해야 합니다. 데이터 관리자는 Adobe에 데이터 주체의 액세스 요청을 도와줄 것을 요청할 수 있습니다.

<br> 

**** 삭제:GDPR은 "잊혀질 권리" 또는 "삭제 권한"을 간략하게 설명합니다. 데이터 주체는 데이터 관리자가 개인 데이터를 삭제하도록 요구할 권리가 있습니다. 데이터 컨트롤러는 Adobe를 비롯한 해당 프로세서와 함께 데이터 주체의 삭제 요청을 지원합니다.

<br> 

**** 수정:데이터 주체가 부정확한 개인 데이터를 시정하도록 데이터 관리자를 요구할 권리가 있습니다. 데이터 컨트롤러는 Adobe를 비롯한 프로세서와 함께 데이터 주체의 수정 요청을 지원합니다.

<br> 

**** Audience Manager 식별자(ID):Adobe Audience Manager는 다양한 유형의 ID를 저장합니다. Audience [Manager의 GDPR](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) 페이지에서는 이러한 ID, 해당 데이터 소스 및 간략한 설명을 제공합니다. Adobe에 요청을 제공할 때 이러한 ID를 참조하여 데이터 주체의 삭제 또는 액세스 요청을 수행하십시오.

<br> 

**** 개인 데이터:GDPR은 개인 데이터의 정의를 확장합니다. GDPR에서 Audience Manager의 모든 데이터는 고객 사용 사례에 따라 개인 데이터로 분류될 수 있습니다.

<br> 

**** 금지된 데이터:Audience Manager에서는 고객이 개인 식별을 위해 사용할 수 있는 이름 및 성, 이메일 ID, CRM ID와 같은 직접 식별 가능한 정보를 인제스트할 수 없습니다. 또한 Adobe Experience Cloud 솔루션은 민감한 정보를 금지합니다. 이러한 요구 사항에 대한 자세한 내용은 Adobe와의 계약을 참조하십시오. 이러한 유형의 데이터 포인트를 Audience Manager로 인제스트해야 하는 경우 인제스트 전에 Adobe 컨설팅 팀에 이러한 ID 해싱에 대한 권장 사항을 문의하십시오.

<br> 

## 개별 GDPR 권한 관리 {#manage-ind-gdpr-rights}

**옵트인 관리/동의 받기**

GDPR은 데이터 관리자의 동의가 필요한 경우 변경되지 않으며, 동의 방법을 변경합니다. 특정 마케팅 활동에 대한 동의가 필요한 경우, 소비자 동의는 활성(예를 들어, 사전 선택된 상자나 묵음이 없는 경우), 번들로 묶이지 않고, 서비스 오퍼는 데이터 주체의 동의를 조건으로 하지 않아야 합니다. 앞으로 계속 데이터를 사용할 수 있도록 특정 동의를 새로 고쳐야 하는 경우도 있을 수 있습니다.

Adobe는 귀하의 데이터 처리자로서 동의 받기에 대한 법적 조언을 제공할 수 없습니다. 법률 팀에 도움을 요청하십시오. Evidon 또는 TrustArc와 같은 동의 관리 솔루션 제공업체와 [함께](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) 작업하여 [더 나은](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) 추천을 제공할 것을 권장합니다. Adobe는 Adobe Launch를 통해 이러한 통합을 지원하기 위해 여러 제공업체와 파트너 관계를 맺었습니다.

Audience Manager 고객은 Audience Manager에서 광고 또는 개인화와 같은 다양한 사용 사례에 대한 사용자 동의를 저장할 수 있습니다. 그런 다음 이러한 트레이트를 사용하여 세그먼트를 작성하면 이러한 각 사용 사례에 대한 각각의 동의를 제공하는 사용자만 포함됩니다. 이 방법을 사용하면 데이터 수집이 중지되지는 않지만 활성화를 위해 세그먼트를 보낼 때만 데이터 사용에 영향을 줍니다. 사용자가 동의를 철회하면 아래 설명된 대로 Audience Manager [인바운드 배치 프로세스](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) 또는 Audience Manager 옵트아웃 프로세스를 사용하여 사용자 프로필에서 이러한 트레이트를 제거할 수 있습니다.

<br> 

**동의 거부/철회 관리**

옵트아웃은 Your Privacy Choices [페이지를 통해 Adobe Experience Cloud에 대해 관리할 수](https://www.adobe.com/privacy/opt-out.html#customeruse) 있습니다. 1번의 클릭으로 최종 사용자가 Adobe Experience Cloud 광고 솔루션(Audience Manager 포함)의 데이터 수집을 제어하고 옵트아웃할 수 있습니다. 특히 개인 정보 선택 페이지의 [비즈니스 고객 섹션을](https://www.adobe.com/privacy/opt-out.html#customeruse) 참조하십시오. 타사 쿠키를 지원하지 않는 브라우저의 경우 선언된 [ID 타깃팅을](../../features/declared-ids.md#declared-id-targeting)참조하십시오. 모바일 장치의 경우, 관련 Audience Manager 식별자를 검색하고 선언된 ID 옵트아웃 예제에 [](../../features/declared-ids.md#opt-out-examples)나와 있는 Audience Manager 옵트아웃 API를 호출하십시오. 이후 Mobile SDK에서 옵트아웃 API를 사용하는 사용자에 대한 모든 데이터 수집을 중단할 수 있습니다. Android [장치](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) 및 [iOS 장치를](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)참조하십시오. 옵트아웃에 대한 자세한 내용은 Audience Manager 옵트아웃 [설명서에서 확인할 수 있습니다](../../overview/data-security-and-privacy/opt-out-management.md).

<br> 

**Adobe에 Audience Manager GDPR 액세스 및 삭제 요청 제출**

GDPR Client Services UI를 통해 또는 GDPR API를 [통해](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) 액세스 및 삭제에 대한 개별 GDPR 요청을 제출할 [수 있습니다](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md). 모든 [Audience Manager 식별자는](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)해당 네임스페이스 ID(데이터 소스 ID)와 함께 요청에서 제출할 수 있습니다. CRM ID와 같은 장치 간 식별자를 제출하는 경우 Audience Manager는 인증된 프로필뿐만 아니라 연결된 장치 ID에 대해 조치를 취합니다. 가능한 한 Audience Manager 고유 사용자 ID(AAM UUID)를 사용하는 것이 좋습니다.

<br> 

**액세스 요청 관리**

2018년 5월 25일 이전에 Audience Manager는 Audience Manager 내의 고유 ID와 연결된 트레이트, 고객 ID 및 세그먼트에 수동으로 액세스할 수 있도록 지원했습니다. 2018년 5월 25일부터 Adobe는 상기에 명시된 방법으로 다양한 제품 및 서비스 개선 사항을 지원합니다. 트레이트, 고객 ID, 세그먼트, Access 요청에 대한 응답에는 해당 데이터 소스 이름과 함께 총 트레이트 및 세그먼트 수, 트레이트 유형, 트레이트 및 세그먼트에 대한 요약 정보가 포함됩니다. 액세스 응답에는 퍼스트 파티 데이터와 함께 데이터 컨트롤러에 액세스할 수 있는 제2자 및 제3자 데이터도 포함됩니다. 데이터 액세스 [요청에서 더 많은 내용을 참조하십시오](../../overview/aam-gdpr/aam-gdpr-details.md#access-data).

<br> 

**삭제 요청 관리**

2018년 5월 25일 이전에는 Audience Manager에서 고유한 ID와 연결된 트레이트, 고객 ID 및 세그먼트의 수동 삭제를 지원했습니다. GDPR이 발효되면 Adobe는 위의 다양한 제품 및 서비스 개선 사항에 대한 방식으로 이러한 요청을 지원합니다. 삭제 작업 외에, 데이터 주체의 각 Audience Manager 식별자는 추가 데이터 수집에서 옵트아웃되고 해당 ID 매핑이 제거됩니다. 데이터 삭제 [요청에서 자세히 살펴보십시오](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data).

<br> 

**제2자 데이터 제공업체 및 동의 관리**

제2자 데이터 제공자는 일반적으로 데이터 관리자입니다. 또한 데이터를 제2자 데이터 파트너와 공유할 수 있도록 데이터 주체로부터 필요한 동의를 얻는 프로세스를 소유합니다. Audience Manager 고객은 제2자 데이터 제공업체가 사용자의 사용 사례에 필요한 동의를 받았는지 확인해야 합니다. 동의에 대한 자세한 내용은 위에 나와 있습니다.

<br> 

**제3자 데이터 제공업체 및 동의 관리**

데이터 제공자는 또한 데이터 관리자입니다. 동의 및 액세스/삭제/수정 요청을 관리하는 프로세스를 소유합니다. Adobe는 데이터 제공업체가 Adobe Audience Finder에서 회사 프로필 정보를 업데이트하여 [사용자 데이터](https://www.adobe-audience-finder.com/) 수집에 대한 추가 정보를 제공하도록 적극적으로 요청하고 있습니다. 정보는 데이터 제공업체로부터 공급되며 목표는 2018년 2분기까지 도구를 업데이트하기 위한 것입니다. 그러나 제3자 데이터 제공업체가 해당 고객의 사용 사례에 대해 필요한 동의를 얻었는지 여부는 각 Audience Manager 고객에게 달려 있습니다. Adobe는 특정 사용 사례에 대해 제3자 데이터 제공자가 취득하거나 보고한 동의의 범위나 유효성에 대해 진술하지 않습니다.

<br> 

**대상 활성화를 위한 삭제 요청의 영향**

Audience Manager는 특정 데이터 삭제를 요청하는 데이터 주체의 세그먼트 해제 정보를 보내 활성화 파트너에게 삭제 요청에 대해 알립니다. 그러나 일부 정품 인증 파트너는 다음과 같습니다.1) Adobe 및/또는 2)에서 세그먼트 해제(또는 세그먼트 제거) 요청을 지원할 수 없습니다. 30일 미만의 빈도로 Adobe로부터 업데이트를 받을 수 없습니다. 이러한 경우 Audience Manager 고객은 Audience Manager를 통해 자동화된 방식으로 활성화 파트너에게 삭제 요청을 보낼 수 없습니다. GDPR [Partner Unsegment 설명서에는](../../overview/aam-gdpr/aam-gdpr-partners.md) 모든 정품 인증 파트너를 위한 세그먼트 해제 기능 및 데이터 교환 빈도에 대한 정보가 제공됩니다.

<br> 

**Audience Manager의 데이터 유지**

GDPR을 준수하기 위해서는 데이터에 적절하고 안전하며 시기 적절한 데이터 보존 정책을 적용해야 합니다. Audience Manager 고객은 필요한 TTL(Time to Live)을 정의하여 트레이트 및 세그먼트에 사용자 지정 유지 기간을 설정할 수 있습니다. 보유 기간 [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF])과 [!UICONTROL Batch Outbound] 주문 기간을 8일로 단축했습니다. 또한 비활성 CRM 프로필 및 ID 매핑에 보존 기간을 적용할 예정입니다. 데이터 유지 FAQ에서 보존 기간에 대한 자세한 [정보를 참조하십시오](../../faq/faq-privacy.md).

<br> 

**데이터 수정에 대한 요청 관리**

Audience Manager가 데이터의 소스가 아니기 때문에 Audience Manager에는 데이터 교정을 위한 제한된 역할이 있습니다. 수정은 데이터 주체가 잘못된 트레이트/세그먼트에서 실격 처리되거나 원하는 트레이트/세그먼트에 자격이 있음을 의미할 수 있습니다. Audience Manager 고객은 사용자 프로필에 대해 관련 신호/트레이트/세그먼트를 캡처하고 오프라인 데이터 수집을 통해 Audience Manager에 이 정보를 전송할 수 있습니다. 사용자가 동작을 반복할 경우 원래 트레이트 및 세그먼트에 계속 자격을 얻게 됩니다.

<br> 

**국경을 통한 데이터 전송**

GDPR에서는 유럽 외부의 데이터 전송을 금지하지 않습니다. 이는 데이터가 전송될 때마다 유럽 데이터에 대한 개인정보 보호 보호가 유지되어야 합니다. 자세한 내용은 [Adobe](https://www.adobe.com/privacy/eudatatransfers.html) 개인 정보 보호 센터를 참조하십시오.

<br> 

## Audience Manager 고객을 위한 GDPR 준비 지침(데이터 관리자) {#gdpr-readiness-guidance}

Adobe는 데이터 거버넌스 및 조직의 준비 분야에 선제적으로 대처하도록 권장합니다. 이를 통해 소비자 데이터가 액세스 또는 삭제 요청과 관련된 프로세스에 맞게 구성되고 팀이 이러한 요청을 활성화하고 관리할 수 있으며 소비자(데이터 주체)는 브랜드에 긍정적이고 차별화된 경험을 갖게 됩니다.

데이터 프로세서로서 Adobe는 GDPR 요구 사항과 귀하의 데이터 주체로부터 동의를 얻기 위한 프로세스에 대한 법률 자문을 제공할 수 없습니다. 조직의 GDPR 준수에 대한 지침은 법률 담당자와 문의하십시오.

<br> 

**데이터 거버넌스:Audience Manager 인스턴스에서 소비자 데이터를 관리하는 방법에 대해 생각해 보십시오**

* 마케팅 팀이 Audience Manager의 사용자를 식별하는 데 사용하는 다양한 고객 ID와 저장된 데이터 소스를 검토합니다. 이렇게 하면 특정 데이터 유형이 Audience Manager에 수집되기 전에 팀에서 해시하므로 요청(예: 삭제 또는 액세스)에 대한 프로세스가 간소화됩니다.
* IDFA/GAID 모바일 장치 ID 파섹 Adobe Mobile SDK를 사용하는 경우 IDFA/GAID와 함께 Experience Cloud ID(MID)를 제출하여 GDPR 응답이 완료되었는지 확인하십시오.
* 개인 데이터의 정의가 더욱 확대되고 있으므로 IP 주소는 해당 지역의 개인 데이터로 간주될 수 있습니다. Adobe Consulting과 적극적으로 협력하여 마지막 8진수를 난독화합니다.
* GDPR 요청 시 데이터 주체의 ID를 확인하는 유효성 검사/인증 정책 및 프로세스를 결정합니다.
* 데이터 내보내기 [제어 기능을](../../features/data-export-controls.md) 사용하여 개인 데이터를 포함하는 기술에 대한 고객 활성화를 차단하는 것이 좋습니다. 예를 들어 서드 파티 데이터가 있는 세그먼트는 이메일 서비스 제공업체에 전달되어서는 안 됩니다. 조직 내에서 이 데이터를 실수로 활성화하지 [!UICONTROL Data Export Control] 않도록 을 설정합니다.
* 역할 기반 [액세스 제어](../../features/administration/administration-overview.md) 기능을 활용하여 적합한 팀이 적절한 데이터에 액세스할 수 있도록 합니다.
* 데이터에 적절한 [보존 기간을](../../faq/faq-privacy.md#data-retention-faq) 고려합니다.
* ID 연결 및 개인 정보 보호 정책 및 법적 요구 사항을 검토하여 ID를 언제 어디서 연계할 수 있는지 확인합니다.audience Manager의 프로필 병합 규칙을 통해 [적절하게 사용하십시오](../../features/profile-merge-rules/merge-rules-overview.md).

<br> 

**조직 준비:비즈니스 프로세스 수립**

* 데이터 주체의 요청을 받고 응답하는 프로세스를 식별합니다. Audience Manager에 요청을 제출할 수 있는 자동화된 툴을 구축하는 것이 좋습니다.
* 탁월한 DMP 센터에서 개인 정보 보호 담당자를 지정할 수 있습니다. 조직의 개인 정보 보호 담당자와 Audience Manager 제품 사용 팀과 연결하여 입력 ID 요구 사항을 관리하는 방법을 이해합니다.
* 데이터 주체와 공유하기 전에 데이터 검토를 수행합니다. 적절한 단계를 문서화하여 책임을 확정할 수 있습니다.

