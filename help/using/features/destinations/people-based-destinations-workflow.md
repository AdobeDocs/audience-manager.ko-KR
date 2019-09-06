---
description: 사용자 기반 대상은 고객 데이터가 구조화되는 방식에 따라 여러 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 사람 기반 대상에 대해 따라야 하는 구현 단계에 대한 개요를 제공합니다.
seo-description: '사용자 기반 대상은 고객 데이터가 구조화되는 방식에 따라 여러 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 사람 기반 대상에 대해 따라야 하는 구현 단계에 대한 개요를 제공합니다.  '
seo-title: 인물 기반 대상 구현 지침
solution: Audience Manager
title: 구현 지침
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# 구현 지침 {#implementation-guidance}

[!DNL People-Based Destinations] 고객 데이터가 구조화되는 방식에 따라 다양한 구현 전략을 제공합니다. 이 문서에서는 시나리오에 따라 따라야 하는 구현 단계에 대한 [!DNL People-Based Destinations]개요를 제공합니다.

## 개요 {#overview}

구성은 Audience Manager의 여러 섹션을 통해 [!DNL People-Based Destinations] 이루어지며, Audience Manager에서 이미 보유하고 있는 고객 데이터와 수행하려는 대상 타깃팅에 따라 다른 설정 및 데이터 교육 방법을 필요로 합니다.

>[!IMPORTANT]
> 구성하기 [!DNL People-Based Destinations]전에 반드시 이 문서를 정확하고 완전하게 읽으십시오. 이 안내서를 읽고 나면 활성화할 시나리오를 명확하게 이해해야 [!DNL People-Based Destinations]합니다.

사용하기 전에 명확히 해야 하는 구현 측면에는 [!DNL People-Based Destinations]6 가지가 있습니다. 이 문서는 현재 구성이 무엇인지 이해하는 데 도움이 되므로 시나리오의 구현 단계를 올바로 따를 수 있습니다.

![PBD-구현](assets/pbd-implementation.png)

## 1. 사용 사례 정의 {#defining-your-use-case}

구현을 [!DNL People-Based Destinations]시작하기 전에 이 기능을 사용할 사용 사례를 명확하게 정의해야 합니다. 고객 활동을 [!DNL People-Based Destinations] 기반으로 두 가지 방법으로 대상을 타깃팅할 수 있습니다.

**A) 통합 온라인 및 오프라인 사용자 활동을**&#x200B;기반으로 한 고객 타깃팅 이 시나리오에서는 Audience Manager의 기존 대상 데이터를 내부 [!DNL CRM] 시스템의 데이터와 결합하고 결과 대상 세그먼트를 [!DNL People-Based Destinations]발송할 수 있습니다. 다음은 시나리오를 보여주는 예입니다.

항공사, 항공사는 서로 다른 고객 계층 (브론즈, 실버 및 골드) 를 가지며 소셜 플랫폼을 통해 개인화된 제안을 각 계층에 제공하려고 합니다. Audience Manager를 사용하여 웹 사이트에서 고객 활동을 분석할 수 있습니다. 그러나 일부 고객은 항공사의 모바일 앱을 사용하는 것은 아니며 일부 고객은 회사의 웹 사이트에 로그인하지 않았습니다. 고객 데이터는 주로 멤버십 ID와 이메일 주소로 제한됩니다.

소셜 미디어 및 유사한 인물 기반 채널에서 타깃팅하려면 [해시된 이메일 주소를 Audience Manager](people-based-destinations-prerequisites.md) 로 가져와 기존 온라인 활동 트레이트와 결합하여 새로운 고객 세그먼트를 구축할 수 있습니다. 다음으로, 세그먼트를 사용하여 대상을 [!DNL People-Based Destinations]타깃팅할 수 있습니다.

**B) 오프라인 사용자 활동을**&#x200B;기반으로 한 대상 타깃팅 이 시나리오에서는 [!DNL CRM] 시스템에 고객 이메일 주소 및 기타 고객 속성이 포함되어 있지만 고객은 웹 사이트와 상호 작용하지 않아 Audience Manager에 고객 활동이 없습니다. 다음은 시나리오를 보여주는 예입니다.

