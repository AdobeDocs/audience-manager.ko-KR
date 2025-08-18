---
description: 사용자 기반 대상을 사용하여 자사 대상 세그먼트를 사용자 기반 환경으로 보냅니다. 이러한 환경은 그 안에 표시되는 콘텐츠를 제어하는 하나의 엔티티에 속하는 폐쇄형 생태계입니다. 여기에는 Facebook과 같은 소셜 플랫폼과, 고객 계정에 의존하여 표시된 콘텐츠를 개인화하는 기타 플랫폼이 포함됩니다.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: 개요 및 사용 사례
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# 개요 및 사용 사례 {#overview-use-cases}

[!DNL People-Based Destinations]을(를) 사용하여 자사 대상 세그먼트를 사용자 기반 환경으로 보냅니다. 이러한 환경은 그 안에 표시되는 콘텐츠를 제어하는 하나의 엔티티에 속하는 폐쇄형 생태계입니다. 여기에는 [!DNL Facebook]과(와) 같은 소셜 플랫폼과 고객 계정에 의존하여 표시된 콘텐츠를 개인화하는 기타 플랫폼이 포함됩니다.

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용 방법을 안내하는 제품 설명서가 포함되어 있습니다. 여기에는 법률적인 조언이 들어 있지 않습니다. 법률 지도가 필요한 경우 법률 자문을 구하십시오.

## 개요 {#overview}

[!DNL People-Based Destinations]을(를) 사용하면 온라인 및 오프라인 데이터에 세그멘테이션을 적용하여 전자 메일 주소와 같은 [해시된 식별자](people-based-destinations-prerequisites.md#hashing-requirements)를 기반으로 대상 세그먼트를 만들 수 있습니다. 그런 다음 이러한 세그먼트를 [!DNL Facebook]과(와) 같은 &quot;담으로 둘러싸인 정원&quot;에 보내면 소셜 플랫폼에서 대상자를 타깃팅할 수 있습니다. [!DNL People-Based Destinations]이(가) 도움을 줄 수 있습니다.

* 해시된 이메일 주소를 기반으로 [!DNL Facebook]과(와) 같은 플랫폼의 오프라인 및 온라인 대상자를 타깃팅합니다.
* Audience Manager의 기존 장치 및 쿠키 타깃팅 기능 보완
* 타사 데이터 온보딩 솔루션과 관련된 비용 절감
* 맞춤형 데이터 온보딩 워크플로우 개발과 관련된 비용 절감
* 쿠키가 없는 환경에서 대상을 타깃팅합니다.
* 고객 ID와 일치하는 해시된 이메일 주소를 중복 제거하여 대상을 타깃팅합니다.

[!DNL People-Based Destinations]을(를) 사용하여 웹 사이트를 방문하지 않았을 수 있는 고부가가치 고객을 세분화하고 타겟팅하거나 이미 오프라인으로 전환한 고객을 타겟팅하는 작업을 중단할 수 있습니다. 또한 [!DNL Profile Merge Rules]을(를) 활용하여 오프라인 자사 데이터와 다른 Adobe Experience Cloud 솔루션의 고객 데이터를 포함한 온라인 자사 데이터를 결합하여 소셜 미디어 광고 노력을 최적화할 수 있습니다.

![pbd-overview](assets/pbd-overview.png)

## 가용성 {#availability}

[!DNL People-Based Destinations]은(는) 프리미엄 Audience Manager 통합입니다. 이 프리미엄 기능을 활용하려면 Adobe 담당자에게 문의하십시오.

## [!UICONTROL People-Based Destinations]을(를) 사용하는 이유 {#why-use}

**Audience Manager 내에서 전체 대상자 세분화를 관리하여 고객에게 일관된 크로스 채널 경험을 제공합니다.**

Audience Manager을 통해 사용자 기반 채널에서 대상 세그먼트를 활성화하지 않으면 고객이 웹 사이트를 방문할 때 보게 되는 내용과 [!DNL Facebook] 피드에서 보게 되는 내용 간에 일치하지 않는 경험이 발생합니다. 채널 간에 일관된 타겟팅을 확보하면 광고 지출을 최적화하는 동시에 광고 매출을 높일 수 있습니다.

**대상자를 보내기 위한 전용 데이터 온보딩 솔루션이나 사용자 지정 워크플로 없이도 사용자 기반 채널에서 대상자에게 도달할 수 있습니다.**

사용자 기반 채널에서 대상을 타기팅하는 보다 &quot;일반적인&quot; 방법에는 고객 데이터를 광고하려는 플랫폼에서 허용하는 형식으로 내보낸 다음 플랫폼의 전용 데이터 온보딩 방법을 사용하여 고객 데이터를 광고주 계정으로 가져와야 하는 작업이 포함됩니다. 이는 광고하려는 각 플랫폼에 대해 수행해야 하는 모든 수동 작업입니다. 또한 플랫폼마다 데이터 형식 요구 사항이 다를 수 있으므로 프로세스가 훨씬 더 지루할 수 있습니다.

![pbd-overview](assets/pbd-diagram.png)

Audience Manager은 [!DNL People-Based Destinations]을(를) 통해 고객 데이터를 중앙 집중화하고, 대상 세그먼트를 만들고, 여러 사용자 기반 채널에서 활성화할 수 있도록 지원합니다. Audience Manager 사용자 인터페이스 내에서 이 모든 작업을 수행할 수 있으므로 데이터를 각 플랫폼에 수동으로 업로드하는 추가 작업을 피할 수 있으므로 프로세스에서 귀중한 시간을 절약할 수 있습니다.

**완전히 오프라인 프로필에서 대상 세그먼트를 만들고 활성화합니다.**

[!DNL People-Based Destinations] 이전에는 장치 활동을 기반으로 대상 세그먼트만 활성화할 수 있었던 문제를 해결했습니다. [!DNL People-Based Destinations]을(를) 사용하면 사용자의 [!DNL CRM]에서 완전히 오프라인 데이터로 세그먼트를 만들고 사용자 기반 플랫폼에서 활성화할 수 있습니다. 또한 오프라인 데이터를 Audience Manager에 이미 있는 장치 데이터와 상호 연관시킬 수 있습니다.

**Audience Manager의 데이터 거버넌스 및 개인 정보 보호 컨트롤을 활용하여 고객 데이터를 안전하게 처리하십시오.**

[!DNL People-Based Destinations]에서는 비가역적으로 해시된 식별자만 사용해야 합니다. 이렇게 하면 고객 데이터를 각 대상 플랫폼에 수동으로 업로드하는 것과 관련된 위험이 줄어듭니다.

[!UICONTROL People-Based Destinations]을(를) 사용할 때 데이터 흐름에 대한 개요를 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/31969?captions=kor)

