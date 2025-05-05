---
description: 이 페이지에는 Audience Manager 및 사용자 기반 플랫폼 간의 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다.
seo-description: This page contains guidance on how to configure and manage the integration between Audience Manager and people-based platforms.
seo-title: Authentication with People-Based Platforms
solution: Audience Manager
title: 사용자 기반 플랫폼을 통한 인증
feature: People-based Destinations
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: 1809e9ee0b19a8ffb4bec38162f728d543d13701
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---


# 사용자 기반 플랫폼을 통한 인증 {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용 방법을 안내하는 제품 설명서가 포함되어 있습니다. 여기에는 법률적인 조언이 들어 있지 않습니다. 법률 지도가 필요한 경우 법률 자문을 구하십시오.

이 페이지에는 통합을 구성하고 관리하는 방법에 대한 지침이 포함되어 있습니다
Audience Manager 및 사용자 기반 플랫폼 간에 매핑할 수 있습니다.

>[!NOTE]
>이 단계는 구현 시나리오와 관계없이 사용자 기반 대상에 대한 필수 단계입니다.

## 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**(으)로 이동합니다. 소셜 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사용자 기반 통합](assets/pbd-config.png)
2. **[!UICONTROL Add Account]** 아이콘을 클릭합니다.
3. **[!UICONTROL People-Based Platform]** 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![사용자 기반 플랫폼](assets/pbd-add.png)
4. 선택한 플랫폼의 인증 페이지로 리디렉션하려면 **[!UICONTROL Confirm]**&#x200B;을(를) 클릭하십시오.
5. 소셜 플랫폼 계정을 인증하면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!UICONTROL Confirm]**&#x200B;을(를) 클릭합니다.
6. Audience Manager은 계정이 성공적으로 추가되었는지 여부를 알려주는 알림을 페이지 맨 위에 표시합니다. 또한 알림을 사용하면 소셜 플랫폼 인증이 곧 만료될 때 Adobe에서 알림을 받을 연락처 이메일 주소를 추가할 수 있습니다.

## 인증 토큰 만료 및 알림 관리 {#token-expiration-notification}

Audience Manager은 일정 시간이 지나면 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 토큰 유효 기간은 각 소셜 플랫폼의 통합 규칙에 따라 다릅니다. 인증 토큰이 만료되면 Audience Manager은 대상 세그먼트를 대상으로 전송할 수 없습니다. 이 시나리오를 방지하려면 인증 토큰이 만료되는 즉시 알림을 받을 수 있도록 통합에 하나 이상의 연락처 이메일 주소를 추가하는 것이 좋습니다. 이런 경우 다시 인증하여 대상이 대상 세그먼트를 계속 수신하는지 확인할 수 있습니다.

기존 통합에 이메일 주소를 추가하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**(으)로 이동합니다.
1. 토큰 만료 알림을 받을 통합을 확인하고 **[!UICONTROL Edit]** 아이콘을 클릭합니다.
1. 토큰 만료 알림을 수신할 이메일 주소를 쉼표로 구분하여 입력합니다.
1. **[!UICONTROL Save]** 아이콘을 클릭합니다.

## 인증 토큰 갱신 {#token-renewal}

인증 토큰이 만료되면 Audience Manager과 해당 소셜 플랫폼 간의 통합이 중단되므로 Audience Manager은 더 이상 대상 세그먼트를 대상으로 보낼 수 없습니다. [!UICONTROL Integrated Accounts] 페이지에는 [!UICONTROL Expiration] 열에 있는 각 통합의 만료 상태가 표시되며 언제든지 인증을 갱신할 수 있습니다.

만료되었거나 만료될 예정인 인증을 갱신하는 방법은 다음과 같습니다.
1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**(으)로 이동합니다.
1. 인증을 갱신해야 하는 통합을 식별합니다. 만료된 인증은 [!UICONTROL Expired] (으)로 표시되지만 곧 만료될 인증은 남은 인증일 수를 표시합니다.
1. [!UICONTROL Expiration] 열에서 해당 **[!UICONTROL Renew]** 아이콘을 클릭합니다. 이렇게 하면 소셜 플랫폼의 인증 페이지를 다시 안내하는 **[!UICONTROL Renew Account]** 워크플로우가 트리거됩니다. 인증하면 토큰이 새 만료 날짜로 갱신됩니다.
   ![pbd-renew](assets/pbd-renew.png)