텔레콤 서비스 제공업체인 Your Company는 이메일 주소와 같은 고객 데이터를 보관하고 내부 텔레콤 플랜을 내부에 [!DNL CRM]구입합니다. 소셜 플랫폼에서 기존 고객을 타깃팅하여 기존 구독을 기반으로 업그레이드 패키지를 제공할 수 있습니다. 이를 위해 고객 이메일 주소를 Audience Manager로 해시하여 기존 고객 구독을 기반으로 세그먼트를 만들 수 있습니다. 그런 다음 이러한 세그먼트를 전송하여 [!DNL People-Based Destinations] 개인화된 제안을 통해 고객을 타겟팅할 수 있습니다.

## 2. 타깃팅된 이메일 주소 유형 정의 {#define-target-email}

구현 전략을 정의하는 두 번째 단계는 타깃팅할 고객 이메일 주소 유형을 결정하는 것입니다.

**A) 인증된 이메일 주소를**&#x200B;기반으로 대상 타깃팅 이 시나리오에서는 사용자가 여러 개의 이메일 주소와 연결된 여러 개의 계정을 가지고 있으며, 웹 사이트에서 실시간으로 인증한 이메일 주소만 기반으로 개인화된 오퍼로 타깃팅하려고 합니다.

**B) 연결된 모든 이메일 주소를**&#x200B;기반으로 대상 타깃팅 이 시나리오에서는 사용자에게 여러 개의 이메일 주소와 연결된 계정이 여러 개 있으며 인증된 활동에 관계없이 연결된 모든 이메일 주소에 걸쳐 타깃팅하려고 합니다.

## 3. 보유한 고객 ID (CRM ID) 유형 식별 {#identify-customer-id}

대상을 [!DNL People-Based Destinations] 타깃팅하려면 고객 이메일 주소의 [SHA 256 해시](people-based-destinations-prerequisites.md) 버전을 전송해야 합니다. 기존 Audience Manager 구성에 따라 다음 두 가지 시나리오 중 하나를 사용할 수 있습니다.

**A) Audience Manager 고객 ID ([DPUUIDS](../../reference/ids-in-aam.md)) 는 이미 소문자인 해시된 이메일 주소입니다**. 이 시나리오에서는 이러한 기존 ID를 사용하여 대상을 [!DNL People-Based Destinations]타깃팅할 수 있습니다.

**B) Audience Manager 고객 ID ([DPUUIDS](../../reference/ids-in-aam.md)) 는 소문자로 해시된 이메일 주소가 아닙니다**. 이 시나리오에서는 기존 고객 ID를 보낼 [!DNL People-Based Destinations]수 없습니다. 사용하려면 [!DNL People-Based Destinations]기존 고객 ID와 해시된 버전의 고객 이메일 주소 사이에 ID 동기화를 수행해야 합니다. 파일 기반 ID 동기화를 사용하거나 [선언된 ID를 사용하여](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) [이 작업을](../declared-ids.md)수행합니다.

## 4. 특성 자격 조건 {#trait-qualification}

고객을 정확하게 [!DNL People-Based Destinations]타겟팅하려면 수행하려는 대상 타깃팅의 유형에 따라 규칙 기반 또는 온보드 트레이트에 대한 자격을 갖추어야 합니다.

**A) 규칙 기반의 트레이트에**&#x200B;대한 고객 ID 및 디바이스 ID를 실시간으로 검증 이 옵션은 1의 사용 사례 A에 [적용됩니다. 사용 사례 정의를](people-based-destinations-workflow.md#defining-your-use-case)참조하십시오. 온라인 및 오프라인 활동을 기반으로 대상 고객을 타깃팅하는 경우, 규칙 기반의 트레이트에 대한 [잠재 고객을](../traits/trait-qualification-reference.md)이미 자격을 갖추게 됩니다.

