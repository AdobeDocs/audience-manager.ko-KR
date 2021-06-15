---
description: '이 페이지에는 오프라인 전용 고객 데이터에서 대상 세그먼트를 작성하고 사용자 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-description: '이 페이지에는 오프라인 전용 고객 데이터에서 대상 세그먼트를 작성하고 사용자 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-title: 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화
solution: Audience Manager
title: 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화
feature: 사용자 기반 대상
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 6%

---

# 워크플로우 B - 오프라인 전용 데이터를 기반으로 개인화 {#workflow-b}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떤 것도 법률적인 조언이 아닙니다. 법률 자문을 구하시려면 법률 자문을 구하십시오.

이 페이지에는 오프라인 전용 고객 데이터에서 대상 세그먼트를 작성하고 사용자 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.

## 1단계 - 온보드 오프라인 트레이트 {#step-1-onboard-traits}

이 시나리오에서 대상 세그먼트를 만드는 첫 번째 단계는 오프라인 고객 데이터를 Audience Manager으로 가져오는 것입니다.

>[!IMPORTANT]
>
> 계속하기 전에, 온보딩하려는 고객 활동이 해당 [온보딩된 트레이트](../traits/trait-and-segment-qualification-reference.md)가 있는 Audience Manager에 이미 정의되어 있는지 확인하십시오.

기존 Audience Manager 고객 ID([DPUUIDs](../../reference/ids-in-aam.md))가 해시된 이메일인지 여부에 관계없이 [DPUUIDs](../../reference/ids-in-aam.md)가 포함된 데이터 소스에 대해 트레이트 온보딩을 수행해야 합니다.

### 예

아래 표에서 고객 ID에 해당하는 온보딩된 트레이트 ID를 자격을 부여하려고 합니다. [DPUUIDs](../../reference/ids-in-aam.md)가 ID 999999의 데이터 소스에 저장되고 Audience Manager 데이터 소스 ID가 123이라고 가정해 보겠습니다.

| 고객 ID(DPUUID) | 온보딩된 트레이트 ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

위의 예에서 해당 온보딩된 트레이트에 대해 고객 ID를 분류하려면 다음 컨텐츠로 [인바운드 데이터 파일](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)을(를) 업로드해야 합니다.

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

파일 이름은 다음과 같습니다.`ftp_dpm_999999_123_TIMESTAMP.sync.gz`
파일 이름 구조에 대한 자세한 내용은 인바운드 데이터 파일에 대한 [Amazon S3 이름 및 파일 크기 요구 사항](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)을 참조하십시오.

## 2단계 - 데이터 소스 설정 구성 {#configure-data-source-settings}

[DPUUIDs](../../reference/ids-in-aam.md)가 소문자인지 여부에 따라 해시된 이메일 주소가 저장되는 데이터 소스를 구성해야 할 수 있습니다.

 

**시나리오 1:dpuuid [](../../reference/ids-in-aam.md) 는 이미 소문자이고 해시된 이메일 주소입니다.**

이 경우 다음과 같이 해당 데이터 소스에 레이블을 지정해야 합니다.

1. **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** 로 이동합니다.
1. [DPUUIDs](../../reference/ids-in-aam.md)가 포함된 데이터 소스를 찾아 클릭합니다.
1. **[!UICONTROL Cannot be tied to personally identifiable information]** 옵션이 선택 취소되어 있는지 확인합니다.
1. 데이터 소스 설정을 저장합니다.

 

**시나리오 2:dpuuid [](../../reference/ids-in-aam.md) 는 소문자로 해시된 이메일 주소가 아닙니다.**

