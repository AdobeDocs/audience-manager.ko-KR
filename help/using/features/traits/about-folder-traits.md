---
description: 폴더 트레이트를 사용하면 동일한 폴더 및 모든 하위 폴더 내에 있는 트레이트를 타겟팅 가능한 세그먼트로 자동으로 집계할 수 있습니다.
keywords: 세그먼트 크기 견적 도구;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: 폴더 트레이트 정보
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# 폴더 트레이트: 설명 {#folder-traits-about}

[!UICONTROL Folder traits] 에서는 동일한 폴더 및 모든 하위 폴더 내에 있는 트레이트를 타겟팅 가능한 세그먼트로 자동으로 집계할 수 있습니다.

## 폴더 트레이트 사용의 이점 {#benefits}

A [!UICONTROL folder trait] 상위 폴더 및 연결된 하위 폴더의 모든 트레이트가 포함됩니다. 이렇게 하면 사용자를 다양한 폴더 수준에서 자동으로 세그먼트화하고 타깃팅할 수 있습니다. 예를 들어 다음과 같은 폴더 구조가 있다고 가정해 보겠습니다.

`*` 전자 제품(상위)

    `*` 노트북(하위)

        `*` 브랜드(손자)

[!UICONTROL Folder traits] 자동으로 생성된 를 통해 이러한 폴더의 모든 사용자 자격 부여 [!DNL Electronics] [!UICONTROL Folder Trait] (상위 폴더의 이름을 기반으로 함). 또한 파일 구조를 아래로 이동할 때 이 프로세스가 반복됩니다. 이 경우 폴더 트레이트는 자동으로 생성된 랩톱에서 랩탑 및 브랜드 폴더의 모든 사용자를 캡처합니다 [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] 세그먼트 표현식에서 선택할 수 있습니다. 선택 [!UICONTROL folder trait] 는 해당 폴더 내의 모든 트레이트 및 하위 폴더에 있는 [!UICONTROL OR] 그룹화.

![](assets/folder-traits-compare-border.jpg)

## 폴더 트레이트 실현 - 최신성 및 빈도 {#folder-traits-realization}

폴더 트레이트의 빈도 수는 해당 폴더 및 하위 폴더에 있는 트레이트의 실현 횟수 합계입니다. 아래 그림은 자동차 폴더에 있는 트레이트 A, B 및 C를 보여줍니다. 각 트레이트에 다음과 같은 실현이 있다고 가정해 보겠습니다.

* 트레이트 A: 5
* 트레이트 B: 1
* 트레이트 C: 1

이 경우 [!DNL Automobile Folder Trait] 에는 7개의 실현이 있습니다.

![](assets/folder_traits_rollup_border.png)

## 폴더 트레이트 보고 {#folder-traits-reporting}

[!UICONTROL Folder traits] 아래 폴더 구조의 트레이트에서 모든 사용자를 캡처합니다. 폴더에서 다른 폴더로 트레이트를 이동하면 변경 사항이 [데이터 수집 서버](../../reference/system-components/components-data-collection.md) 트레이트 규칙 변경처럼. 다음 보고 실행에서 이 변경 사항을 보고 날짜 범위(1, 7, 14, 30, 60, 90)에 반영하도록 보고가 업데이트됩니다. 이전 일자의 이전 보고 번호는 변경되지 않습니다.

## RBAC(역할 기반 액세스 제어) 권한 {#role-based-access-controls}

을 사용하는 회사의 경우 [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC])을 클릭하여 적절한 권한이 있는 사용자에게 [!UICONTROL RBAC] 권한은에 연결된 데이터 소스를 변경할 수 있습니다. [!UICONTROL folder trait]. 사용자는 다음 중 하나가 있는 그룹에 속해야 합니다.

* `READ` 및 `WRITE` 트레이트 데이터 소스에 대한 그룹 권한.
* `VIEW_ALL_TRAITS` 및 `EDIT_ALL_TRAITS` 트레이트 데이터 소스에 대한 와일드카드 권한.

할당 방법 알아보기 [!UICONTROL RBAC] 의 권한 [관리 설명서](../../features/administration/administration-overview.md#create-group).

## 제한 및 기타 고려 사항 {#limits}

| 항목 | 설명 |
|---|---|
| 트레이트 유형 | [!UICONTROL Onboarded traits] 및 [!UICONTROL algorithmic traits] 최대 1개의 구현에 참여 [!UICONTROL folder trait]의 빈도입니다. |
| 폴더 간 트레이트 이동 | 폴더에서 다른 폴더로 트레이트를 이동하면 해당 트레이트가 첫 번째 폴더 트레이트에서 자격을 박탈하고 두 번째 폴더에 적합합니다 [!UICONTROL folder trait]. 즉, 폴더에서 트레이트를 삭제하거나 이동하면 트레이트 모집단의 사용자가 폴더 트레이트를 세그먼트 표현식으로 사용하여 세그먼트에서 세그먼트화되지 않습니다. <br> Adobe Analytics 세그먼트 또는 보고서 세트를 Experience Cloud 조직에 매핑하면 Audience Manager에서 자동으로 새로운 해당 읽기 전용 세그먼트 및 트레이트를 만듭니다. Audience Manager에서 이러한 트레이트의 저장 위치를 편집하거나 변경할 수 없습니다. 그러나 매핑된 Adobe Analytics 세그먼트 또는 보고서 세트에 대해 수행하는 모든 변경 사항은 Audience Manager에 반영됩니다. |
| 시스템 변수 | [!UICONTROL Folder traits] 를 사용하여 이벤트 호출에서 실현할 수 없습니다. `d_sid` 매개 변수. |
| 보고 | [!UICONTROL Folder traits] 은 자동 계산된 트레이트이며 에는 표시되지 않습니다. **[!UICONTROL Overlap Reports]**. |
