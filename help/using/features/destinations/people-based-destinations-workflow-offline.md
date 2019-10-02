---
description: '이 페이지에는 오프라인 전용 고객 데이터에서 고객 세그먼트를 만들고 이를 사람 기반 대상으로 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-description: '이 페이지에는 오프라인 전용 고객 데이터에서 고객 세그먼트를 만들고 이를 사람 기반 대상으로 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-title: 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화
solution: Audience Manager
title: 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화 {#workflow-b}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떠한 것도 법적 충고는 아닙니다. 법률 자문을 위해 법률 자문을 구하십시오.

이 페이지에는 오프라인 전용 고객 데이터에서 고객 세그먼트를 만들고 이를 사람 기반 대상으로 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다.

## 1단계 - 오프라인 트레이트 가입 {#step-1-onboard-traits}

이 시나리오에서 대상 세그먼트를 만드는 첫 번째 단계는 오프라인 고객 데이터를 Audience Manager로 가져오는 것입니다.

>[!IMPORTANT]
>
> 계속하기 전에, 등록하려는 고객 활동이 해당 온보딩 트레이트와 함께 Audience Manager에 이미 정의되어 [있는지](../traits/trait-qualification-reference.md)확인하십시오.

기존 Audience Manager 고객 ID([DPUUID](../../reference/ids-in-aam.md))가 해시된 이메일인지 여부에 관계없이 DPUUID가 포함된 데이터 소스에 대해 트레이트 온보딩을 수행해야 [합니다](../../reference/ids-in-aam.md).

### 예

아래 표에서 해당 온보드 트레이트 ID에 대한 고객 ID의 자격을 얻고자 합니다. DPUUID가 [ID](../../reference/ids-in-aam.md) 99999의 데이터 소스에 저장되고 Audience Manager 파트너 ID가 123인 경우를 고려해 보십시오.

| 고객 ID(DPUUID) | 온보드 트레이트 ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
위의 예에서 해당 온보드 트레이트에 대한 고객 ID의 자격을 갖추려면 [인바운드 데이터 파일](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)을 업로드해야 합니다.

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

The file name would look like this: .
`ftp_dpm_999999_123_TIMESTAMP.sync.gz`
See Amazon S3 Name and File Size Requirements for Inbound Data Files for detailed information on the file name structure.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

## Step 2 - Configure Data Source Settings {#configure-data-source-settings}

Depending on whether your DPUUIDs are lowercase, hashed email addresses, you might need to configure the data source that will store the hashed email addresses.[](../../reference/ids-in-aam.md)

 

**Scenario 1: your DPUUIDs are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to need to label the corresponding data source as such:

1. Go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]**
1. Find the data source that contains your DPUUIDs, and click it.[](../../reference/ids-in-aam.md)
1. Make sure the option  is unchecked.**[!UICONTROL Cannot be tied to personally identifiable information]**
1. Save the data source settings.

 

**Scenario 2: your DPUUIDs are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to create a new cross-device data source that will store your hashed email addresses. Here's how to do this:

