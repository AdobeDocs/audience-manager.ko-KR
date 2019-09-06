---
description: '이 페이지에는 Audience Manager와 사용자 기반 플랫폼 간의 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다. '
seo-description: '이 페이지에는 Audience Manager와 사용자 기반 플랫폼 간의 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다. '
seo-title: 사용자 기반 플랫폼을 사용한 인증
solution: Audience Manager
title: 사용자 기반 플랫폼을 사용한 인증
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# 사용자 기반 플랫폼을 사용한 인증 {#authentication-with-people-based-platforms}

이 페이지에는 Audience Manager와 사용자 기반 플랫폼 간의 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다.

>[!NOTE]
>구현 시나리오에 관계없이 사람 기반 대상의 필수 단계입니다.

## 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**로 이동합니다. 이전에 소셜 플랫폼과 통합을 구성한 경우 이 페이지에 나열된 것이 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![people-based-integration](assets/pbd-config.png)
1. 클릭 **[!UICONTROL Add Account]**.
1. 드롭다운 **[!UICONTROL People-Based Platform]** 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![People-based-platform](assets/pbd-add.png)
1. 을 클릭하여 **[!UICONTROL Confirm]** 선택한 플랫폼의 인증 페이지로 리디렉션됩니다.
1. 소셜 플랫폼 계정에 인증하면 연결된 광고주 계정을 보아야 하는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고를 **[!UICONTROL Confirm]**&#x200B;클릭합니다.
1. Audience Manager는 계정 상단에 알림이 표시되어 계정이 성공적으로 추가되었는지 알려줍니다. 이 알림을 통해 소셜 플랫폼 인증이 만료될 때 알림을 받을 연락처 이메일 주소를 추가할 수도 있습니다.

## 인증 토큰 만료 및 알림 관리 {#token-expiration-notification}

Audience Manager는 일정 시간 후 만료되는 인증 토큰을 통해 소셜 플랫폼과 통합을 처리합니다. 토큰 유효 기간은 각 소셜 플랫폼의 통합 규칙의 적용을 받습니다. 인증 토큰이 만료되면 Audience Manager에서 대상 세그먼트를 대상으로 보낼 수 없습니다. 이러한 상황을 방지하려면, 통합 토큰이 만료되려고 하는 즉시 알림을 받을 수 있도록 하나 이상의 연락처 이메일 주소를 통합에 추가하는 것이 좋습니다. 이러한 경우 대상이 대상 세그먼트를 계속 수신하도록 재인증할 수 있습니다.

기존 통합에 이메일 주소를 추가하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**&#x200B;로 이동합니다.
1. 토큰 만료 알림을 받을 통합을 식별하고 **[!UICONTROL Edit]** 아이콘을 클릭합니다.
1. 토큰 만료 알림을 받을 이메일 주소를 쉼표로 구분하여 입력합니다.
1. 클릭 **[!UICONTROL Save]**.

## 인증 토큰 갱신 {#token-renewal}

인증 토큰이 만료되면 Audience Manager와 해당 소셜 플랫폼 간의 통합이 중단되므로 Audience Manager는 대상 세그먼트를 대상 세그먼트로 더 이상 보낼 수 없습니다. [!UICONTROL Integrated Accounts] 이 페이지에서는 [!UICONTROL Expiration] 열의 각 통합에 대한 만료 상태를 보여주며 언제든지 인증을 갱신할 수 있습니다.

만료되거나 만료될 인증을 갱신하는 방법은 다음과 같습니다.
1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**&#x200B;로 이동합니다.
1. 인증을 갱신하기 위해 필요한 통합을 식별합니다. 만료된 인증은 것으로 [!UICONTROL Expired]표시되지만 곧 만료될 인증은 남은 인증된 일 수를 나타냅니다.
1. 열의 해당 **[!UICONTROL Renew]** 아이콘을 [!UICONTROL Expiration] 클릭합니다. 이렇게 하면 소셜 플랫폼의 인증 페이지를 다시 안내하는 **[!UICONTROL Renew Account]** 워크플로우가 트리거됩니다. 인증하면 토큰이 새 만료 날짜로 갱신됩니다.
   ![PBD-Renew](assets/pbd-renew.png)
