---
description: 이 페이지에는 오프라인 CRM 데이터를 인증된 사용자의 실시간 행동 데이터와 결합하여 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 사람 기반 대상으로 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동을 기반으로 한 Personalization
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 1%

---

# 워크플로우 C - 오프라인 데이터와 결합된 인증된 활동을 기반으로 한 Personalization {#workflow-c}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용 방법을 안내하는 제품 설명서가 포함되어 있습니다. 여기에는 법률적인 조언이 들어 있지 않습니다. 법률 지도가 필요한 경우 법률 자문을 구하십시오.

이 페이지에는 오프라인 [!DNL CRM] 데이터를 인증된 사용자에 대한 실시간 동작 데이터와 결합하여 대상 세그먼트를 만든 다음 이러한 대상 세그먼트를 [!DNL People-Based Destinations]에 보내는 방법에 대한 단계별 지침이 포함되어 있습니다.

## 1단계 - Data Source 설정 구성 {#configure-data-source-settings}

[DPUUID](../../reference/ids-in-aam.md)이(가) 해시된 소문자인지 여부에 따라 해시된 이메일 주소를 저장할 데이터 소스를 구성해야 할 수 있습니다.

 

**시나리오 1: [DPUUID](../../reference/ids-in-aam.md)이(가) 이미 소문자이고 해시된 이메일 주소입니다.**

이 경우 [5단계 - 사용자 기반 플랫폼 인증 구성](#configure-authentication)으로 건너뜁니다.

 

**시나리오 2: [DPUUIDs](../../reference/ids-in-aam.md)이(가) 소문자가 아니며 해시된 이메일 주소입니다.**

이 경우 해시된 이메일 주소를 저장할 새 크로스 디바이스 데이터 소스를 만들어야 합니다. 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**(으)로 이동한 다음 **[!UICONTROL Add New]**&#x200B;을(를) 클릭합니다.
1. 새 데이터 원본에 대한 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을(를) 입력하십시오.
1. **[!UICONTROL ID Type]** 드롭다운 메뉴에서 **[!UICONTROL Cross Device]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Data Source Settings]** 섹션에서 **[!UICONTROL Inbound]** 및 **[!UICONTROL Outbound]** 옵션을 모두 선택하고 **[!UICONTROL Share associated cross-device IDs in people-based destinations]** 옵션을 사용하도록 설정합니다.
1. 드롭다운 메뉴를 사용하여 이 데이터 원본에 대한 **[!UICONTROL Emails(SHA256, lowercased)]** 레이블을 선택합니다.
   >[!IMPORTANT]
   >
   >이 옵션은 특정 알고리즘으로 해시된 데이터를 포함하는 것으로 데이터 소스에만 레이블을 지정합니다. Audience Manager은 이 단계에서 데이터를 해시하지 않습니다. 이 데이터 원본에 저장할 전자 메일 주소를 [!DNL SHA256] 알고리즘으로 이미 해시했는지 확인하세요. 그렇지 않으면 [!DNL People-Based Destinations]에 사용할 수 없습니다.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > 오프라인 데이터를 사용자 기반 대상의 Audience Manager으로 가져오는 방법에 대한 FAQ는 [데이터 온보딩](people-based-destinations-prerequisites.md#data-onboarding)을 참조하십시오.

[!UICONTROL People-Based Destinations]에 대한 데이터 원본을 만드는 방법에 대한 비디오 튜토리얼을 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/31965?captions=kor)

## 2단계 - 선언된 ID를 사용하여 실시간 HTTP 호출을 통해 DPUUID를 해시된 이메일 주소와 일치시킵니다. {#match-email-addresses}

인증된 사용자에게 규칙 기반 특성을 부여하려면 [선언된 ID](../declared-ids.md)를 통해 특성 자격을 보내야 합니다.

### 예

다음과 같은 두 개의 데이터 소스를 만들었다고 가정합니다.

| 데이터 소스 ID | 데이터 소스 콘텐츠 |
| -------------- | -------------------------- |
| 999999 | 기존 DPUUID(CRM ID) |
| 987654 | 해시된 이메일 주소 |

 

그런 다음 아래의 CRM ID를 표에서 트레이트에 맞게 검증하려고 합니다.

| DPUUID (CRM ID) | 이메일 주소 | 해시된 이메일 주소 | 특성 |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | 위치 = 미국 |

 

선언된 ID는 다음 구문을 따라야 합니다.

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

위의 예에서 선언된 ID 호출은 다음과 같아야 합니다.

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## 3단계 - 세분화를 위한 프로필 병합 규칙 만들기 {#create-profile-merge-rule-segmentation}

