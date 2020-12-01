---
description: '사람 기반 대상을 사용하여 자사 고객 세그먼트를 사람 기반 환경으로 보냅니다. 이러한 환경은 안에 표시되는 컨텐츠를 제어하는 하나의 엔티티에 속한 폐쇄된 생태계입니다. 여기에는 Facebook과 같은 소셜 플랫폼과 고객 계정을 사용하여 표시된 컨텐츠를 개인화하는 기타 플랫폼이 포함됩니다. '
seo-description: '사람 기반 대상을 사용하여 자사 고객 세그먼트를 사람 기반 환경으로 보냅니다. 이러한 환경은 안에 표시되는 컨텐츠를 제어하는 하나의 엔티티에 속한 폐쇄된 생태계입니다. 여기에는 Facebook과 같은 소셜 플랫폼과 고객 계정을 사용하여 표시된 컨텐츠를 개인화하는 기타 플랫폼이 포함됩니다.  '
seo-title: 사용자 기반 대상 개요 및 사용 사례
solution: Audience Manager
title: 개요 및 사용 사례
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 1%

---


# 개요 및 사용 사례 {#overview-use-cases}

퍼스트 파티 대상 세그먼트를 사람 기반 환경으로 보내려면 [!DNL People-Based Destinations]을 사용합니다. 이러한 환경은 안에 표시되는 컨텐츠를 제어하는 하나의 엔티티에 속한 폐쇄된 생태계입니다. 여기에는 [!DNL Facebook]과 같은 소셜 플랫폼과 고객 계정을 사용하여 표시된 컨텐츠를 개인화하는 기타 플랫폼이 포함됩니다.

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 권고사항이다. 법률 자문을 위해 법률 자문을 구할 수 있습니다.

## 개요 {#overview}

