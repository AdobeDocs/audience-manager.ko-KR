---
description: 이 페이지에는 오프라인 CRM 데이터를 이미 Audience Manager에 있는 동작 데이터와 결합하여 새 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 사람 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: 워크플로우 A - 오프라인 데이터와 결합된 모든 온라인 활동을 기반으로 한 개인화
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 6%

---

# 워크플로우 A - 오프라인 데이터와 결합된 모든 온라인 활동을 기반으로 한 개인화 {#workflow-a}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용 방법을 안내하는 제품 설명서가 포함되어 있습니다. 여기에는 법률적인 조언이 들어 있지 않습니다. 법률 지도가 필요한 경우 법률 자문을 구하십시오.

이 페이지에는 오프라인을 결합하는 방법에 대한 단계별 지침이 포함되어 있습니다 [!DNL CRM] 이미 Audience Manager에 가지고 있는 동작 데이터가 있는 데이터로 새 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 [!DNL People-Based Destinations].

## 1단계 - 데이터 소스 설정 구성 {#configure-data-source-settings}

다음에 대한 [DPUUIDs](../../reference/ids-in-aam.md) 는 소문자이고 해시된 이메일 주소입니다. 해시된 이메일 주소를 저장할 데이터 소스를 구성해야 할 수도 있습니다.

 

**시나리오 1: [DPUUIDs](../../reference/ids-in-aam.md) 은(는) 이미 소문자로 해시된 이메일 주소입니다.**

이 경우 해당 데이터 소스에 다음과 같이 레이블을 지정해야 합니다.

