---
description: '[관리] 메뉴의 옵션을 사용하여 Audience Manager 사용자를 만들고 그룹에 지정할 수 있습니다. 한도(트레이트, 세그먼트, 대상 및 모델)를 볼 수도 있습니다.'
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: '[관리] 메뉴의 옵션을 사용하여 Audience Manager 사용자를 만들고 그룹에 지정할 수 있습니다. 한도(트레이트, 세그먼트, 대상 및 모델)를 볼 수도 있습니다.'
seo-title: 관리
solution: Audience Manager
title: 관리
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---


# [!UICONTROL Administration] (RBAC 컨트롤)  {#administration}

![](assets/rbac-controls.png)

[!UICONTROL Administration] 메뉴의 옵션을 사용하여 Audience Manager 사용자를 만들고 그룹에 할당할 수 있습니다. 한도(트레이트, 세그먼트, 대상 및 모델)를 볼 수도 있습니다.

[!DNL Audience Manager]을(를) 사용하는 기업 고객은 모든 데이터에 대해 하나의 데이터 관리 플랫폼이 필요하지만 특정 사업부에 대해 다른 데이터 요소의 가시성을 제어할 수 있어야 합니다. 이 작업은 [!UICONTROL Role-Based Access Control]([!UICONTROL RBAC])이라고도 하는 그룹 권한을 사용하여 수행할 수 있습니다.