[!DNL People-Based Destinations] 온라인 및 오프라인 데이터에 세그먼테이션을 적용하여 이메일 주소 또는 전화 번호 등 해시된 식별자를 기반으로  [고객 세그먼트를](people-based-destinations-prerequisites.md#hashing-requirements) 만들 수 있습니다. 그런 다음 이러한 세그먼트를 소셜 플랫폼에서 고객을 타깃팅할 수 있는 [!DNL Facebook]과 같은 &quot;벽으로 둘러싸인 정원&quot;으로 보낼 수 있습니다. [!DNL People-Based Destinations] 다음을 수행할 수 있습니다.

* 해시된 이메일 주소를 기반으로 하여 [!DNL Facebook] 등의 플랫폼에서 오프라인 및 온라인 고객 Target
* Audience Manager의 기존 장치 및 쿠키 타깃팅 기능 보완
* 타사 데이터 온보딩 솔루션과 관련된 비용 제거
* 맞춤형 데이터 온보딩 워크플로우 개발과 관련된 비용 제거
* 쿠키 없는 환경에서 Target 대상
* 고객 ID와 일치하는 해시된 이메일 주소를 중복 제거하여 고객 Target 대상

[!DNL People-Based Destinations]을(를) 사용하여 웹 사이트를 방문하지 않을 수 있는 고부가가치 고객을 세그먼트화하고 타게팅하거나 이미 오프라인으로 전환한 고객을 타깃팅하지 않을 수 있습니다. 또한 [!DNL Profile Merge Rules]을(를) 활용하여 오프라인 자사 데이터와 다른 Adobe Experience Cloud 솔루션의 고객 데이터를 비롯한 온라인 자사 데이터를 결합하여 소셜 미디어 광고 활동을 최적화할 수 있습니다.

![pbd-overview](assets/pbd-overview.png)

## 가용성 {#availability}

[!DNL People-Based Destinations] 프리미엄 Audience Manager 통합입니다. 이 프리미엄 기능을 활용하려면 Adobe 담당자에게 문의하십시오.

## [!UICONTROL People-Based Destinations] {#why-use}을 사용해야 하는 이유

**Audience Manager 내에서 전체 고객 세분화를 관리하여 일관된 크로스채널 경험을 제공할 수 있습니다.**

Audience Manager을 통해 사람 기반 채널에서 고객 세그먼트를 활성화하지 않으면 고객이 웹 사이트를 방문할 때 보는 것과 고객이 보게 되는 것(예: [!DNL Facebook] 피드)에서 보는 것 간에 경험이 단절됩니다. 채널 전반에서 일관된 타깃팅을 사용하면 광고 지출을 최적화하는 동시에 광고 수익을 향상시킬 수 있습니다.

**전용 데이터 온보딩 솔루션이나 사용자 정의 워크플로우를 사용하지 않고도 사람 기반의 채널에서 고객에게 도달할 수 있습니다.**

사람 기반 채널에서 고객을 타깃팅하는 보다 일반적인 방법은 광고하려는 플랫폼에서 허용하는 형식으로 고객 데이터를 내보낸 다음, 플랫폼의 전용 데이터 온보딩 방법을 사용하여 고객 데이터를 광고주 계정으로 가져와야 합니다. 광고하려는 각 플랫폼에 대해 수동으로 작업해야 합니다. 또한 서로 다른 플랫폼마다 서로 다른 데이터 형식 요구 사항이 있기 때문에 프로세스가 더 길어질 수 있습니다.

![pbd-overview](assets/pbd-diagram.png)

Audience Manager을 사용하면 고객 데이터를 중앙에서 관리하고 고객 세그먼트를 생성하며 여러 사람 기반 채널에서 활성화할 수 있습니다. [!DNL People-Based Destinations] 이러한 모든 작업을 Audience Manager 사용자 인터페이스 내에서 수행할 수 있으므로 각 플랫폼에 데이터를 수동으로 업로드하는 추가 작업을 하지 않아도 되므로 프로세스 시간을 절약할 수 있습니다.

**순전히 오프라인 프로필에서 고객 세그먼트를 만들고 활성화합니다.**

[!DNL People-Based Destinations] 이전에는 디바이스 활동을 기반으로 고객 세그먼트만 활성화할 수 있었던 문제를 해결했습니다. [!DNL People-Based Destinations]을(를) 사용하여 자신의 [!DNL CRM]에서 순전히 오프라인 데이터에서 세그먼트를 만들고, 사람 기반 플랫폼에서 활성화할 수 있습니다. 또한 오프라인 데이터를 Audience Manager에 이미 있는 장치 데이터와 상호 연관시킬 수 있습니다.

**Audience Manager의 데이터 거버넌스 및 개인 정보 제어 기능을 활용하여 고객 데이터를 안전하게 처리할 수 있습니다.**

[!DNL People-Based Destinations] 에는 되돌릴 수 없는 해시된 식별자만 사용해야 합니다. 이를 통해 각 대상 플랫폼에 고객 데이터를 수동으로 업로드하는 것과 관련된 위험을 줄일 수 있습니다.

[!UICONTROL People-Based Destinations]을(를) 사용할 때 데이터 흐름에 대한 개요를 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## 사용 사례 {#use-cases}

[!DNL People-Based Destinations]을 사용해야 하는 방법과 시기를 더 잘 이해할 수 있도록 Audience Manager 고객이 이 기능을 사용하여 해결할 수 있는 두 가지 샘플 사용 사례를 소개합니다.

### 사용 사례 #1 {#use-case-1}

온라인 소매업체는 소셜 플랫폼을 통해 기존 고객에게 도달하고 이전 주문에 따라 개인화된 제안을 제공하고자 합니다. 온라인 소매업체는 [!DNL People-Based Destinations]을(를) 사용하여 해시 처리된 이메일 주소를 자체 [!DNL CRM]에서 Audience Manager으로 인제스트하고, 자체 오프라인 데이터에서 세그먼트를 만들고, 이러한 세그먼트를 광고하려는 소셜 플랫폼으로 보내 광고 지출을 최적화할 수 있습니다.

### 사용 사례 #2 {#use-case-2}

항공사는 다양한 고객 계층(브론즈, 실버, 골드)을 보유하고 있으며 소셜 플랫폼을 통해 각 계층에 맞춤형 제안을 제공하려고 합니다. 이 회사는 Audience Manager을 사용하여 웹 사이트의 고객 활동을 분석합니다. 그러나 모든 고객이 항공사 모바일 앱을 사용하는 것은 아니며, 일부 고객은 회사의 웹사이트에 로그인하지 않았습니다. 회사가 이러한 고객에 대해 가지고 있는 유일한 식별자는 멤버십 ID와 이메일 주소입니다.

소셜 미디어 및 유사한 사용자 기반 채널에서 타깃팅하기 위해 해시 처리된 이메일 주소를 식별자로 사용하여 고객 데이터를 [!DNL CRM]의 Audience Manager으로 온정할 수 있습니다.

그런 다음 오프라인 데이터를 기존 온라인 활동 트레이트와 결합하여 새로운 고객 세그먼트를 만들어 [!DNL People-Based Destinations]을 통해 타깃팅할 수 있습니다.