1. 다음으로 이동 [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. 다음을 포함하는 데이터 소스 찾기 [DPUUIDs](../../reference/ids-in-aam.md)을 클릭하고 을 클릭합니다.
1. 다음에서 **[!UICONTROL ID Type]** 드롭다운 메뉴에서 다음을 선택합니다. **[!UICONTROL Cross Device]**.
1. 옵션을 확인하십시오. [!UICONTROL Cannot be tied to personally identifiable information] 이(가) 선택되지 않았습니다.
1. 다음에서 **[!UICONTROL Data Source Settings]** 섹션에서 다음을 모두 선택합니다. **[!UICONTROL Inbound]** 및 **[!UICONTROL Outbound]** 옵션 및 활성화 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 선택합니다.
1. 드롭다운 메뉴를 사용하여 **[!UICONTROL Emails(SHA256, lowercased)]** 이 데이터 소스의 레이블입니다.
   >[!IMPORTANT]
   >
   >이 옵션은 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 데이터 소스에만 레이블을 지정합니다. Audience Manager은 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장할 이메일 주소를 이미 해시했는지 확인합니다. [!DNL SHA256] 알고리즘. 그렇지 않으면 다음에 사용할 수 없습니다. [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 데이터 소스 설정을 저장합니다.

 

**시나리오 2: [DPUUIDs](../../reference/ids-in-aam.md) 은 소문자가 아니며 해시된 이메일 주소입니다.**

이 경우 해시된 이메일 주소를 저장할 새 크로스 디바이스 데이터 소스를 만들어야 합니다. 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 다음으로 이동 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**, 및 클릭 **[!UICONTROL Add New]**.
1. 입력 [!UICONTROL Name] 및 [!UICONTROL Description] 새 데이터 소스.
1. 다음에서 **[!UICONTROL ID Type]** 드롭다운 메뉴에서 다음을 선택합니다. **[!UICONTROL Cross Device]**.
1. 다음에서 **[!UICONTROL Data Source Settings]** 섹션에서 다음을 모두 선택합니다. **[!UICONTROL Inbound]** 및 **[!UICONTROL Outbound]** 옵션 및 활성화 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 선택합니다.
1. 드롭다운 메뉴를 사용하여 **[!UICONTROL Emails(SHA256, lowercased)]** 이 데이터 소스의 레이블입니다.
   >[!IMPORTANT]
   >
   >이 옵션은 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 데이터 소스에만 레이블을 지정합니다. Audience Manager은 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 소스에 저장할 이메일 주소를 이미 해시했는지 확인합니다. [!DNL SHA256] 알고리즘. 그렇지 않으면 다음에 사용할 수 없습니다. [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. 데이터 소스 설정을 저장합니다.

데이터 소스를 만드는 방법에 대한 비디오 튜토리얼은 아래 비디오를 시청하십시오. [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> 다음을 참조하십시오 [데이터 온보딩](people-based-destinations-prerequisites.md#data-onboarding) 오프라인 데이터를 사용자 기반 대상의 Audience Manager으로 가져오는 방법에 대한 faq입니다.

## 2단계 - 파일 기반 ID 동기화를 통해 DPUUID를 해시된 이메일 주소와 일치 {#match-ids-emails}

>[!IMPORTANT]
>
> 이 단계는 에만 적용됩니다 [시나리오 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) 위에서 설명했습니다. 기존 [DPUUIDs](../../reference/ids-in-aam.md) 은(는) 이미 해시된 이메일 주소입니다. (으)로 건너뛰기 [3단계 - 세분화를 위한 프로필 병합 규칙 만들기](people-based-destinations-workflow-combined.md#create-merge-rule).

기존 을(를) 일치시키려고 한다고 가정해 보겠습니다 [DPUUIDs](../../reference/ids-in-aam.md) 해시된 이메일 주소를 아래 표(오른쪽 열)에 추가하고 해시된 이메일 주소를 만든 새 데이터 소스에 저장합니다. [1단계 - 데이터 소스 설정 구성](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (CRM ID) | 이메일 주소 | 해시된 이메일 주소 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

단일 항목에 최대 10개의 해시된 이메일 주소를 연결할 수 있습니다 [DPUUID](../../reference/ids-in-aam.md). 이렇게 하려면 해시된 이메일 주소를 `<TAB>`동기화 파일 내에서 사용됩니다.

이 예제에서는 두 개의 데이터 소스가 있습니다.

| 데이터 소스 ID | 데이터 소스 콘텐츠 |
| -------------- | -------------------------- |
| 999999 | 기존 DPUUID(CRM ID) |
| 987654 | 해시된 이메일 주소 |

 

사용자 [ID 동기화 파일](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 에는 다음 내용이 포함됩니다.

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

다음 [ID 동기화 파일](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) 은(는) 다음 이름 지정 구조를 따라야 합니다.

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

위의 예에서 파일 이름은 다음과 같습니다.
`c2c_id_999999_987654_1560431657.sync`

[여기에 예제 파일 다운로드](assets/c2c_id_999999_987654_1560431657.sync).

ID 동기화 파일을 만든 후에는 [!DNL Amazon S3] 버킷. ID 동기화 파일을 업로드하는 방법은 를 참조하십시오. [Audience Manager에 배치 데이터 보내기](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## 3단계 - 세분화를 위한 프로필 병합 규칙 만들기 {#create-merge-rule}

다음 단계는 사람 기반 대상으로 전송할 대상 세그먼트를 만드는 데 도움이 되는 새 병합 규칙을 만드는 것입니다.

>[!IMPORTANT]
>
> 규칙이 이미 정의된 경우 [!UICONTROL Current Authenticated Profiles] 또는 [!UICONTROL Last Authenticated Profiles] 옵션, 건너뛰기할 수 있음 [4단계 - 대상 세그먼트 만들기](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Audience Manager 계정에 로그인하고 다음으로 이동 **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. 클릭 **[!UICONTROL Add New Rule]**.
1. 프로필 병합 규칙 입력 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**.
1. 다음에서 **[!UICONTROL Profile Merge Rule Setup]** 섹션에서 **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]** 옵션.
1. 다음에서 **[!UICONTROL Cross-Device Profile Options]** 세분화를 실행할 데이터 소스를 나열합니다. 기존 항목을 포함하는 데이터 소스여야 합니다. [DPUUIDs](../../reference/ids-in-aam.md).

## 4단계 - 대상 세그먼트 만들기 {#create-audience-segments}

새 대상 세그먼트를 만들려면 [세그먼트 빌더](../segments/segment-builder.md). 에 보낼 대상 세그먼트가 이미 있는 경우 [!DNL People-Based Destinations], 다음으로 건너뛰기 [5단계 - 사용자 기반 플랫폼 인증 구성](people-based-destinations-workflow-combined.md#configure-authentication).

## 5단계 - 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 다음으로 이동 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. 소셜 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사용자 기반 통합](assets/pbd-config.png)
1. 클릭 **[!UICONTROL Add Account]**.
1. 사용 **[!UICONTROL People-Based Platform]** 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![사용자 기반 플랫폼](assets/pbd-add.png)
1. 클릭 **[!UICONTROL Confirm]** 을(를) 선택한 플랫폼의 인증 페이지로 리디렉션합니다.
1. 소셜 플랫폼 계정을 인증하면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!UICONTROL Confirm]**.
1. Audience Manager은 계정이 성공적으로 추가되었는지 여부를 알려주는 알림을 페이지 맨 위에 표시합니다. 알림을 사용하면 소셜 플랫폼 인증이 곧 만료될 때 알림을 받을 연락처 이메일 주소를 추가할 수도 있습니다.

>[!IMPORTANT]
>
>Audience Manager는 일정 시간이 지나면 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 만료된 토큰을 갱신하는 방법에 대한 자세한 내용은 인증 토큰 갱신 을 참조하십시오.

## 6단계 - 사람 기반 대상 만들기 {#create-destination}

1. Audience Manager 계정에 로그인하고 다음으로 이동 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**, 및 클릭 **[!UICONTROL Create Destination]**.
1. 다음에서 **[!UICONTROL Basic Information]** 섹션, 입력 **[!UICONTROL Name]** 및 **[!UICONTROL Description]** 새 데이터 소스에 대해 다음 설정을 사용하십시오.
   * **[!UICONTROL Category]**: 통합 플랫폼
   * **[!UICONTROL Type]**: 사용자 기반;
   * **[!UICONTROL Platform]**: 대상 세그먼트를 보낼 사람 기반 플랫폼을 선택합니다.
   * **[!UICONTROL Account]**: 선택한 플랫폼과 연결된 원하는 광고주 계정을 선택합니다.
      ![create-destination](assets/pbd-create-destination.png)
1. 클릭 **[!UICONTROL Next]**.
1. 다음을 선택합니다. **[!UICONTROL Data Export Labels]** 이 대상에 대해 설정할 수 있습니다.
1. 다음에서 **[!UICONTROL Configuration]** 섹션에서 해시된 데이터 소스가 포함된 데이터 소스를 선택합니다.
1. 다음에서 **[!UICONTROL Segment Mappings]** 섹션에서 이 대상으로 전송할 세그먼트를 선택합니다. 이 세그먼트는에서 생성한 것입니다. [4단계 - 대상 세그먼트 만들기](people-based-destinations-workflow-combined.md#create-audience-segments).
1. 대상을 저장합니다.
