---
description: 폴더 트레이트를 만들고 편집하고 삭제합니다.
keywords: 폴더 특성; Folder Traits; Folder Traits; 폴더 특성
seo-description: 폴더 트레이트를 만들고 편집하고 삭제합니다.
seo-title: 폴더 특성 관리
solution: Audience Manager
title: 폴더 특성 관리
uuid: 287 AC 280-BD 58-4985-85 BD-B 6501 EB 64 B 7 F
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

폴더 트레이트를 만들고 편집하고 삭제합니다.

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. **[!UICONTROL Audience Data > Traits]****트레이트** 대시보드로 이동하려면 이동합니다.
1. [!UICONTROL Trait Storage] 창에서 마우스를 가리킵니다.

   * " 모든 트레이트 "텍스트를 사용하여 새로운 루트 수준 폴더를 추가합니다.
   * 새 하위 폴더를 추가할 기존 상위 폴더입니다.
   ![](assets/folder_traits_create.PNG)

1. 폴더를 만들려면 + 아이콘을 클릭합니다. 분류에 최대 2000개의 폴더를 만들 수 있습니다. 자세한 내용은 [사용 제한](../../features/administration/usage-limits.md) 문서를 참조하십시오.
1. Name the folder and click **Save**. 예를 들어 Electronics 라는 이름의 폴더에'Electronics Folder Trait'라는 이름의 폴더 속성이 있습니다. Traits 대시보드에서 새 폴더 트레이트를 보고 선택할 수 있습니다.
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. [!UICONTROL Traits] 대시보드에서 편집할 폴더 특성에 대한 **[!UICONTROL Actions]** 열 위로 마우스를 가져갑니다.
1. 연필을 클릭하여 트레이트를 편집합니다.

   ![](assets/folder_traits_edit_border.png)

1. **[!UICONTROL Edit]** 워크플로우에서는 폴더 특성에 대한 데이터 소스를 변경할 수 있습니다. Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>폴더 특성 이름은 직접 변경할 수 없습니다. [폴더 특성 이름을 변경하려면 연결된 저장소 폴더](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 이름을 변경합니다.

## Delete a Folder Trait {#delete-folder-trait}

트레이트가 속한 저장소 폴더를 삭제하여 폴더 특성을 삭제합니다.

<!-- delete-folder-trait.xml -->

1. **대상 데이터 &gt; 트레이트를** **참조하십시오.**
1. [!UICONTROL Trait Storage] 창에서 폴더 위에 마우스를 놓고 X 아이콘을 클릭하여 폴더를 삭제합니다.

   ![단계 결과](assets/folder_traits_create.PNG)

>[!NOTE]
>
>세그먼트 표현식에서 사용되는 경우 폴더 트레이트는 삭제할 수 없습니다. [특성 보기](../../features/traits/trait-details-page.md) 섹션으로 이동하여 폴더 트레이트를 사용하는 세그먼트를 확인합니다. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.