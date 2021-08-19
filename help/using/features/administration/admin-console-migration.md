---
description: Audience Manager 사용자 관리를 Adobe Admin Console으로 이동 중입니다. 이 문서에서는 사용자 마이그레이션을 준비하기 위해 수행해야 하는 작업과 마이그레이션이 완료되면 변경되는 작업을 설명합니다.
keywords: rbac;RBAC;역할 기반;역할 기반 액세스 제어
seo-description: Audience Manager 사용자 관리를 Adobe Admin Console으로 이동 중입니다. 이 문서에서는 사용자 마이그레이션을 준비하기 위해 수행해야 하는 작업과 마이그레이션이 완료되면 변경되는 작업을 설명합니다.
seo-title: Admin Console으로 Audience Manager 사용자 마이그레이션
solution: Audience Manager
title: Admin Console으로 Audience Manager 사용자 마이그레이션
feature: 관리
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---

# [!DNL Audience Manager] 사용자로의 마이그레이션  [!DNL Admin Console] {#user-migration}

## 개요 {#overview}

[!DNL Audience Manager] Adobe 솔루션에서 보다 능률적인 경험을 위해 사용자 계정 관리를  [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)로 이동 중입니다.

[!DNL Admin Console]을 사용하면 다음과 같은 이점이 있습니다.

| 이점 | 설명 |
|---|---|
| 단일 사인온 다양한 솔루션 | [!DNL Audience Manager] 사용자는 또는  [!DNL Experience Cloud] 를 사용하여 및 기타 모든 솔루션에 로그인할 수  [!DNL Adobe ID] 있습니다  [!DNL Enterprise ID]. 이 로그인을 사용하면 [!DNL Experience Cloud]에서 통합 솔루션 및 핵심 서비스에 액세스할 수 있습니다. 마이그레이션 후 기존 로그인(`bank.demdex.com`)을 통해 로그인하려는 사용자는 `experiencecloud.adobe.com` 로 리디렉션됩니다. |
| 사용자 및 그룹 관리 | 마이그레이션이 완료되면 [!DNL Audience Manager] 관리자는 [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)에서 배타적으로 사용자 및 그룹을 관리합니다. |
| 제품 및 서비스 관리 | [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)에서 관리자는 다음을 수행할 수 있습니다. <ul><li>사용자 만들기, 업데이트 및 제거</li><li>솔루션 및 서비스에 대한 액세스 권한 부여</li></ul> |

사용자 마이그레이션을 용이하게 하기 위해 Adobe에서는 모든 [!DNL Audience Manager] 관리자에게 이 문서에 설명된 단계를 수행하여 가능한 한 빨리 사용자 계정을 [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)로 마이그레이션하도록 요청하고 있습니다.

## 사용자가 수행해야 하는 작업 {#what-to-do-users}

Audience Manager 사용자라면 [!DNL Audience Manager] 관리자에게 연락하여 [!DNL Admin Console]에서 새 사용자 계정을 만들라고 요청하기만 하면 됩니다.

## 관리자가 수행해야 하는 작업 {#what-to-do-admins}

Audience Manager 관리자는 아래 단계에 따라 사용자를 [!DNL Admin Console]으로 마이그레이션해야 합니다.

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com)로 이동한 다음 Adobe ID 또는 Enterprise ID을 사용하여 로그인합니다. [!DNL Admin Console]에 액세스할 수 없는 경우 고객 지원 센터 또는 Adobe 컨설턴트에게 문의하십시오.
2. 사용자 계정을 만들고 관리하는 방법에 대한 자세한 지침은 [!DNL Adobe Admin Console] [도움말 안내서](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html)를 참조하십시오.
3. 모든 기존 Audience Manager 사용자를 위한 새 사용자 계정을 만듭니다.
4. 새로 만든 사용자 계정에 대해 사용자에게 알려줍니다. 사용자가 [!DNL Admin Console]로 마이그레이션되면 기존 로그인 사용을 중지해야 합니다.

## 사용자 마이그레이션 고려 사항 {#considerations}

사용자와 관리자 모두 Audience Manager 사용자 마이그레이션에 대해 다음과 같은 고려 사항을 염두에 두어야 합니다.

* 새 사용자 계정이 Admin Console에 만들어지면 기존 사용자 계정의 기존 권한이 계속 적용됩니다.
* 사용자 권한에 대한 업데이트는 [!DNL Audience Manager]에서 계속 관리됩니다. [!DNL Admin Console]은 사용자 및 그룹 관리만 다룹니다.
* 관리자는 기존 사용자 계정을 비활성화할 필요가 없습니다. 이전 사용자 계정은 자동으로 마이그레이션된 사용자 계정에 병합됩니다.