## 사용 사례 {#use-cases}

[!DNL People-Based Destinations]을(를) 사용하는 방법과 시기를 더 잘 이해할 수 있도록 Audience Manager 고객이 이 기능을 사용하여 해결할 수 있는 두 가지 샘플 사용 사례를 소개합니다.

### 사용 사례 #1 {#use-case-1}

온라인 retailer은 소셜 플랫폼을 통해 기존 고객에게 도달하고 이전 주문을 기반으로 개인화된 오퍼를 표시하려고 합니다. [!DNL People-Based Destinations]을(를) 사용하면 온라인 retailer이 자체 [!DNL CRM]에서 Audience Manager으로 해시된 이메일 주소를 수집하고, 자체 오프라인 데이터에서 세그먼트를 작성하고, 광고 지출을 최적화하여 광고하려는 소셜 플랫폼으로 이러한 세그먼트를 보낼 수 있습니다.

### 사용 사례 #2 {#use-case-2}

항공사에는 다양한 고객 계층(브론즈, 실버 및 골드)이 있으며 소셜 플랫폼을 통해 각 계층에 개인화된 오퍼를 제공하려고 합니다. 이 회사는 Audience Manager을 사용하여 웹 사이트에서의 고객 활동을 분석합니다. 다만 모든 고객이 항공사의 모바일 앱을 사용하는 것은 아니며, 이들 중 일부는 회사 홈페이지에 로그인하지 않은 상태다. 회사에 이러한 고객에 대한 유일한 식별자는 멤버십 ID와 이메일 주소입니다.

소셜 미디어와 유사한 사용자 기반 채널에서 사용자를 타겟팅하기 위해 해시된 이메일 주소를 식별자로 사용하여 [!DNL CRM]에서 Audience Manager으로 고객 데이터를 온보딩할 수 있습니다.

그런 다음 오프라인 데이터를 기존의 온라인 활동 트레이트와 결합하여 [!DNL People-Based Destinations]을(를) 통해 타깃팅할 수 있는 새 대상 세그먼트를 만들 수 있습니다.
