---
description: 관리 메뉴 아래의 옵션을 사용하면 Audience Manager 사용자를 만들고 그룹에 할당할 수 있습니다. 제한(트레이트, 세그먼트, 대상 및 모델)을 볼 수도 있습니다.
keywords: rbac;RBAC;역할 기반;역할 기반;역할 기반 액세스 제어
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 관리
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] (RBAC 컨트롤) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)(으)로 이동합니다. 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객이 이 문서에 설명된 대로 즉시 필요한 조치를 취해야 합니다. [Admin Console으로 사용자 마이그레이션 Audience Manager](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 문서의 사용자 관리 섹션이 사라집니다.

>[!IMPORTANT]
>
> [!DNL RBAC]을(를) 사용하려면 먼저 조직의 Adobe에서 이 기능을 활성화해야 합니다. 계정 팀에 연락하여 [!DNL RBAC] 활성화를 요청하거나 고객 지원 센터에 문의하십시오.


[!UICONTROL Administration] 메뉴 아래의 옵션을 사용하면 Audience Manager 사용자를 만들고 그룹에 할당할 수 있습니다. 제한(트레이트, 세그먼트, 대상 및 모델)을 볼 수도 있습니다.

[!DNL Audience Manager]을(를) 사용하는 기업 고객은 모든 데이터에 대해 하나의 데이터 관리 플랫폼이 필요하지만 특정 비즈니스 단위에 대해 서로 다른 데이터 요소의 가시성을 제어할 수 있어야 합니다. [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC])이라고도 하는 그룹 권한을 사용하여 이를 수행할 수 있습니다.

