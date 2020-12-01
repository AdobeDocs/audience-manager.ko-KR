---
description: 이 문서에서는 Audience Manager 사용자 인터페이스에서 새 장치 기반 대상을 구성하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Manager 사용자 인터페이스에서 새 장치 기반 대상을 구성하는 방법에 대해 설명합니다.
seo-title: 새 장치 기반 대상 추가
solution: Audience Manager
title: 새 장치 기반 대상 추가
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 4%

---


# 새 장치 기반 대상 추가 {#add-new-device-based-destinations}

이 문서에서는 Audience Manager 사용자 인터페이스에서 새 장치 기반 대상을 구성하는 방법에 대해 설명합니다.

>[!IMPORTANT]
>
>현재 대부분의 장치 기반 대상은 셀프 서비스 구성 작업 과정에 적합하지 않습니다. 추가해야 할 장치 기반 대상이 대상 목록에 표시되지 않는 경우 Adobe 컨설턴트 또는 고객 지원에 문의하십시오.

## 개요 {#overview}

새 장치 기반 대상을 추가하는 프로세스는 두 가지 기본 단계로 구성됩니다. 먼저 Audience Manager과 대상 파트너 간의 통합을 구성해야 합니다. 이렇게 하면 새 장치 기반 대상을 만들 수 있습니다.

## 사전 요구 사항 {#prerequisites}

통합 플랫폼을 사용하여 첫 번째 장치 기반 대상을 만들 때는 Adobe 컨설팅 또는 고객 지원 센터에 연락하여 Audience Manager과 계정에 대한 통합 플랫폼 간의 ID 동기화를 활성화하십시오. Audience Manager과 대상 플랫폼 간의 올바른 동기화를 위해 필요합니다.

## 1단계. 대상 플랫폼 {#step1}으로 인증

새 장치 기반 대상을 만들려면 먼저 Audience Manager과 대상 플랫폼 간의 통합을 구성해야 합니다. 이 작업을 수행하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!DNL Administration > Integrated Accounts]**&#x200B;으로 이동합니다. 대상 플랫폼과의 이전에 구성한 통합이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
1. 클릭 **[!DNL Add Account]**.
1. 인증할 대상 플랫폼을 선택하고 **[!DNL Confirm]**&#x200B;을 클릭하여 선택한 플랫폼의 인증 페이지로 리디렉션합니다.

   ![통합 플랫폼](assets/dbd-integrated-platforms.png)

1. 대상 플랫폼 계정으로 인증하면 연결된 광고주 계정을 볼 수 있는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!DNL Confirm]**&#x200B;을 클릭합니다.

## 2단계. 새 장치 기반 대상 만들기 {#step2}

대상 플랫폼 통합을 구성한 후에는 새 대상을 만들 수 있습니다. 이 작업을 수행하는 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 제공하십시오.

1. Audience Manager 계정에 로그인하고 **[!DNL Audience Data > Destinations]**&#x200B;으로 이동한 다음 **[!DNL Create Destination]**&#x200B;을 클릭합니다.
1. **[!DNL Basic Information]** 섹션에서 새 대상에 대해 **[!DNL Name]** 및 **[!DNL Description]**&#x200B;를 입력하고 아래 목록에 있는 설정을 사용하십시오.

   ![설정](assets/dbd-new-basic.png)

   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:대상 세그먼트를 보낼 대상 플랫폼을 선택합니다.
   * **[!DNL Account]**:선택한 플랫폼과 연관된 원하는 광고주 계정을 선택합니다.
1. 클릭 **[!DNL Next]**.
1. 이 대상에 대해 설정할 [데이터 내보내기 레이블](/help/using/features/data-export-controls.md#controls-labels)을 선택합니다.
1. 클릭 **[!DNL Save]**.
1. **[!DNL Segment Mappings]** 섹션에서 이 대상으로 전송할 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.
