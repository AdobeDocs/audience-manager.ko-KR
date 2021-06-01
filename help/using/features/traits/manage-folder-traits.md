---
description: 폴더 트레이트를 만들고, 편집하고, 삭제합니다.
keywords: 폴더 트레이트;폴더 트레이트;폴더 트레이트;폴더 트레이트
seo-description: 폴더 트레이트를 만들고, 편집하고, 삭제합니다.
seo-title: 폴더 트레이트 관리
solution: Audience Manager
title: 폴더 트레이트 관리
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: 트레이트
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 9%

---

# 폴더 트레이트 관리 {#manage-folder-traits}

폴더 트레이트를 만들고, 편집하고, 삭제합니다.

## 폴더 트레이트 {#create-folder-trait} 만들기

분류에 새 폴더를 만들 때 자동으로 [!UICONTROL folder trait]이 만들어집니다.

<!-- create-folder-trait.xml -->

1. **[!UICONTROL Audience Data > Traits]** 로 이동하여 **트레이트** 대시보드로 이동합니다.
1. [!UICONTROL Trait Storage] 창에서 다음 위로 마우스를 가져갑니다.

   * 새 루트 수준 폴더를 추가할 &quot;모든 트레이트&quot; 텍스트입니다.
   * 새 하위 폴더를 추가할 기존 상위 폴더입니다.

   ![](assets/folder_traits_create.PNG)

1. 폴더를 만들려면 + 아이콘을 클릭합니다. 분류에 최대 2000개의 폴더를 만들 수 있습니다. 자세한 내용은 [사용 제한](../../features/administration/usage-limits.md) 문서를 참조하십시오.
1. 폴더 이름을 지정하고 **저장**&#x200B;을 클릭합니다. 예를 들어 Electronics라는 폴더에는 &#39;전자 폴더 트레이트&#39;라는 폴더 트레이트가 있습니다. 트레이트 대시보드에서 새 폴더 트레이트를 보고 선택할 수 있습니다.
1. 새 폴더 트레이트는 생성된 데이터 소스에 자동으로 할당됩니다. [!DNL Audience Manager] 적절한 [!UICONTROL Role-Based Access Control]([!DNL RBAC]) 권한을 가진 사용자는 폴더 트레이트 편집 워크플로우에서 데이터 소스를 변경할 수 있습니다. [폴더 트레이트 편집](../../features/traits/manage-folder-traits.md#edit-folder-trait)을 참조하십시오.

## 폴더 트레이트 {#edit-folder-trait} 편집

[!UICONTROL folder trait]을 편집하는 방법에 대해 설명합니다.

<!-- edit-folder-trait.xml -->

1. [!UICONTROL Traits] 대시보드에서 편집할 폴더 트레이트에 대한 **[!UICONTROL Actions]** 열을 마우스로 가리킵니다.
1. 연필을 클릭하여 트레이트를 편집합니다.

   ![](assets/folder_traits_edit_border.png)

1. **[!UICONTROL Edit]** 워크플로우를 통해 폴더 트레이트의 데이터 소스를 변경할 수 있습니다. 원하는 데이터 소스를 선택하고 **[!UICONTROL Save]** 을 클릭합니다. 데이터 소스는 드롭다운 상자에서 [!DNL DPID] 별로 숫자로 정렬됩니다.

   회사에서 [!UICONTROL Role-Based Access Rights (RBAC)]을 사용하는 경우, 사용자나 사용자는 데이터 소스를 트레이트하기 위해 [액세스 권한](../../features/traits/about-folder-traits.md#role-based-access-controls)이 필요합니다.

>[!NOTE]
>
>폴더 트레이트의 이름은 직접 변경할 수 없습니다. [폴더 트레이트의 ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) 이름을 변경하려면 관련 저장소 폴더의 이름을 변경합니다.

## 폴더 트레이트 {#delete-folder-trait} 삭제

트레이트가 속한 저장소 폴더를 삭제하여 폴더 트레이트를 삭제합니다.

<!-- delete-folder-trait.xml -->

1. **대상 데이터 >** 트레이트 를 사용하여 트레이트 대시보드로  **** 이동합니다.
1. [!UICONTROL Trait Storage] 창에서 폴더를 마우스로 가리키고 X 아이콘을 클릭하여 삭제합니다.

   ![단계 결과](assets/folder_traits_create.PNG)

>[!NOTE]
>
>폴더 트레이트가 세그먼트 표현식에서 사용되는 경우 삭제할 수 없습니다. [트레이트 보기](../../features/traits/trait-details-page.md) 섹션으로 이동하여 폴더 트레이트를 사용하는 세그먼트를 확인합니다. 그런 다음 세그먼트 이름을 클릭하여 [세그먼트 요약 보기](../../features/segments/segment-summary-view.md)를 엽니다. 그러면 세그먼트 표현식에서 특성을 제거할 수 있습니다.
