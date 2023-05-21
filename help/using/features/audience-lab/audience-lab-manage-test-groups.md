---
description: 이 절차에서는 Audience Lab에서 테스트 그룹을 생성, 편집 또는 삭제하는 데 필요한 단계를 안내합니다
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: 테스트 그룹 관리
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---

# 테스트 그룹 관리 {#manage-test-groups}

이 절차는에서 테스트 그룹을 생성, 편집 또는 삭제하는 데 필요한 단계를 안내합니다 [!UICONTROL Audience Lab].

## 세그먼트 테스트 그룹 만들기 {#create-test-groups}

### 사전 요구 사항

<!-- create-test-group.xml -->

* 최소 하나 이상 있어야 합니다. **전환 트레이트** 설정합니다. 에서 전환 트레이트를 설정할 수 있습니다. [트레이트 빌더](../../features/traits/create-onboarded-rule-based-traits.md), 을 선택하여 **전환** 를 이벤트 유형으로 사용하십시오. 전환 트레이트가 무엇이며 이를 설정하는 방법에 대한 자세한 내용을 보려면 다음을 준비했습니다. [비디오](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) 당신을 위해.

   >[!IMPORTANT]
   >
   >[폴더 트레이트](../../features/traits/about-folder-traits.md) 은(는) **지원되지 않음** 작성자: [!UICONTROL Audience Lab]. 설정 [이벤트 유형](../../features/traits/create-onboarded-rule-based-traits.md) 의 폴더 트레이트 **전환** 에서 데이터를 생성하지 않습니다. [!UICONTROL Audience Lab] 특정 폴더 트레이트에 대해 설명합니다.

