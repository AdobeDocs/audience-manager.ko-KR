---
description: 사용자 기반 대상은 고객 데이터의 구성 방식에 따라 다양한 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 사람 기반 대상에 대해 수행해야 하는 구현 단계에 대한 개요를 제공합니다.
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: 구현 지침
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1350'
ht-degree: 2%

---

# 구현 지침 {#implementation-guidance}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용 방법을 안내하는 제품 설명서가 포함되어 있습니다. 여기에는 법률적인 조언이 들어 있지 않습니다. 법률 지도가 필요한 경우 법률 자문을 구하십시오.

[!DNL People-Based Destinations]은(는) 고객 데이터가 구조화되는 방식에 따라 다양한 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 [!DNL People-Based Destinations]에 대해 따라야 하는 구현 단계에 대한 개요를 제공합니다.

## 개요 {#overview}

[!DNL People-Based Destinations]을(를) 구성하면 Audience Manager의 여러 섹션을 볼 수 있으며, Audience Manager에 이미 있는 고객 데이터의 종류와 수행할 대상 타깃팅에 따라 서로 다른 설정 및 데이터 온보딩 메서드가 필요합니다.

>[!IMPORTANT]
> [!DNL People-Based Destinations]을(를) 구성하기 전에 이 문서를 주의 깊게 완전히 읽으십시오. 이 안내서를 읽은 후에는 [!DNL People-Based Destinations]을(를) 통해 활성화할 시나리오를 명확하게 이해해야 합니다.

[!DNL People-Based Destinations]을(를) 사용하기 전에 명확히 해야 하는 6가지 구현 측면이 있습니다. 이 문서는 시나리오의 구현 단계를 올바르게 따를 수 있도록 현재 구성이 무엇인지 이해하는 데 도움이 됩니다.

![pbd-implementation](assets/pbd-implementation.png)

## 1. 사용 사례 정의 {#defining-your-use-case}

[!DNL People-Based Destinations] 구현을 시작하기 전에 이 기능을 사용할 사용 사례를 명확히 정의해야 합니다. 대상 활동을 기반으로 두 가지 방법으로 대상을 타기팅하는 데 [!DNL People-Based Destinations]을(를) 사용할 수 있습니다.

**A) 온라인 및 오프라인 사용자 활동을 결합한 대상 타깃팅**. 이 시나리오에서는 Audience Manager의 기존 대상 데이터를 내부 [!DNL CRM] 시스템의 데이터와 결합하고 결과 대상 세그먼트를 [!DNL People-Based Destinations](으)로 보냅니다. 다음은 이 시나리오를 보여 주는 예입니다.

항공사인 귀사에는 다양한 고객 계층(브론즈, 실버 및 골드)이 있으며, 소셜 플랫폼을 통해 각 계층에 개인화된 오퍼를 제공하려고 합니다. Audience Manager을 사용하여 웹 사이트에서의 고객 활동을 분석합니다. 다만 모든 고객이 항공사의 모바일 앱을 사용하는 것은 아니며, 이들 중 일부는 회사 홈페이지에 로그인하지 않은 상태다. 고객 데이터는 대부분 멤버십 ID 및 이메일 주소로 제한됩니다.

소셜 미디어와 유사한 사용자 기반 채널에서 이러한 사용자를 타겟팅하려면 [해시된 이메일 주소](people-based-destinations-prerequisites.md)를 Audience Manager으로 가져와서 기존의 온라인 활동 트레이트와 결합하여 새로운 대상 세그먼트를 만들 수 있습니다. 그런 다음 이러한 세그먼트를 사용하여 [!DNL People-Based Destinations]을(를) 통해 대상자를 타깃팅할 수 있습니다.

**B) 오프라인 사용자 활동만을 기반으로 대상 타깃팅**. 이 시나리오에서는 [!DNL CRM] 시스템에 고객 이메일 주소와 기타 고객 특성이 포함되어 있지만 고객이 웹 사이트와 전혀 상호 작용하지 않았으므로 Audience Manager 시 고객 활동이 없습니다. 다음은 이 시나리오를 보여 주는 예입니다.