**B) 인바운드 데이터 파일을 통해 고객 ID에 대한 트레이트를 실행합니다**. 이 옵션은 1의 사용 사례 B에 [적용됩니다. 사용 사례 정의를](people-based-destinations-workflow.md#defining-your-use-case)참조하십시오. 순전히 오프라인 활동을 기반으로 고객을 타깃팅할 때에는 인바운드 데이터 파일을 통해 [온보드 트레이트에 대한 고객 ID를 정규화해야](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)합니다.

## 5. 데이터 소스 생성 또는 레이블 지정 해싱된 이메일 주소 {#create-label-data-sources}

Audience Manager에 있는 고객 ID 유형에 따라 [다릅니다 (3 참조. 보유하고 있는](people-based-destinations-workflow.md#identify-customer-id)고객 ID (CRM ID) 유형을 식별하면 다음 시나리오 중 하나를 사용할 수 있습니다.

**A) 기존 데이터 소스에 레이블을 지정합니다**. 이 옵션은 Audience Manager 고객 ID ([DPUUIDS](../../reference/ids-in-aam.md)) 가 이미 소문자인 해시된 이메일 주소인 시나리오에 적용됩니다. 이 경우, ID를 [!DNL PII] 데이터 소스로 저장하는 데이터 소스에 레이블을 지정하면 됩니다. 데이터 소스 설정에 대한 자세한 내용은 [데이터 소스 설정을](../datasources-list-and-settings.md) 참조하십시오. 이렇게 하려면 [개인 식별 가능 정보에 연결 안 함] 옵션을 선택 해제해야 합니다.

**B) 새 데이터 소스를 만듭니다**. 이 옵션은 Audience Manager 고객 ID ([DPUUIDS](../../reference/ids-in-aam.md)) 가 해시된 이메일 주소가 아닌 시나리오에 적용됩니다. 이 경우, 새 크로스 장치 데이터 소스를 만들고 그에 대해 해시된 이메일 주소를 적용해야 합니다. 다음 두 가지 방법으로 수행할 수 있습니다.

* 파일 기반 ID 동기화 사용 ID [동기화 파일에 대한 자세한 내용은 ID 동기화 파일에](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 대한 이름 및 컨텐츠 요구 사항을 참조하십시오. 이 방법을 사용하는 경우 [!DNL CRM] 데이터베이스에서 해시된 모든 이메일 주소를 타깃팅할 수 있습니다.
* 인증된 고객 ID를 전달할 때 [선언된 ID](../declared-ids.md) 를 사용하여 해시된 이메일 주소를 선언합니다. 이 방법을 사용할 경우 Audience Manager는 온라인으로 인증된 사용자의 해시된 이메일 주소만 타깃팅합니다. Facebook를 통해 타깃팅된 이메일 주소는 선언된 ID 이벤트 호출의 이메일 주소입니다. 고객 ID와 연결된 다른 이메일 주소는 실시간으로 활성화되지 않습니다.

## 6. 세그멘테이션에 프로필 병합 규칙 사용 {#use-profile-merge-rules}

사용 사례에 따라 [(1. 사용 사례](people-based-destinations-workflow.md#defining-your-use-case)정의를 [!DNL Profile Merge Rules] 참조하십시오.

**A)[!DNL Profile Merge Rules]**&#x200B;기존 버전을 사용합니다. 이 옵션은 첫 번째 사용 사례에 적용됩니다 (결합된 온라인 및 오프라인 사용자 활동을 기반으로 대상 타깃팅). 이 시나리오에서는 Audience Manager에서 기존 고객 활동을 가지고 있으며 세그멘테이션에서 사용한 프로필 병합 규칙을 이미 하나 이상 정의했습니다. [!DNL Profile Merge Rules]이 경우 새로 만들 필요가 없습니다.

**B) 새 규칙[!DNL All Cross-Device Profiles]병합 규칙을 만듭니다**. 이 옵션은 두 번째 사용 사례에 적용됩니다 (오프라인 사용자 활동만을 기반으로 대상 타깃팅). 이 시나리오에서는 오프라인 고객 데이터를 Audience Manager에서 [!DNL CRM] 가져오는 중이며 해당 데이터에서 세그먼트를 만들고자 합니다. 이렇게 하려면 [!DNL People-Based Destinations] 새로운 네 번째 프로필 병합 규칙 (호출된 **[!DNL All Cross-Device Profiles]**&#x200B;규칙) 를 도입하십시오. 이것은 순전히 오프라인 데이터를 세그먼트화할 때 사용해야 하는 규칙입니다.
