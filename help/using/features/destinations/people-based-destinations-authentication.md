---
description: '이 페이지에는 Audience Manager와 사람 기반 플랫폼 간의 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다. '
seo-description: '이 페이지에는 Audience Manager와 사람 기반 플랫폼 간의 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다. '
seo-title: 사용자 기반 플랫폼을 통한 인증
solution: Audience Manager
title: 사용자 기반 플랫폼을 통한 인증
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# 사용자 기반 플랫폼을 통한 인증 {#authentication-with-people-based-platforms}

이 페이지에는 Audience Manager와 사람 기반 플랫폼 간의 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다.

>[!NOTE]
>이 단계는 구현 시나리오에 상관없이 사람 기반 대상에 대한 필수 단계입니다.

## 사람 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**로 이동합니다. 이전에 소셜 플랫폼과 통합한 적이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사람 기반 통합](assets/pbd-config.png)
1. 클릭 **[!UICONTROL Add Account]**.
1. 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다. **[!UICONTROL People-Based Platform]**
   ![사용자 기반 플랫폼](assets/pbd-add.png)
1. 아이콘을 **[!UICONTROL Confirm]** 클릭하여 선택한 플랫폼의 인증 페이지로 리디렉션합니다.
1. 소셜 플랫폼 계정에 인증되면 연결된 광고주 계정이 표시되는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 을 **[!UICONTROL Confirm]**&#x200B;클릭합니다.
1. Audience Manager는 계정 성공적으로 추가되었는지 여부를 알려주는 알림을 페이지 상단에 표시합니다. 또한 이 알림을 통해 소셜 플랫폼 인증이 만료될 때 Adobe로부터 알림을 수신할 연락처 이메일 주소를 추가할 수 있습니다.

## 인증 토큰 만료 및 알림 관리 {#token-expiration-notification}

Audience Manager는 일정 시간 후 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 토큰 유효 기간은 각 소셜 플랫폼의 통합 규칙에 따릅니다. 인증 토큰이 만료되면 Audience Manager가 대상 세그먼트를 대상으로 보낼 수 없습니다. 이 시나리오를 방지하려면 인증 토큰이 만료되는 즉시 알림을 받을 수 있도록 하나 이상의 연락처 이메일 주소를 통합에 추가하는 것이 좋습니다. 이러한 경우 대상이 대상 세그먼트를 계속 수신하도록 재인증할 수 있습니다.

기존 통합에 이메일 주소를 추가하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**&#x200B;로 이동합니다.
1. 토큰 만료 알림을 받을 통합을 확인하고 **[!UICONTROL Edit]** 아이콘을 클릭합니다.
1. 토큰 만료 알림을 받을 이메일 주소를 쉼표로 구분하여 입력합니다.
1. 클릭 **[!UICONTROL Save]**.

## 인증 토큰 갱신 {#token-renewal}

인증 토큰이 만료되면 Audience Manager와 해당 소셜 플랫폼 간의 통합이 중단되므로 Audience Manager는 대상 세그먼트를 더 이상 대상으로 보낼 수 없습니다. 이 [!UICONTROL Integrated Accounts] 페이지에는 [!UICONTROL Expiration] 열에 있는 각 통합의 만료 상태가 표시되며, 언제든지 인증을 갱신할 수 있습니다.

만료되거나 만료될 예정인 인증을 갱신하는 방법은 다음과 같습니다.
1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**&#x200B;로 이동합니다.
1. 인증을 갱신해야 하는 통합을 식별합니다. 만료된 인증은 [!UICONTROL Expired]으로 표시되지만 곧 만료될 인증에는 나머지 인증된 일 수가 표시됩니다.
1. 열에서 해당 **[!UICONTROL Renew]** 아이콘을 [!UICONTROL Expiration] 클릭합니다. 이렇게 하면 **[!UICONTROL Renew Account]** 워크플로우가 트리거되어 소셜 플랫폼의 인증 페이지를 다시 안내합니다. 인증하면 새로운 만료 날짜로 토큰이 갱신됩니다.
   ![pbd-renew](assets/pbd-renew.png)