통신 서비스 공급자인 귀사는 내부 [!DNL CRM]에 전자 메일 주소 및 구매한 통신 계획과 같은 고객 데이터를 보관합니다. 소셜 플랫폼에서 기존 고객을 타겟팅하여 기존 구독을 기반으로 업그레이드 패키지를 제공하려고 합니다. 이를 위해 해시된 고객 이메일 주소를 Audience Manager에 수집하고 기존 고객 구독을 기반으로 세그먼트를 만들 수 있습니다. 그런 다음 이러한 세그먼트를 [!DNL People-Based Destinations]에 보내어 개인화된 오퍼로 고객을 타겟팅할 수 있습니다.

## 2. 타겟팅된 이메일 주소 유형 정의 {#define-target-email}

구현 전략을 정의하는 두 번째 단계는 타깃팅할 고객 이메일 주소 유형을 결정하는 것입니다.

**A) 인증된 이메일 주소를 기반으로 대상 타깃팅**. 이 시나리오에서는 여러 개의 계정이 여러 이메일 주소와 연결되어 있으며, 사용자가 웹 사이트에서 실시간으로 인증하는 이메일 주소만 기반으로 개인화된 오퍼를 통해 사용자를 타겟팅하려고 합니다.

**B) 연결된 모든 전자 메일 주소를 기반으로 대상 타깃팅**. 이 시나리오에서는 사용자가 여러 이메일 주소와 연결된 여러 계정을 가지며, 인증된 활동에 관계없이 연결된 모든 이메일 주소에서 해당 계정을 타겟팅하려고 합니다.

## 3. 보유하고 있는 고객 ID(CRM ID)의 유형을 식별합니다 {#identify-customer-id}

[!DNL People-Based Destinations]에서 대상을 타기팅하려면 고객 이메일 주소의 [SHA256 해시된](people-based-destinations-prerequisites.md) 버전을 보내야 합니다. 기존 Audience Manager 구성에 따라 다음 두 가지 시나리오 중 하나에 해당될 수 있습니다.

**A) Audience Manager 고객 ID([DPUUID](../../reference/ids-in-aam.md))가 이미 소문자이고 해시된 이메일 주소입니다**. 이 시나리오에서는 이러한 기존 ID를 사용하여 [!DNL People-Based Destinations]에서 대상을 타깃팅할 수 있습니다.

**B) Audience Manager 고객 ID([DPUUIDs](../../reference/ids-in-aam.md))가 소문자가 아니며 해시된 이메일 주소**&#x200B;입니다. 이 시나리오에서는 기존 고객 ID를 [!DNL People-Based Destinations](으)로 보낼 수 없습니다. [!DNL People-Based Destinations]을(를) 사용하려면 기존 고객 ID와 고객 이메일 주소의 해시된 소문자 버전 간에 ID 동기화를 수행해야 합니다. [파일 기반 ID 동기화](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)를 통해 또는 [선언된 ID](../declared-ids.md)를 사용하여 이 작업을 수행합니다.

## 4. 트레이트 자격 요건 {#trait-qualification}

[!DNL People-Based Destinations]에서 대상을 정확하게 타기팅하려면 사용자는 수행할 대상 타기팅 유형에 따라 규칙 기반 트레이트 또는 온보딩된 트레이트 중 하나를 사용할 자격이 있어야 합니다.

