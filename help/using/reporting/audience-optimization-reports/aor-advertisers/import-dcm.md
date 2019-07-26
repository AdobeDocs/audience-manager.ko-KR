---
description: Google 그룹을 설정하여 doubleclick Campaign Manager (DCM) 데이터 파일을 Audience Manager로 가져옵니다. 이 섹션의 내용은 통합 프로세스를 요약하고, 작업을 시작하는 데 도움이 되는 DCM 리소스에 대한 링크를 제공합니다.
seo-description: Google 그룹을 설정하여 doubleclick Campaign Manager (DCM) 데이터 파일을 Audience Manager로 가져옵니다. 이 섹션의 내용은 통합 프로세스를 요약하고, 작업을 시작하는 데 도움이 되는 DCM 리소스에 대한 링크를 제공합니다.
seo-title: Audience Manager로 DCM 데이터 파일 가져오기
solution: Audience Manager
title: Audience Manager로 DCM 데이터 파일 가져오기
uuid: 3578 CFE 1-6 D 30-4 A 73-AB 75-8 D 272 BEBCD 60
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Google 그룹을 설정하여 doubleclick Campaign Manager (DCM) 데이터 파일을 Audience Manager로 가져옵니다. 이 섹션의 내용은 통합 프로세스를 요약하고, 작업을 시작하는 데 도움이 되는 DCM 리소스에 대한 링크를 제공합니다.

## 통합 요약

DCM은 [!DNL Google]의 DFA([!DNL DoubleClick for Advertisers])를 대체한 것입니다. DFA와 마찬가지로 DCM 고객은 [!DNL Audience Manager]에 데이터를 가져와서 보고 작업할 수 있습니다. But [!DNL Audience Manager] cannot directly access and import your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files. 이러한 파일을 가져오려면 고객의 노력이 필요합니다.

However, the set up procedure is well documented in the [DoubleClick Campaign Manager Help](https://support.google.com/dcm/partner/answer/2941575?hl=en&ref_topic=6107456). 또한 아래 나열된 단계를 검토하여 작업을 시작할 수 있습니다.

>[!CAUTION]
>
>DCM 데이터 파일에는 모든 광고주 또는 클라이언트용 데이터가 포함되어 있습니다. If you need to omit specific clients, then you must edit the files before making them available to [!DNL Audience Manager].

## 데이터 전송 빈도 및 가용성

[!DNL Audience Manager] 하루에 한 번 데이터를 확인하고 전송합니다. Data is usually available in [!DNL Audience Manager] after 24-hours.

## 단계

1. [그룹을 만듭니다](https://support.google.com/dcm/partner/answer/3370419?hl=en&ref_topic=6107456).

   그룹은 DCM 데이터에 대한 액세스를 제어합니다. Eventually, you'll invite and add [!DNL Audience Manager] to this group.

1. [Google 클라우드 스토리지 상태를 확인합니다](https://support.google.com/dcm/partner/answer/3370481?hl=en&ref_topic=6107456).

   Google Cloud Storage contains the data bucket that holds your [!UICONTROL Data Transfer] and [!UICONTROL Match Tables]. 버킷을 설정하거나 새 그룹이 기존 데이터 저장소 버킷에 대한 액세스 권한을 가지고 있는지 확인해야 합니다.

1. [데이터 파일 URL를 가져옵니다](https://support.google.com/dcm/partner/answer/3370482?hl=en&ref_topic=6107456).

   DCM 계정 관리자 또는 플랫폼 솔루션 컨설턴트와 함께 작업할 수 있습니다. 데이터 파일에 대한 URL를 제공합니다. [!DNL Google] 향후 릴리스에서 버킷 및 파일 이름에 대한 형식을 변경할 수 있습니다. DCM 계정 관리자와 함께 작업하여 올바른 포맷을 사용하고 있는지 확인하십시오.

1. [버킷 권한을 설정합니다](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   The [!DNL Cloud Storage Manager] lets you control data sharing and bucket access. Give your group read access to the bucket that contains your [!UICONTROL Data Transfer] and [!UICONTROL Match Table] files.

1. [데이터 공유를 설정합니다](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   공유 DCM 사용자 ID는 암호화되어 개인 정보를 보호합니다. Encryption adds 2 columns to the end of your Data Transfer file, `PartnerId1` and `PartnerId2`. 이러한 열에는 이러한 파일을 받는 각 회사에 대한 인코딩된 사용자 ID가 포함됩니다.

   As an authorized third-party, [!DNL Audience Manager] can receive DCM data, but cannot decode the IDs. However, on the [!DNL Audience Manager] side, we know how the encoded IDs match our IDs. 즉, 사용자와 신뢰 및 정확도를 정확하게 일치시킬 수 있습니다.

   >[!NOTE]
   >You cannot import DCM files into [!DNL Audience Manager] if you're already sharing data with 2 other third-party partners.

1. Invite [!DNL Audience Manager] to join the group.

   After you create a group and give it access to a data bucket, invite [!DNL Audience Manager] to join the group. 초대 이메일을 DFA-AAM@adobe.com로 보내주십시오. 3 단계의 데이터 파일 URL를 포함해야 합니다. Adobe의 내부 팀은 귀하와의 협력을 통해 초대를 수락한 후 액세스를 확인합니다. 1. Set up two data sources for DCM data in the [!DNL Audience Manager] User Interface.

   Name the data sources `Advertiser Analytics: DCM Platform` and `Advertiser Analytics: AAM+DCM Platform`. In the [Create Data Sources](../../../features/manage-datasources.md#create-data-source) workflow, set the ID type to `Cookie`. 두 개의 새로운 데이터 소스의 ID를 내부 팀과 공유합니다.

1. You can easily create traits from the DCM files you import into [!DNL Audience Manager]. [실행 가능한 로그 파일을](../../../integration/media-data-integration/actionable-log-files.md) 보고 [!DNL Audience Manager] 컨설턴트나 고객 지원 센터에 이 기능을 사용하도록 요청하십시오.
