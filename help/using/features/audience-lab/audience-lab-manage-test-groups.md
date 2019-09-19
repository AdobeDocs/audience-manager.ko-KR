---
description: 이 절차에서는 Audience Lab에서 테스트 그룹을 생성, 편집 또는 삭제하는 데 필요한 단계를 안내합니다
seo-description: 이 절차에서는 Audience Lab에서 테스트 그룹을 생성, 편집 또는 삭제하는 데 필요한 단계를 안내합니다
seo-title: 테스트 그룹 관리
solution: Audience Manager
title: 테스트 그룹 관리
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 테스트 그룹 관리 {#manage-test-groups}

이 절차에서는 에서 테스트 그룹을 생성, 편집 또는 삭제하는 데 필요한 단계를 안내합니다. [!UICONTROL Audience Lab]

## 세그먼트 테스트 그룹 만들기 {#create-test-groups}

### 전제 조건

<!-- create-test-group.xml -->

* 하나 이상의 **전환 트레이트를** 설정해야 합니다. 이벤트 유형으로 [전환을](../../features/traits/create-onboarded-rule-based-traits.md)선택하여 트레이트 빌더에서 전환 **** 트레이트를 설정할 수 있습니다. 전환 특성에 대한 자세한 내용과 설정 방법을 살펴보려면 [비디오를](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) 준비했습니다.

   >[!IMPORTANT]
   >
   >[폴더 트레이트는](../../features/traits/about-folder-traits.md) 에서 지원되지 **않습니다** [!UICONTROL Audience Lab]. 폴더 [트레이트의 이벤트](../../features/traits/create-onboarded-rule-based-traits.md) 유형을 **변환으로** 설정하면 해당 특정 폴더 트레이트에 [!UICONTROL Audience Lab] 대한 데이터가 생성되지 않습니다.

* 역할 기반 액세스 [제어를 사용하는 회사의 경우](../../features/administration/administration-overview.md):액세스 권한을 제공하도록 [!UICONTROL Audience Lab] 와일드카드 [권한을](../../features/administration/administration-overview.md#wild-card-permissions) 지정합니다 **[!UICONTROL User Groups]** . 사용자는 이 권한을 사용하여 테스트 결과를 만들고 볼 수 있습니다. 사용자는 **읽은** 데이터 소스의 세그먼트만 사용할 수 있고 대상 **권한에** 매핑할 수 있습니다. 사용자는 **"읽기"** 권한이 있는 데이터 소스의 전환 특성만 사용할 수 있습니다. 사용자는 액세스 권한이 있는 대상만 볼 수 있습니다. 따라서 그룹에 와일드카드 [!DNL Audience Lab] 권한을 추가하기 전에 그룹에 다음이 있는지 확인합니다.
   * 관련 전환 트레이트를 읽을 수 있는 액세스
   * 테스트를 위한 관련 세그먼트를 읽고 매핑할 수 있습니다.
   * 관련 대상에 대한 액세스

새로 만들려면 [!UICONTROL Segment Test Group]다음을 수행하십시오.

1. 대시보드를 **[!UICONTROL Create New Test Group]** 선택하여 [!UICONTROL Audience Lab] 마법사를 시작합니다.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * a **[!UICONTROL Test Group Name]** 및 a를 **[!UICONTROL Description]**&#x200B;입력합니다.
   * 파일 브라우저에서 탐색하거나 검색 표시줄을 입력하여 **[!UICONTROL Base Segment]** 선택합니다. **[!UICONTROL Choose Segment.]**
   * 테스트 그룹을 초안으로 저장하고 나중에 다시 작업할 수 있습니다.
   * 선택한 기본 세그먼트가 다른 테스트 그룹에서 이미 사용된 경우 경고가 표시됩니다. 기본 세그먼트를 두 번 사용하면 두 테스트 모두에 대한 전환 결과가 왜곡될 수 있습니다.

1. **[!UICONTROL Allocate Test Segments]**

   * 최대 **15개의 테스트 세그먼트를** 만들고 원하는 대로 장치 비율을 나눌 수 있습니다.
   * 테스트 세그먼트 이름을 클릭하여 편집할 수 있습니다.
   * 새 테스트 세그먼트가 할당되면 백분율은 100%로 균등하게 자동 나눕니다. 그런 다음 비율을 수동으로 편집할 수 있습니다. 백분율을 편집한 후 확인란을 클릭하고 최대 100%까지 추가했는지 확인하십시오. 그렇지 않으면 다음 단계로 진행할 수 없습니다.

1. **[!UICONTROL Set a Control Segment]**

   * 제어 그룹으로 사용할 세그먼트의 특정 부분을 제외하려면 제어 세그먼트를 선택합니다. 제어 그룹을 사용하면 벤치마크와 비교하여 만든 테스트 세그먼트의 영향을 볼 수 있습니다.
   * 드롭다운 목록에서 테스트 세그먼트를 제어 세그먼트로 선택하거나 컨트롤 없이 선택할 **[!UICONTROL None]** 수 있습니다.
   * 완료되면 **[!UICONTROL Next]** 을 클릭합니다.

1. **[!UICONTROL Select Conversion Traits]**

   * 전환 트레이트 창에 입력하여 전환 트레이트를 추가합니다. 이것은 **필수** 단계이며 하나 이상의 전환 트레이트를 추가하지 않는 한 다음 단계로 진행할 수 없습니다.
   * 원하는 경우 최대 5개의 전환 트레이트를 추가할 수 있습니다.
   * 다른 테스트 그룹에 이미 사용된 전환 트레이트를 선택하는 경우 경고가 표시됩니다.

1. **[!UICONTROL Choose Destinations & Dates]**

   * 검색 필드에 원하는 대상을 입력하거나 드롭다운 화살표를 사용합니다. [!UICONTROL Audience Lab] 테스트 세그먼트는 URL, 쿠키 또는 서버 간 대상으로 전송할 수 있습니다.
   * 세그먼트를 대상에 드래그하여 놓습니다.
   * 대상에 세그먼트를 놓은 후 블라인드의 **[!UICONTROL Destination Mapping Value]** 세그먼트를 채웁니다.
   * 동일한 테스트 세그먼트를 여러 대상에 보내고 여러 테스트 세그먼트를 단일 대상에 추가할 수 있습니다.
   * 대상이 데이터 내보내기 컨트롤을 기반으로 하는 특정 테스트 세그먼트에 사용할 수 없는 경우 대상이 [회색으로 표시됩니다](../../features/data-export-controls.md).
   * 사용자는 자신이 속한 RBAC 사용자 그룹을 기반으로 액세스할 수 있는 [대상만](../../features/administration/administration-overview.md) 볼 수 있습니다.
   * 마지막으로 테스트 그룹의 시작 날짜를 선택해야 합니다. 이 날짜는 테스트 그룹이 대상에 게시되는 기간의 시작을 표시합니다. 테스트 **세그먼트를** 무기한 비교하려면 종료 날짜 없음을 선택합니다.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] 인증된 프로필은 실시간 대상에서만 지원됩니다. 해당 구성의 프로필 병합 규칙이 있는 테스트 세그먼트를 파일 기반 서버 간 대상으로 보내는 경우 대상이 채워지지 않을 수 있습니다.

   을 **[!UICONTROL Next]** 클릭하여 테스트 그룹을 검토하고 마무리합니다.

1. **[!UICONTROL Summary & Finalize]**

   * 이전 단계에서 추가한 정보를 검토하고 **[!UICONTROL Finalize Group]**&#x200B;선택합니다.
   * 테스트 그룹을 완료하면 복제 또는 삭제할 수 있지만 편집할 수는 없습니다.
   >[!NOTE]
   >* 작성 프로세스의 어느 시점에서나 테스트 그룹을 저장하고 나중에 마법사로 돌아갈 수 있습니다. 테스트 그룹 상태는 **[!UICONTROL Draft]** 유지되며, 세그먼트 테스트 그룹을 완료할 때까지 테스트 그룹은 대상으로 데이터를 전송하지 않습니다.
   >* 초안 테스트의 경우 기본 **[!UICONTROL Edit]** [!UICONTROL Audience Lab] 보기에서 테스트 그룹 카드를 클릭하여 뒤로 돌아가서 테스트 그룹을 편집할 수 있습니다.


## 세그먼트 테스트 그룹 편집 {#edit-test-groups}

에서는 [!UICONTROL Audience Lab]초안 테스트 그룹만 편집할 수 있습니다. 마법사에서 테스트 그룹을 초안으로 저장하고 나중에 다시 작업할 수 있습니다. [!UICONTROL Create Segment Test Group]

1. 기본 보기로 [!UICONTROL Audience Lab] 이동합니다.
1. 초안 테스트 그룹을 검색하고 테스트 그룹 카드에서 **[!UICONTROL Edit]** 컨트롤을 선택합니다.
1. 세그먼트 [테스트 그룹 만들기](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) 마법사를 다시 시작하고 **[!UICONTROL Finalize Group]** 완료시 선택합니다.

## 세그먼트 테스트 그룹 삭제 {#delete-test-groups}

1. 기본 보기로 [!UICONTROL Audience Lab] 이동합니다.
1. 삭제할 테스트 그룹을 찾습니다. 다음 중 하나를 수행할 수 있습니다.

   * 테스트 그룹 카드의 **[!UICONTROL Delete]** 컨트롤을 누르거나,
   * 테스트 그룹 카드의 테스트 그룹 제목을 눌러 테스트 그룹 정보 [보기로 이동한](../../features/audience-lab/audience-lab-information-view.md) 후 제목 **[!UICONTROL Delete]** 표시줄의 컨트롤을 누릅니다.

1. 완료된 테스트 세그먼트의 [](../../features/audience-lab/audience-lab.md#status)경우, 원할 경우 CSV 파일을 다운로드하여 보고서를 저장하라는 경고가 표시됩니다.