[!DNL Audience Manager]은(는) 그룹을 사용하여 권한을 할당합니다. 사용자 수준에서 권한이 할당되지 않습니다. 그룹 권한은 개체([!UICONTROL traits], 세그먼트 등)에 연결되어 있습니다. 해당 객체(편집, 보기 등)에 대해 수행할 수 있는 작업입니다. 이러한 컨트롤은 Audience Manager REST API를 통해서도 사용할 수 있습니다. [사용자 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [그룹 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) 및 [권한 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API 메서드를 참조하십시오.

## 사용자 만들기 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)(으)로 이동합니다. 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객이 이 문서에 설명된 대로 즉시 필요한 조치를 취해야 합니다. [Admin Console으로 사용자 마이그레이션 Audience Manager](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 문서의 사용자 관리 섹션이 사라집니다.
> 
>[!DNL Audience Manager]에서 사용자를 만들고 사용자 세부 정보, 로그인 상태를 지정하고 사용자를 그룹에 할당합니다.

1. **[!UICONTROL Administration]** > **[!UICONTROL Users]**&#x200B;을(를) 클릭합니다.
1. ![](assets/icon_add.png)을(를) 클릭하여 [!UICONTROL Create New User] 페이지를 표시합니다.
1. **[!UICONTROL User Details]**&#x200B;에서 다음 필드를 채웁니다.
   * **[!UICONTROL Username]:** Audience Manager에 대한 고유한 사용자 이름을 지정합니다.
   * **[!UICONTROL First Name]:** 사용자의 이름을 지정합니다.
   * **[!UICONTROL Last Name]:** 사용자의 성을 지정합니다.
   * **[!UICONTROL Email Address]:** 사용자의 전자 메일 주소를 지정합니다. [!DNL Audience Manager]이(가) 사용자에게 일반 알림을 보내지 않습니다. [!DNL Audience Manager] 관리자는 사용자의 전자 메일 주소에 액세스할 수 있으며 필요에 따라 사용자에게 수동으로 전자 메일을 보낼 수 있습니다. 예를 들어 사용자가 암호를 잊어버린 경우 이 필드에 지정된 이메일 주소를 사용하여 임시 암호와 암호 재설정 지침을 보냅니다.
   * **[!UICONTROL Phone Number]:** 사용자의 전화 번호를 지정합니다.
   * **[!UICONTROL Is Admin]:** 이 사용자가 [!DNL Audience Manager] 관리자인지 여부를 지정합니다. 관리자 사용자는 사용자를 관리(만들기, 편집 등)할 수 있습니다. 및 그룹(만들기, 권한 할당 등). 관리자가 아닌 사용자는 이메일 주소 편집 및 암호 재설정 등 자신의 사용자 프로필만 제어할 수 있습니다. 자세한 내용은 [계정 설정 편집](../../features/administration/edit-account-settings.md)을 참조하세요.
1. **[!UICONTROL Login]**&#x200B;에서 원하는 상태를 선택합니다.
   * **[!UICONTROL Active]:**&#x200B;명의 활성 사용자가 [!DNL Audience Manager]에 액세스하여 그룹 멤버십에 의해 부여된 권한을 가질 수 있습니다.
   * **[!UICONTROL Deactivated]:** 비활성화된 사용자는 [!DNL Audience Manager]에 액세스할 수 없으며 사용 권한이 없습니다. 사용자를 비활성화하면 해당 사용자 정보가 [!DNL Audience Manager]에 남아 있으며 필요한 경우 간단히 다시 활성화할 수 있습니다. 사용자를 제거하면 나중에 [!DNL Audience Manager]을(를) 다시 사용해야 하는 경우 다시 만들어야 합니다.
   * **[!UICONTROL Expired]:** 사용자의 암호가 90일 이상입니다.
   * **[!UICONTROL Pending]:** 암호 재설정 후나 새 계정으로 사용자에게 임시 암호가 있으며 아직 영구 암호를 설정하지 않았습니다.
   * **[!UICONTROL Locked Out]:** 5번의 잘못된 로그인 시도로 사용자가 잠깁니다.
1. **[!UICONTROL Assigned Groups]**&#x200B;의 드롭다운 목록에서 이 사용자를 할당할 원하는 그룹을 선택합니다.
그룹 및 사용 권한에 대한 자세한 내용은 [그룹 만들기](../../features/administration/administration-overview.md#create-group)를 참조하세요.
1. **[!UICONTROL Save]** 아이콘을 클릭합니다.

## [!UICONTROL Group] 만들기 {#create-group}

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)(으)로 이동합니다. 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객이 이 문서에 설명된 대로 즉시 필요한 조치를 취하는 것이 좋습니다. [Admin Console으로 사용자 마이그레이션 Audience Manager](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 섹션은 사라집니다.

*그룹*&#x200B;은(는) [!UICONTROL destination], [!UICONTROL segment] 및 [!UICONTROL trait] 개체에 대한 액세스 권한을 공유하는 사용자 컬렉션입니다. 그룹을 단일 객체로만 제한하거나 서로 다른 객체의 조합에 광범위한 액세스를 제공할 수 있습니다.

<!-- t_create_groups.xml -->

그룹을 만들려면 다음 작업을 수행하십시오.

1. **[!UICONTROL Administration]** > **[!UICONTROL Groups]**&#x200B;을(를) 클릭합니다.
2. ![](assets/icon_add.png)을(를) 클릭하여 [!UICONTROL Group Settings] 페이지를 엽니다.
3. [!UICONTROL Group Details]에서:
   * 그룹 이름을 지정합니다.
   * 간단한 그룹 설명을 입력합니다.
4. [!UICONTROL Group Members]에서 **[!UICONTROL Add Users]** 옵션에서 사용자를 클릭하여 그룹에 추가합니다.
5. [!UICONTROL Group Permissions]에서 **[!UICONTROL Add Object]**&#x200B;의 [트레이트](../../features/traits/trait-details-page.md), [세그먼트](../../features/segments/segments-purpose.md) 또는 [대상](../../features/destinations/destinations.md)을(를) 선택하십시오.
선택한 객체에 대한 권한 창이 열립니다.
6. 그룹 구성원에게 부여할 권한에 대한 확인란을 선택합니다.
7. *(선택 사항)* 그룹에 [와일드카드 권한](../../features/administration/administration-overview.md#wild-card-permissions)을 할당하십시오.
8. **[!UICONTROL Save Group]** 아이콘을 클릭합니다.

## [!UICONTROL Wild Card Permissions] 이해 {#wild-card-permissions}

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html)(으)로 이동합니다. 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객이 이 문서에 설명된 대로 즉시 필요한 조치를 취하는 것이 좋습니다. [Admin Console으로 사용자 마이그레이션 Audience Manager](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 섹션은 사라집니다.

[!UICONTROL Wild Card Permissions]을(를) 사용하여 그룹 권한 관리를 단순화합니다.

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions]은(는) 그룹 구성원에게 [!UICONTROL segment], [!UICONTROL destination] 또는 [!UICONTROL trait]에 연결된 각 데이터 원본에 대한 자동 액세스 권한을 부여합니다. 이에 비해 일반 사용 권한에서는 이러한 개체 중 하나에 특정 [!UICONTROL data sources]을(를) 할당할 수만 있습니다. 새 [!UICONTROL data sources]을(를) 추가하면 그룹 구성원이 해당 새 소스에 액세스할 수 없습니다.

그룹 권한을 열고 새 [!UICONTROL data sources]을(를) 그룹에 할당해야 합니다. [!UICONTROL Wild Card Permissions]을(를) 사용하면 이러한 수동 [!UICONTROL data source] 업데이트 프로세스를 피할 수 있습니다. [!UICONTROL Wild Card Permissions]이(가) 있는 그룹은 명시적 권한 부여 없이 새 [!UICONTROL data sources]에 액세스할 수 있습니다.

![](assets/wild-card.png)

각 [!UICONTROL wildcard permission]의 의미에 대한 설명은 아래를 참조하십시오.

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - 사용자는 [!UICONTROL traits]을(를) [!UICONTROL models]의 기준선으로 선택할 수 있습니다.
* `EDIT_ALL_TRAITS` - 사용자는 회사 계정 내에서 설정된 모든 [!UICONTROL traits]을(를) 편집할 수 있습니다.
* `VIEW_ALL_TRAITS` - 사용자는 회사 계정 내에서 설정된 모든 [!UICONTROL traits]을(를) 볼 수 있습니다.
* `DELETE_ALL_TRAITS` - 사용자는 회사 계정 내에서 설정된 모든 [!UICONTROL traits]을(를) 삭제할 수 있습니다.
* `CREATE_ALL_ALGO_TRAITS` - 사용자가 [!UICONTROL algorithmic traits]을(를) 만들 수 있습니다.
* `MAP_ALL_TO_SEGMENTS` - 사용자는 회사에 속한 [!UICONTROL traits]을(를) [!UICONTROL segments]에 추가할 수 있습니다.
* `CREATE_ALL_TRAITS` - 사용자가 [!UICONTROL traits]을(를) 만들 수 있습니다.

**[!UICONTROL Models]**

* `VIEW_MODELS` - 사용자는 회사에 속한 [!UICONTROL models]을(를) 볼 수 있는 권한이 있습니다.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - 사용자는 회사에 속한 모든 [!UICONTROL derived signals]을(를) 볼 수 있습니다.
* `CREATE_DERIVED_SIGNALS` - 사용자가 [!UICONTROL derived signals]을(를) 만들 수 있습니다.
* `EDIT_DERIVED_SIGNALS` - 사용자는 회사에 속한 모든 [!UICONTROL derived signals]을(를) 편집할 수 있습니다.
* `DELETE_DERIVED_SIGNALS` - 사용자는 회사에 속한 [!UICONTROL derived signals]을(를) 삭제할 수 있습니다.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - 사용자는 회사 계정 내에서 설정된 모든 [!UICONTROL destinations]을(를) 편집할 수 있습니다.
* `CREATE_DESTINATIONS` - 사용자가 [!UICONTROL destinations]을(를) 만들 수 있습니다.
* `VIEW_ALL_DESTINATIONS` - 사용자는 회사 계정 내에서 설정된 모든 [!UICONTROL destinations]을(를) 볼 수 있습니다.
* `DELETE_ALL_DESTINATIONS` - 사용자는 회사 계정 내에서 설정된 모든 [!UICONTROL destinations]을(를) 삭제할 수 있습니다.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - 사용자는 [!UICONTROL Tag Containers]에서 모든 작업(보기, 만들기, 편집, 삭제)을 수행할 수 있습니다.

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - 사용자는 [!UICONTROL Audience Lab] 테스트 그룹에서 모든 작업(보기, 만들기, 편집, 삭제)을 수행할 수 있습니다.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - 사용자가 세그먼트를 만들 수 있습니다.
* `DELETE_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 삭제할 수 있습니다.
* `MAP_ALL_TO_DESTINATIONS` - 사용자는 회사에 속한 모든 세그먼트를 대상에 매핑할 수 있습니다.
* `EDIT_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 편집할 수 있습니다.
* `MAP_ALL_SEGMENTS_TO_MODELS` - 사용자는 세그먼트를 모델의 기준선으로 선택할 수 있습니다.
* `VIEW_ALL_SEGMENTS` - 사용자는 회사 계정 내에서 설정된 모든 세그먼트를 볼 수 있습니다.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - 사용자는 [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md)에서 캡처된 모든 신호를 볼 수 있습니다.

## 사용 사례 {#use-cases}

### 사용자 액세스 모니터링 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control]은(는) 사용자 로그인 상태를 모니터링하는 데 도움이 되며, Audience Manager 인스턴스에 액세스할 수 있는 사용자를 명확하게 파악할 수 있습니다.

비즈니스 요구 사항에 따라 필요에 따라 사용자 계정을 활성화 및 비활성화할 수 있습니다.

![사용자 액세스 모니터링](assets/monitor-user-access.png)

### 중요한 [!UICONTROL Data Sources]에 대한 액세스 보호 확인 {#protect-sensitive-data-sources}

각 사용자 그룹에 대해 [!UICONTROL trait], 세그먼트 및 [!UICONTROL destination] 수준에서 [!UICONTROL Role-Based Access Control]을(를) 구성할 수 있습니다.

이 기능을 사용하면 사용자가 특정 데이터 세트를 보고, 만들고, 읽고, 쓰고, 편집하는 방법을 관리하고 사용자가 사용할 수 없어야 하는 데이터 세트에 액세스하지 못하도록 제한할 수도 있습니다.

![액세스 보호](assets/access-protection.png)