다음 단계는 [!DNL People-Based Destinations]에 보낼 대상 세그먼트를 만드는 데 도움이 되는 새 병합 규칙을 만드는 것입니다.

>[!IMPORTANT]
>
>**[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]** 옵션으로 이미 정의된 규칙이 있는 경우 [4단계 - 대상 세그먼트 만들기](#create-audience-segments)로 건너뛸 수 있습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**(으)로 이동합니다.
2. **[!UICONTROL Add New Rule]** 아이콘을 클릭합니다.
3. 프로필 병합 규칙 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을(를) 입력하십시오.
4. **[!UICONTROL Profile Merge Rule Setup]** 섹션의 **[!UICONTROL Cross-Device Options]** 목록에서 **[!UICONTROL Current Authenticated Profiles]** 또는 **[!UICONTROL Last Authenticated Profiles]** 규칙을 선택합니다.
5. **[!UICONTROL Cross-Device Profile Options]** 목록에서 세그먼테이션을 실행할 데이터 원본을 선택합니다. 기존 DPUUID가 포함된 데이터 소스여야 합니다.
   ![병합 규칙 설정](assets/pbd-pmr-combined.png)

## 4단계 - 대상 세그먼트 만들기 {#create-audience-segments}

새 세그먼트를 만들려면 [세그먼트 빌더](../segments/segment-builder.md)를 사용하십시오. [!DNL People-Based Destinations]에게 보낼 대상 세그먼트가 이미 있는 경우 [5단계 - 사용자 기반 플랫폼 인증 구성](#configure-authentication)으로 건너뛰십시오.

## 5단계 - 사용자 기반 플랫폼 인증 구성 {#configure-authentication}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**(으)로 이동합니다. 소셜 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
   ![사용자 기반 통합](assets/pbd-config.png)
2. **[!UICONTROL Add Account]** 아이콘을 클릭합니다.
3. **[!UICONTROL People-Based Platform]** 드롭다운 메뉴를 사용하여 통합을 구성할 플랫폼을 선택합니다.
   ![사용자 기반 플랫폼](assets/pbd-add.png)
4. 선택한 플랫폼의 인증 페이지로 리디렉션하려면 **[!UICONTROL Confirm]**&#x200B;을(를) 클릭하십시오.
5. 소셜 플랫폼 계정을 인증하면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!UICONTROL Confirm]**&#x200B;을(를) 클릭합니다.
6. Audience Manager은 계정이 성공적으로 추가되었는지 여부를 알려주는 알림을 페이지 맨 위에 표시합니다. 알림을 사용하면 소셜 플랫폼 인증이 곧 만료될 때 알림을 받을 연락처 이메일 주소를 추가할 수도 있습니다.

>[!IMPORTANT]
>
>Audience Manager은 일정 시간이 지나면 만료되는 인증 토큰을 통해 소셜 플랫폼과의 통합을 처리합니다. 만료된 토큰을 갱신하는 방법에 대한 자세한 내용은 인증 토큰 갱신 을 참조하십시오.

## 6단계 - 사람 기반 대상 만들기 {#create-destination}

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**(으)로 이동한 다음 **[!UICONTROL Create Destination]**&#x200B;을(를) 클릭합니다.
1. **[!UICONTROL Basic Information]** 섹션에서 새 데이터 원본의 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을(를) 입력하고 다음 설정을 사용합니다.
   * **[!UICONTROL Category]**: 통합 플랫폼;
   * **[!UICONTROL Type]**: 사용자 기반;
   * **[!UICONTROL Platform]**: 대상 세그먼트를 보낼 사람 기반 플랫폼을 선택하십시오.
   * **[!UICONTROL Account]**: 선택한 플랫폼과 연결된 원하는 광고주 계정을 선택합니다.

     ![create-destination](assets/pbd-create-destination.png)
1. **[!UICONTROL Next]** 아이콘을 클릭합니다.
1. 이 대상에 대해 설정할 **[!UICONTROL Data Export Labels]**&#x200B;을(를) 선택하십시오.
1. **[!UICONTROL Configuration]** 섹션에서 해시된 데이터 원본이 포함된 데이터 원본을 선택합니다.
1. **[!UICONTROL Segment Mappings]** 섹션에서 이 대상으로 보낼 세그먼트를 선택합니다. 이는 [4단계 - 대상 세그먼트 만들기](#create-audience-segments)에서 만든 세그먼트입니다.
1. 대상을 저장합니다.
