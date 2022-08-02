---
description: 폴더 트레이트를 만들고, 편집하고, 삭제합니다.
keywords: 폴더 트레이트;폴더 트레이트;폴더 트레이트;폴더 트레이트
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: 폴더 트레이트 관리
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 5%

---

# 폴더 트레이트 관리 {#manage-folder-traits}

폴더 트레이트를 만들고, 편집하고, 삭제합니다.

## 폴더 트레이트 만들기 {#create-folder-trait}

A [!UICONTROL folder trait] 분류에서 새 폴더를 만들 때 자동으로 만들어집니다.

<!-- create-folder-trait.xml -->

1. 이동 **[!UICONTROL Audience Data > Traits]** 로 이동 **트레이트** 대시보드 .
1. 에서 [!UICONTROL Trait Storage] 창을 마우스로 가리킨 다음,

   * 새 루트 수준 폴더를 추가할 &quot;모든 트레이트&quot; 텍스트입니다.
   * 새 하위 폴더를 추가할 기존 상위 폴더입니다.

   ![](assets/folder_traits_create.PNG)

1. 폴더를 만들려면 + 아이콘을 클릭합니다. 분류에 최대 2000개의 폴더를 만들 수 있습니다. 자세한 내용은 [사용 제한](../../features/administration/usage-limits.md) 문서를 참조하십시오.
1. 폴더 이름을 지정하고 **저장**. 예를 들어 Electronics라는 폴더에는 &#39;전자 폴더 트레이트&#39;라는 폴더 트레이트가 있습니다. 트레이트 대시보드에서 새 폴더 트레이트를 보고 선택할 수 있습니다.
1. 새 폴더 트레이트가 자동으로 [!DNL Audience Manager] 생성된 데이터 소스입니다. 적절한 사용자를 [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) 권한은 폴더 트레이트 편집 워크플로우에서 데이터 소스를 변경할 수 있습니다. 자세한 내용은 [폴더 트레이트 편집](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## 폴더 트레이트 편집 {#edit-folder-trait}

편집 방법을 설명합니다. [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. 에서 [!UICONTROL Traits] 대시보드 위에 마우스를 놓습니다 **[!UICONTROL Actions]** 편집할 폴더 트레이트에 대한 열입니다.
1. 연필을 클릭하여 트레이트를 편집합니다.

   ![](assets/folder_traits_edit_border.png)

1. 다음 **[!UICONTROL Edit]** 워크플로우를 통해 폴더 트레이트에 대한 데이터 소스를 변경할 수 있습니다. 원하는 데이터 소스를 선택하고 을(를) 클릭합니다 **[!UICONTROL Save]**. 데이터 소스는 숫자로 정렬됩니다. [!DNL DPID]를 입력합니다.

   회사에서 [!UICONTROL Role-Based Access Rights (RBAC)], 또는 사용자에게 필요한 [액세스 권한](../../features/traits/about-folder-traits.md#role-based-access-controls) 트레이트 데이터 소스에 추가합니다.

>[!NOTE]
>
>폴더 트레이트의 이름은 직접 변경할 수 없습니다. [연결된 저장소 폴더의 이름을 변경합니다](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 폴더 트레이트의 이름을 변경하려면 다음을 수행하십시오.

## 폴더 트레이트 삭제 {#delete-folder-trait}

트레이트가 속한 저장소 폴더를 삭제하여 폴더 트레이트를 삭제합니다.

<!-- delete-folder-trait.xml -->

1. **대상 데이터 > 트레이트** 로 이동 **트레이트** 대시보드 .
1. 에서 [!UICONTROL Trait Storage] 폴더로 마우스를 가져간 후 X 아이콘을 클릭하여 폴더를 삭제합니다.

   ![단계 결과](assets/folder_traits_create.PNG)

>[!NOTE]
>
>폴더 트레이트가 세그먼트 표현식에서 사용되는 경우 삭제할 수 없습니다. 로 이동합니다 [트레이트 보기](../../features/traits/trait-details-page.md) 섹션을 참조하십시오. 그런 다음 세그먼트 이름을 클릭하여 를 엽니다 [세그먼트 요약 보기](../../features/segments/segment-summary-view.md): 세그먼트 표현식에서 트레이트를 제거할 수 있습니다.