* 을 사용하는 회사의 경우 [역할 기반 액세스 제어](../../features/administration/administration-overview.md): 할당 [!UICONTROL Audience Lab] [와일드카드 권한](../../features/administration/administration-overview.md#wild-card-permissions) 끝 **[!UICONTROL User Groups]** 액세스 권한을 제공합니다. 이 권한을 사용하면 테스트 결과를 만들고 볼 수 있습니다. 사용자는 보유한 데이터 소스의 세그먼트만 사용할 수 있습니다. **읽기** 및 **대상에 매핑** 다음에 대한 권한. 사용자는 보유한 데이터 소스로부터의 전환 트레이트만 사용할 수 있습니다. **&quot;읽기&quot;** 사용 권한. 사용자는 액세스 권한이 있는 대상만 볼 수 있습니다. 따라서 을(를) 추가하기 전에 [!DNL Audience Lab] 그룹에 대한 와일드카드 권한으로, 그룹에 다음이 있는지 확인하십시오.
   * 관련 전환 트레이트 읽기에 대한 액세스
   * 테스트를 위해 관련 세그먼트를 읽고 매핑할 수 있는 액세스 권한
   * 관련 대상에 대한 액세스 권한.

To create a new [!UICONTROL Segment Test Group]:

1. 선택 **[!UICONTROL Create New Test Group]** 다음에서 [!UICONTROL Audience Lab] 대시보드를 클릭하여 마법사를 시작합니다.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * 다음을 입력하십시오. **[!UICONTROL Test Group Name]** 및 a **[!UICONTROL Description]**.
   * 다음을 선택합니다. **[!UICONTROL Base Segment]** 파일 브라우저로 이동하거나 검색 막대에 입력하여 다음을 눌러 확인합니다. **[!UICONTROL Choose Segment.]**
   * 테스트 그룹을 초안으로 저장하고 나중에 작업을 재개할 수 있습니다.
   * 선택한 기본 세그먼트가 다른 테스트 그룹에서 이미 사용되고 있는 경우 경고가 표시됩니다. 기본 세그먼트를 두 번 사용하면 두 테스트에 대한 전환 결과가 왜곡될 수 있습니다.

1. **[!UICONTROL Allocate Test Segments]**

   * 다음을 만들 수 있습니다. **최대 15개의 테스트 세그먼트** 원하는 대로 장치의 비율을 나눕니다.
   * 테스트 세그먼트를 클릭하여 세그먼트 이름을 편집할 수 있습니다.
   * 새 테스트 세그먼트가 할당되면 백분율이 자동으로 100%로 균등하게 분할됩니다. 그런 다음 백분율을 수동으로 편집할 수 있습니다. 백분율을 편집한 후 확인란을 클릭하여 최대 100%까지 추가하는지 확인합니다. 그렇게 하지 않으면 다음 단계로 진행할 수 없습니다.

1. **[!UICONTROL Set a Control Segment]**

   * 제어 그룹으로 사용할 세그먼트의 특정 부분을 지정하려는 경우 제어 세그먼트를 선택합니다. 컨트롤 그룹을 사용하면 벤치마크와 비교하여 만든 테스트 세그먼트의 영향을 볼 수 있습니다.
   * 드롭다운 목록에서 테스트 세그먼트를 제어 세그먼트로 선택하거나 **[!UICONTROL None]** 제어하지 않습니다.
   * 클릭 **[!UICONTROL Next]** 다 끝나면.

1. **[!UICONTROL Select Conversion Traits]**

   * 변환 트레이트 창에 를 입력하여 변환 트레이트를 추가합니다. (이)는 **필수** 단계를 수행하면 하나 이상의 전환 트레이트를 추가하지 않으면 다음 단계로 진행할 수 없습니다.
   * 원할 경우 최대 5개의 전환 트레이트를 추가할 수 있습니다.
   * 다른 테스트 그룹에 이미 사용된 전환 트레이트를 선택하면 경고가 표시됩니다.
   * Audience Manager은 를 지원하지 않습니다. [폴더 트레이트](/help/using/features/traits/about-folder-traits.md) 전환 트레이트로서, 폴더 트레이트를 전환 트레이트로 선택하면 테스트 내에 0개의 집계 및 트렌드 보고가 표시됩니다.

1. **[!UICONTROL Choose Destinations & Dates]**

   * 검색 필드에 원하는 대상을 입력하거나 드롭다운 화살표를 사용합니다. [!UICONTROL Audience Lab] 테스트 세그먼트는 URL, 쿠키 또는 서버 간 대상으로 전송할 수 있습니다.
   * 세그먼트를 대상으로 드래그 앤 드롭하십시오.
   * 대상에 세그먼트를 드롭한 후 다음을 입력합니다. **[!UICONTROL Destination Mapping Value]** 앞을 못 보는 사람.
   * 동일한 테스트 세그먼트를 여러 대상에 보내고 여러 테스트 세그먼트를 단일 대상에 추가할 수 있습니다.
   * 대상을 기반으로 하는 특정 테스트 세그먼트에 사용할 수 없는 경우 대상이 회색으로 표시됩니다. [데이터 내보내기 제어](../../features/data-export-controls.md).
   * 사용자는 를 기반으로 액세스 권한이 있는 대상만 볼 수 있습니다. [RBAC 사용자 그룹](../../features/administration/administration-overview.md) 속해 있습니다.
   * 마지막으로 테스트 그룹의 시작 날짜를 선택해야 합니다. 이 날짜는 테스트 그룹이 대상에 게시되는 기간의 시작을 나타냅니다. 선택 **종료 일자 없음** 테스트 세그먼트의 무한한 비교.

   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 인증된 프로필의 경우 실시간 대상에서만 지원됩니다. 해당 구성의 프로필 병합 규칙이 있는 테스트 세그먼트를 파일 기반 서버 간 대상으로 전송하는 경우 대상자가 채워지지 않을 수 있습니다.

   클릭 **[!UICONTROL Next]** 테스트 그룹을 검토하고 마무리합니다.

1. **[!UICONTROL Summary & Finalize]**

   * 이전 단계에서 추가한 정보를 검토하고 다음을 선택합니다. **[!UICONTROL Finalize Group]**.
   * 테스트 그룹을 완료한 후에는 복제하거나 삭제할 수 있지만 편집할 수는 없습니다.

   >[!NOTE]
   >* 생성 프로세스의 어느 시점에서든 테스트 그룹을 저장하고 나중에 마법사로 돌아갈 수 있습니다. 테스트 그룹 상태는 다음과 같습니다 **[!UICONTROL Draft]** 그리고 테스트 그룹은 세그먼트 테스트 그룹을 완료할 때까지 데이터를 대상으로 전송하지 않습니다.
   >* 초안 테스트의 경우 뒤로 돌아가서 다음을 클릭하여 테스트 그룹을 편집할 수 있습니다. **[!UICONTROL Edit]** 기본 의 테스트 그룹 카드에서 [!UICONTROL Audience Lab] 보기.


## 세그먼트 테스트 그룹 편집 {#edit-test-groups}

위치 [!UICONTROL Audience Lab], 초안 테스트 그룹만 편집할 수 있습니다. 다음에서 [!UICONTROL Create Segment Test Group] 마법사에서 테스트 그룹을 초안으로 저장하고 나중에 작업을 재개할 수 있습니다.

1. 다음 위치로 이동 [!UICONTROL Audience Lab] 기본 보기입니다.
1. 초안 테스트 그룹을 검색하고 **[!UICONTROL Edit]** 테스트 그룹 카드에서 제어합니다.
1. 다시 시작 [세그먼트 테스트 그룹 만들기](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 마법사 및 선택 **[!UICONTROL Finalize Group]** 다 끝나면.

## 세그먼트 테스트 그룹 삭제 {#delete-test-groups}

1. 다음 위치로 이동 [!UICONTROL Audience Lab] 기본 보기입니다.
1. 삭제할 테스트 그룹을 찾습니다. 다음 중 하나를 수행할 수 있습니다.

   * 누르기 **[!UICONTROL Delete]** 테스트 그룹 카드에서 제어 또는
   * 테스트 그룹 카드에서 테스트 그룹 제목을 눌러 [테스트 그룹 정보](../../features/audience-lab/audience-lab-information-view.md) 보기 및 누르기 **[!UICONTROL Delete]** 제목 표시줄에 있는 컨트롤입니다.

1. 대상 [완료된 테스트 세그먼트](../../features/audience-lab/audience-lab.md#status)원하는 경우 보고를 저장할 CSV 파일을 다운로드하라는 경고가 표시됩니다.
