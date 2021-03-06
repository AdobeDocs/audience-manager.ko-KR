---
description: Google Campaign Manager 데이터 파일을 Audience Manager으로 가져오기 위해 Google 그룹을 설정합니다. 이 섹션의 컨텐츠는 통합 프로세스를 요약하며 시작하는 데 도움이 되도록 Google Campaign Manager 리소스에 대한 링크를 제공합니다.
seo-description: Google Campaign Manager 데이터 파일을 Audience Manager으로 가져오기 위해 Google 그룹을 설정합니다. 이 섹션의 컨텐츠는 통합 프로세스를 요약하며 시작하는 데 도움이 되도록 Google Campaign Manager 리소스에 대한 링크를 제공합니다.
seo-title: Google Campaign Manager 데이터 파일을 Audience Manager에 가져오기
solution: Audience Manager
title: Google Campaign Manager 데이터 파일을 Audience Manager에 가져오기
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: 대상 최적화 보고서
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 2%

---

# Google Campaign Manager 데이터 파일을 Audience Manager {#import-dcm-data-files-into-audience-manager}에 가져오기

[!DNL Google Campaign Manager] 데이터 파일을 Audience Manager으로 가져오려면 [!DNL Google] 그룹을 설정하십시오. 이 섹션의 컨텐츠는 통합 프로세스를 요약하며 시작하는 데 도움이 되는 [!DNL Google Campaign Manager] 리소스에 대한 링크를 제공합니다.

## 통합 요약

[!DNL Google Campaign Manager] 은  [!DNL Google]의 DFA( [!DNL DoubleClick for Advertisers] )를 대체한 것입니다. DFA와 마찬가지로 [!DNL Google Campaign Manager] 고객은 [!DNL Audience Manager]에서 데이터를 가져오고 보고 작업할 수 있습니다. 그러나 [!DNL Audience Manager]은(는) [!UICONTROL Data Transfer] 및 [!UICONTROL Match Table] 파일에 직접 액세스하여 가져올 수 없습니다. 이러한 파일을 가져오려면 고객의 노력이 필요합니다.

그러나 설정 프로시저는 [DoubleClick Campaign Manager 도움말](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)에 설명되어 있습니다. 또한 아래 나열된 단계를 검토하여 시작할 수도 있습니다.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] 데이터 파일에는 모든 광고주 또는 클라이언트의 데이터가 포함되어 있습니다. 특정 클라이언트를 생략해야 하는 경우 [!DNL Audience Manager]에서 사용할 수 있도록 하기 전에 파일을 편집해야 합니다.

## 데이터 전송 빈도 및 가용성

[!DNL Audience Manager] 에서는 매일 데이터를 확인하고 전송합니다. 데이터는 일반적으로 24시간 후에 [!DNL Audience Manager]에서 사용할 수 있습니다.

## 단계

1. [그룹을 만듭니다](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   그룹은 [!DNL Google Campaign Manager] 데이터에 대한 액세스를 제어합니다. 결국 이 그룹에 [!DNL Audience Manager]을 초대하고 추가합니다.

1. [Google Cloud 저장소 상태를 확인합니다](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud 저장소에는 [!UICONTROL Data Transfer] 및 [!UICONTROL Match Tables]을(를) 보유하는 데이터 버킷이 포함되어 있습니다. 버킷을 설정하거나 새 그룹이 기존 데이터 저장소 버킷에 액세스할 수 있는지 확인해야 합니다.

1. [데이터 파일 URL을 가져옵니다](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   [!DNL Google Campaign Manager] 계정 관리자 또는 플랫폼 솔루션 컨설턴트와 작업합니다. 그러면 데이터 파일에 URL을 제공합니다. [!DNL Google] 향후 릴리스에서 버킷 및 파일 이름의 형식을 변경할 수 있습니다. 다시 한 번 [!DNL Google Campaign Manager] 계정 관리자와 함께 올바른 형식을 사용하고 있는지 확인하십시오.

1. [버킷 권한을 설정합니다](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   [!DNL Cloud Storage Manager]을(를) 사용하면 데이터 공유 및 버킷 액세스를 제어할 수 있습니다. 그룹에 [!UICONTROL Data Transfer] 및 [!UICONTROL Match Table] 파일이 포함된 버킷에 대한 읽기 권한을 제공합니다.

1. [데이터 공유를 설정합니다](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   공유된 [!DNL Google Campaign Manager] 사용자 ID는 개인 정보를 보호하기 위해 암호화되어 있습니다. 암호화는 데이터 전송 파일 `PartnerId1` 및 `PartnerId2`의 끝에 2개의 열을 추가합니다. 이러한 열에는 이러한 파일을 받는 각 회사에 대한 인코딩된 사용자 ID가 포함됩니다.

   승인된 타사 제품인 [!DNL Audience Manager]은 [!DNL Google Campaign Manager] 데이터를 받을 수 있지만 ID를 디코딩할 수 없습니다. 그러나 [!DNL Audience Manager] 측에서는 인코딩된 ID가 ID와 어떻게 일치하는지 알고 있습니다. 즉, 사용자를 일치시키고 신뢰도와 정확도와 동기화할 수 있습니다.

   >[!NOTE]
   >이미 다른 2개의 타사 파트너와 데이터를 공유하는 경우 [!DNL Google Campaign Manager] 파일을 [!DNL Audience Manager]에 가져올 수 없습니다.

1. [!DNL Audience Manager]을(를) 그룹에 가입하도록 초대합니다.

   그룹을 만들어 데이터 버킷에 대한 액세스 권한을 제공한 후 [!DNL Audience Manager]을(를) 초대하여 그룹에 참여하십시오. DFA-AAM@adobe.com으로 초대 이메일을 보냅니다. 3단계의 데이터 파일 URL을 포함해야 합니다. Adobe의 내부 팀은 초대장을 수락한 후 액세스 여부를 확인하기 위해 귀사와 협력합니다. 1. [!DNL Audience Manager] 사용자 인터페이스에서 [!DNL Google Campaign Manager] 데이터에 대해 두 개의 데이터 소스를 설정합니다.

   데이터 소스 이름을 `Advertiser Analytics: DCM Platform` 및 `Advertiser Analytics: AAM+DCM Platform`로 지정합니다. [데이터 소스 만들기](../../../features/manage-datasources.md#create-data-source) 워크플로우에서 ID 유형을 `Cookie`로 설정합니다. 두 개의 새 데이터 소스의 ID를 내부 팀과 공유합니다.

1. [!DNL Audience Manager]에 가져오는 [!DNL Google Campaign Manager] 파일에서 트레이트를 쉽게 만들 수 있습니다. [실행 가능 로그 파일](../../../integration/media-data-integration/actionable-log-files.md) 을 참조하고 [!DNL Audience Manager] 컨설턴트나 고객 지원 센터에 문의하여 기능을 활성화하십시오.
