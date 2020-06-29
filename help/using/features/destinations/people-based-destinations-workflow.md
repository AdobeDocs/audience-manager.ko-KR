---
description: 인력 기반 목적지는 고객 데이터의 구성 방식에 따라 다양한 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 사람 기반 대상에 대해 수행해야 하는 구현 단계에 대한 개요를 제공합니다.
seo-description: '인력 기반 목적지는 고객 데이터의 구성 방식에 따라 다양한 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 사람 기반 대상에 대해 수행해야 하는 구현 단계에 대한 개요를 제공합니다.  '
seo-title: 사용자 기반 대상 구현 지침
solution: Audience Manager
title: 구현 지침
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1379'
ht-degree: 2%

---


# 구현 지침 {#implementation-guidance}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 권고사항이다. 법률 자문을 위해 법률 자문을 구할 수 있습니다.

[!DNL People-Based Destinations] 고객 데이터의 구성 방식에 따라 다양한 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 수행해야 하는 구현 단계 [!DNL People-Based Destinations]에 대한 개요를 제공합니다.

## 개요 {#overview}

이 구성 [!DNL People-Based Destinations] 은 여러 Audience Manager 섹션을 안내하고 Audience Manager에서 이미 보유하고 있는 고객 데이터의 종류와 수행하려는 대상 유형 등에 따라 서로 다른 설정 및 데이터 온보딩 방법이 필요합니다.

>[!IMPORTANT]
> 구성 전 [!DNL People-Based Destinations]에 이 아티클을 주의하여 완전히 읽으십시오. 이 가이드를 읽고 나면 다음을 통해 활성화할 시나리오에 대해 명확하게 이해해야 합니다 [!DNL People-Based Destinations].

사용하기 전에 분명히 해야 하는 6가지 구현 측면이 있습니다 [!DNL People-Based Destinations]. 이 문서는 현재 구성이 무엇인지 이해하는 데 도움이 되므로 시나리오에 대한 구현 단계를 올바르게 수행할 수 있습니다.

![pbd-implementation](assets/pbd-implementation.png)

## 1. 사용 사례 정의 {#defining-your-use-case}

구현을 시작하기 전에 이 기능 [!DNL People-Based Destinations]을 사용할 사용 사례를 명확하게 정의해야 합니다. 다음 두 가지 방법 [!DNL People-Based Destinations] 으로 대상 활동을 기반으로 대상을 타게팅할 수 있습니다.

**A) 통합된 온라인 및 오프라인 사용자 활동을 기반으로 하는 고객 타깃팅입니다**. 이 시나리오에서는 Audience Manager의 기존 대상 데이터와 내부 [!DNL CRM] 시스템의 데이터를 결합하고 결과 대상 세그먼트를 로 보내려고 합니다 [!DNL People-Based Destinations]. 다음은 이 시나리오를 보여주는 예입니다.

항공사인 귀사는 서로 다른 고객 계층(브론즈, 실버, 골드)을 가지며 각 계층에 소셜 플랫폼을 통해 개인화된 상품을 제공해야 합니다. Audience Manager을 사용하여 웹 사이트의 고객 활동을 분석합니다. 그러나 모든 고객이 항공사 모바일 앱을 사용하는 것은 아니며, 일부 고객은 회사의 웹사이트에 로그인하지 않았습니다. 고객 데이터는 대부분 멤버십 ID 및 이메일 주소로 제한됩니다.

소셜 미디어 및 유사한 사용자 기반 채널에서 타깃팅하기 위해 [해시된 이메일 주소를](people-based-destinations-prerequisites.md) Audience Manager으로 가져와 기존 온라인 활동 트레이트와 결합하여 새로운 고객 세그먼트를 만들 수 있습니다. 그런 다음 이러한 세그먼트를 사용하여 고객을 타깃팅할 수 있습니다 [!DNL People-Based Destinations].

**B) 오프라인 사용자 활동만을 기반으로 하는 고객 타깃팅**. 이 시나리오에서는 [!DNL CRM] 시스템에 고객 이메일 주소와 기타 고객 속성이 포함되어 있지만 고객은 웹 사이트와 전혀 상호 작용하지 않으므로 Audience Manager에서 고객 활동이 없습니다. 다음은 이 시나리오를 보여주는 예입니다.

