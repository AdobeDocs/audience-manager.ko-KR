---
description: 이 문서에서는 Audience Manager UI에서 새 장치 기반 대상을 구성하는 방법을 설명합니다.
seo-description: 이 문서에서는 Audience Manager UI에서 새 장치 기반 대상을 구성하는 방법을 설명합니다.
seo-title: 새 장치 기반 대상 추가
solution: Audience Manager
title: 새 장치 기반 대상 추가
translation-type: tm+mt
source-git-commit: d185a1d418e99abb99c36b28dfb419a1fb3b60f5

---


# 새 장치 기반 대상 추가 {#add-new-device-based-destinations}

이 문서에서는 Audience Manager UI에서 새 장치 기반 대상을 구성하는 방법을 설명합니다.

## 개요 {#overview}

새 장치 기반 대상을 추가하는 프로세스는 두 가지 주요 단계로 구성됩니다. 먼저 대상 관리자와 대상 파트너 간의 통합을 구성해야 합니다. 이렇게 하면 새 장치 기반 대상을 만들 수 있습니다.

>[!IMPORTANT]
>
>일부 장치 기반 대상은 셀프 서비스 구성 워크플로우에 사용할 수 없습니다. 추가해야 하는 장치 기반 대상이 대상 목록에 표시되지 않으면 Adobe 컨설턴트나 고객 지원에 지원을 요청하십시오.

## 1단계. 대상 플랫폼에서 인증 {#step1}

새 장치 기반 대상을 만들려면 대상 관리자와 대상 플랫폼 간의 통합을 구성해야 합니다. 이 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!DNL Administration > Integrated Accounts]**&#x200B;로그인합니다. 이전에 대상 플랫폼과 통합을 구성한 경우 이 페이지에 나열된 것이 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
2. 클릭 **[!DNL Add Account]**.
3. 인증하려는 대상 플랫폼을 선택하고 클릭하여 **[!DNL Confirm]** 선택한 플랫폼의 인증 페이지로 리디렉션합니다. ![통합 플랫폼](assets/dbd-integrated-platforms.png)
4. 대상 플랫폼 계정에 인증하면 연결된 광고주 계정을 보아야 하는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고를 **[!DNL Confirm]**&#x200B;클릭합니다.

## 2단계. 새 장치 기반 대상 만들기 {#step2}

대상 플랫폼 통합을 구성한 후 새 대상을 만들 수 있습니다. 이 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 정확하게 식별하는 데 도움이 되는 이름을 제공하십시오.

1. Audience Manager 계정에 로그인하고, 이동한 **[!DNL Audience Data > Destinations]****[!DNL Create Destination]**&#x200B;다음을 클릭합니다.
2. **[!DNL Basic Information]** 섹션에서 새 **[!DNL Name]** 대상을 입력하고 **[!DNL Description]** 다음 목록의 설정을 사용합니다. ![설정](assets/dbd-new-basic.png)
   * **[!DNL Category]**: [!DNL Integrated Platforms];
   * **[!DNL Type]**: [!DNL Device-Based];
   * **[!DNL Platform]**: 대상 세그먼트를 보낼 대상 플랫폼을 선택합니다.
   * **[!DNL Account]**: 선택한 플랫폼과 연관된 광고주 계정을 선택합니다.
3. 클릭 **[!DNL Next]**.
4. 이 대상에 대해 설정할 [데이터 내보내기 레이블을](/help/using/features/data-export-controls.md#controls-labels) 선택합니다.
5. 클릭 **[!DNL Save]**.
6. **[!DNL Segment Mappings]** 섹션에서 이 대상에 보낼 대상 세그먼트를 선택합니다.
7. 대상을 저장합니다.

