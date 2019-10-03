---
description: '이 페이지에는 오프라인 CRM 데이터를 Audience Manager에 이미 있는 행동 데이터와 결합하여 새 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 사람 기반 대상으로 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-description: '이 페이지에는 오프라인 CRM 데이터를 Audience Manager에 이미 있는 행동 데이터와 결합하여 새 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 사람 기반 대상으로 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다.   '
seo-title: 워크플로우 A - 오프라인 데이터와 결합된 모든 온라인 활동을 기반으로 개인화
solution: Audience Manager
title: 워크플로우 A - 오프라인 데이터와 결합된 모든 온라인 활동을 기반으로 개인화
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Workflow A - Personalization Based on All Online Activity Combined with Offline Data {#workflow-a}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떠한 것도 법적 충고는 아닙니다. 법률 자문을 위해 법률 자문을 구하십시오.

This page includes step-by-step guidance on how to combine offline  data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to .[!DNL CRM][!DNL People-Based Destinations]

## Step 1 - Configure Data Source Settings {#configure-data-source-settings}

Depending on whether your DPUUIDs are lowercase, hashed email addresses, you might need to configure the data source that will store the hashed email addresses.[](../../reference/ids-in-aam.md)

 

**Scenario 1: your DPUUIDs are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to need to label the corresponding data source as such:

1. -&gt; [!UICONTROL Audience Data] 으로 이동합니다 [!UICONTROL Data Sources].
1. DPUUID가 포함된 데이터 [소스를](../../reference/ids-in-aam.md)찾아 클릭합니다.
1. 드롭다운 **[!UICONTROL ID Type]** 메뉴에서 을 선택합니다 **[!UICONTROL Cross Device]**.
1. 옵션을 선택 [!UICONTROL Cannot be tied to personally identifiable information] 취소했는지 확인합니다.
1. 섹션에서 **[!UICONTROL Data Source Settings]** 및 **[!UICONTROL Inbound]** 옵션을 모두 선택하고 **[!UICONTROL Outbound]** **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 활성화합니다.
1. 드롭다운 메뉴를 사용하여 이 데이터 소스의 **[!UICONTROL Emails(SHA256, lowercased)]** 레이블을 선택합니다.
   >[!IMPORTANT]
   >
   >이 옵션은 데이터 소스를 해당 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 레이블을 지정합니다. Audience Manager는 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장할 이메일 주소가 이미 [!DNL SHA256] 알고리즘으로 해시되었는지 확인하십시오. 그렇지 않으면 사용하지 못할 [!DNL People-Based Destinations]것입니다.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 데이터 소스 설정을 저장합니다.

 

**시나리오 2:dpuuid[는](../../reference/ids-in-aam.md)소문자가 아닌 해시된 이메일 주소입니다.**

이 경우 해시된 이메일 주소를 저장할 새로운 크로스 디바이스 데이터 소스를 만들어야 합니다. 이 작업을 수행하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**&#x200B;로 이동하여 을 **[!UICONTROL Add New]**&#x200B;클릭합니다.
1. 새 데이터 소스에 대한 [!UICONTROL Name] 및 [!UICONTROL Description] 를 입력합니다.
1. 드롭다운 **[!UICONTROL ID Type]** 메뉴에서 을 선택합니다 **[!UICONTROL Cross Device]**.
1. 섹션에서 **[!UICONTROL Data Source Settings]** 및 **[!UICONTROL Inbound]** 옵션을 모두 선택하고 **[!UICONTROL Outbound]** **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 활성화합니다.
1. 드롭다운 메뉴를 사용하여 이 데이터 소스의 **[!UICONTROL Emails(SHA256, lowercased)]** 레이블을 선택합니다.
   >[!IMPORTANT]
   >
   >이 옵션은 데이터 소스를 해당 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 레이블을 지정합니다. Audience Manager는 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장할 이메일 주소가 이미 [!DNL SHA256] 알고리즘으로 해시되었는지 확인하십시오. 그렇지 않으면 사용하지 못할 [!DNL People-Based Destinations]것입니다.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 데이터 소스 설정을 저장합니다.

Watch the video below for a video tutorial of how to create a data source for .[!UICONTROL People-Based Destinations]

>[!VIDEO](https://video.tv.adobe.com/v/29006/?captions=kor)

>[!NOTE]
>
> 오프라인 [데이터를 사용자](people-based-destinations-prerequisites.md#data-onboarding) 기반 대상에 대한 Audience Manager로 가져오는 방법에 대한 FAQ는 데이터 온보딩을 참조하십시오.

## 2단계 - 파일 기반 ID 동기화를 통해 DPUUID를 해시된 이메일 주소에 일치 {#match-ids-emails}

>[!IMPORTANT]
>
> 이 단계는 위에서 설명한 시나리오 [2에만](people-based-destinations-workflow-combined.md#configure-data-source-settings) 적용됩니다. If your existing DPUUIDs are already hashed email addresses, skip to Step 3 - Create a Profile Merge Rule for Segmentation.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#create-merge-rule)

Let's say you want to match your existing DPUUIDs to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at Step 1 - Configure Data Source Settings.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#configure-data-source-settings)

| DPUUID (CRM ID) | 이메일 주소 | Hashed email address |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

해시된 이메일 주소를 최대 10개까지 하나의 DPUUID에 연결할 수 [있습니다](../../reference/ids-in-aam.md). 이렇게 하려면 해시 처리한 이메일 주소를 동기화 파일 내에서 쉼표로 구분합니다.

이 예에서는 두 개의 데이터 소스가 있습니다.

| 데이터 소스 ID | 데이터 소스 컨텐츠 |
| -------------- | -------------------------- |
| 999999 | 기존 DPUUID(CRM ID) |
| 987654 | 해시된 이메일 주소 |

 

ID [동기화 파일에는](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 다음 내용이 있습니다.

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

ID [동기화 파일은](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 다음 이름 지정 구조를 따라야 합니다.

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

위의 예에서 파일 이름은 다음과 같습니다.
`c2c_id_999999_987654_1560431657.sync`

[예제 파일을 다운로드하십시오](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync).

ID 동기화 파일을 만든 후에는 [!DNL Amazon S3] 버킷에 업로드해야 합니다. ID 동기화 파일을 업로드하는 방법에 대한 자세한 내용은 Audience [Manager에 배치 데이터 전송을 참조하십시오](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## 3단계 - 세그멘테이션을 위한 프로필 병합 규칙 만들기 {#create-merge-rule}

다음 단계에서는 사람 기반 대상으로 전송할 대상 세그먼트를 만드는 데 도움이 되는 새로운 병합 규칙을 만듭니다.

>[!IMPORTANT]
>
> 이미 [!UICONTROL Current Authenticated Profiles] 또는 [!UICONTROL Last Authenticated Profiles] 옵션으로 정의된 규칙이 있는 경우 4단계 - 대상 세그먼트 [만들기로 건너뛸 수 있습니다](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**&#x200B;로 이동합니다.
1. 클릭 **[!UICONTROL Add New Rule]**.
1. 프로필 병합 규칙을 **[!UICONTROL Name]** 입력하고 **[!UICONTROL Description]**&#x200B;을 클릭합니다.
1. 섹션에서 **[!UICONTROL Profile Merge Rule Setup]** 또는 **[!UICONTROL Current Authenticated Profiles]** **[!UICONTROL Last Authenticated Profiles]** 옵션을 선택합니다.
1. 목록에서 세그멘테이션을 실행할 데이터 소스를 **[!UICONTROL Cross-Device Profile Options]** 선택합니다. 기존 DPUUID를 포함하는 데이터 소스여야 [합니다](../../reference/ids-in-aam.md).

## 4단계 - 대상 세그먼트 만들기 {#create-audience-segments}

새 대상 세그먼트를 만들려면 세그먼트 빌더를 [사용하십시오](../segments/segment-builder.md). 보낼 기존 대상 세그먼트가 있는 [!DNL People-Based Destinations]경우 5단계 - [사용자 기반 플랫폼 인증 구성으로 건너뜁니다](people-based-destinations-workflow-combined.md#configure-authentication).

## 5단계 - 사람 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**로 이동합니다. 이전에 소셜 플랫폼과 통합한 적이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사람 기반 통합](assets/pbd-config.png)
1. 클릭 **[!UICONTROL Add Account]**.
1. 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다. **[!UICONTROL People-Based Platform]**
   ![사용자 기반 플랫폼](assets/pbd-add.png)
1. Click  to be redirected to the authentication page of the selected platform.**[!UICONTROL Confirm]**
1. Once you've authenticated to your social platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. 사용할 광고주 계정을 선택하고 을 **[!UICONTROL Confirm]**&#x200B;클릭합니다.
1. Audience Manager는 계정 성공적으로 추가되었는지 여부를 알려주는 알림을 페이지 상단에 표시합니다. 또한 알림을 통해 소셜 플랫폼 인증이 만료될 때 알림을 수신할 연락처 이메일 주소를 추가할 수 있습니다.

>[!IMPORTANT]
>
>Audience Manager는 일정 시간 후 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 만료된 토큰 갱신 방법에 대한 자세한 내용은 인증 토큰 갱신을 참조하십시오.

## 6단계 - 사람 기반 대상 만들기 {#create-destination}

1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]**&#x200B;로 이동한 다음 을 클릭합니다 **[!UICONTROL Create Destination]**.
1. 섹션에서 새 데이터 소스에 대한 **[!UICONTROL Basic Information]** 및 **[!UICONTROL Name]** **[!UICONTROL Description]** 를 입력하고 다음 설정을 사용합니다.
   * **[!UICONTROL Category]**:통합 플랫폼;
   * **[!UICONTROL Type]**:사용자 기반;
   * **[!UICONTROL Platform]**:대상 세그먼트를 보낼 사람 기반 플랫폼을 선택합니다.
   * **[!UICONTROL Account]**:선택한 플랫폼과 연관된 원하는 광고주 계정을 선택합니다.
      ![create-destination](assets/pbd-create-destination.png)
1. 클릭 **[!UICONTROL Next]**.
1. 이 대상에 대해 설정할 **[!UICONTROL Data Export Labels]** 항목을 선택합니다.
1. 섹션에서 해시된 데이터 소스가 포함된 데이터 소스를 **[!UICONTROL Configuration]** 선택합니다.
1. 섹션에서 **[!UICONTROL Segment Mappings]** 이 대상으로 전송할 세그먼트를 선택합니다. 이것은 4단계 - 대상 세그먼트 [만들기에서 만든 세그먼트입니다](people-based-destinations-workflow-combined.md#create-audience-segments).
1. 대상을 저장합니다.