텔레콤 서비스 제공업체인 Your company, a twitter services, keep customer data like email address, and purchased telecom plan in an internal [!DNL CRM]. 소셜 플랫폼의 기존 고객을 타깃팅하여 기존 구독을 기반으로 업그레이드 패키지를 제공하고자 합니다. 이렇게 하려면 해시된 고객 이메일 주소를 Audience Manager으로 인제스트하고 기존 고객 구독을 기반으로 세그먼트를 만들 수 있습니다. 그런 다음 이러한 세그먼트를 전송하여 개인화된 제안 [!DNL People-Based Destinations] 으로 고객을 타겟팅할 수 있습니다.

## 2. 타깃팅된 이메일 주소 유형을 정의합니다. {#define-target-email}

구현 전략을 정의하는 두 번째 단계는 타깃팅할 고객 이메일 주소 유형을 결정하는 것입니다.

**A) 인증된 이메일 주소를 기반으로 하는 대상 타깃팅입니다**. 이 시나리오에서는 사용자가 여러 이메일 주소와 연관된 여러 개의 계정을 가지고 있으며 웹 사이트에서 인증하는 이메일 주소를 기반으로 개인화된 오퍼로 타깃팅하고자 할 수 있습니다.

**B) 관련된 모든 이메일 주소를 기반으로 하는 대상 타깃팅입니다**. 이 시나리오에서는 사용자가 여러 이메일 주소와 연결된 여러 개의 계정을 가지고 있으며 인증된 활동과 관계없이 모든 연결된 이메일 주소에 걸쳐 계정을 타깃팅하려고 합니다.

## 3. 보유하고 있는 고객 ID(CRM ID)의 유형을 확인합니다. {#identify-customer-id}

의 대상을 타깃팅하려면 [!DNL People-Based Destinations] 고객 이메일 [주소의 해시된](people-based-destinations-prerequisites.md) 버전을 보내야 합니다. 기존 Audience Manager 구성에 따라 다음 두 가지 시나리오 중 하나를 통해 자신을 찾을 수 있습니다.

**A) Audience Manager 고객 ID([DPUUID](../../reference/ids-in-aam.md))가 이미 소문자이고 해시된 이메일 주소입니다**. 이 시나리오에서는 이러한 기존 ID를 사용하여 대상을 타깃팅할 수 있습니다 [!DNL People-Based Destinations].