**A) 고객 ID 및 장치 ID를 실시간으로 규칙 기반 트레이트에 적합하게 만듭니다**. 이 옵션은 [1의 사용 사례 A에 적용됩니다. 사용 사례 정의](people-based-destinations-workflow.md#defining-your-use-case). 온라인 및 오프라인 활동을 기반으로 대상을 타기팅하는 계획이라면 이미 [규칙 기반 특성](../traits/trait-and-segment-qualification-reference.md)에 대해 대상에 자격을 부여하고 있을 것입니다.

**B) 인바운드 데이터 파일을 통해 고객 ID에 대한 트레이트를 온보딩합니다**. 이 옵션은 [1의 사용 사례 B에 적용됩니다. 사용 사례 정의](people-based-destinations-workflow.md#defining-your-use-case). 순전히 오프라인 활동을 기반으로 대상을 타기팅할 때 [인바운드 데이터 파일](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)을 통해 고객 ID를 온보딩된 트레이트에 적합하게 지정해야 합니다.

## 5. 데이터 소스 만들기 또는 레이블 지정 및 해시된 이메일 주소 온보드 {#create-label-data-sources}

Audience Manager에 있는 고객 ID 유형에 따라 다릅니다([3 참조). 보유 중인 고객 ID(CRM ID)의 유형을 식별하면 다음 시나리오 중 하나를 받게 됩니다.](people-based-destinations-workflow.md#identify-customer-id)

**A) 기존 데이터 원본에 레이블을 지정합니다**. 이 옵션은 Audience Manager 고객 ID([DPUUIDs](../../reference/ids-in-aam.md))가 이미 소문자이고 해시된 이메일 주소인 시나리오에 적용됩니다. 이 경우 ID를 [!DNL PII] 데이터 소스로 저장하는 데이터 소스에 레이블을 지정해야 합니다. 데이터 원본 설정에 대한 자세한 내용은 [데이터 Source 설정](../datasources-list-and-settings.md)을 참조하세요. 개인 식별 정보에 연결할 수 없음 옵션의 선택을 취소해야 합니다.

**B) 새 데이터 원본을 만듭니다**. 이 옵션은 Audience Manager 고객 ID([DPUUIDs](../../reference/ids-in-aam.md))가 해시된 이메일 주소가 아닌 시나리오에 적용됩니다. 이 경우 새 크로스 디바이스 데이터 소스를 만들고 이에 대해 해시된 이메일 주소를 온보딩해야 합니다. 다음 두 가지 방법으로 이 작업을 수행할 수 있습니다.

* 파일 기반 ID 동기화를 사용합니다. ID 동기화 파일의 모습에 대한 자세한 내용은 [ID 동기화 파일 이름 및 컨텐츠 요구 사항](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)을 참조하십시오. 이 메서드를 사용하는 경우 [!DNL CRM] 데이터베이스에서 해시된 모든 이메일 주소를 타겟팅할 수 있습니다.
* 인증된 고객 ID를 전달할 때 [선언된 ID](../declared-ids.md)를 사용하여 해시된 이메일 주소를 선언하십시오. 이 방법을 사용하는 경우 귀하를 대신하여 Audience Manager은 온라인에서 인증된 사용자의 해시된 이메일 주소만 타겟팅합니다. 사용자 기반 채널에서 타겟팅되는 이메일 주소는 선언된 ID 이벤트 호출에 있는 이메일 주소만 해당됩니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 활성화되지 않습니다.

## 6. 세분화를 위해 프로필 병합 규칙 사용 {#use-profile-merge-rules}

사용 사례에 따라 다릅니다([1 참조). 사용 사례 ](people-based-destinations-workflow.md#defining-your-use-case)을(를) 정의하면 세분화를 위해 [!DNL Profile Merge Rules]을(를) 사용하는 두 가지 방법이 있습니다.

**A) 기존[!DNL Profile Merge Rules]**&#x200B;을(를) 사용합니다. 이 옵션은 첫 번째 사용 사례(온라인과 오프라인의 결합된 사용자 활동을 기반으로 하는 대상 타깃팅)에 적용됩니다. 이 시나리오에서는 Audience Manager에 기존 고객 활동이 있고 세분화에 사용한 프로필 병합 규칙을 하나 이상 이미 정의했습니다. 이 경우 새 [!DNL Profile Merge Rules]을(를) 만들 필요가 없습니다.

**B) 새 [!DNL All Cross-Device Profiles] 병합 규칙을 만듭니다**. 이 옵션은 두 번째 사용 사례(오프라인 사용자 활동만을 기반으로 하는 대상 타깃팅)에 적용됩니다. 이 시나리오에서는 오프라인 고객 데이터를 [!DNL CRM]에서 Audience Manager으로 가져오고 해당 데이터에서 세그먼트를 만들려고 합니다. 이를 위해 [!DNL People-Based Destinations]은(는) **[!DNL All Cross-Device Profiles]**&#x200B;이라는 새로운 네 번째 프로필 병합 규칙을 도입합니다. 순수하게 오프라인 데이터를 세그먼트화할 때 사용해야 하는 규칙입니다.
