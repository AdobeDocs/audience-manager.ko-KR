---
description: '이 페이지에는 오프라인 전용 고객 데이터에서 고객 세그먼트를 작성하고 이를 사람 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-description: '이 페이지에는 오프라인 전용 고객 데이터에서 고객 세그먼트를 작성하고 이를 사람 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-title: 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화
solution: Audience Manager
title: 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화
feature: 사람 기반 대상
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 6%

---

# 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화 {#workflow-b}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하기 위한 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 충고이다. 법률 자문을 위해 법률 자문을 구할 수 있는 법률 자문을 구할 수 있다.

이 페이지에는 오프라인 전용 고객 데이터에서 고객 세그먼트를 작성하고 이를 사람 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.

## 1단계 - 오프라인 트레이트 온보드 {#step-1-onboard-traits}

이 시나리오에서 대상 세그먼트를 만드는 첫 번째 단계는 오프라인 고객 데이터를 Audience Manager으로 가져오는 것입니다.

>[!IMPORTANT]
>
> 계속하기 전에 탑승하려는 고객 활동이 해당 [온보드 트레이트](../traits/trait-and-segment-qualification-reference.md)와 함께 Audience Manager에 이미 정의되어 있는지 확인하십시오.

기존 Audience Manager 고객 ID([DPUUIDs](../../reference/ids-in-aam.md))가 해시된 이메일인지 여부에 관계없이 [DPUUID](../../reference/ids-in-aam.md)가 포함된 데이터 소스에 대해 트레이트 온보딩을 수행해야 합니다.

### 예

아래 표에서 해당 온보드 트레이트 ID에 대한 고객 ID의 자격을 얻고자 합니다. [DPUUID](../../reference/ids-in-aam.md)가 ID 999999의 데이터 소스에 저장되고 Audience Manager 파트너 ID가 123이 된다고 가정합니다.

| 고객 ID(DPUUID) | 온보드 트레이트 ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

위의 예에서 해당 온보드 트레이트에 대한 고객 ID의 자격을 갖추려면 다음 내용으로 [인바운드 데이터 파일](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)을 업로드해야 합니다.

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

