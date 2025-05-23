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
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Admin Console] (으)로 [!DNL Audience Manager] 사용자 마이그레이션 {#user-migration}

## 개요 {#overview}

Adobe 솔루션 전반에서 보다 간소화된 환경을 제공하기 위해 [!DNL Audience Manager] 사용자 계정 관리가 [Adobe Admin Console](https://helpx.adobe.com/kr/enterprise/using/admin-console.html)(으)로 이동하고 있습니다.

[!DNL Admin Console]을(를) 사용하면 다음과 같은 이점이 있습니다.

| 이점 | 설명 |
|---|---|
| 솔루션 간 SSO(Single Sign-On) | [!DNL Audience Manager]명의 사용자가 [!DNL Adobe ID] 또는 [!DNL Enterprise ID]을(를) 사용하여 [!DNL Experience Cloud] 및 다른 모든 솔루션에 로그인할 수 있습니다. 이 로그인을 사용하면 [!DNL Experience Cloud]에서 통합 솔루션 및 핵심 서비스에 액세스할 수 있습니다. 마이그레이션 후 기존 로그인(`bank.demdex.com`)을 통해 로그인하려는 사용자는 `experiencecloud.adobe.com`(으)로 리디렉션됩니다. |
| 사용자 및 그룹 관리 | 마이그레이션이 완료되면 [!DNL Audience Manager] 관리자는 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)에서만 사용자 및 그룹을 관리합니다. |
| 제품 및 서비스 관리 | 관리자는 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)에서 다음을 수행할 수 있습니다. <ul><li>사용자 만들기, 업데이트 및 제거</li><li>솔루션 및 서비스에 대한 액세스 권한 부여</li></ul> |

사용자 마이그레이션을 용이하게 하기 위해 모든 [!DNL Audience Manager] 관리자에게 이 문서에 설명된 단계를 따라 가능한 한 빨리 [Adobe Admin Console](https://helpx.adobe.com/kr/enterprise/using/admin-console.html)(으)로 사용자 계정 마이그레이션을 시작하도록 요청하고 있습니다.

## 사용자가 수행해야 하는 작업 {#what-to-do-users}

Audience Manager 사용자는 [!DNL Audience Manager] 관리자에게 연락하여 [!DNL Admin Console]에서 새 사용자 계정을 만들도록 요청하기만 하면 됩니다.

## 관리자가 수행해야 하는 작업 {#what-to-do-admins}

Audience Manager 관리자는 아래 단계에 따라 사용자를 [!DNL Admin Console] (으)로 마이그레이션해야 합니다.

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com)(으)로 이동한 다음 Adobe ID 또는 Enterprise ID을 사용하여 로그인합니다. [!DNL Admin Console]에 액세스할 수 없는 경우 고객 지원 센터 또는 Adobe 컨설턴트에게 문의하십시오.
2. 사용자 계정을 만들고 관리하는 방법에 대한 자세한 지침은 [!DNL Adobe Admin Console] [도움말 안내서](https://helpx.adobe.com/kr/enterprise/admin-guide.html/enterprise/using/users.ug.html)를 참조하세요.
3. 모든 기존 Audience Manager 사용자에 대한 새 사용자 계정을 만듭니다.
4. 새로 생성된 사용자 계정에 대해 사용자에게 알립니다. 사용자가 [!DNL Admin Console] (으)로 마이그레이션되면 이전 로그인의 사용을 중지해야 합니다.

## 사용자 마이그레이션 고려 사항 {#considerations}

사용자와 관리자 모두 Audience Manager 사용자 마이그레이션을 위해 다음 사항을 고려해야 합니다.

* Admin Console에서 새 사용자 계정이 만들어지면 기존 사용자 계정의 기존 권한이 계속 적용됩니다.
* 사용자 권한에 대한 업데이트는 [!DNL Audience Manager]에서 계속 관리됩니다. [!DNL Admin Console]은(는) 사용자 및 그룹 관리만 포함합니다.
* 관리자는 이전 사용자 계정을 비활성화할 필요가 없습니다. 이전 사용자 계정은 마이그레이션된 계정에 자동으로 병합됩니다.