[!DNL Audience Manager] 그룹을 사용하여 권한을 할당합니다. 권한은 사용자 수준에서 할당되지 않습니다. 그룹 권한은 개체([!UICONTROL traits], 세그먼트 등)에 연결되어 있습니다. and to actions you can perform on those objects (edit, view 등). 이러한 컨트롤은 Audience Manager REST API를 통해서도 사용할 수 있습니다. [사용자 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [그룹 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) 및 [권한 관리](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API 메서드를 참조하십시오.

## 사용자 만들기 {#create-users}

<!-- t_create_users.xml -->

[!DNL Audience Manager]에서 사용자를 만들고 사용자 세부 사항, 로그인 상태를 지정하고 사용자를 그룹에 할당합니다.

1. 클릭 **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. ![](assets/icon_add.png)을 클릭하여 [!UICONTROL Create New User] 페이지를 표시합니다.
1. **[!UICONTROL User Details]**&#x200B;에서 필드를 채웁니다.
   * **[!UICONTROL Username]:** Audience Manager에 대한 고유한 사용자 이름을 지정합니다.
   * **[!UICONTROL First Name]:** 사용자의 이름을 지정합니다.
   * **[!UICONTROL Last Name]:** 사용자의 성을 지정합니다.
   * **[!UICONTROL Email Address]:** 사용자의 이메일 주소를 지정합니다. [!DNL Audience Manager] 사용자에게 정기적인 알림을 보내지 않습니다. [!DNL Audience Manager] 관리자는 사용자의 이메일 주소에 액세스할 수 있으며 필요에 따라 수동으로 사용자에게 이메일을 보낼 수 있습니다. 예를 들어 사용자가 암호를 잊은 경우 이 필드에 지정된 이메일 주소는 임시 암호와 암호 재설정을 위한 지침을 보내는 데 사용됩니다.
   * **[!UICONTROL Phone Number]:** 사용자의 전화 번호를 지정합니다.
   * **[!UICONTROL Is Admin]:** 이 사용자가  [!DNL Audience Manager] 관리자인지 지정합니다. 관리 사용자는 사용자를 관리(만들기, 편집 등)할 수 있습니다. 및 그룹(만들기, 권한 할당 등). 관리자가 아닌 사용자는 이메일 주소 편집 및 자체 암호 재설정을 포함하여 자신의 사용자 프로필만 제어할 수 있습니다. 자세한 내용은 [계정 설정 편집](../../features/administration/edit-account-settings.md)을 참조하십시오.
1. **[!UICONTROL Login]** 아래에서 원하는 상태를 선택합니다.
   * **[!UICONTROL Active]:**  활성 사용자는 그룹 구성원 [!DNL Audience Manager] 이 부여한 권한을 액세스하고 가질 수 있습니다.
   * **[!UICONTROL Deactivated]:**  비활성화된 사용자는 액세스할 수  [!DNL Audience Manager] 없으며 권한이 없습니다. 사용자를 비활성화하면 사용자 정보가 [!DNL Audience Manager]에 남아 있으며 필요한 경우 간단히 다시 활성화할 수 있습니다. 사용자를 제거하는 경우 나중에 다시 [!DNL Audience Manager]을(를) 사용해야 하는 경우 사용자를 다시 만들어야 합니다.
   * **[!UICONTROL Expired]사용자** 의 암호가 90일 이전입니다.
   * **[!UICONTROL Pending]사용자** 는 암호 재설정 후나 새 계정으로 임시 암호를 가지고 있으며 아직 영구 암호를 설정하지 않았습니다.
   * **[!UICONTROL Locked Out]:** 5번 잘못된 로그인 시도가 있으면 사용자가 잠깁니다.
1. **[!UICONTROL Assigned Groups]** 드롭다운 목록에서 이 사용자를 할당할 그룹을 선택합니다.
그룹 및 권한에 대한 자세한 내용은 [그룹 만들기](../../features/administration/administration-overview.md#create-group)를 참조하십시오.
1. 클릭 **[!UICONTROL Save]**.

## 웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!UICONTROL Group] {#create-group}

*group*&#x200B;은 [!UICONTROL destination], [!UICONTROL segment] 및 [!UICONTROL trait] 개체에 대한 액세스 권한을 공유하는 사용자의 컬렉션입니다. 그룹을 단일 개체로만 제한하거나 다양한 개체의 조합에 광범위한 액세스 권한을 부여할 수 있습니다.

<!-- t_create_groups.xml -->

그룹을 만들려면:

1. 클릭 **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. ![](assets/icon_add.png)을 클릭하여 [!UICONTROL Group Settings] 페이지를 엽니다.
1.  [!UICONTROL Group Details]:
   * 그룹 이름을 지정합니다.
   * 간단한 그룹 설명을 제공합니다.
1. [!UICONTROL Group Members]에서 **[!UICONTROL Add Users]** 옵션에서 사용자를 클릭하여 그룹에 추가합니다.
1. [!UICONTROL Group Permissions]에서 [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md) 또는 **[!UICONTROL Add Object]**&#x200B;에서 [destination](../../features/destinations/destinations.md)을 선택합니다.
선택한 개체에 대한 권한 창이 열립니다.
1. 그룹 구성원이 보유할 권한에 대한 확인란을 선택합니다.
1. *(선택 사항)* 그룹에  [와일드카드 권한](../../features/administration/administration-overview.md#wild-card-permissions) 을 지정합니다.
1. 클릭 **[!UICONTROL Save Group]**.

## [!UICONTROL Wild Card Permissions] {#wild-card-permissions} 이해

[!UICONTROL Wild Card Permissions]으로 그룹 권한 관리를 간소화할 수 있습니다.

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] 그룹 구성원에게  [!UICONTROL segment],  [!UICONTROL destination]또는 [!UICONTROL trait] 등과 연관된 각 데이터 소스에 대한 자동 액세스 권한을 부여합니다. 이에 비해 일반 권한에서는 이러한 개체 중 하나에 특정 [!UICONTROL data sources]만 할당할 수 있습니다. 또한 새 [!UICONTROL data sources]을(를) 추가하면 그룹 구성원이 해당 새로운 소스에 액세스할 수 없습니다.

그룹 권한을 열고 새 [!UICONTROL data sources]을 그룹에 할당해야 합니다. [!UICONTROL Wild Card Permissions] 이 수동  [!UICONTROL data source] 업데이트 프로세스를 피할 수 있습니다. [!UICONTROL Wild Card Permissions]이(가) 있는 그룹은 명시적인 권한 없이 새 [!UICONTROL data sources]에 액세스할 수 있습니다.

![](assets/wild-card.png)

각 [!UICONTROL wildcard permission]의 의미에 대한 설명은 아래를 참조하십시오.

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - 사용자는 기준 [!UICONTROL traits] 으로 선택할 수  [!UICONTROL models]있습니다.
* `EDIT_ALL_TRAITS` - 사용자는 회사 계정 내에서  [!UICONTROL traits] 설정한 모든 설정을 편집할 수 있습니다.
* `VIEW_ALL_TRAITS` - 사용자는 회사 계정 내에서  [!UICONTROL traits] 설정한 모든 설정을 볼 수 있습니다.
* `DELETE_ALL_TRAITS` - 사용자는 회사 계정 내에서  [!UICONTROL traits] 설정한 모든 설정을 삭제할 수 있습니다.
* `CREATE_ALL_ALGO_TRAITS` - 사용자가 만들 수  [!UICONTROL algorithmic traits]있습니다.
* `MAP_ALL_TO_SEGMENTS` - 사용자는 자신의 회사 [!UICONTROL traits] 에 속하는 항목을 추가할 수  [!UICONTROL segments]있습니다.
* `CREATE_ALL_TRAITS` - 사용자가 만들 수  [!UICONTROL traits]있습니다.

**[!UICONTROL Reports]**

* `PTRREPORTS` -  [!UICONTROL wildcard permission] 이것은 오래된 기능을 의미하며, 곧 Audience Manager 사용자 인터페이스에서 제거됩니다.

**[!UICONTROL Models]**

* `VIEW_MODELS` - 사용자에게 회사  [!UICONTROL models] 소속을 볼 수 있는 권한이 있습니다.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - 사용자는 자신의 회사에  [!UICONTROL derived signals] 속하는 모든 항목을 볼 수 있습니다.
* `CREATE_DERIVED_SIGNALS` - 사용자가 만들 수  [!UICONTROL derived signals]있습니다.
* `EDIT_DERIVED_SIGNALS` - 사용자는 회사에  [!UICONTROL derived signals] 속한 모든 항목을 편집할 수 있습니다.
* `DELETE_DERIVED_SIGNALS` - 사용자가 회사의  [!UICONTROL derived signals] 소속을 삭제할 수 있습니다.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - 사용자는 회사 계정 내에서  [!UICONTROL destinations] 설정한 모든 설정을 편집할 수 있습니다.
* `CREATE_DESTINATIONS` - 사용자가 만들 수  [!UICONTROL destinations]있습니다.
* `VIEW_ALL_DESTINATIONS` - 사용자는 회사 계정 내에서  [!UICONTROL destinations] 설정한 모든 설정을 볼 수 있습니다.
* `DELETE_ALL_DESTINATIONS` - 사용자는 회사 계정 내에서  [!UICONTROL destinations] 설정한 모든 설정을 삭제할 수 있습니다.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - 사용자는 모든 작업(보기, 만들기, 편집, 삭제)을 수행할 수 있습니다 [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - 사용자는  [!UICONTROL Audience Lab] 테스트 그룹에서 모든 작업(보기, 만들기, 편집, 삭제)을 수행할 수 있습니다.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - 사용자는 세그먼트를 만들 수 있습니다.
* `DELETE_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 삭제할 수 있습니다.
* `MAP_ALL_TO_DESTINATIONS` - 사용자는 회사에 속하는 세그먼트를 대상에 매핑할 수 있습니다.
* `EDIT_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 편집할 수 있습니다.
* `MAP_ALL_SEGMENTS_TO_MODELS` - 사용자는 세그먼트를 모델의 기준선으로 선택할 수 있습니다.
* `VIEW_ALL_SEGMENTS` - 사용자는 회사 계정 내에 설정된 모든 세그먼트를 볼 수 있습니다.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - 사용자는  [Data Explorer에서 캡처한 모든 신호를 볼 수 있습니다](/help/using/features/data-explorer/data-explorer-overview.md).

## 사용 사례 {#use-cases}

### 사용자 액세스 모니터링 {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] 사용자 로그인 상태를 모니터링하여 Audience Manager 인스턴스에 액세스할 수 있는 사용자를 명확하게 파악할 수 있도록 할 수 있습니다.

비즈니스 요구 사항에 따라 필요에 따라 사용자 계정을 활성화하거나 비활성화할 수 있습니다.

![모니터 사용자 액세스](assets/monitor-user-access.png)

### 민감한 [!UICONTROL Data Sources] {#protect-sensitive-data-sources}에 대한 액세스 보호 확인

각 사용자 그룹에 대해 [!UICONTROL trait], 세그먼트 및 [!UICONTROL destination] 수준에서 [!UICONTROL Role-Based Access Control]을 구성할 수 있습니다.

이 기능은 사용자가 특정 데이터 세트를 보고, 만들고, 읽고, 쓰고, 편집하는 방법을 관리하고, 사용자가 사용할 수 없도록 데이터 세트에 액세스하는 것을 제한하도록 도와줍니다.

![접근 보호](assets/access-protection.png)
