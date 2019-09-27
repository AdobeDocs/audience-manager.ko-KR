---
description: 폴더 트레이트를 사용하면 동일한 폴더 내에 있는 트레이트와 모든 하위 폴더를 타깃팅 가능한 세그먼트에 자동으로 집계할 수 있습니다.
keywords: 세그먼트 크기 견적 도구;sse
seo-description: 폴더 트레이트를 사용하면 동일한 폴더 내에 있는 트레이트와 모든 하위 폴더를 타깃팅 가능한 세그먼트에 자동으로 집계할 수 있습니다.
seo-title: 폴더 트레이트 정보
solution: Audience Manager
title: 폴더 트레이트 정보
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

---


# 폴더 트레이트:정보 {#folder-traits-about}

[!UICONTROL Folder traits] 동일한 폴더 및 모든 하위 폴더에 있는 트레이트를 타깃팅 가능한 세그먼트에 자동으로 집계할 수 있습니다.

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. This lets you automatically segment and target your users at different folder levels. For example, let's say you have a folder structure like this:

`*` Electronics (parent)

     Laptops (child)`*`

         Brands (grandchild)`*`

[!UICONTROL Folder traits] qualify all the users in these folders in an automatically created   (based on the name of the parent folder). [!DNL Electronics][!UICONTROL Folder Trait] And, this process repeats itself as you move down the file structure. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops .[!UICONTROL Folder Trait]

[!UICONTROL Folder traits] 세그먼트 표현식에서 선택할 수 있습니다. 를 [!UICONTROL folder trait] [!UICONTROL OR] 선택하는 것은 해당 폴더 및 하위 폴더에서 그룹을 사용하여 모든 트레이트를 선택하는 것과 같습니다.

![](assets/folder-traits-compare-border.jpg)

## 폴더 트레이트 구현 - 최근 및 빈도 {#folder-traits-realization}

폴더 트레이트의 빈도 수는 해당 폴더 및 하위 폴더의 트레이트의 합입니다. 아래 그림에서는 Automobile 폴더에 있는 트레이트 A, B 및 C를 보여 줍니다. 각 트레이트에는 다음과 같은 재정의가 있습니다.

* 특성 A:5
* 트레이트 B:1
* 트레이트 C:1

이 경우 7개의 [!DNL Automobile Folder Trait] 깨달음이 있습니다.

![](assets/folder_traits_rollup_border.png)

## 폴더 특성 보고 {#folder-traits-reporting}

[!UICONTROL Folder traits] 아래 폴더 구조의 트레이트에서 모든 사용자를 캡처합니다. 한 폴더에서 다른 폴더로 트레이트를 이동하는 경우 변경 사항이 트레이트 규칙 변경과 마찬가지로 [데이터 수집 서버로](../../reference/system-components/components-data-collection.md) 전파됩니다. 보고 날짜 범위(1, 7, 14, 30, 60, 90)에서 이 변경 사항을 반영하도록 다음 보고 실행의 보고 업데이트가 업데이트됩니다. The old reporting numbers from the previous days will not change.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using  (), your users with the appropriate  permissions are able to change the data source associated to the . [!UICONTROL Role-Based Access Controls][!UICONTROL RBAC][!UICONTROL RBAC][!UICONTROL folder trait] A user must belong to a group with either of the following:

* `READ` and  group permissions to a trait data source.`WRITE`
* `VIEW_ALL_TRAITS` and  wild card permissions for trait data sources.`EDIT_ALL_TRAITS`

Learn how to assign  permissions in our administration documentation.[!UICONTROL RBAC][](../../features/administration/administration-overview.md#create-group)

## 제한 및 기타 고려 사항 {#limits}

| 항목 | 설명 |
|---|---|
| 특성 유형 | [!UICONTROL Onboarded traits] 그리고 [!UICONTROL algorithmic traits] 대부분의 1회 구현 시 [!UICONTROL folder trait]빈도에 기여합니다. |
| 폴더 간 트레이트 이동 | 한 폴더에서 다른 폴더로 트레이트를 이동하면 해당 트레이트가 첫 번째 폴더 트레이트로부터 가려져서 두 번째 폴더로 자격이 [!UICONTROL folder trait]주어집니다. 즉, 폴더에서 트레이트를 삭제하거나 이동하는 경우, 특성 모집단의 사용자는 세그먼트 표현식으로 폴더 트레이트를 사용하여 세그먼트에서 세그먼트화되지 않습니다. <br> Adobe Analytics 세그먼트 또는 보고서 세트를 Experience Cloud 조직에 매핑하면 Audience Manager는 자동으로 해당 읽기 전용 새 세그먼트 및 트레이트를 만듭니다. Audience Manager에서는 이러한 트레이트의 저장 위치를 편집하거나 변경할 수 없습니다. 그러나 매핑된 Adobe Analytics 세그먼트 또는 보고서 세트에서 수행한 모든 변경 사항은 Audience Manager에 반영됩니다. |
| 시스템 변수 | [!UICONTROL Folder traits] 매개 변수를 사용하여 이벤트 호출에서 구현할 수 `d_sid` 없습니다. |
| 보고 | [!UICONTROL Folder traits] 는 자동 계산되는 트레이트이며 에 나타나지 않습니다 **[!UICONTROL Overlap Reports]**. |