이 경우 해시된 이메일 주소를 저장할 새로운 교차 장치 데이터 소스를 만들어야 합니다. 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** 로 이동한 다음 **[!UICONTROL Add New]** 를 클릭합니다.
1. 새 데이터 소스에 대해 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을 입력합니다.
1. **[!UICONTROL ID Type]** 드롭다운 메뉴에서 **[!UICONTROL Cross Device]** 을 선택합니다.
1. **[!UICONTROL Data Source Settings]** 섹션에서 **[!UICONTROL Inbound]** 옵션과 **[!UICONTROL Outbound]** 옵션을 모두 선택하고 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 활성화합니다.
1. 드롭다운 메뉴를 사용하여 이 데이터 소스에 대한 **[!UICONTROL Emails(SHA256, lowercased)]** 레이블을 선택합니다.
   >[!IMPORTANT]
   >
   >이 선택 사항은 해당 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 데이터 소스에 레이블을 지정합니다. Audience Manager은 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장할 이메일 주소가 이미 [!DNL SHA256] 알고리즘으로 해시되었는지 확인합니다. 그렇지 않으면 [!DNL People-Based Destinations]에 사용할 수 없습니다.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 오프라인 데이터를 사용자 기반 대상의 Audience Manager에 가져오는 방법에 대한 FAQ는 [데이터 온보딩](people-based-destinations-prerequisites.md#data-onboarding) 을 참조하십시오.

[!UICONTROL People-Based Destinations]에 대한 데이터 소스를 만드는 방법에 대한 비디오 자습서를 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## 3단계 - 파일 기반 ID 동기화를 통해 DPUUID를 해시된 이메일 주소에 일치 {#match-ids-emails}

>[!IMPORTANT]
>
> 이 단계는 위에 설명된 [시나리오 2](people-based-destinations-workflow-offline.md#configure-data-source-settings)에만 적용됩니다. 기존 [DPUUIDs](../../reference/ids-in-aam.md)가 이미 해시된 이메일 주소인 경우 [4단계 - 세그먼테이션에 대한 프로필 병합 규칙 만들기](#create-profile-merge-rule)로 건너뜁니다.

1단계의 예에서 아래 (오른쪽 열)의 해시된 이메일 주소에 기존 [DPUUID](../../reference/ids-in-aam.md)을 연결하고, 해시된 이메일 주소를 [2단계에서 만든 새 데이터 소스에 저장한다고 가정합니다](#configure-data-source-settings).

다시 말해서 이제 두 개의 데이터 소스가 있습니다.

| 데이터 소스 ID | 데이터 소스 콘텐츠 |
| -------------- | -------------------------- |
| 999999 | 기존 DPUUID(CRM ID) |
| 987654 | 해시된 이메일 주소 |

| DPUUID(CRM ID) | 이메일 주소 | 해시된 이메일 주소 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | fec5devcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

이 예제에서 [ID 동기화 파일](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)에는 다음 내용이 있습니다.

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

[ID 동기화 파일](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)은(는) 다음 이름 지정 구조를 따라야 합니다.

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

위의 예에서 파일 이름은 다음과 같습니다.
`c2c_id_999999_987654_1560431657.sync`

[](assets/c2c_id_999999_987654_1560431657.sync)에서 예제 파일을 다운로드합니다.

ID 동기화 파일을 만들면 이를 [!DNL Amazon S3] 버킷에 업로드해야 합니다. ID 동기화 파일을 업로드하는 방법에 대해 알려면 [Audience Manager에 배치 데이터 보내기](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)를 참조하십시오.

## 4단계 - 세그먼테이션을 위한 프로필 병합 규칙 만들기 {#create-profile-merge-rule}

다음 단계는 [!DNL People-Based Destinations]에 보낼 대상 세그먼트를 만드는 데 도움이 되는 새 병합 규칙을 만드는 것입니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**&#x200B;로 이동합니다.
2. 클릭 [!UICONTROL Add New Rule].
3. 프로필 병합 규칙 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을 입력합니다.
4. **[!UICONTROL Profile Merge Rule Setup]** 섹션의 **[!UICONTROL Cross-Device Options]** 목록에서 **[!UICONTROL All Cross-Device Profiles]** 규칙을 선택합니다.
5. **[!UICONTROL Cross-Device Profile Options]** 목록에서 트레이트가 온보딩되는 데이터 소스를 선택합니다.
   ![병합 규칙 설정](assets/pbd-pmr.png)

## 5단계 - 대상 세그먼트 만들기 {#create-audience-segments}

오프라인 전용 데이터에서 새 세그먼트를 만들려면 [세그먼트 빌더](../segments/segment-builder.md) 를 사용하고 세그먼트를 만들 때 이전 단계에서 만든 새 프로필 병합 규칙을 사용해야 합니다.

## 6단계 - 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**로 이동합니다. 소셜 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 해당 통합이 표시되어야 합니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사용자 기반 통합](assets/pbd-config.png)
1. 클릭 **[!UICONTROL Add Account]**.
1. **[!UICONTROL People-Based Platform]** 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![사용자 기반 플랫폼](assets/pbd-add.png)
1. 선택한 플랫폼의 인증 페이지로 리디렉션하려면 **[!UICONTROL Confirm]** 을 클릭하십시오.
1. 소셜 플랫폼 계정에 인증되면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!UICONTROL Confirm]** 을 클릭합니다.
1. Audience Manager은 페이지 상단에 계정이 성공적으로 추가되었는지 확인하는 알림을 표시합니다. 또한 소셜 플랫폼 인증이 만료될 때 알림을 받을 연락처 이메일 주소를 추가할 수 있습니다.

>[!IMPORTANT]
>
>Audience Manager은 특정 시간 후에 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 만료된 토큰을 갱신하는 방법에 대한 자세한 내용은 인증 토큰 갱신 을 참조하십시오.

## 7단계 - 사용자 기반 대상 만들기 {#create-destination}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** 로 이동한 다음 **[!UICONTROL Create Destination]** 를 클릭합니다.
1. **[!UICONTROL Basic Information]** 섹션에서 새 데이터 소스에 대해 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;를 입력하고 다음 설정을 사용하십시오.
   * **[!UICONTROL Category]**:통합 플랫폼
   * **[!UICONTROL Type]**:사용자 기반;
   * **[!UICONTROL Platform]**:대상 세그먼트를 보낼 사람 기반 플랫폼을 선택합니다.
   * **[!UICONTROL Account]**:선택한 플랫폼과 연결된 원하는 광고주 계정을 선택합니다.
      ![create-destination](assets/pbd-create-destination.png)
1. 클릭 **[!UICONTROL Next]**.
1. 이 대상에 대해 설정할 **[!UICONTROL Data Export Labels]**&#x200B;을 선택합니다.
1. **[!UICONTROL Configuration]** 섹션에서 해시된 데이터 소스가 포함된 데이터 소스를 선택합니다.
1. **[!UICONTROL Segment Mappings]** 섹션에서 이 대상에 전송할 세그먼트를 선택합니다. 이 세그먼트는 [5단계 - 대상 세그먼트 만들기](people-based-destinations-workflow-offline.md#create-audience-segments)에서 만든 세그먼트입니다.
1. 대상을 저장합니다.