1. Log in to your Audience Manager account and go to  -&gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]****[!UICONTROL Add New]**
1. 새 데이터 소스에 대한 **[!UICONTROL Name]** 및 **[!UICONTROL Description]** 를 입력합니다.
1. In the  drop-down menu, select .**[!UICONTROL ID Type]****[!UICONTROL Cross Device]**
1. 섹션에서 **[!UICONTROL Data Source Settings]** 및 **[!UICONTROL Inbound]** 옵션을 모두 선택하고 **[!UICONTROL Outbound]** **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 활성화합니다.
1. 드롭다운 메뉴를 사용하여 이 데이터 소스의 **[!UICONTROL Emails(SHA256, lowercased)]** 레이블을 선택합니다.
   >[!IMPORTANT]
   >
   >이 옵션은 데이터 소스를 해당 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 레이블을 지정합니다. Audience Manager는 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장할 이메일 주소가 이미 [!DNL SHA256] 알고리즘으로 해시되었는지 확인하십시오. 그렇지 않으면 사용하지 못할 [!DNL People-Based Destinations]것입니다.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 오프라인 [데이터를 사용자](people-based-destinations-prerequisites.md#data-onboarding) 기반 대상에 대한 Audience Manager로 가져오는 방법에 대한 FAQ는 데이터 온보딩을 참조하십시오.

## 3단계 - 파일 기반 ID 동기화를 통해 DPUUID를 해시된 이메일 주소에 일치 {#match-ids-emails}

>[!IMPORTANT]
>
> 이 단계는 위에서 설명한 시나리오 [2에만](people-based-destinations-workflow-offline.md#configure-data-source-settings) 적용됩니다. 기존 DPUUID [가](../../reference/ids-in-aam.md) 이미 해시된 이메일 주소를 사용하는 경우 4단계 - [세그멘테이션에 대한 프로필 병합 규칙 만들기로 건너뜁니다](#create-profile-merge-rule).

1단계의 예에서 아래 [표의 해시된 이메일 주소(오른쪽 열)와](../../reference/ids-in-aam.md) 기존 DPUUID를 일치시키고 2단계 - 데이터 소스 설정 [구성에서 만든 새 데이터 소스에 해시된 이메일 주소를 저장한다고 가정해 보겠습니다](#configure-data-source-settings).

이제 두 개의 데이터 소스가 있습니다.

| 데이터 소스 ID | 데이터 소스 컨텐츠 |
| -------------- | -------------------------- |
| 999999 | 기존 DPUUID(CRM ID) |
| 987654 | 해시된 이메일 주소 |

| DPUUID(CRM ID) | 이메일 주소 | 해시된 이메일 주소 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

이 예제에서는 ID [동기화 파일에](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 다음 내용이 있습니다.

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

## 4단계 - 세그멘테이션을 위한 프로필 병합 규칙 만들기 {#create-profile-merge-rule}

다음 단계에서는 대상 세그먼트를 만들어 사용자에게 보내는 데 도움이 되는 새로운 병합 규칙을 만듭니다 [!DNL People-Based Destinations].

1. Audience Manager 계정에 로그인한 다음 **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**&#x200B;으로 이동합니다.
2. 클릭 [!UICONTROL Add New Rule].
3. Enter a profile merge rule  and .**[!UICONTROL Name]****[!UICONTROL Description]**
4. In the  section, select the  rule from the  list.**[!UICONTROL Profile Merge Rule Setup]****[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]**
5. In the  list, select the data source that your traits are onboarded against.**[!UICONTROL Cross-Device Profile Options]**
   ![merge-rule-setup](assets/pbd-pmr.png)

## Step 5 - Create Audience Segments {#create-audience-segments}

To create new segments from offline-only data, use the Segment Builder and make sure you use the new profile merge rule that you created in the previous step when creating the segment.[](../segments/segment-builder.md)

## Step 6 - Configure People-Based Platform Authentication {#configure-authentication}

1. Log in to your Audience Manager account and go to  &gt; . **[!UICONTROL Administration]****[!UICONTROL Integrated Accounts]** If you have a previously configured integration with a social platform, you should see it listed in this page. Otherwise, the page is empty.
   ![people-based-integration](assets/pbd-config.png)
1. 클릭 **[!UICONTROL Add Account]**.
1. 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다. **[!UICONTROL People-Based Platform]**
   ![사용자 기반 플랫폼](assets/pbd-add.png)
1. 아이콘을 **[!UICONTROL Confirm]** 클릭하여 선택한 플랫폼의 인증 페이지로 리디렉션합니다.
1. 소셜 플랫폼 계정에 인증되면 연결된 광고주 계정이 표시되는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 을 **[!UICONTROL Confirm]**&#x200B;클릭합니다.
1. Audience Manager는 계정 성공적으로 추가되었는지 여부를 알려주는 알림을 페이지 상단에 표시합니다. 또한 알림을 통해 소셜 플랫폼 인증이 만료될 때 알림을 수신할 연락처 이메일 주소를 추가할 수 있습니다.

>[!IMPORTANT]
>
>Audience Manager는 일정 시간 후 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 만료된 토큰 갱신 방법에 대한 자세한 내용은 인증 토큰 갱신을 참조하십시오.

## 7단계 - 사람 기반 대상 만들기 {#create-destination}

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
1. 섹션에서 **[!UICONTROL Segment Mappings]** 이 대상으로 전송할 세그먼트를 선택합니다. 이는 5단계 - 대상 세그먼트 [만들기에서 만든 세그먼트입니다](people-based-destinations-workflow-offline.md#create-audience-segments).
1. 대상을 저장합니다.
