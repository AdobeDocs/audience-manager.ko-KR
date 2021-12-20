---
description: 관리 메뉴 아래의 옵션을 사용하면 Audience Manager 사용자를 만들고 그룹에 할당할 수 있습니다. 제한(트레이트, 세그먼트, 대상 및 모델)을 볼 수도 있습니다.
keywords: rbac;RBAC;역할 기반;역할 기반 액세스 제어
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: 관리
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: 8ef6e8eb4351c24b55703b1788c68c580f199fc8
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 2%

---

# [!UICONTROL Administration] (RBAC 컨트롤) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객이 이 문서에 설명된 필요한 조치를 즉시 취해야 합니다. [Admin Console으로 Audience Manager 사용자 마이그레이션](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 문서의 사용자 관리 섹션이 사라집니다.


아래의 옵션 [!UICONTROL Administration] 메뉴를 사용하면 Audience Manager 사용자를 만들어 그룹에 지정할 수 있습니다. 제한(트레이트, 세그먼트, 대상 및 모델)을 볼 수도 있습니다.

을 사용하는 엔터프라이즈 고객 [!DNL Audience Manager] 모든 데이터에 하나의 데이터 관리 플랫폼이 필요하지만 특정 비즈니스 단위에 대해 다양한 데이터 요소의 가시성을 제어할 수 있어야 합니다. 그룹 권한( 라고 함)을 사용하여 이를 수행할 수 있습니다 [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] 그룹을 사용하여 권한을 할당합니다. 사용 권한은 사용자 수준에서 할당되지 않습니다. 그룹 권한은 개체에 연결되어 있습니다([!UICONTROL traits], 세그먼트 등) 그리고 해당 객체(편집, 보기 등)에 대해 수행할 수 있는 작업에 대해 이러한 컨트롤은 Audience Manager REST API를 통해서도 사용할 수 있습니다. 자세한 내용은 [사용자 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [그룹 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), 및 [권한 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API 메서드.

## 사용자 만들기 {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객이 이 문서에 설명된 필요한 조치를 즉시 취해야 합니다. [Admin Console으로 Audience Manager 사용자 마이그레이션](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 문서의 사용자 관리 섹션이 사라집니다.
에서 사용자 만들기 [!DNL Audience Manager] 및 사용자 세부 사항, 로그인 상태 및 사용자를 그룹에 지정합니다.

1. 클릭 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. 클릭 ![](assets/icon_add.png) 를 [!UICONTROL Create New User] 페이지.
1. 아래 **[!UICONTROL User Details]**&#x200B;을 눌러 다음 필드를 채웁니다.
   * **[!UICONTROL Username]:** Audience Manager에 대한 고유 사용자 이름을 지정합니다.
   * **[!UICONTROL First Name]:** 사용자의 이름을 지정합니다.
   * **[!UICONTROL Last Name]:** 사용자의 성을 지정합니다.
   * **[!UICONTROL Email Address]:** 사용자의 이메일 주소를 지정합니다. [!DNL Audience Manager] 사용자에게 일반 알림을 전송하지 않습니다. [!DNL Audience Manager] 관리자는 사용자의 이메일 주소에 액세스할 수 있으며 필요에 따라 수동으로 사용자에게 이메일을 보낼 수 있습니다. 예를 들어 사용자가 암호를 잊어버리면 이 필드에 지정된 이메일 주소가 임시 암호와 암호 재설정 지침을 보내는 데 사용됩니다.
   * **[!UICONTROL Phone Number]:** 사용자의 전화 번호를 지정합니다.
   * **[!UICONTROL Is Admin]:** 이 사용자가 [!DNL Audience Manager] 관리자 관리 사용자는 사용자를 관리(만들기, 편집 등)할 수 있습니다. 및 그룹(만들기, 권한 할당 등)에 사용됩니다. 관리자가 아닌 사용자는 이메일 주소 편집 및 자체 암호 재설정 등 자체 사용자 프로필만 제어할 수 있습니다. 자세한 내용은 [계정 설정 편집](../../features/administration/edit-account-settings.md).
1. 아래 **[!UICONTROL Login]**&#x200B;에서 원하는 상태를 선택합니다.
   * **[!UICONTROL Active]:**  활성 사용자가 [!DNL Audience Manager] 및 은(는) 그룹 멤버십에서 부여한 권한을 갖습니다.
   * **[!UICONTROL Deactivated]:**  비활성화된 사용자는 액세스할 수 없습니다 [!DNL Audience Manager] 사용 권한이 없습니다. 사용자를 비활성화하면 해당 사용자 정보는 [!DNL Audience Manager] 필요한 경우 간단하게 재활성화할 수 있습니다. 사용자를 제거하는 경우, 사용자를 다시 만들어야 할 경우 다시 만들어야 합니다 [!DNL Audience Manager] 미래에 다시.
   * **[!UICONTROL Expired]:** 사용자의 암호가 90일 이상 걸립니다.
   * **[!UICONTROL Pending]:** 사용자는 암호 재설정 후 또는 새 계정으로 임시 암호가 있으며, 아직 영구 암호를 설정하지 않았습니다.
   * **[!UICONTROL Locked Out]:** 5번의 잘못된 로그인 시도로 사용자가 잠깁니다.
1. 아래 **[!UICONTROL Assigned Groups]**을 누르고 있는 경우 드롭다운 목록에서 이 사용자를 지정할 그룹을 선택합니다.
그룹 및 권한에 대한 자세한 내용은 [그룹 만들기](../../features/administration/administration-overview.md#create-group).
1. 클릭 **[!UICONTROL Save]**.

## 웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객에게 이 문서에 설명된 필요한 조치를 즉시 취할 것을 권장합니다. [Admin Console으로 Audience Manager 사용자 마이그레이션](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 섹션이 사라집니다.

A *그룹* 는 액세스 권한을 공유하는 사용자의 모음입니다 [!UICONTROL destination], [!UICONTROL segment], 및 [!UICONTROL trait] 개체. 그룹을 단일 개체로만 제한하거나 다양한 개체의 조합에 대한 광범위한 액세스 권한을 제공할 수 있습니다.

<!-- t_create_groups.xml -->

그룹을 만들려면:

1. 클릭 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. 클릭  ![](assets/icon_add.png) 열다 [!UICONTROL Group Settings] 페이지.
3.  [!UICONTROL Group Details]:
   * 그룹 이름을 지정합니다.
   * 간단한 그룹 설명을 제공합니다.
4. in [!UICONTROL Group Members]에서 사용자를 클릭합니다. **[!UICONTROL Add Users]** 그룹에 추가하는 옵션.
5. in [!UICONTROL Group Permissions], 을 선택합니다. [트레이트](../../features/traits/trait-details-page.md), [세그먼트](../../features/segments/segments-purpose.md), 또는 [대상](../../features/destinations/destinations.md) 변환 전: **[!UICONTROL Add Object]**.
선택한 객체에 대한 권한 창이 열립니다.
6. 그룹 구성원이 가질 권한에 대한 확인란을 선택합니다.
7. *(선택 사항)* 지정 [와일드카드 권한](../../features/administration/administration-overview.md#wild-card-permissions) 그룹에 속해 있어야 합니다.
8. 클릭 **[!UICONTROL Save Group]**.

## 이해 [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> 사용자 계정 관리가 [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). 사용자 마이그레이션을 시작하려면 모든 Audience Manager 고객에게 이 문서에 설명된 필요한 조치를 즉시 취할 것을 권장합니다. [Admin Console으로 Audience Manager 사용자 마이그레이션](admin-console-migration.md).
> 
> 모든 고객이 마이그레이션되면 이 섹션이 사라집니다.

그룹 권한 관리 간소화 [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 그룹 구성원에게 [!UICONTROL segment], [!UICONTROL destination], 또는 [!UICONTROL trait]. 비교를 통해 일반 권한만 특정 [!UICONTROL data sources] 이러한 객체 중 하나에 매핑됩니다. 그리고 새 [!UICONTROL data sources]를 입력하면 그룹 구성원이 해당 새 소스에 액세스할 수 없습니다.

그룹 권한을 열고 새 권한을 할당해야 합니다 [!UICONTROL data sources] 그룹에 속해 있어야 합니다. [!UICONTROL Wild Card Permissions] 이 설명서를 사용하지 않도록 합니다. [!UICONTROL data source] 프로세스 업데이트. 그룹 [!UICONTROL Wild Card Permissions] 새로운 [!UICONTROL data sources] 명시적 권한 없이

![](assets/wild-card.png)

각 항목에 대한 설명은 아래 참조 [!UICONTROL wildcard permission] 의미:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - 사용자가 선택할 수 있음 [!UICONTROL traits] 을 기준 요소로 사용 [!UICONTROL models].
* `EDIT_ALL_TRAITS` - 사용자가 모두 편집 가능 [!UICONTROL traits] 회사 계정 내에서 설정합니다.
* `VIEW_ALL_TRAITS` - 사용자가 모두 볼 수 있음 [!UICONTROL traits] 회사 계정 내에서 설정합니다.
* `DELETE_ALL_TRAITS` - 사용자가 모두 삭제할 수 있음 [!UICONTROL traits] 회사 계정 내에서 설정합니다.
* `CREATE_ALL_ALGO_TRAITS` - 사용자가 만들 수 있음 [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - 사용자는 [!UICONTROL traits] 소속사에 속함 [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - 사용자가 만들 수 있음 [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - 사용자에게 볼 수 있는 권한이 있습니다. [!UICONTROL models] 해당 회사에 속해 있어야 합니다.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - 사용자가 모든 [!UICONTROL derived signals] 해당 회사에 속해 있어야 합니다.
* `CREATE_DERIVED_SIGNALS` - 사용자가 만들 수 있음 [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - 사용자가 모든 [!UICONTROL derived signals] 해당 회사에 속해 있어야 합니다.
* `DELETE_DERIVED_SIGNALS` - 사용자는 [!UICONTROL derived signals] 해당 회사에 속해 있어야 합니다.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - 사용자가 모든 [!UICONTROL destinations] 회사 계정 내에서 설정합니다.
* `CREATE_DESTINATIONS` - 사용자가 만들 수 있음 [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - 사용자가 모든 [!UICONTROL destinations] 회사 계정 내에서 설정합니다.
* `DELETE_ALL_DESTINATIONS` - 사용자가 모든 [!UICONTROL destinations] 회사 계정 내에서 설정합니다.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - 사용자는 자신의 모든 작업(보기, 만들기, 편집, 삭제)을 수행할 수 있습니다 [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - 사용자는 자신의 모든 작업(보기, 만들기, 편집, 삭제)을 수행할 수 있습니다 [!UICONTROL Audience Lab] 테스트 그룹 을 참조하십시오.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - 사용자가 세그먼트를 만들 수 있습니다.
* `DELETE_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 삭제할 수 있습니다.
* `MAP_ALL_TO_DESTINATIONS` - 사용자는 회사에 속하는 세그먼트를 대상에 매핑할 수 있습니다.
* `EDIT_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 편집할 수 있습니다.
* `MAP_ALL_SEGMENTS_TO_MODELS` - 사용자는 모델을 기준으로 세그먼트를 선택할 수 있습니다.
* `VIEW_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 볼 수 있습니다.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - 사용자는 캡처된 모든 신호를 볼 수 있습니다. [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## 사용 사례 {#use-cases}

### 사용자 액세스 모니터링 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 에서는 사용자 로그인 상태를 모니터하여 Audience Manager 인스턴스에 액세스할 수 있는 사용자를 명확하게 파악할 수 있습니다.

비즈니스 요구 사항에 따라 필요에 따라 사용자 계정을 활성화 및 비활성화할 수 있습니다.

![monitor-user-access](assets/monitor-user-access.png)

### 중요한 사용자를 위한 액세스 보호 보장 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

다음을 구성할 수 있습니다 [!UICONTROL Role-Based Access Control] at [!UICONTROL trait], 세그먼트 및 [!UICONTROL destination] 수준(각 사용자 그룹에 대해)을 지정할 수 있습니다.

이 기능을 사용하면 사용자가 특정 데이터 세트를 보고, 만들고, 읽고, 쓰고, 편집하는 방법을 관리하고, 사용자가 사용할 수 없도록 해야 하는 데이터 세트에 액세스하는 것을 제한할 수 있습니다.

![액세스 보호](assets/access-protection.png)
