---
description: 폴더 트레이트를 생성, 편집 및 삭제합니다.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: 폴더 트레이트를 생성, 편집 및 삭제합니다.
seo-title: 폴더 트레이트 관리
solution: Audience Manager
title: 폴더 트레이트 관리
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# 폴더 트레이트 관리 {#manage-folder-traits}

폴더 트레이트를 생성, 편집 및 삭제합니다.

## 폴더 특성 만들기 {#create-folder-trait}

분류 [!UICONTROL folder trait] 에서 새 폴더를 만들면 자동으로 가 만들어집니다.

<!-- create-folder-trait.xml -->

1. 트레이트 대시보드 **[!UICONTROL Audience Data > Traits]** 로 **이동합니다** .
1. 창에서 [!UICONTROL Trait Storage] 마우스를 가져갑니다.

   * &quot;모든 특성&quot; 텍스트를 추가하여 새 루트 수준 폴더를 추가합니다.
   * 새 하위 폴더를 추가할 기존 상위 폴더.

   ![](assets/folder_traits_create.PNG)

1. 폴더를 만들려면 + 아이콘을 클릭합니다. 분류에 최대 2000개의 폴더를 만들 수 있습니다. 자세한 내용은 [사용 제한](../../features/administration/usage-limits.md) 문서를 참조하십시오.
1. 폴더 이름을 지정하고 [저장]을 **클릭합니다**. 예를 들어 Electronics라는 폴더에는 &#39;Electronics Folder Trait&#39;이라는 폴더 특성이 있습니다. 트레이트 대시보드에서 새 폴더 트레이트를 보고 선택할 수 있습니다.
1. 새 폴더 특성은 생성된 데이터 소스에 자동으로 [!DNL Audience Manager] 할당됩니다. 적절한 [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) 권한을 가진 사용자는 폴더 특성 편집 워크플로우에서 데이터 소스를 변경할 수 있습니다. 폴더 [특성 편집을 참조하십시오](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## 폴더 특성 편집 {#edit-folder-trait}

컨텐츠를 편집하는 방법에 대해 설명합니다 [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. 대시보드에서 편집할 폴더 트레이트에 대한 [!UICONTROL Traits] **[!UICONTROL Actions]** 열 위로 마우스를 가져갑니다.
1. 연필을 클릭하여 트레이트를 편집합니다.

   ![](assets/folder_traits_edit_border.png)

1. 워크플로우에서는 **[!UICONTROL Edit]** 폴더 트레이트의 데이터 소스를 변경할 수 있습니다. 원하는 데이터 소스를 선택하고 을 클릭합니다 **[!UICONTROL Save]**. 데이터 소스는 드롭다운 상자 [!DNL DPID]에서 숫자로 정렬됩니다.

   회사에서 사용하는 경우 사용자 [!UICONTROL Role-Based Access Rights (RBAC)]또는 사용자는 데이터 소스를 트레이트할 [수](../../features/traits/about-folder-traits.md#role-based-access-controls) 있는 권한이 필요합니다.

>[!NOTE]
>
>폴더 트레이트의 이름을 직접 변경할 수는 없습니다. [폴더 특성 이름을 변경하려면 관련 저장소 폴더](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 이름을 변경합니다.

## 폴더 특성 삭제 {#delete-folder-trait}

트레이트가 속한 저장소 폴더를 삭제하여 폴더 트레이트를 삭제합니다.

<!-- delete-folder-trait.xml -->

1. **대상 데이터 > 트레이트를** 클릭하여 트레이트 **대시보드로** 이동합니다.
1. 창에서 폴더 위로 마우스를 가져간 다음 X 아이콘을 클릭하여 폴더를 [!UICONTROL Trait Storage] 삭제합니다.

   ![단계 결과](assets/folder_traits_create.PNG)

>[!NOTE]
>
>세그먼트 표현식에 사용하는 경우 폴더 트레이트를 삭제할 수 없습니다. 특성 [보기](../../features/traits/trait-details-page.md) 섹션으로 이동하여 폴더 특성을 사용하는 세그먼트를 확인합니다. 그런 다음 세그먼트 이름을 클릭하여 [세그먼트 요약 보기를](../../features/segments/segment-summary-view.md)열고 세그먼트 표현식에서 트레이트를 제거할 수 있습니다.
