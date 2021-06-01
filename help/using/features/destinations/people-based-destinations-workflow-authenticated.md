---
description: '이 페이지에는 오프라인 CRM 데이터를 인증된 사용자를 위한 실시간 행동 데이터와 결합하여 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 사용자 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다. '
seo-description: '이 페이지에는 오프라인 CRM 데이터를 인증된 사용자를 위한 실시간 행동 데이터와 결합하여 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 사용자 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.  '
seo-title: 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동을 기반으로 한 개인화
solution: Audience Manager
title: 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동을 기반으로 한 개인화
feature: 사용자 기반 대상
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동을 기반으로 한 개인화 {#workflow-c}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떤 것도 법률적인 조언이 아닙니다. 법률 자문을 구하시려면 법률 자문을 구하십시오.

이 페이지에는 오프라인 [!DNL CRM] 데이터를 인증된 사용자를 위한 실시간 행동 데이터와 결합하여 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 [!DNL People-Based Destinations]에 전송하는 방법에 대한 단계별 지침이 포함되어 있습니다.

## 1단계 - 데이터 소스 설정 구성 {#configure-data-source-settings}

[DPUUIDs](../../reference/ids-in-aam.md)가 소문자인지 여부에 따라 해시된 이메일 주소가 저장되는 데이터 소스를 구성해야 할 수 있습니다.

 

**시나리오 1:dpuuid [](../../reference/ids-in-aam.md) 는 이미 소문자이고 해시된 이메일 주소입니다.**

이 경우 [5단계 - 사용자 기반 플랫폼 인증 구성](#configure-authentication)으로 건너뜁니다.

 

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

## 2단계 - 실시간 HTTP 호출 {#match-email-addresses}을 통해 선언된 ID를 해시된 이메일 주소에 일치시키려면 사용합니다.

인증된 사용자에게 규칙 기반 트레이트에 대한 자격을 부여하려면 [선언된 ID](../declared-ids.md)를 통해 트레이트 자격을 전송해야 합니다.

### 예

다음 두 데이터 소스를 만들었다고 가정합니다.

| 데이터 소스 ID | 데이터 소스 콘텐츠 |
| -------------- | -------------------------- |
| 999999 | 기존 DPUUID(CRM ID) |
| 987654 | 해시된 이메일 주소 |

 

그런 다음 표에 있는 트레이트에 대해 아래 CRM ID에 자격을 부여하려고 합니다.

| DPUUID(CRM ID) | 이메일 주소 | 해시된 이메일 주소 | 트레이트 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

선언된 ID는 다음 구문을 따라야 합니다.

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

위의 예에서 선언된 ID 호출은 다음과 같아야 합니다.

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 3단계 - 세그먼테이션을 위한 프로필 병합 규칙 만들기 {#create-profile-merge-rule-segmentation}

다음 단계는 [!DNL People-Based Destinations]에 보낼 대상 세그먼트를 만드는 데 도움이 되는 새 병합 규칙을 만드는 것입니다.

>[!IMPORTANT]
>
>이미 **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]** 옵션으로 정의된 규칙이 있는 경우 [4단계 - 대상 세그먼트 만들기](#create-audience-segments)로 건너뛸 수 있습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**&#x200B;로 이동합니다.
2. 클릭 **[!UICONTROL Add New Rule]**.
3. 프로필 병합 규칙 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을 입력합니다.
4. **[!UICONTROL Profile Merge Rule Setup]** 섹션의 **[!UICONTROL Cross-Device Options]** 목록에서 **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]** 규칙을 선택합니다.
5. **[!UICONTROL Cross-Device Profile Options]** 목록에서 세그멘테이션을 실행할 데이터 소스를 선택합니다. 이는 기존 DPUUID가 포함된 데이터 소스여야 합니다.
   ![병합 규칙 설정](assets/pbd-pmr-combined.png)

## 4단계 - 대상 세그먼트 만들기 {#create-audience-segments}

새 세그먼트를 만들려면 [세그먼트 빌더](../segments/segment-builder.md)를 사용하십시오. [!DNL People-Based Destinations]에 보내려는 기존 대상 세그먼트가 있는 경우 [5단계 - 사용자 기반 플랫폼 인증 구성](#configure-authentication)으로 건너뜁니다.

## 5단계 - 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**로 이동합니다. 소셜 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 해당 통합이 표시되어야 합니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사용자 기반 통합](assets/pbd-config.png)
2. 클릭 **[!UICONTROL Add Account]**.
3. **[!UICONTROL People-Based Platform]** 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![사용자 기반 플랫폼](assets/pbd-add.png)
4. 선택한 플랫폼의 인증 페이지로 리디렉션하려면 **[!UICONTROL Confirm]** 을 클릭하십시오.
5. 소셜 플랫폼 계정에 인증되면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!UICONTROL Confirm]** 을 클릭합니다.
6. Audience Manager은 페이지 상단에 계정이 성공적으로 추가되었는지 확인하는 알림을 표시합니다. 또한 소셜 플랫폼 인증이 만료될 때 알림을 받을 연락처 이메일 주소를 추가할 수 있습니다.

>[!IMPORTANT]
>
>Audience Manager은 특정 시간 후에 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 만료된 토큰을 갱신하는 방법에 대한 자세한 내용은 인증 토큰 갱신 을 참조하십시오.

## 6단계 - 사용자 기반 대상 만들기 {#create-destination}

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
1. **[!UICONTROL Segment Mappings]** 섹션에서 이 대상에 전송할 세그먼트를 선택합니다. 이 세그먼트는 [4단계 - 대상 세그먼트 만들기](#create-audience-segments)에서 만든 세그먼트입니다.
1. 대상을 저장합니다.
