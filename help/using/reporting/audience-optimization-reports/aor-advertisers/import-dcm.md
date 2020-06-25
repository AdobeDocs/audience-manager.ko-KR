---
description: DoubleClick 캠페인 관리자(DCM) 데이터 파일을 Audience Manager으로 가져오도록 Google 그룹을 설정합니다. 이 섹션의 내용은 통합 프로세스를 요약하고, 시작하는 데 도움이 되는 DCM 리소스에 대한 링크를 제공합니다.
seo-description: DoubleClick 캠페인 관리자(DCM) 데이터 파일을 Audience Manager으로 가져오도록 Google 그룹을 설정합니다. 이 섹션의 내용은 통합 프로세스를 요약하고, 시작하는 데 도움이 되는 DCM 리소스에 대한 링크를 제공합니다.
seo-title: DCM 데이터 파일을 Audience Manager에 가져오기
solution: Audience Manager
title: DCM 데이터 파일을 Audience Manager에 가져오기
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 8%

---


# DCM 데이터 파일을 Audience Manager에 가져오기 {#import-dcm-data-files-into-audience-manager}

DoubleClick 캠페인 관리자(DCM) 데이터 파일을 Audience Manager으로 가져오도록 Google 그룹을 설정합니다. 이 섹션의 내용은 통합 프로세스를 요약하고, 시작하는 데 도움이 되는 DCM 리소스에 대한 링크를 제공합니다.

## 통합 요약

DCM은 [!DNL Google]의 DFA([!DNL DoubleClick for Advertisers])를 대체한 것입니다. DFA와 마찬가지로 DCM 고객은 [!DNL Audience Manager]에 데이터를 가져와서 보고 작업할 수 있습니다. 그러나 사용자 [!DNL Audience Manager] 및 [!UICONTROL Data Transfer] [!UICONTROL Match Table] 파일을 직접 액세스하고 가져올 수는 없습니다. 이러한 파일을 가져오려면 고객의 노력이 필요합니다.

하지만 설정 절차는 [DoubleClick 캠페인 관리자 도움말에 잘 설명되어 있습니다](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). 또한 아래 나열된 단계를 검토하여 시작할 수 있습니다.

>[!CAUTION]
>
>DCM 데이터 파일에는 모든 광고주 또는 클라이언트에 대한 데이터가 포함됩니다. 특정 클라이언트를 생략해야 하는 경우 해당 파일을 사용할 수 있도록 하기 전에 파일을 편집해야 합니다 [!DNL Audience Manager].

## 데이터 전송 빈도 및 가용성

[!DNL Audience Manager] 매일 데이터를 확인하고 전송합니다. 데이터는 보통 24시간 [!DNL Audience Manager] 후에 사용할 수 있습니다.

## 단계

1. [그룹을 만듭니다](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   그룹은 DCM 데이터에 대한 액세스를 제어합니다. 이 그룹에 초대하고 추가할 수 [!DNL Audience Manager] 있습니다.

1. [Google 클라우드 스토리지 상태를 확인합니다](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456).

   Google Cloud Storage에는 [!UICONTROL Data Transfer] 및 를 포함하는 데이터 버킷이 포함되어 [!UICONTROL Match Tables]있습니다. 버킷을 설정하거나 새 그룹이 기존 데이터 저장소 버킷에 액세스할 수 있는지 확인해야 합니다.

1. [데이터 파일 URL을 가져옵니다](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456).

   DCM 계정 관리자 또는 Platform 솔루션 컨설턴트와 상담하십시오. 데이터 파일에 대한 URL을 제공합니다. [!DNL Google] 향후 릴리스에서 버킷 및 파일 이름의 형식을 변경할 수 있습니다. DCM 계정 관리자에게 문의하여 올바른 형식을 사용하고 있는지 확인하십시오.

1. [버킷 권한을 설정합니다](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission).

   데이터 공유 및 버킷 액세스를 제어할 [!DNL Cloud Storage Manager] 수 있습니다. 그룹에 사용자 [!UICONTROL Data Transfer] 및 [!UICONTROL Match Table] 파일이 포함된 버킷에 대한 읽기 권한을 부여합니다.

1. [데이터 공유를 설정합니다](https://support.google.com/dcm/partner/answer/6206106?hl=en).

   공유 DCM 사용자 ID가 암호화되어 개인 정보를 보호합니다. 암호화는 데이터 전송 파일 끝에 2개의 열 `PartnerId1` `PartnerId2`을 추가하며, 이러한 열에는 이러한 파일을 수신하는 각 회사별 인코딩된 사용자 ID가 포함됩니다.

   공인 타사에서 DCM 데이터를 받을 [!DNL Audience Manager] 수 있지만 ID를 디코딩할 수는 없습니다. 그러나 [!DNL Audience Manager] 한편에서는 인코딩된 ID가 ID와 어떻게 일치하는지 알고 있습니다. 즉, 사용자를 정확하게 일치시키고 동기화할 수 있습니다.

   >[!NOTE]
   >이미 다른 두 타사 파트너와 데이터를 공유하는 [!DNL Audience Manager] 경우 DCM 파일을 로 가져올 수 없습니다.

1. 그룹 [!DNL Audience Manager] 에 가입하도록 초대합니다.

   그룹을 만들어 데이터 버킷에 액세스할 수 있도록 한 후 그룹에 가입하도록 초대합니다 [!DNL Audience Manager] . DFA-AAM@adobe.com으로 초대 이메일을 보냅니다. 3단계에서 데이터 파일 URL을 포함해야 합니다. Adobe 내부 팀은 초대를 수락한 후 액세스 여부를 확인하기 위해 사용자와 협력합니다. 1. 사용자 인터페이스에서 DCM 데이터에 대한 두 개의 데이터 소스를 [!DNL Audience Manager] 설정합니다.

   데이터 소스 이름 `Advertiser Analytics: DCM Platform` 과 `Advertiser Analytics: AAM+DCM Platform`이름을 지정합니다. 데이터 소스 [만들기](../../../features/manage-datasources.md#create-data-source) 워크플로우에서 ID 유형을 로 설정합니다 `Cookie`. 두 개의 새로운 데이터 소스의 ID를 내부 팀과 공유합니다.

1. 가져오는 DCM 파일에서 트레이트를 손쉽게 만들 수 있습니다 [!DNL Audience Manager]. 실행 [가능한 로그 파일](../../../integration/media-data-integration/actionable-log-files.md) 을 참조하고 컨설턴트나 고객 지원 센터에 문의하여 [!DNL Audience Manager] 이러한 기능을 사용하도록 설정하십시오.
