---
description: 광고주용 Audience Optimization은 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 될 수 있습니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심의 최적화와 효과적인 채널 혼합을 알려줍니다.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: 광고주를 위한 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 1%

---

# [!UICONTROL Audience Optimization] 광고주용{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 광고주용 는 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 될 수 있습니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager과 결합합니다. [!UICONTROL segment] 세그먼트 중심 최적화 및 효과적인 채널 혼합을 알리는 지표.

## 데이터 수집 방법 {#data-ingestion-methods}

다음 대상에게 데이터를 보낼 수 있습니다. [!DNL Audience Manager] 다음 방법 중 하나를 사용하여 이러한 보고서에 사용할 수 있습니다. 경우에 따라 고객은 두 가지 방법으로 데이터를 전송합니다. 이렇게 하면 보고서에 방문자에 대한 가장 포괄적이고 정확한 정보가 포함되어 있습니다. 을(를) 사용하려면 [!UICONTROL Audience Optimization] 보고서, 이벤트 호출에는 다음이 포함되어야 합니다. *모두* 다음에 나열된 매개 변수 중 [메타데이터 파일에 대한 개요 및 매핑](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 설명서를 참조하십시오. 아래 나열된 방법을 통해 데이터를 보낼 수 있습니다.

* 픽셀 호출: 필요한 메타데이터 매개 변수를 전달하려면 [!DNL Audience Manager] 참조 [픽셀 호출을 통해 캠페인 클릭 데이터 캡처](../../../integration/media-data-integration/click-data-pixels.md) 및 [픽셀 호출을 통해 캠페인 노출 횟수 데이터 캡처](../../../integration/media-data-integration/impression-data-pixels.md).

* 데이터 파일: 이러한 보고서를 사용하여 자체 데이터 또는 와 통합되지 않은 소스의 데이터를 분석하려는 경우 [!DNL Audience Manager], 해당 데이터에 대한 데이터 및 메타데이터 파일을 만들고 업로드해야 합니다. 자세한 내용은 [Audience Optimization 보고서용 데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 및 [Audience Optimization 보고서용 데이터 및 메타데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

볼 수 있는 보고서 유형은 다음에 따라 다릅니다. [!UICONTROL RBAC] 할당된 그룹. 다음을 참조하십시오 [관리](../../../features/administration/administration-overview.md) 및 [그룹 만들기](../../../features/administration/administration-overview.md#create-group) 추가 정보.

[!UICONTROL RBAC] 을(를) 보려면 그룹에 일부 데이터 소스가 설정되어 있어야 합니다. [!UICONTROL Audience Optimization] 보고서. 사용자 [!DNL Audience Manager] 컨설턴트가 다음을 설정합니다. [!UICONTROL data sources] 당신을 위해. 더 많은 [!UICONTROL data sources] 각 [!UICONTROL RBAC] 사용자 그룹일수록 해당 그룹 구성원이 액세스할 수 있는 데이터가 더 많습니다. 최소한 컨설턴트가 다음 중 하나 이상을 설정합니다. [!UICONTROL data sources]:

* 광고주 [!UICONTROL data source ]
* 브랜드 [!UICONTROL data source]
* 플랫폼 [!UICONTROL data source]

둘 이상에 속하는 사용자 [!UICONTROL RBAC] 사용자 그룹은 각 그룹의 보기 간에 전환할 수 있습니다. 표시된 데이터가 선택한 그룹에 맞게 업데이트됩니다. 회사에서 를 사용하지 않는 경우 [!UICONTROL RBAC], 모든 사용자는 관리자 권한을 가지며 [!UICONTROL data sources] (전환 그룹).

## 전환 그룹 {#conversion-groups}

다음에서 [!UICONTROL Audience Optimization] 보고서, **[!UICONTROL Conversion Groups]** 은 와 동의어입니다. [!UICONTROL data sources] 전환 트레이트가 하나 이상 포함된 경우. [!UICONTROL Data sources] 전환 트레이트가 하나 이상 포함되지 않은 은 [!UICONTROL Audience Optimization] 보고서. 에서 전환 그룹에 대한 전환 트레이트를 볼 수 있습니다. [보고된 전환 트레이트](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 보고서.
