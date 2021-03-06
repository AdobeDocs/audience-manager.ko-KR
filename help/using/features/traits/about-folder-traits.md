---
description: 폴더 트레이트를 사용하면 동일한 폴더 및 모든 하위 폴더에 있는 트레이트를 타겟팅 가능한 세그먼트에 자동으로 집계할 수 있습니다.
keywords: 세그먼트 크기 견적 도구;sse
seo-description: 폴더 트레이트를 사용하면 동일한 폴더 및 모든 하위 폴더에 있는 트레이트를 타겟팅 가능한 세그먼트에 자동으로 집계할 수 있습니다.
seo-title: 폴더 트레이트 정보
solution: Audience Manager
title: 폴더 트레이트 정보
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: 트레이트
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 1%

---

# 폴더 트레이트: 설명 {#folder-traits-about}

[!UICONTROL Folder traits] 동일한 폴더 및 모든 하위 폴더에 있는 트레이트를 타겟팅 가능한 세그먼트에 자동으로 집계할 수 있습니다.

## 폴더 트레이트 사용의 이점 {#benefits}

[!UICONTROL folder trait] 은 상위 폴더 및 관련 하위 폴더의 모든 트레이트를 포함합니다. 이렇게 하면 다른 폴더 수준에서 사용자를 자동으로 세그먼트화하고 타깃팅할 수 있습니다. 예를 들어 다음과 같은 폴더 구조가 있다고 가정합니다.

`*` 전자 제품(상위)

    `*` 노트북(하위)

        `*` 브랜드(손자)

[!UICONTROL Folder traits] 상위 폴더의 이름에 따라 자동으로 생성된  [!DNL Electronics] [!UICONTROL Folder Trait] 에서 이러한 폴더의 모든 사용자를 분류합니다. 파일 구조를 아래로 이동할 때 이 프로세스가 반복됩니다. 이 경우 폴더 트레이트는 자동으로 생성된 랩탑 [!UICONTROL Folder Trait]에서 랩탑 및 브랜드 폴더의 모든 사용자를 캡처합니다.

[!UICONTROL Folder traits] 세그먼트 표현식에서 선택할 수 있습니다. [!UICONTROL folder trait] 을 선택하는 것은 해당 폴더 내의 모든 트레이트와 하위 폴더를 [!UICONTROL OR] 그룹으로 선택하는 것과 같습니다.

![](assets/folder-traits-compare-border.jpg)

## 폴더 트레이트 실현 - 최신성 및 빈도 {#folder-traits-realization}

폴더 트레이트의 빈도 수는 폴더 및 해당 하위 폴더에 있는 트레이트의 실현 합계입니다. 아래 그림은 자동차 폴더에 있는 트레이트 A, B 및 C를 보여줍니다. 각 트레이트에 다음과 같은 실현을 고려합니다.

* 트레이트 A:5개
* 트레이트 B:3
* 트레이트 C:3

이 경우 [!DNL Automobile Folder Trait]은 7개의 실현을 갖습니다.

![](assets/folder_traits_rollup_border.png)

## 폴더 트레이트 보고 {#folder-traits-reporting}

[!UICONTROL Folder traits] 아래 폴더 구조의 트레이트에서 모든 사용자를 캡처합니다. 폴더에서 다른 폴더로 트레이트를 이동하면 트레이트 규칙 변경과 마찬가지로 변경 사항이 [데이터 수집 서버](../../reference/system-components/components-data-collection.md)로 전달됩니다. 보고 날짜 범위(1, 7, 14, 30, 60, 90)에서 이 변경 사항을 반영하도록 다음 보고 실행의 보고 업데이트가 있습니다. 이전 날짜의 이전 보고 번호는 변경되지 않습니다.

## 역할 기반 액세스 제어(RBAC) 권한 {#role-based-access-controls}

[!UICONTROL Role-Based Access Controls]([!UICONTROL RBAC])을 사용하는 회사의 경우 적절한 [!UICONTROL RBAC] 권한을 가진 사용자는 [!UICONTROL folder trait]에 연결된 데이터 소스를 변경할 수 있습니다. 사용자는 다음 중 하나가 있는 그룹에 속해야 합니다.

* `READ` 및  `WRITE` 그룹 권한을 트레이트 데이터 소스에 그룹화합니다.
* `VIEW_ALL_TRAITS` 및  `EDIT_ALL_TRAITS` 특성 데이터 소스에 대한 와일드카드 권한 을 사용하십시오.

[관리 설명서](../../features/administration/administration-overview.md#create-group)에서 [!UICONTROL RBAC] 권한을 할당하는 방법을 알아봅니다.

## 제한 및 기타 고려 사항 {#limits}

| 항목 | 설명 |
|---|---|
| 트레이트 유형 | [!UICONTROL Onboarded traits] 그리고  [!UICONTROL algorithmic traits] 의 주파수에 대한 최대 1가지 실현 [!UICONTROL folder trait]에 기여합니다. |
| 폴더 간 트레이트 이동 | 폴더에서 다른 폴더로 트레이트를 이동하면 해당 트레이트가 첫 번째 폴더 트레이트에서 자격을 잃게 되고 두 번째 [!UICONTROL folder trait]에 대한 자격이 부여됩니다. 즉, 폴더에서 트레이트를 삭제하거나 이동하는 경우 트레이트 모집단의 사용자가 폴더 트레이트를 세그먼트 표현식으로 사용하여 세그먼트에서 세그먼트화되지 않습니다. <br> Adobe Analytics 세그먼트 또는 보고서 세트를 Experience Cloud 조직에 매핑하면 Audience Manager이 자동으로 해당 읽기 전용 새 세그먼트와 트레이트를 만듭니다. Audience Manager에서 이러한 트레이트의 저장소 위치를 편집하거나 변경할 수 없습니다. 하지만 매핑된 Adobe Analytics 세그먼트 또는 보고서 세트에서 수행한 변경 사항은 Audience Manager에 반영됩니다. |
| 시스템 변수 | [!UICONTROL Folder traits] 은  `d_sid` 매개 변수를 사용하여 이벤트 호출에서 구현할 수 없습니다. |
| 보고 | [!UICONTROL Folder traits] 는 자동으로 계산되는 트레이트이며 에는 표시되지 않습니다 **[!UICONTROL Overlap Reports]**. |
