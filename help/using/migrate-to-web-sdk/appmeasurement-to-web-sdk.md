---
title: AppMeasurement JavaScript 라이브러리에서 웹 SDK JavaScript 라이브러리로 Audience Manager을 위해 데이터 수집 라이브러리를 업데이트합니다.
description: AppMeasurement JavaScript 라이브러리에서 웹 SDK JavaScript 라이브러리로 Audience Manager을 위해 데이터 수집 라이브러리를 업데이트하는 단계를 이해합니다.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f8d8eb722e7b5cc4371f400a76fbd548a1318668
workflow-type: tm+mt
source-wordcount: '2589'
ht-degree: 0%

---


# AppMeasurement JavaScript 라이브러리에서 웹 SDK JavaScript 라이브러리로 Audience Manager을 위해 데이터 수집 라이브러리 업데이트

## 의도한 대상 {#intended-audience}

이 페이지는 [!DNL AppMeasurement] JavaScript 라이브러리를 사용하여 웹 데이터를 Audience Manager으로 보내는 Audience Manager 및 Adobe Analytics 고객을 위한 페이지입니다.

현재 데이터 수집 방법에 따라 Web SDK로 마이그레이션하는 방법에 대한 지침은 아래 표를 참조하십시오.

| 기존 데이터 수집 방법 | 웹 SDK 마이그레이션 지침 |
|---------|----------|
| [!DNL AppMeasurement] JavaScript 라이브러리 | 이 안내서의 지침을 따르십시오. |
| [!DNL Audience Manager] [태그 확장](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | [데이터 수집 라이브러리를 Audience Manager 태그 확장에서 Web SDK 태그 확장으로 업데이트](dil-extension-to-web-sdk.md)의 지침을 따릅니다. |
| [!DNL AppMeasurement] JavaScript 라이브러리 + [!DNL Audience Manager] [DIL 라이브러리](../dil/dil-overview.md) | [데이터 수집 라이브러리를 Audience Manager 태그 확장에서 Web SDK 태그 확장으로 업데이트](dil-extension-to-web-sdk.md)의 지침을 따릅니다. |

## 마이그레이션 개요 {#overview}

[!DNL AppMeasurement]에서 [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)(으)로의 마이그레이션은 주로 Adobe Analytics 마이그레이션입니다. Audience Manager 고객의 경우 이 마이그레이션에 Audience Manager 도 포함됩니다. 둘 다 함께 마이그레이션해야 합니다. 주로 Analytics를 사용하는 경우 이 Audience Manager에 Analytics 팀이 참여하도록 하십시오.

Audience Manager 데이터 수집에 [!DNL AppMeasurement]을(를) 사용하는 경우 현재 [!DNL Server-side Forwarding (SSF)] 접근 방식을 사용하여 Analytics 데이터를 Audience Manager으로 보냅니다. 이 설정에서는 Analytics 데이터 수집 요청이 Audience Manager으로 전달되며, 이 요청은 페이지에 대한 Audience Manager 응답도 처리합니다.

이는 수년 동안 표준 접근 방식이었으며 현재 설정일 가능성이 높습니다. [!DNL AppMeasurement] 라이브러리에 `AudienceManagement` 모듈이 있고 데이터 수집 호출에 요청(`/b/ss/examplereportsuite/10/`)의 `/10/` 경로가 포함된 경우 이 안내서는 사용자를 위한 것입니다.

## SSF(서버 측 전달) 대 웹 SDK 데이터 흐름 {#data-flows}

Web SDK(및 Edge Network)로 이동할 때 Analytics와 Audience Manager 간의 데이터 흐름 차이를 이해하는 것은 아래 지침에 중요합니다.

서버측 전달을 통해 Analytics 지역 데이터 수집 노드는 데이터를 수집하여 Audience Manager이 수락하는 신호로 변환한 다음 Audience Manager으로 전송하고 Audience Manager 응답을 페이지로 반환합니다. 그런 다음 [!DNL AppMeasurement] 라이브러리의 [!DNL AudienceManagement] 모듈이 응답을 처리합니다(예: 쿠키 삭제, URL 대상 전송). 이 프로세스를 서버측 전달이라고 하는 이유는 Analytics가 Adobe 서버를 사용하여 데이터를 Audience Manager에 전달하기 때문입니다.

Web SDK를 사용하면 Edge Network이 별도의 작업으로 데이터를 Analytics와 Audience Manager에 보냅니다. Web SDK는 모든 솔루션에 데이터를 전송하는 단일 라이브러리이며, Edge Network은 솔루션에 관계없는 데이터 포인트를 솔루션별 형식으로 변환합니다.

이 새로운 데이터 흐름에서는 모든 데이터가 Edge Network [데이터스트림](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview)(으)로 전송되며, 필요에 따라 데이터를 Adobe 솔루션으로 보내도록 [구성](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure)할 수 있습니다. Audience Manager의 경우 데이터 스트림에서 Audience Manager 서비스를 활성화하면 [!DNL XDM] 및 Analytics 데이터가 Audience Manager에서 허용하는 신호로 변환됩니다. 또한 Edge Network은 [!DNL AppMeasurement] 및 [!DNL AudienceManagement] 모듈의 응답 방식과 유사한 방식으로 Web SDK가 응답을 처리하는 Audience Manager 응답을 페이지에 반환합니다.

## 태그와 비 태그 마이그레이션 {#tags-vs-non-tags}

[!DNL AppMeasurement] 확장명이 있는 태그, 다른 태그 관리 시스템에 있는 [!DNL AppMeasurement] 라이브러리 또는 페이지에 직접 [!DNL AppMeasurement]을(를) 배치하든 간에 Audience Manager을 Web SDK로 마이그레이션하는 단계는 동일합니다. Audience Manager 마이그레이션은 Analytics 마이그레이션에 따라 다르므로 Analytics 마이그레이션 중에 [!DNL AppMeasurement]에서 Web SDK로 마이그레이션하는 단계가 결정됩니다.

해당 정보는 Analytics 설명서에서 [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) 또는 [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) 기반 구현에 대해 다룹니다.

## XDM 및 `data.__adobe.` 노드 {#xdm-data-nodes}

[Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)의 기본 함수 중 하나는 데이터를 [RTCDP(Real-time Customer Data Platform)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home)에 보내는 것입니다. 이를 실현하고 완전히 다시 구현하지 않고 다른 Experience Cloud 솔루션에 대한 데이터를 계속 수집하기 위해 솔루션별 데이터는 데이터 수집 서버 호출 내에서 구분됩니다. 이 호출에서는 [XDM(경험 데이터 모델)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)이라는 표준화된 JSON 스키마를 사용합니다

브라우저 및 장치에 대한 정보와 같은 솔루션과 관계없는 요소는 미리 결정된 XDM 구조로 Edge Network에게 전송됩니다. 이 Edge Network은 이 데이터를 솔루션별 형식으로 변환합니다. 그러나 Target, Analytics 및 Audience Manager에 고유한 데이터는 XDM 페이로드 내의 전용 `data.__adobe` 노드에 저장됩니다.

예:

* Analytics 변수 `s.eVar1`이(가) XDM 페이로드에 `data.__adobe.analytics.evar1`(으)로 표시됩니다.
* 고객 충성도 상태와 관련된 Target 매개 변수는 `data.__adobe.target.loyaltyStatus`(으)로 저장됩니다.

데이터 스트림에서 Experience Platform 서비스가 활성화되어 있더라도 `__adobe` 노드의 데이터는 Experience Platform으로 전송되지 않고 각 솔루션(예: Analytics 및 Audience Manager)으로 전송됩니다. 즉, [데이터 수집을 위한 데이터 준비](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep)를 사용하여 Experience Platform에서 실시간 사용 사례를 위해 필요한 데이터 요소를 XDM 스키마 요소에 매핑하는 유연성을 가지면서 분석 및 Audience Manager에 대한 현재 구성을 유지할 수 있습니다.

예를 들어 체크아웃 중에 장바구니 컨텐츠를 보고하는 데 사용되는 Analytics `s.products` 문자열은 여전히 원래 형식으로 Analytics 및 Audience Manager에 보낼 수 있습니다. 동시에 이 문자열의 요소를 사용하여 Experience Platform 사용 사례에 대한 보다 직관적인 XDM 장바구니 스키마를 만들 수 있습니다.

대부분의 Audience Manager 구현은 Analytics에 전달된 Audience Manager 데이터를 사용하므로 대부분의 Audience Manager 트레이트 표현식은 Analytics 변수(`c_evar#`, `c_prop#` 및 `c_events`)를 기반으로 할 수 있습니다. 마이그레이션 중에 XDM 형식을 사용하여 트레이트 식을 다시 작성하지 않도록 `data.__adobe.analytics` 노드에 있는 모든 Analytics 변수를 Audience Manager 신호로 변환하도록 Edge Network이 기본적으로 구성됩니다. 이 프로세스는 서버 측 전달 워크플로우와 유사합니다.

Edge Network의 단일 데이터 수집 호출이 여러 Adobe 솔루션을 피드하는 단일 데이터 스트림으로 전송되므로 이 변환은 페이지에서 수행할 수 있습니다. 따라서 Analytics와 Audience Manager 모두에 대해 [!DNL AppMeasurement]에서 Web SDK로 마이그레이션하는 대부분의 경우 주로 `data.__adobe.analytics` 노드를 사용합니다.

Edge Network은 XDM 페이로드 및 패킷 헤더에서 장치 및 브라우저 데이터를 Audience Manager 신호로 변환합니다. 이렇게 하면 Audience Manager 트레이트 식에서 `h_` 및 `d_` 플랫폼 키를 계속 사용할 수 있습니다.

## `data.__adobe.audiencemanager` 노드 {#data-note}

`data.__adobe.audiencemanager` 노드는 Analytics에 의존하지 않는 Audience Manager 구현에 사용됩니다. [DIL 확장 마이그레이션 안내서](dil-extension-to-web-sdk.md)에 설명된 대로 이전에 [Audience Manager 라이브러리](../dil/dil-overview.md) 라이브러리를 통해 전송된 사용자 지정 키/값 쌍을 저장합니다.

이 안내서에 요약된 마이그레이션에 `data.__adobe.audiencemanager` 노드가 필요하지 않지만 여기에 설명된 새로운 데이터 흐름을 사용하면 Analytics에 기록되지 않고 데이터를 Audience Manager으로 보낼 수 있습니다.

사용자 지정 키/값 쌍을 Analytics에 포함하지 않고 Analytics로 보내야 하는 경우 `data.__adobe.audiencemanager` Audience Manager을 사용할 수 있습니다. 이 노드의 모든 데이터 세트는 데이터 수집 서버 호출에서 Audience Manager 변환된 Analytics 데이터에 추가됩니다.

## 이 구현 경로의 장단점

이러한 마이그레이션 접근 방식을 사용하면 장점과 단점이 모두 있습니다. 각 옵션을 신중히 평가하여 조직에 가장 적합한 접근 방식을 결정하십시오.

| 장점 | 단점 |
| --- | --- |
| <ul><li>**기존 구현을 사용**: 이 방법을 사용하려면 일부 구현을 변경해야 하지만 처음부터 완전히 새로운 구현이 필요하지 않습니다. 구현 논리를 최소한으로 변경하여 기존 데이터 레이어 및 코드를 사용할 수 있습니다.</li><li>**스키마가 필요하지 않습니다**: Web SDK로 마이그레이션하는 이 단계에서는 XDM 스키마가 필요하지 않습니다. 대신 Audience Manager으로 직접 데이터를 보내는 `data` 개체를 채울 수 있습니다. 웹 SDK로의 마이그레이션이 완료되면 조직에 대한 스키마를 만들고 데이터스트림 매핑을 사용하여 적용 가능한 XDM 필드를 채울 수 있습니다. 마이그레이션 프로세스의 이 단계에서 스키마가 필요한 경우 조직에서 Audience Manager XDM 스키마를 사용해야 합니다. 이 스키마를 사용하면 향후 조직에서 자체 스키마를 사용하는 것이 더 어려워집니다.</li></ul> | <ul><li>**구현 기술 부채**: 이 방법은 기존 구현의 수정된 형식을 사용하므로 구현 논리를 추적하고 필요한 경우 나중에 변경을 수행하는 것이 더 어려울 수 있습니다.</li><li>**데이터를 플랫폼에 보내려면 매핑이 필요합니다**: 조직에서 Real-Time CDP을 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. 이 작업을 수행하려면 `data` 개체의 모든 필드가 XDM 스키마 필드에 할당하는 데이터 스트림 매핑 도구의 항목이어야 합니다. 매핑은 이 워크플로우에 대해 한 번만 수행하면 되며 구현 변경을 수반하지 않습니다. 그러나 XDM 개체에서 데이터를 전송할 때는 필요하지 않은 추가 단계입니다.</li></ul> |

Adobe은 다음 시나리오에서 이 구현 경로를 따를 것을 권장합니다.

* Adobe Analytics AppMeasurement JavaScript 라이브러리를 사용하는 기존 구현이 있습니다. Audience Manager 태그 확장을 사용하는 구현이 있는 경우 대신 [Audience Manager 태그 확장에서 Web SDK 태그 확장으로 마이그레이션](dil-extension-to-web-sdk.md)을 따르십시오.
* 나중에 Real-Time CDP을 사용할 예정이지만 Audience Manager 구현을 처음부터 웹 SDK 구현으로 바꾸지는 않을 것입니다. 웹 SDK에서 구현을 처음부터 교체하려면 가장 많은 노력이 필요하지만 가장 실행 가능한 장기 구현 아키텍처도 제공합니다. 조직에서 깔끔한 웹 SDK 구현을 수행하려는 경우 자세한 내용은 [웹 SDK 설명서](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)를 참조하십시오.

## 웹 SDK로 마이그레이션하는 데 필요한 단계

데이터 수집 통합을 웹 SDK로 마이그레이션하려면 아래 단계를 따르십시오.

+++**1. Analytics 구현**&#x200B;을(를) 마이그레이션합니다.

Analytics 팀과 함께 [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) 또는 [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) 기반 구현에서 Analytics 마이그레이션 단계를 따릅니다. Analytics 구현을 마이그레이션한 후 다음 단계를 계속 진행합니다.

+++

+++**2. 데이터 스트림에 Audience Manager 서비스 추가**

1단계 동안 만든 데이터 스트림에 Audience Manager 서비스를 추가합니다.

1. [experience.adobe.com](https://experience.adobe.com)(으)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
1. **[!UICONTROL Data Collection]**(으)로 이동하려면 오른쪽 상단의 홈 페이지 또는 제품 선택기를 사용하십시오.
1. 왼쪽 탐색에서 **[!UICONTROL Datastreams]**&#x200B;을(를) 선택합니다.
1. 1단계에서 Analytics 마이그레이션의 일부로 만든 데이터 스트림을 선택합니다.
1. **[!UICONTROL Add Service]**&#x200B;을(를) 선택합니다.
1. 서비스 드롭다운 메뉴에서 **[!UICONTROL Audience Manager]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Cookie Destinations Enabled]** 및 **[!UICONTROL URL Destinations Enabled]** 옵션을 확인하십시오. 이 옵션을 사용하면 Edge Network은 이러한 Audience Manager 대상 유형을 페이지에 반환할 수 있습니다.
1. **[!UICONTROL Enable XDM Flattened Fields]**&#x200B;이(가) 비활성화되어 있는지 확인하십시오. 이 옵션은 Analytics 변수를 Audience Manager 신호로 자동 변환하는 기능을 비활성화합니다. 이 옵션은 Edge Network이 Analytics 데이터를 Audience Manager 신호로 자동 변환하기 전에 Web SDK로 마이그레이션한 사용자에 대한 이전 버전과의 호환성을 유지하도록 설계되었습니다.

   >[!NOTE]
   >
   >**[!UICONTROL Enabled XDM Flattened Fields]** 옵션이 활성화된 Web SDK로 마이그레이션하려면 XDM 형식의 Audience Manager에 필요한 모든 데이터와 prop, eVar 또는 이벤트를 사용하는 모든 Audience Manager 트레이트를 대신 업데이트하여 XDM 형식의 데이터를 찾아야 합니다. Adobe은 이 옵션을 비활성화하는 것을 권장합니다.


   ![Audience Manager 서비스 추가](assets/add-service.png) {style="border:1px solid lightslategray"}

1. 데이터 스트림 구성을 저장하려면 **[!UICONTROL Save]**&#x200B;을(를) 선택하십시오.

이제 데이터 스트림이 데이터를 받아서 Audience Manager에 전달할 준비가 되었습니다. 코드에서 웹 SDK를 구성할 때 이 ID가 필요하므로 데이터 스트림 ID를 참고하십시오.

+++

+++**3. 타사 ID 동기화를 사용하도록 설정하고 Audience Manager 컨테이너 ID**&#x200B;을(를) 설정합니다.

1. [experience.adobe.com](https://experience.adobe.com)(으)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
1. **[!UICONTROL Data Collection]**(으)로 이동하려면 오른쪽 상단의 홈 페이지 또는 제품 선택기를 사용하십시오.
1. 왼쪽 탐색에서 **[!UICONTROL Datastreams]**&#x200B;을(를) 선택합니다.
1. 1단계에서 Analytics 마이그레이션의 일부로 만든 데이터 스트림을 선택합니다.
1. 데이터 스트림 구성 페이지의 오른쪽 상단 모서리에서 **[!UICONTROL Edit]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Advanced Options]** 드롭다운 메뉴를 확장하고 아직 활성화되지 않은 경우 **[!UICONTROL Third Party ID Sync]** 기능을 활성화합니다. 이 옵션은 Edge Network에게 Audience Manager 및 Experience Platform 데이터 파트너에 대한 파트너 ID 동기화를 반환하도록 지시합니다.

   ![타사 ID 동기화를 사용합니다.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. 대부분의 경우 **[!UICONTROL Third Party ID Sync Container ID]** 필드를 비워 둘 수 있습니다. 기본적으로 `0`(으)로 설정됩니다. 그러나 올바른 컨테이너 ID가 사용되도록 하려면 다음 단계를 따르십시오.
   * 시크릿 또는 비공개 모드로 브라우저 창을 열고 마이그레이션에 포함된 페이지로 이동합니다.
   * 브라우저의 개발자 도구를 사용하여 `dpm.demdex.net/id`에 대한 네트워크 호출을 필터링합니다. 이 호출은 첫 번째 방문의 첫 페이지에서만 실행되므로 시크릿 또는 비공개 브라우저가 필요합니다.
   * 요청의 페이로드를 확인합니다. `d_nsid` 매개 변수가 0이 아니면 **[!UICONTROL Third Party ID Sync Container ID]** 필드에 복사하십시오.

1. **[!UICONTROL Save]**&#x200B;을(를) 선택합니다.

이제 데이터 스트림이 Audience Manager에 데이터를 보내고 Audience Manager 응답을 웹 SDK에 전달할 준비가 되었습니다.

+++

+++**4. ID 맵에 고객 ID 추가**

대부분의 Audience Manager 구현은 교차 장치 개인화 시나리오에서 [프로필 병합 규칙](../features/profile-merge-rules/merge-rules-overview.md)을 사용하며 인증 상태(로그인 또는 로그아웃)에 따라 방문자가 자격을 부여할 수 있는 세그먼트를 제어하는 데 도움이 됩니다. 프로필 병합 규칙을 사용하려면 인증 후 모든 데이터 수집 호출에서 고객 소유 식별자(CRM ID, 계정 번호 등)를 Audience Manager에게 보내야 합니다. 이전에는 방문자 ID 서비스([!DNL visitor.js])의 `setCustomerIDs` 함수를 사용하여 고객 ID를 각 Analytics 데이터 수집 호출에 추가한 다음 Audience Manager으로 전달했습니다.

웹 SDK을 사용하면 이제 [IdentityMap](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap)이라는 특수한 XDM 구문을 사용하여 이러한 ID를 Edge Network으로 전송해야 합니다.

ID 맵에서 ID를 올바르게 전달하려면 [ID 네임스페이스](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/namespaces)를 이해하고 전달할 ID를 신중하게 고려해야 합니다. 특히 Experience Platform 샌드박스로 데이터를 전송할 때 더욱 그렇습니다. [이 문서](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305)에서는 이러한 고려 사항과 지침을 간략하게 설명합니다.

전달할 ID와 시기를 결정했으면 Tags 내에서 [!UICONTROL Identity map] **[!UICONTROL Identity map]** [데이터 요소](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map)를 사용하기 위한 안내서를 따르거나 [ID 데이터 개요](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview)에 설명된 대로 수동으로 설정하여 웹 SDK 배포 전략에 맞게 조정하십시오.

+++

## Analytics 보고서 세트 관리자 UI에서 서버측 전달 및 Audience Analytics 구성 {#configure-ssf-analytics}

Analytics [서버측 전달](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) 기능을 잘 알고 있다면 &quot;*Analytics 데이터를 Audience Manager에게 두 번 보내지 않도록 Analytics Report Suite Manager UI에서 서버측 전달 설정을 비활성화해야 합니까?*&quot;라는 의문이 들 수 있습니다.

대답은 아니오입니다. 이 설정을 비활성화하면 안 됩니다. 이유는 다음과 같습니다.

이 설정을 사용하도록 설정하고 [!DNL AudienceManagement] 모듈을 페이지의 [!DNL AppMeasurement] 라이브러리에 추가하면 해당 보고서 세트로 전송된 모든 데이터도 Audience Manager으로 이동합니다.

GDPR 개인 정보 보호 규정을 준수하기 위해 Analytics에서는 데이터를 수집할 수 있지만 Audience Manager에서는 데이터를 수집할 수 없는 시나리오가 있습니다. 또한 일부 데이터 수집 호출이 Audience Manager으로 전송되지 않아야 하는 글로벌 보고서 세트와 관련된 사례와 지역별 사용 사례가 있습니다. 이 문제를 해결하기 위해 Adobe은 서버측 전달 &quot;끄기 버튼&quot;을 도입했습니다.

서버측 전달에 중점을 둔 [Analytics 및 GDPR 준수 페이지에서 설명한 대로](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr)에서 Analytics 데이터 수집 서버에 `cm.ssf=1` 컨텍스트 변수를 추가하면 해당 데이터 수집 호출이 Audience Manager으로 전달되지 않습니다.

이 설정을 사용하지 않도록 설정하는 이유는 두 가지가 있습니다.

1. Audience Manager 서비스가 데이터 스트림에서 활성화되면 Edge Network은 Analytics로 보낸 모든 데이터 수집 요청에 `cm.ssf` 변수를 추가합니다. 이렇게 하면 Analytics 데이터가 Audience Manager으로 전송되지 않습니다. Audience Manager 서비스가 데이터 스트림에서 활성화되면 Analytics 마이그레이션의 유효성을 검사하는 데 사용되는 모든 Assurance 로그에 `cm.ssf=1` 변수가 표시됩니다.
1. 이 설정을 사용하면 [!DNL Audience Analytics] 통합을 위한 데이터 흐름도 사용할 수 있습니다. [Audience Analytics 개요](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam)에 설명된 대로 Analytics 데이터 수집 서버에 대한 Audience Manager 응답이 처리 전에 Analytics 히트에 추가되므로 이 통합에는 서버측 전달이 필요합니다. Edge Network 내에서 유사한 프로세스가 발생합니다. 서버측 전달이 활성화되면 Edge Network은 Audience Manager 응답에서 Analytics로 전송된 데이터에 필요한 세그먼트를 추가합니다.

요약하면, Audience Analytics이 웹 SDK 구현과 함께 계속 작동하고 데이터가 Audience Manager에서 두 번 계산되지 않도록 이 설정을 활성화한 상태로 유지하는 것이 중요합니다.