파일 이름은 다음과 같습니다.`ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
파일 이름 구조에 대한 자세한 내용은 [Amazon S3 이름 및 인바운드 데이터 파일에 대한 파일 크기 요구 사항](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)을 참조하십시오.

## 2단계 - 데이터 소스 설정 구성 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md)가 소문자인지, 해시된 이메일 주소인지에 따라 해시된 이메일 주소를 저장할 데이터 소스를 구성해야 할 수 있습니다.

 

**시나리오 1:DPUUID  [](../../reference/ids-in-aam.md) sare already lowercase, hashed email address.**

이 경우 다음과 같이 해당 데이터 소스에 레이블을 지정해야 합니다.

1. **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**&#x200B;로 이동합니다.
1. [DPUUID](../../reference/ids-in-aam.md)가 포함된 데이터 소스를 찾아 클릭합니다.
1. **[!UICONTROL Cannot be tied to personally identifiable information]** 옵션이 선택되어 있지 않아야 합니다.
1. 데이터 소스 설정을 저장합니다.

 

**시나리오 2:DPUUID  [](../../reference/ids-in-aam.md) sare not lowercase, hashed email address.**

이 경우 해시된 이메일 주소를 저장할 새로운 장치 간 데이터 소스를 만들어야 합니다. 이를 위한 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**&#x200B;로 이동한 다음 **[!UICONTROL Add New]**&#x200B;를 클릭합니다.
1. 새 데이터 소스에 대해 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을 입력합니다.
1. **[!UICONTROL ID Type]** 드롭다운 메뉴에서 **[!UICONTROL Cross Device]**&#x200B;을 선택합니다.
1. **[!UICONTROL Data Source Settings]** 섹션에서 **[!UICONTROL Inbound]** 및 **[!UICONTROL Outbound]** 옵션을 모두 선택하고 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 활성화합니다.
1. 드롭다운 메뉴를 사용하여 이 데이터 소스의 **[!UICONTROL Emails(SHA256, lowercased)]** 레이블을 선택합니다.
   >[!IMPORTANT]
   >
   >이 옵션은 데이터 소스를 해당 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 레이블을 지정합니다. Audience Manager은 이 단계에서 데이터를 해시 처리하지 않습니다. 이 데이터 소스에 저장할 이메일 주소가 이미 [!DNL SHA256] 알고리즘으로 해시되었는지 확인하십시오. 그렇지 않으면 [!DNL People-Based Destinations]에 사용할 수 없습니다.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 오프라인 데이터를 사람 기반 대상에 대한 Audience Manager으로 가져오는 방법에 대한 FAQ는 [데이터 온보딩](people-based-destinations-prerequisites.md#data-onboarding)을 참조하십시오.

[!UICONTROL People-Based Destinations]에 대한 데이터 소스를 만드는 방법에 대한 비디오 자습서는 아래 비디오를 참조하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 3단계 - 파일 기반 ID 동기화를 통해 DPUUID를 해시된 이메일 주소에 일치 {#match-ids-emails}

>[!IMPORTANT]
>
> 이 단계는 위에서 설명한 [시나리오 2](people-based-destinations-workflow-offline.md#configure-data-source-settings)에만 적용됩니다. 기존 [DPUUID](../../reference/ids-in-aam.md)가 이미 해시된 이메일 주소를 사용할 경우 [4단계 - 세그멘테이션에 대한 프로필 병합 규칙 만들기](#create-profile-merge-rule)로 건너뜁니다.

1단계의 예에서 아래 표의 해시 이메일 주소(오른쪽 열)로 기존 [DPUUID](../../reference/ids-in-aam.md)를 일치시키고 [2단계 - 데이터 소스 설정 구성](#configure-data-source-settings)에서 만든 새로운 데이터 해시 소스에 이메일 주소를 저장한다고 가정해 봅시다.

다시 말해서, 이제 두 개의 데이터 소스가 있습니다.

| 데이터 소스 ID | 데이터 소스 내용 |
| -------------- | -------------------------- |
| 999.999 | 기존 DPUUID(CRM ID) |
| 9876.54 | 해시된 이메일 주소 |

| DPUUID(CRM ID) | 이메일 주소 | 해시된 이메일 주소 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

이 예제에서는 [ID 동기화 파일](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)에 다음 내용이 있습니다.

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID 동기화 파일](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)은 다음 이름 지정 구조를 따라야 합니다.

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

위의 예에서 파일 이름은 다음과 같습니다.
`c2c_id_999999_987654_1560431657.sync`

[예제 파일을 여기에서 다운로드합니다](assets/c2c_id_999999_987654_1560431657.sync).

ID 동기화 파일을 만든 후 [!DNL Amazon S3] 버킷에 업로드해야 합니다. ID 동기화 파일을 업로드하는 방법에 대해 알아보려면 [Audience Manager에 배치 데이터 보내기](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)를 참조하십시오.

## 4단계 - 세그먼테이션에 대한 프로필 병합 규칙 만들기 {#create-profile-merge-rule}

다음 단계는 대상 세그먼트를 만들어 [!DNL People-Based Destinations]에 전송하는 데 도움이 되는 새 병합 규칙을 만드는 것입니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**&#x200B;로 이동합니다.
2. 클릭 [!UICONTROL Add New Rule].
3. 프로필 병합 규칙 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을 입력합니다.
4. **[!UICONTROL Profile Merge Rule Setup]** 섹션의 **[!UICONTROL Cross-Device Options]** 목록에서 **[!UICONTROL All Cross-Device Profiles]** 규칙을 선택합니다.
5. **[!UICONTROL Cross-Device Profile Options]** 목록에서 트레이트가 온보드 대상 데이터 소스를 선택합니다.
   ![병합 규칙 설정](assets/pbd-pmr.png)

## 5단계 - 대상 세그먼트 만들기 {#create-audience-segments}

오프라인 전용 데이터에서 새 세그먼트를 만들려면 [세그먼트 빌더](../segments/segment-builder.md)를 사용하고 세그먼트를 만들 때 이전 단계에서 만든 새 프로필 병합 규칙을 사용해야 합니다.

## 6단계 - 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**로 이동합니다. 이전에 소셜 플랫폼과 통합한 적이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사람 기반 통합](assets/pbd-config.png)
1. 클릭 **[!UICONTROL Add Account]**.
1. **[!UICONTROL People-Based Platform]** 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![사용자 기반 플랫폼](assets/pbd-add.png)
1. 선택한 플랫폼의 인증 페이지로 리디렉션하려면 **[!UICONTROL Confirm]**&#x200B;을 클릭합니다.
1. 소셜 플랫폼 계정에 인증하면 연결된 광고주 계정을 볼 수 있는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!UICONTROL Confirm]**&#x200B;을 클릭합니다.
1. Audience Manager은 계정을 성공적으로 추가했는지 여부를 알 수 있도록 페이지 상단에 알림을 표시합니다. 또한 소셜 플랫폼 인증이 만료될 때 알림을 수신할 연락처 이메일 주소를 추가할 수도 있습니다.

>[!IMPORTANT]
>
>Audience Manager은 특정 시간 이후에 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 만료된 토큰 갱신 방법에 대한 자세한 내용은 인증 토큰 갱신을 참조하십시오.

## 7단계 - 사람 기반 대상 만들기 {#create-destination}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**&#x200B;로 이동한 다음 **[!UICONTROL Create Destination]**&#x200B;를 클릭합니다.
1. **[!UICONTROL Basic Information]** 섹션에서 새 데이터 소스에 대해 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;를 입력하고 다음 설정을 사용합니다.
   * **[!UICONTROL Category]**:통합 플랫폼;
   * **[!UICONTROL Type]**:사람 기반;
   * **[!UICONTROL Platform]**:대상 세그먼트를 보낼 사람 기반 플랫폼을 선택합니다.
   * **[!UICONTROL Account]**:선택한 플랫폼과 연관된 원하는 광고주 계정을 선택합니다.
      ![create-destination](assets/pbd-create-destination.png)
1. 클릭 **[!UICONTROL Next]**.
1. 이 대상에 대해 설정할 **[!UICONTROL Data Export Labels]**&#x200B;을 선택합니다.
1. **[!UICONTROL Configuration]** 섹션에서 해시된 데이터 소스가 포함된 데이터 소스를 선택합니다.
1. **[!UICONTROL Segment Mappings]** 섹션에서 이 대상에 보낼 세그먼트를 선택합니다. 이것은 [5단계 - 대상 세그먼트 만들기](people-based-destinations-workflow-offline.md#create-audience-segments)에 만든 세그먼트입니다.
1. 대상을 저장합니다.
