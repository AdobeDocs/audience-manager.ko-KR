---
description: 관리 메뉴 아래의 옵션을 사용하여 Audience Manager 사용자를 만들고 그룹에 할당할 수 있습니다. 한도 (트레이트, 세그먼트, 대상 및 모델) 도 볼 수 있습니다.
keywords: rbac; rbac; 역할 기반; 역할 기반; 역할 기반의 액세스 제어
seo-description: 관리 메뉴 아래의 옵션을 사용하여 Audience Manager 사용자를 만들고 그룹에 할당할 수 있습니다. 한도 (트레이트, 세그먼트, 대상 및 모델) 도 볼 수 있습니다.
seo-title: 관리
solution: Audience Manager
title: 관리
topic: DIL API
uuid: 498 E 0316-CF 1 B -43 E 9-88 BA -338 EE 0 DAF 225
translation-type: tm+mt
source-git-commit: 5d66c44a9072129de9da69918e9eeda2e18ccb22

---


# Administration (RBAC Controls) {#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] 메뉴 아래의 옵션을 사용하여 Audience Manager 사용자를 만들고 그룹에 할당할 수 있습니다. 한도 (트레이트, 세그먼트, 대상 및 모델) 도 볼 수 있습니다.

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] 그룹을 사용하여 권한을 지정합니다. 권한은 사용자 수준에서 할당되지 않습니다. 그룹 권한은 개체 (특성, 세그먼트 등) 와 And to action you can perform on those objects (edit, view, etc.). 이러한 컨트롤은 Audience Manager REST API를 통해서도 사용할 수 있습니다. [사용자 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [그룹 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)및 [권한 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API 방법을 참조하십시오.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. **[!UICONTROL Administration]****[!UICONTROL Users]**&gt;를 클릭합니다.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **사용자 이름:** Audience Manager에 대한 고유한 사용자 이름을 지정합니다.
   * **이름:** 사용자의 이름을 지정합니다.
   * **성:** 사용자의 성을 지정합니다.
   * **이메일 주소:** 사용자의 이메일 주소를 지정합니다. [!DNL Audience Manager] 사용자에게 정기적인 알림을 보내지 않습니다. [!DNL Audience Manager] 관리자는 사용자의 이메일 주소에 액세스할 수 있으며 필요에 따라 사용자를 수동으로 보낼 수 있습니다. 예를 들어 사용자가 자신의 암호를 잊어버린 경우 이 필드에 지정된 이메일 주소를 사용하여 임시 암호 및 암호를 재설정하는 지침을 보냅니다.
   * **전화 번호:** 사용자의 전화 번호를 지정합니다.
   * **관리자임:** 이 사용자가 [!DNL Audience Manager] 관리자인지 여부를 지정합니다. 관리 사용자는 사용자를 관리할 수 있습니다 (만들기, 편집 등). AND groups (create, assign permissions, etc.). 관리자가 아닌 사용자는 이메일 주소 편집, 암호 재설정을 비롯하여 자신의 사용자 프로필만 제어할 수 있습니다. For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **활성:** 활성 사용자는 그룹 멤버쉽에 의해 부여된 권한을 [!DNL Audience Manager] 액세스하고 액세스할 수 있습니다.
   * **비활성화됨:** 비활성화된 사용자는 액세스할 [!DNL Audience Manager] 수 없으며 권한이 없습니다. If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **만료됨:** 사용자의 암호가 90 일 미만입니다.
   * **보류 중:** 사용자는 암호 재설정 후 또는 새 계정으로 임시 암호를 가지고 있으며 아직 영구 암호를 설정하지 않았습니다.
   * **잠김:** 5 잘못된 로그인 시도가 수행되면 사용자가 잠깁니다.
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#create-group).
1. 클릭 **[!UICONTROL Save]**.

## 그룹 만들기 {#create-group}

*그룹은* 대상, 세그먼트 및 특성 개체에 대한 액세스 권한을 공유하는 사용자 모음입니다. 그룹을 단일 개체로만 제한하거나 여러 개체의 조합에 대한 광범위한 액세스를 제공할 수 있습니다.

<!-- t_create_groups.xml -->

그룹을 만들려면:

1. **[!UICONTROL Administration]****[!UICONTROL Groups]**&gt;를 클릭합니다.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1.  [!UICONTROL Group Details]:
   * 그룹 이름을 지정합니다.
   * 간단한 그룹 설명을 제공합니다.
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
이렇게 하면 선택한 개체에 대한 권한 창이 열립니다.
1. 그룹 구성원이 보유할 권한에 해당하는 확인란을 선택합니다.
1. *(선택 사항)* [그룹에 와일드카드 권한을](../../features/administration/administration-overview.md#wild-card-permissions) 할당합니다.
1. 클릭 **[!UICONTROL Save Group]**.

## Understanding Wild Card Permissions {#wild-card-permissions}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 그룹 구성원이 세그먼트, 대상 또는 트레이트와 연관된 각 데이터 소스에 자동으로 액세스할 수 있도록 합니다. 비교를 통해 일반 권한은 이러한 개체 중 하나에 특정 Data Sources만 할당할 수 있게 합니다. 또한 새 Data Sources를 추가하면 그룹 구성원이 해당 새 소스에 액세스할 수 없습니다.

그룹 권한을 열고 해당 새 Data Sources를 그룹에 할당해야 합니다. [!UICONTROL Wild Card Permissions] 이 수동 데이터 소스 업데이트 프로세스를 피할 수 있습니다. Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

각 와일드카드 권한이 의미하는 바를 보려면 아래를 참조하십시오.

**특성**

* `MAP_ALL_TRAITS_TO_MODELS` - 사용자는 모델의 기준선으로 트레이트를 선택할 수 있습니다.
* `EDIT_ALL_TRAITS` - 사용자는 회사에 속한 모든 트레이트를 편집할 수 있습니다 (pid).
* `VIEW_ALL_TRAITS` - 사용자는 회사 (pid) 에 속하는 모든 트레이트를 볼 수 있습니다.
* `DELETE_ALL_TRAITS` - 사용자는 회사에 속한 모든 트레이트를 삭제할 수 있습니다 (pid).
* `CREATE_ALL_ALGO_TRAITS` - 사용자는 알고리즘 특성을 만들 수 있습니다.
* `MAP_ALL_TO_SEGMENTS` - 사용자는 회사에 속하는 트레이트를 세그먼트에 추가할 수 있습니다.
* `CREATE_ALL_TRAITS` - 사용자는 트레이트를 만들 수 있습니다.

**보고서**

* `PTRREPORTS` - 이 와일드카드 권한은 오래된 기능을 참조하며 곧 Audience Manager UI에서 제거될 예정입니다.

**models**

* `VIEW_MODELS` - 사용자는 회사에 속한 모델을 볼 수 있는 권한을 가집니다.

**파생 신호**

* `VIEW_DERIVED_SIGNALS` - 사용자는 회사에 속한 모든 파생 신호를 볼 수 있습니다.
* `CREATE_DERIVED_SIGNALS` - 사용자는 파생된 신호를 만들 수 있습니다.
* `EDIT_DERIVED_SIGNALS` - 사용자는 회사에 속한 모든 파생 신호를 편집할 수 있습니다.
* `DELETE_DERIVED_SIGNALS` - 사용자는 회사에 속한 파생된 신호를 삭제할 수 있습니다.

**대상**

* `EDIT_ALL_DESTINATIONS` - 사용자는 회사 계정 내에 설정된 모든 대상을 편집할 수 있습니다.
* `CREATE_DESTINATIONS` - 사용자는 대상을 만들 수 있습니다.
* `VIEW_ALL_DESTINATIONS` - 사용자는 회사 계정 내에 설정된 모든 대상을 볼 수 있습니다.
* `DELETE_ALL_DESTINATIONS` - 사용자는 회사 계정 내에 설정된 모든 대상을 삭제할 수 있습니다.

**태그**

* `VIEW_TAGS` - 사용자는 태그 컨테이너에서 모든 것 (보기, 작성, 편집, 삭제) 를 수행할 수 있습니다.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - 사용자는 Audience Lab 테스트 그룹에서 모든 작업을 수행할 수 있습니다 (보기, 생성, 편집, 삭제).

**세그먼트**

* `CREATE_ALL_SEGMENTS` - 사용자는 세그먼트를 만들 수 있습니다.
* `DELETE_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 삭제할 수 있습니다.
* `MAP_ALL_TO_DESTINATIONS` - 사용자는 회사에 속하는 세그먼트를 대상에 매핑할 수 있습니다.
* `EDIT_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 편집할 수 있습니다.
* `MAP_ALL_SEGMENTS_TO_MODELS` - 사용자는 세그먼트를 모델의 기준선으로 선택할 수 있습니다.
* `VIEW_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 볼 수 있습니다.

**신호**

* `VIEW_ALL_SIGNALS` - 사용자는 [데이터 탐색기에서 캡처한 모든 신호를 볼](/help/using/features/data-explorer/data-explorer-overview.md)수 있습니다.