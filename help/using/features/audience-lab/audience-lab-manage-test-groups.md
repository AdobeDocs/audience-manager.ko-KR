---
description: 이 절차에서는 Audience Lab에서 테스트 그룹을 생성, 편집 또는 삭제하는 데 필요한 단계를 안내합니다.
seo-description: 이 절차에서는 Audience Lab에서 테스트 그룹을 생성, 편집 또는 삭제하는 데 필요한 단계를 안내합니다.
seo-title: 테스트 그룹 관리
solution: Audience Manager
title: 테스트 그룹 관리
uuid: 2 Fadddeb -7574-4853-8 c 52-c 58456582 c 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### 전제 조건

<!-- create-test-group.xml -->

* **전환 트레이트** 설정을 하나 이상 설정해야 합니다. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[폴더 트레이트는](../../features/traits/about-folder-traits.md) 에서 **지원되지** [!UICONTROL Audience Lab]않습니다. Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. 이 권한을 통해 사용자는 테스트 결과를 만들고 볼 수 있습니다. A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **"read"** permissions. 사용자는 액세스 권한이 있는 페이지도 볼 수 있습니다. So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * 관련 전환 트레이트에 대한 액세스
   * 테스트를 위해 관련 세그먼트를 읽고 매핑하는 액세스
   * 관련 대상에 액세스

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * 테스트 그룹을 초안으로 저장하고 나중에 다시 시작할 수 있습니다.
   * 선택한 기본 세그먼트가 다른 테스트 그룹에서 이미 사용되고 있는 경우 경고가 표시됩니다. 기본 세그먼트를 두 번 사용하면 두 테스트 모두에 대한 전환 결과가 왜곡될 수 있습니다.

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * 테스트 세그먼트 이름을 클릭하여 편집할 수 있습니다.
   * 새 테스트 세그먼트가 할당되면 백분율이 자동으로 100%로 분할됩니다. 그런 다음 백분율을 수동으로 편집할 수 있습니다. 백분율을 편집한 후 확인란을 클릭한 다음 최대 100%까지 추가해야 합니다. 그렇지 않으면 다음 단계로 진행되지 않습니다.

1. **[!UICONTROL Set a Control Segment]**

   * 컨트롤 그룹으로 사용할 세그먼트의 특정 부분을 제외하려면 컨트롤 세그먼트를 선택합니다. 제어 그룹을 사용하면 벤치마크와 비교하여 만든 테스트 세그먼트가 미치는 영향을 확인할 수 있습니다.
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * **[!UICONTROL Next]** 완료되면 클릭합니다.

1. **[!UICONTROL Select Conversion Traits]**

   * 전환 트레이트 창에서 입력하여 전환 트레이트를 추가합니다. **이것은 필수** 단계이며 하나 이상의 전환 트레이트를 추가해야 다음 단계로 진행할 수 있습니다.
   * 원할 경우 최대 5 개의 전환 트레이트를 추가할 수 있습니다.
   * 다른 테스트 그룹에 이미 사용된 전환 트레이트를 선택하면 경고가 표시됩니다.

1. **[!UICONTROL Choose Destinations & Dates]**

   * 검색 필드에 원하는 대상을 입력하거나 드롭다운 화살표를 사용합니다. [!UICONTROL Audience Lab] 테스트 세그먼트를 URL, 쿠키 또는 서버-서버 대상으로 보낼 수 있습니다.
   * 세그먼트를 대상에 드래그하여 놓습니다.
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * 동일한 테스트 세그먼트를 여러 대상에 보내고 단일 대상에 여러 테스트 세그먼트를 추가할 수 있습니다.
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * 마지막으로 테스트 그룹의 시작 날짜를 선택해야 합니다. 이 날짜는 테스트 그룹이 대상에 게시될 기간의 시작을 표시합니다. Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 인증된 프로필은 실시간 대상에서만 지원됩니다. 해당 구성의 프로필 병합 규칙이 있는 테스트 세그먼트가 파일 기반 서버-서버 대상으로 전송되면 대상이 채워지지 않을 수 있습니다.

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * 테스트 그룹을 완료한 후에는 중복되거나 삭제되지만 편집할 수는 없다는 점을 기억해야 합니다.
   >[!NOTE]
   >* 제작 프로세스의 어느 시점에서나 테스트 그룹을 저장하고 나중에 마법사로 돌아갈 수 있습니다. The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. [!UICONTROL Create Segment Test Group] 마법사에서 테스트 그룹을 초안으로 저장하고 나중에 다시 시작할 수 있습니다.

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you're done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. 삭제할 테스트 그룹을 찾습니다. 다음 중 하나를 수행할 수 있습니다.

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. [완료된 테스트 세그먼트의](../../features/audience-lab/audience-lab.md#status)경우 원하는 경우 보고서를 저장하도록 CSV 파일을 다운로드하라는 메시지가 표시됩니다.
