---
description: 폴더 트레이트를 사용하면 동일한 폴더 내에 있는 트레이트와 모든 하위 폴더를 하나의 대상 세그먼트로 자동 집계할 수 있습니다.
keywords: 세그먼트 크기 견적 기호; SSE
seo-description: 폴더 트레이트를 사용하면 동일한 폴더 내에 있는 트레이트와 모든 하위 폴더를 하나의 대상 세그먼트로 자동 집계할 수 있습니다.
seo-title: 폴더 특성
solution: Audience Manager
title: 폴더 특성
uuid: E 561 CE 8 F -6 C 90-44 A 7-B 034-685533 F 29030
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] 동일한 폴더 내에 있는 트레이트와 모든 하위 폴더를 하나의 대상 세그먼트로 자동으로 집계할 수 있습니다.

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. 이렇게 하면 자동으로 다른 폴더 수준에서 사용자를 세그먼트화하고 타깃팅할 수 있습니다. 예를 들어 다음과 같은 폴더 구조가 있다고 가정합니다.

`*` Electronics (Parent)

`*` 랩탑 (어린이)

`*` 브랜드 (손자)

[!UICONTROL Folder traits] 자동으로 생성된 [!DNL Electronics][!UICONTROL Folder Trait] (상위 폴더 이름 기준) 폴더의 모든 사용자를 정규화합니다. 또한 파일 구조를 아래로 이동할 때 이 프로세스가 반복됩니다. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] 세그먼트 표현식에서 선택할 수 있습니다. Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

폴더 속성의 빈도 수는 해당 폴더 및 하위 폴더에서 트레이트 실현의 합계입니다. 아래 그림은 자동차 폴더에 있는 traits a, b 및 c를 보여 줍니다. 각 트레이트에 다음과 같은 개념이 있다고 가정해 보십시오.

* 특성 A: 5
* 특성 B: 1
* 특성 C: 1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] 모든 사용자를 아래에 있는 폴더 구조의 특성에서 캡처합니다. If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. 다음 보고 실행 시 보고 업데이트는 보고 날짜 범위 (1, 7, 14, 30, 60, 90, 라이프타임) 에 대한 이 변경을 반영하도록 실행됩니다. 이전 날짜의 이전 보고 수는 변경되지 않습니다.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

[!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) 를 사용하는 회사의 경우 적절한 [!UICONTROL RBAC] 권한이 있는 사용자는에 연결된 데이터 소스를 변경할 수 [!UICONTROL folder trait]있습니다. 사용자는 다음 중 하나를 사용하여 그룹에 속해야 합니다.

* `READ` 특성 데이터 소스에 `WRITE` 대한 그룹 권한을 제공합니다.
* `VIEW_ALL_TRAITS` and `EDIT_ALL_TRAITS` wild card permissions for trait data sources.

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| 항목 | 설명 |
|---|---|
| 트레이트 유형 | [!UICONTROL Onboarded traits] And [!UICONTROL algorithmic traits] Contribute at most 1 implementation to a [!UICONTROL folder trait]'s frequency. |
| 폴더 간 특성 이동 | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. 즉, 폴더에서 트레이트를 삭제하거나 이동하는 경우 트레이트 모집단 사용자는 폴더 트레이트를 세그먼트 표현식으로 사용하여 세그먼트에서 세그먼트화되지 않습니다. <br> Adobe Analytics 세그먼트 또는 보고서 세트를 Experience Cloud 조직에 매핑할 때 Audience Manager는 자동으로 해당 읽기 전용 세그먼트 및 트레이트를 새로 만듭니다. Audience Manager에서 이러한 트레이트의 저장소 위치는 편집하거나 변경할 수 없습니다. 하지만 매핑된 Adobe Analytics 세그먼트 또는 보고서 세트에서 수행하는 모든 변경 사항은 Audience Manager에 반영됩니다. |
| 시스템 변수 | [!UICONTROL Folder traits] 매개 변수를 사용하여 이벤트 호출에서 실현할 `d_sid` 수 없습니다. |
| 보고 | [!UICONTROL Folder traits] 은 자동으로 계산된 트레이트이며 **[!UICONTROL Overlap Reports]**&#x200B;나타나지 않습니다. |