**B) Audience Manager 고객 ID([DPUUIDs](../../reference/ids-in-aam.md))가 소문자가 아닙니다. 해시된 이메일 주소입니다**. 이 시나리오에서는 기존 고객 ID를 보낼 수 없습니다 [!DNL People-Based Destinations]. 이 [!DNL People-Based Destinations]를 사용하려면 기존 고객 ID와 고객 이메일 주소의 해시된 소문자 간 ID 동기화를 수행해야 합니다. 이렇게 하려면 [파일 기반 ID 동기화를](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 사용하거나 [선언된 ID를 사용합니다](../declared-ids.md).

## 4. 특성자격 {#trait-qualification}

고객을 정확하게 타깃팅하려면 [!DNL People-Based Destinations]수행하려는 대상 타깃팅 유형에 따라 사용자가 규칙 기반 트레이트나 온보드 트레이트에 대한 자격을 갖추어야 합니다.

**A) 규칙 기반의 트레이트를 위해 고객 ID와 디바이스 ID를 실시간으로 평가할 수 있습니다**. 이 옵션은 사용 사례 A에 [1부터 적용됩니다. 사용 사례 정의를 참조하십시오](people-based-destinations-workflow.md#defining-your-use-case). 온라인 및 오프라인 활동을 기반으로 고객을 타깃팅하려는 계획인 경우 [규칙 기반의 트레이트에 대한 대상을 이미 정해야 할 가능성이 높습니다](../traits/trait-and-segment-qualification-reference.md).

**B) 인바운드 데이터 파일을 통해 고객 ID에 대한 트레이트를 입상합니다**. 이 옵션은 [1의 사용 사례 B에 적용됩니다. 사용 사례 정의를 참조하십시오](people-based-destinations-workflow.md#defining-your-use-case). 순전히 오프라인 활동을 기반으로 고객을 타깃팅할 때 [인바운드 데이터 파일을 통해 온보딩 트레이트에 대한 고객 ID의 자격을 부여해야 합니다](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. 데이터 소스 및 해시된 이메일 주소를 만들거나 레이블을 지정합니다. {#create-label-data-sources}

Audience Manager에 있는 고객 ID 유형에 따라 다릅니다( [3 참조). 보유하고 있는](people-based-destinations-workflow.md#identify-customer-id)고객 ID(CRM ID)의 유형을 확인합니다. 다음 시나리오 중 하나를 통해 자신을 확인할 수 있습니다.

**A) 기존 데이터 소스에 레이블을 지정합니다**. 이 옵션은 Audience Manager 고객 ID([DPUUID](../../reference/ids-in-aam.md))가 이미 소문자이고 해시된 이메일 주소가 있는 시나리오에 적용됩니다. 이 경우 ID를 [!DNL PII] 데이터 소스로 저장하는 데이터 소스에 레이블을 지정하는 것이 필요합니다. 데이터 소스 [설정에 대한 자세한 내용은 데이터 소스](../datasources-list-and-settings.md) 설정을 참조하십시오. 개인 정보에 연결할 수 없음 옵션을 선택 취소해야 합니다.

**B) 새 데이터 소스를 만듭니다**. 이 옵션은 Audience Manager 고객 ID([DPUUID](../../reference/ids-in-aam.md))가 해시된 이메일 주소가 아닌 시나리오에 적용됩니다. 이 경우 새로운 크로스 디바이스 데이터 소스를 만들고 해시된 이메일 주소를 로그인해야 합니다. 다음 두 가지 방법으로 이 작업을 수행할 수 있습니다.

* 파일 기반 ID 동기화를 사용하십시오. ID 동기화 파일의 모습에 대한 자세한 내용은 [ID 동기화 파일 이름 및 컨텐츠 요구 사항](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)을 참조하십시오. When using this method, you can target all of your hashed email addresses from your [!DNL CRM] database.
* Use [declared IDs](../declared-ids.md) to declare your hashed email addresses when passing in authenticated customer IDs. 이 방법을 사용하는 경우 Audience Manager은 사용자를 대신하여 온라인에서 인증된 사용자의 해시된 이메일 주소만 타깃팅합니다. 사람 기반 채널에서 타깃팅된 이메일 주소는 선언된 ID 이벤트 호출의 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 활성화되지 않습니다.

## 6. 세그멘테이션에 프로필 병합 규칙 사용 {#use-profile-merge-rules}

사용 사례에 따라 다릅니다( [1 참조). 사용 사례](people-based-destinations-workflow.md#defining-your-use-case)정의)에는 두 가지 방법 [!DNL Profile Merge Rules] 으로 세그먼테이션을 사용할 수 있습니다.

**A) 기존[!DNL Profile Merge Rules]**을 사용합니다. 이 옵션은 첫 번째 사용 사례(결합된 온라인 및 오프라인 사용자 활동을 기반으로 하는 대상 타깃팅)에 적용됩니다. 이 시나리오에서는 Audience Manager에 기존 고객 활동이 있으며 세그멘테이션에 사용한 하나 이상의 프로필 병합 규칙을 이미 정의했습니다. 이 경우 새로 만들 필요가 없습니다[!DNL Profile Merge Rules].

**B) 병합 규칙을[!DNL All Cross-Device Profiles]새로 만듭니다**. 이 옵션은 두 번째 사용 사례(오프라인 사용자 활동만을 기반으로 하는 대상 타깃팅)에 적용됩니다. 이 시나리오에서는 오프라인 고객 데이터를 Audience Manager [!DNL CRM] 로 가져오고 해당 데이터에서 세그먼트를 만듭니다. 이렇게 하려면 네 번째 프로필 병합 규칙 [!DNL People-Based Destinations] 을 도입합니다. 이 규칙은 다음과 **[!DNL All Cross-Device Profiles]**&#x200B;같습니다. 이것은 순전히 오프라인 데이터를 세그먼트화할 때 사용해야 하는 규칙입니다.
