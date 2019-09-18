---
description: 이 문서에서는 Audience Manager UI에서 새 장치 기반 대상을 구성하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Manager UI에서 새 장치 기반 대상을 구성하는 방법에 대해 설명합니다.
seo-title: 새 장치 기반 대상 추가
solution: Audience Manager
title: 새 장치 기반 대상 추가
translation-type: tm+mt
source-git-commit: c206246a4a586d1148c18e0bce734d07963a85f6

---


# 새 장치 기반 대상 추가 {#add-new-device-based-destinations}

이 문서에서는 Audience Manager UI에서 새 장치 기반 대상을 구성하는 방법에 대해 설명합니다.

## 개요 {#overview}

새 장치 기반 대상을 추가하는 프로세스는 두 가지 기본 단계로 구성됩니다. 먼저 Audience Manager와 대상 파트너 간의 통합을 구성해야 합니다. 이렇게 하면 새 장치 기반 대상을 만들 수 있습니다.

## 전제 조건 {#prerequisites}

통합 플랫폼을 사용하여 첫 번째 장치 기반 대상을 만들 때는 Adobe Consulting 또는 고객 지원 센터에 연락하여 Audience Manager와 계정의 통합 플랫폼 간에 ID 동기화를 활성화하십시오. Audience Manager와 대상 플랫폼 간의 올바른 동기화를 위해 필요합니다.

>[!IMPORTANT]
>
>일부 장치 기반 대상이 셀프 서비스 구성 워크플로우에 적합한 것은 아닙니다. 추가해야 하는 장치 기반 대상이 대상 목록에 표시되지 않는 경우 Adobe 컨설턴트 또는 고객 지원에 문의하여 지원을 받으십시오.

## 1단계. 대상 플랫폼으로 인증 {#step1}

새 장치 기반 대상을 만들려면 먼저 Audience Manager와 대상 플랫폼 간의 통합을 구성해야 합니다. 이 작업을 수행하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인한 다음 로 **[!DNL Administration > Integrated Accounts]**&#x200B;이동합니다. 대상 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
1. 클릭 **[!DNL Add Account]**.
1. 인증할 대상 플랫폼을 선택하고 선택한 플랫폼의 인증 페이지로 **[!DNL Confirm]** 리디렉션하려면 을 클릭합니다. ![통합 플랫폼](assets/dbd-integrated-platforms.png)
1. 대상 플랫폼 계정으로 인증하면 연결된 광고주 계정이 표시되는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 을 **[!DNL Confirm]**&#x200B;클릭합니다.

## 2단계. 새 장치 기반 대상 만들기 {#step2}

대상 플랫폼 통합을 구성한 후 새 대상을 만들 수 있습니다. 이 작업을 수행하는 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 제공하십시오.

1. Audience Manager 계정에 로그인한 다음 **[!DNL Audience Data > Destinations]**&#x200B;으로 이동한 다음 을 클릭합니다 **[!DNL Create Destination]**.
1. 섹션에서 새 대상에 대한 **[!DNL Basic Information]** 및 **[!DNL Name]** **[!DNL Description]** 를 입력하고 아래 목록에 있는 설정을 사용하십시오. ![설정](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**:대상 세그먼트를 보낼 대상 플랫폼을 선택합니다.
   * **[!DNL Account]**:선택한 플랫폼과 연관된 원하는 광고주 계정을 선택합니다.
1. 클릭 **[!DNL Next]**.
1. 이 [대상에 대해](/help/using/features/data-export-controls.md#controls-labels) 설정할 데이터 내보내기 레이블을 선택합니다.
1. 클릭 **[!DNL Save]**.
1. 섹션에서 **[!DNL Segment Mappings]** 이 대상으로 전송할 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.
