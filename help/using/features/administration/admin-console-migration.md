---
description: Audience Manager 사용자 관리가 Adobe Admin Console으로 이동하고 있습니다. 이 문서에서는 사용자 마이그레이션을 준비하기 위해 수행해야 하는 작업과 마이그레이션이 완료되면 변경되는 작업을 설명합니다.
keywords: rbac;RBAC;역할 기반;역할 기반;역할 기반 액세스 제어
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Admin Console으로 Audience Manager 사용자 마이그레이션
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 3%

---

# [!DNL Audience Manager] 로 사용자 마이그레이션 [!DNL Admin Console] {#user-migration}

## 개요 {#overview}

[!DNL Audience Manager] 사용자 계정 관리가 다음으로 이동 중: [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)Adobe 을 참조하십시오.

를 사용할 때의 이점 [!DNL Admin Console] 포함:

| 이점 | 설명 |
|---|---|
| 단일 사인온 솔루션 간 | [!DNL Audience Manager] 사용자가에 로그인할 수 있음 [!DNL Experience Cloud] 및 를 사용하는 다른 모든 솔루션 [!DNL Adobe ID] 또는 [!DNL Enterprise ID]. 이 로그인을 사용하면 통합 솔루션 및 핵심 서비스에 액세스할 수 있습니다. [!DNL Experience Cloud]. 마이그레이션 후 기존 로그인을 통해 로그인하려는 사용자(`bank.demdex.com`)으로 리디렉션됩니다. `experiencecloud.adobe.com`. |
| 사용자 및 그룹 관리 | 마이그레이션이 완료되면 [!DNL Audience Manager] 관리자는 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| 제품 및 서비스 관리 | 다음에서 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), 관리자는 다음 작업을 수행할 수 있습니다. <ul><li>사용자 만들기, 업데이트 및 제거</li><li>솔루션 및 서비스에 대한 액세스 권한 부여</li></ul> |

사용자 마이그레이션을 용이하게 하기 위해 모든 사용자에게 문의 [!DNL Audience Manager] 관리자에게으로 사용자 계정 마이그레이션을 시작할 수 있습니다. [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) 최대한 빨리 이 문서에 설명된 단계를 수행합니다.

## 사용자가 수행해야 하는 작업 {#what-to-do-users}

Audience Manager 사용자는 [!DNL Audience Manager] 관리자에게에서 새 사용자 계정 만들기를 요청하십시오. [!DNL Admin Console].

## 관리자가 수행해야 하는 작업 {#what-to-do-admins}

Audience Manager 관리자는 아래 단계에 따라 사용자를 로 마이그레이션해야 합니다. [!DNL Admin Console].

1. 다음으로 이동 [https://adminconsole.adobe.com](https://adminconsole.adobe.com) Adobe ID 또는 Enterprise ID을 사용하여 로그인합니다. 다음에 대한 액세스 권한이 없는 경우: [!DNL Admin Console], 고객 지원 센터 또는 Adobe 컨설턴트에게 문의하십시오.
2. 다음 확인: [!DNL Adobe Admin Console] [도움말 안내서](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) 사용자 계정을 만들고 관리하는 방법에 대한 자세한 지침을 제공합니다.
3. 모든 기존 Audience Manager 사용자에 대한 새 사용자 계정을 만듭니다.
4. 새로 생성된 사용자 계정에 대해 사용자에게 알립니다. 사용자가 (으)로 마이그레이션되면 [!DNL Admin Console], 기존 로그인의 사용을 중지해야 합니다.

## 사용자 마이그레이션 고려 사항 {#considerations}

사용자와 관리자 모두 Audience Manager 사용자 마이그레이션을 위해 다음 사항을 고려해야 합니다.

* Admin Console에서 새 사용자 계정이 만들어지면 기존 사용자 계정의 기존 권한이 계속 적용됩니다.
* 사용자 권한에 대한 업데이트는에서 계속 관리됩니다. [!DNL Audience Manager]. 다음 [!DNL Admin Console] 사용자 및 그룹 관리만 다룹니다.
* 관리자는 이전 사용자 계정을 비활성화할 필요가 없습니다. 이전 사용자 계정은 마이그레이션된 계정에 자동으로 병합됩니다.
