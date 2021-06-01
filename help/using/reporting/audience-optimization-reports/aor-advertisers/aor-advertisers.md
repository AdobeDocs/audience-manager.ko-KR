---
description: 광고주를 위한 Audience Optimization을 사용하면 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적 성능 기회를 식별하는 데 도움이 될 수 있습니다. 이 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심의 최적화 및 효과적인 채널 조합을 알려줍니다.
seo-description: 광고주를 위한 Audience Optimization을 사용하면 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적 성능 기회를 식별하는 데 도움이 될 수 있습니다. 이 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심의 최적화 및 효과적인 채널 조합을 알려줍니다.
seo-title: 광고주를 위한 Audience Optimization
solution: Audience Manager
title: 광고주를 위한 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: 대상 최적화 보고서
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 3%

---

# [!UICONTROL Audience Optimization] 광고주용{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 광고주를 위한 은(는) 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적 성능 기회를 식별하는 데 도움이 될 수 있습니다. 이 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager [!UICONTROL segment] 지표와 결합하여 세그먼트 중심의 최적화 및 효과적인 채널 조합을 알려줍니다.

## 데이터 수집 방법 {#data-ingestion-methods}

이러한 방법 중 하나를 사용하여 이러한 보고서에 사용할 데이터를 [!DNL Audience Manager]에 보낼 수 있습니다. 고객이 두 가지 방법으로 데이터를 전송하는 경우가 있습니다. 이렇게 하면 보고서에 방문자에 대한 가장 종합적이고 정확한 정보가 포함되어 있는지 확인할 수 있습니다. [!UICONTROL Audience Optimization] 보고서를 사용하려면 이벤트 호출에 [개요 및 메타데이터 파일에 대한 매핑](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 설명서에 나열된 매개 변수의 모두 *a2/>를 포함해야 합니다.* 아래 나열된 다음 방법을 통해 데이터를 전송할 수 있습니다.

* 픽셀 호출:필요한 메타데이터 매개 변수를 [!DNL Audience Manager]에 전달하려면 픽셀 호출을 통해 캠페인 클릭 데이터 캡처](../../../integration/media-data-integration/click-data-pixels.md) 및 [픽셀 호출을 통해 캠페인 노출 데이터 캡처](../../../integration/media-data-integration/impression-data-pixels.md)를 참조하십시오.[

* 데이터 파일:이 보고서를 사용하여 [!DNL Audience Manager]과 통합되지 않은 소스에서 자체 데이터 또는 데이터를 분석하려는 경우 해당 데이터에 대한 데이터 및 메타데이터 파일을 만들고 업로드해야 합니다. 자세한 내용은 [Audience Optimization 보고서용 데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 및 [Audience Optimization 보고서용 데이터 및 메타데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)을 참조하십시오.

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

볼 수 있는 보고서 유형은 할당된 [!UICONTROL RBAC] 그룹에 따라 다릅니다. 자세한 내용은 [관리](../../../features/administration/administration-overview.md) 및 [그룹 만들기](../../../features/administration/administration-overview.md#create-group)를 참조하십시오.

[!UICONTROL RBAC] 보고서를 보려면 그룹에 몇 가지 데이터 소스가 설정되어 있어야  [!UICONTROL Audience Optimization] 합니다. [!DNL Audience Manager] 컨설턴트가 이러한 [!UICONTROL data sources]을(를) 자동으로 설정합니다. 각 [!UICONTROL RBAC] 사용자 그룹에 더 많은 [!UICONTROL data sources] 데이터가 있으면 해당 그룹 구성원이 액세스할 수 있습니다. 최소한 컨설턴트는 다음 [!UICONTROL data sources] 중 적어도 하나를 설정합니다.

* 광고주 [!UICONTROL data source ]
* 브랜드 [!UICONTROL data source]
* 플랫폼 [!UICONTROL data source]

두 개 이상의 [!UICONTROL RBAC] 사용자 그룹에 속하는 사용자는 각 그룹의 보기 간에 전환할 수 있습니다. 표시된 데이터는 선택한 그룹에 대해 업데이트됩니다. 회사에서 [!UICONTROL RBAC]을 사용하지 않는 경우, 모든 사용자는 관리자 권한과 모든 [!UICONTROL data sources](전환 그룹)에 액세스할 수 있습니다.

## 전환 그룹 {#conversion-groups}

[!UICONTROL Audience Optimization] 보고서에서 **[!UICONTROL Conversion Groups]**&#x200B;은 하나 이상의 전환 트레이트를 포함하는 [!UICONTROL data sources]와 동의어입니다. [!UICONTROL Data sources] 보고서에서 하나 이상의 전환 트레이트가 포함되지 않은 전환 트레이트가  [!UICONTROL Audience Optimization] 표시되지 않습니다. [보고된 전환 특성](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 보고서에서 전환 그룹에 대한 전환 트레이트를 볼 수 있습니다.
