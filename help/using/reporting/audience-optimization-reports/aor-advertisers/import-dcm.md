---
description: Google 그룹을 설정하여 Google Campaign Manager 데이터 파일을 Audience Manager 상태로 만듭니다. 이 섹션의 콘텐츠는 통합 프로세스를 요약하고 시작하는 데 도움이 되는 Google Campaign Manager 리소스 링크를 제공합니다.
seo-description: Set up a Google group to bring your Google Campaign Manager data files into Audience Manager. The content in this section summarizes the integration process and provides you with links to Google Campaign Manager resources to help you get started.
seo-title: Import Google Campaign Manager Data Files Into Audience Manager
solution: Audience Manager
title: Google Campaign Manager 데이터 파일을 Audience Manager으로 가져오기
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: 95b7b4347f3da16be05be60cbefc0e236022a4a7
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 2%

---

# Google Campaign Manager 데이터 파일을 Audience Manager으로 가져오기 {#import-dcm-data-files-into-audience-manager}

[!DNL Google Campaign Manager] 데이터 파일을 Audience Manager 상태로 만들려면 [!DNL Google] 그룹을 설정하십시오. 이 섹션의 콘텐츠는 통합 프로세스를 요약하고 시작하는 데 도움이 되는 [!DNL Google Campaign Manager] 리소스에 대한 링크를 제공합니다.

## 통합 요약

[!DNL Google Campaign Manager]은(는) [!DNL DoubleClick for Advertisers] (DFA)에 대한 [!DNL Google]의 대체입니다. DFA와 마찬가지로 [!DNL Google Campaign Manager] 고객은 [!DNL Audience Manager]에서 데이터를 가져오고 보고 작업할 수 있습니다. 그러나 [!DNL Audience Manager]은(는) [!UICONTROL Data Transfer] 및 [!UICONTROL Match Table] 파일에 직접 액세스하여 가져올 수 없습니다. 이러한 파일을 가져오려면 고객의 노력이 필요합니다.

그러나 설정 절차는 [DoubleClick Campaign Manager 도움말](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)에 잘 설명되어 있습니다. 또한 아래 나열된 단계를 검토하여 시작할 수 있습니다.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 데이터 파일에는 모든 광고주 또는 클라이언트에 대한 데이터가 포함되어 있습니다. 특정 클라이언트를 생략해야 하는 경우 [!DNL Audience Manager]에서 사용할 수 있도록 설정하기 전에 파일을 편집해야 합니다.

## 데이터 전송 빈도 및 가용성

[!DNL Audience Manager]이(가) 매일 한 번씩 데이터를 확인하고 전송합니다. 데이터는 일반적으로 24시간 후에 [!DNL Audience Manager]에서 사용할 수 있습니다.

## 단계

1. [그룹 만들기](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   그룹은 [!DNL Google Campaign Manager] 데이터에 대한 액세스를 제어합니다. 나중에 [!DNL Audience Manager]을(를) 초대하고 이 그룹에 추가합니다.

1. [Google 클라우드 저장소 상태를 확인](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google 클라우드 저장소에는 [!UICONTROL Data Transfer] 및 [!UICONTROL Match Tables]이(가) 들어 있는 데이터 버킷이 있습니다. 버킷을 설정하거나 새 그룹이 기존 데이터 저장소 버킷에 액세스할 수 있는지 확인해야 합니다.

1. [데이터 파일 URL 가져오기](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   [!DNL Google Campaign Manager] 계정 관리자 또는 플랫폼 솔루션 컨설턴트와 함께 작업합니다. 데이터 파일에 대한 URL을 제공합니다. [!DNL Google]은(는) 향후 릴리스에서 버킷 및 파일 이름의 형식을 변경할 수 있습니다. [!DNL Google Campaign Manager] 계정 관리자와 함께 올바른 형식을 사용하고 있는지 확인하십시오.

1. [버킷 권한 설정](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   [!DNL Cloud Storage Manager]을(를) 통해 데이터 공유 및 버킷 액세스를 제어할 수 있습니다. 그룹에 [!UICONTROL Data Transfer] 및 [!UICONTROL Match Table] 파일이 포함된 버킷에 대한 읽기 액세스 권한을 부여합니다.

1. [데이터 공유 설정](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   공유 [!DNL Google Campaign Manager] 사용자 ID는 개인 정보 보호를 위해 암호화됩니다. 암호화는 데이터 전송 파일 `PartnerId1` 및 `PartnerId2`의 끝에 2개의 열을 추가합니다. 이러한 열에는 이러한 파일을 수신하는 각 회사와 관련된 인코딩된 사용자 ID가 포함됩니다.

   승인된 타사 사용자는 [!DNL Audience Manager]에서 [!DNL Google Campaign Manager]개의 데이터를 받을 수 있지만 ID를 디코딩할 수 없습니다. 그러나 [!DNL Audience Manager]에서는 인코딩된 ID가 ID와 어떻게 일치하는지 알고 있습니다. 즉, 신뢰도와 정확도로 사용자를 일치시키고 동기화할 수 있습니다.

   >[!NOTE]
   >이미 다른 타사 파트너 2명과 데이터를 공유하는 경우 [!DNL Google Campaign Manager]개의 파일을 [!DNL Audience Manager] (으)로 가져올 수 없습니다.

1. [!DNL Audience Manager]을(를) 초대하여 그룹에 참가하십시오.

   그룹을 만들고 데이터 버킷에 대한 액세스 권한을 부여한 후 [!DNL Audience Manager]을(를) 초대하여 그룹에 참가하십시오. dfaaam@adobe.com으로 초대 이메일을 보내십시오. 3단계의 데이터 파일 URL을 포함해야 합니다. 내부 팀이 귀하와 협력하여 초대를 수락한 후 액세스를 확인합니다. 1. [!DNL Audience Manager] 사용자 인터페이스에서 [!DNL Google Campaign Manager] 데이터에 대한 두 개의 데이터 원본을 설정합니다.

   데이터 원본 이름을 `Advertiser Analytics: DCM Platform` 및 `Advertiser Analytics: AAM+DCM Platform`로 지정합니다. [데이터 원본 만들기](../../../features/manage-datasources.md#create-data-source) 워크플로우에서 ID 유형을 `Cookie`(으)로 설정합니다. 내부 팀과 두 개의 새 데이터 소스의 ID를 공유합니다.

1. [!DNL Audience Manager] (으)로 가져오는 [!DNL Google Campaign Manager]개 파일에서 특성을 쉽게 만들 수 있습니다. [실행 가능한 로그 파일](../../../integration/media-data-integration/actionable-log-files.md)을 확인하고 [!DNL Audience Manager] 컨설턴트나 고객 지원 팀에 이 기능을 활성화하도록 요청하십시오.
