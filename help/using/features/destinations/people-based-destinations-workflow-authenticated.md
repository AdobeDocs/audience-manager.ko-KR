---
description: '이 페이지에는 인증된 사용자의 실시간 행동 데이터와 오프라인 CRM 데이터를 결합하여 고객 세그먼트를 만든 다음 이러한 대상 세그먼트를 사용자 기반 대상에 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다. '
seo-description: '이 페이지에는 인증된 사용자의 실시간 행동 데이터와 오프라인 CRM 데이터를 결합하여 고객 세그먼트를 만든 다음 이러한 대상 세그먼트를 사용자 기반 대상에 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-title: 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동에 기반한 개인화
solution: Audience Manager
title: 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동에 기반한 개인화
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동에 기반한 개인화 {#workflow-c}

이 페이지에는 인증된 사용자의 실시간 행동 데이터와 오프라인 [!DNL CRM] 데이터를 결합하여 고객 세그먼트를 만든 다음 이러한 대상 세그먼트를 전송하는 방법에 대한 단계별 지침이 포함되어 [!DNL People-Based Destinations]있습니다.

## 1 단계 - 데이터 소스 설정 구성 {#configure-data-source-settings}

[Dpuuids가](../../reference/ids-in-aam.md) 소문자로 된 소문자를 사용하는지에 따라 해시된 이메일 주소를 저장할 데이터 소스를 구성해야 할 수 있습니다.

**시나리오 1:[Dpuuids](../../reference/ids-in-aam.md)는 이미 소문자인 해시된 이메일 주소입니다.**

이 경우 5 [단계로 건너뛰기 - 인물 기반 플랫폼 인증을 구성합니다](#configure-authentication).

**시나리오 2:[Dpuuids](../../reference/ids-in-aam.md)는 소문자로 해시된 이메일 주소가 아닙니다.**

이 경우 해시된 이메일 주소를 저장할 새 크로스 장치 데이터 소스를 만들어야 합니다. 이 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**&#x200B;를 클릭하고를 클릭합니다 **[!UICONTROL Add New]**.
1. A **[!UICONTROL Name]** 와 **[!UICONTROL Description]** 새 데이터 소스를 입력합니다.
1. 드롭다운 **[!UICONTROL ID Type]** 메뉴에서 **[!UICONTROL Cross Device]**&#x200B;를 선택합니다.
1. **[!UICONTROL Data Source Settings]** 섹션에서 **[!UICONTROL Inbound]** 및 **[!UICONTROL Outbound]** 옵션을 모두 선택하고 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 활성화합니다.
1. 드롭다운 메뉴를 사용하여 이 데이터 소스의 **[!UICONTROL Emails(SHA256, lowercased)]** 레이블을 선택합니다.
   >[!IMPORTANT]
   >
   >이 옵션은 해당 특정 알고리즘으로 해시된 데이터를 포함하는 데이터 소스에만 레이블을 지정합니다. Audience Manager는 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장하려는 이메일 주소가 [!DNL SHA256] 알고리즘으로 해시되어 있는지 확인하십시오. [!DNL People-Based Destinations]그렇지 않으면 사용할 수 없게 됩니다.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 사용자 기반 대상의 Audience Manager로 오프라인 데이터를 가져와야 하는 방법에 대한 FAQ는 [데이터 등록에 대한](people-based-destinations-prerequisites.md#data-onboarding) 자세한 내용을 참조하십시오.

## 2 단계 - 선언된 ID를 사용하여 실시간 HTTP 호출을 통해 dpuuids를 해시된 이메일 주소와 일치 {#match-email-addresses}

규칙 기반의 트레이트에 대해 인증된 사용자를 자격을 얻으려면 선언된 ID를 통해 [트레이트 자격 조건을 전송해야](../declared-ids.md)합니다.

### 예

다음의 두 데이터 소스를 만들었다고 가정하겠습니다.

| 데이터 소스 ID | 데이터 소스 컨텐츠 |
|-|-|
| 999999 | 기존 Dpuuids (CRM ID)|
| 987654 | 해시 이메일 주소|

그런 다음 아래 표에 있는 특성에 대해 아래의 CRM ID를 적용하려고 합니다.

| Dpuuid (CRM ID)| 이메일 주소 | 해시된 이메일 주소 | 특성|
|-|-|-|-|
|6807998276567319850405265607445607196039|`johndoe@example.com`| 55 e 79200 c 1635 b 37 ad 31 a 378 c 39 feb 12 f 120 f 116625093 a 19 bc 32 fff 15041149 | location = US|

선언된 ID는 다음 구문을 따라야 합니다.

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

위의 예에서 선언된 ID 호출은 다음과 같아야 합니다.

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## 3 단계 - 세그멘테이션에 대한 프로필 병합 규칙 만들기 {#create-profile-merge-rule-segmentation}

다음 단계는 사용자에게 보낼 대상 세그먼트를 만드는 데 도움이 [!DNL People-Based Destinations]되는 새 병합 규칙을 만드는 단계입니다.

>[!IMPORTANT]
>
>**[!UICONTROL Current Authenticated Profiles]** OR **[!UICONTROL Last Authenticated Profiles]** 옵션으로 정의한 규칙이 이미 있는 경우 4 [단계로 건너뛰기 - 대상 세그먼트를 만들](#create-audience-segments)수 있습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**&#x200B;로 이동합니다.
2. 클릭 **[!UICONTROL Add New Rule]**.
3. 프로필 병합 규칙 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을 입력합니다.
4. **[!UICONTROL Profile Merge Rule Setup]** 섹션에서 목록에서 **[!UICONTROL All Cross-Device Profiles]** 규칙을 **[!UICONTROL Cross-Device Options]** 선택합니다.
5. **[!UICONTROL Cross-Device Profile Options]** 목록에서 세그멘테이션을 실행할 데이터 소스를 선택합니다. 이것은 기존 DPUUID를 포함하는 데이터 소스여야 합니다.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## 4 단계 - 대상 세그먼트 만들기 {#create-audience-segments}

새 세그먼트를 만들려면 [세그먼트 빌더를 사용합니다](../segments/segment-builder.md). 보내려는 기존 대상 세그먼트가 있는 경우 5 [!DNL People-Based Destinations][단계로 건너뛰기 - 인물 기반 플랫폼 인증을 구성합니다](#configure-authentication).

## 5 단계 - 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**로 이동합니다. 이전에 소셜 플랫폼과 통합을 구성한 경우 이 페이지에 나열된 것이 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![people-based-integration](assets/pbd-config.png)
2. 클릭 **[!UICONTROL Add Account]**.
3. 드롭다운 **[!UICONTROL People-Based Platform]** 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![People-based-platform](assets/pbd-add.png)
4. 을 클릭하여 **[!UICONTROL Confirm]** 선택한 플랫폼의 인증 페이지로 리디렉션됩니다.
5. 소셜 플랫폼 계정에 인증하면 연결된 광고주 계정을 보아야 하는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고를 **[!UICONTROL Confirm]**&#x200B;클릭합니다.
6. Audience Manager는 계정 상단에 알림이 표시되어 계정이 성공적으로 추가되었는지 알려줍니다. 이 알림을 통해 소셜 플랫폼 인증이 만료될 때 알림을 받을 연락처 이메일 주소를 추가할 수도 있습니다.

>[!IMPORTANT]
>
>Udience Manager는 일정 시간 후 만료되는 인증 토큰을 통해 소셜 플랫폼과 통합을 처리합니다. 만료된 토큰을 갱신하는 방법에 대한 자세한 내용은 인증 토큰 갱신을 참조하십시오.

## 6 단계 - 인물 기반 대상 만들기 {#create-destination}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** &gt; &gt; **[!UICONTROL Destinations]**&#x200B;를 클릭합니다 **[!UICONTROL Create Destination]**.
1. **[!UICONTROL Basic Information]** 이 섹션에서 새 **[!UICONTROL Name]** 데이터 소스에 **[!UICONTROL Description]** 대한 AND를 입력하고 다음 설정을 사용합니다.
   * **[!UICONTROL Category]**: 통합 플랫폼;
   * **[!UICONTROL Type]**: People-based;
   * **[!UICONTROL Platform]**: 대상 세그먼트를 보낼 사람 기반 플랫폼을 선택합니다.
   * **[!UICONTROL Account]**: 선택한 플랫폼과 연관된 광고주 계정을 선택합니다.
      ![create-destination](assets/pbd-create-destination.png)
1. 클릭 **[!UICONTROL Next]**.
1. 이 대상에 **[!UICONTROL Data Export Labels]** 대해 설정할을 선택합니다.
1. **[!UICONTROL Configuration]** 섹션에서 해시된 Data Sources가 들어 있는 데이터 소스를 선택합니다.
1. **[!UICONTROL Segment Mappings]** 섹션에서 이 대상에 보낼 세그먼트를 선택합니다. 이것은 4 [단계에서 만든 세그먼트 - 대상 세그먼트를 만듭니다](#create-audience-segments).
1. 대상을 저장합니다.
