---
description: 광고업체를 위한 고객 최적화는 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 됩니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심의 최적화 및 효과적인 채널 조합을 제공합니다.
seo-description: 광고업체를 위한 고객 최적화는 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 됩니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심의 최적화 및 효과적인 채널 조합을 제공합니다.
seo-title: 광고주를 위한 Audience Optimization
solution: Audience Manager
title: 광고주를 위한 Audience Optimization
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---


# [!UICONTROL Audience Optimization] 광고주{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] 광고주는 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 될 수 있습니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 지표과 결합하여 세그먼트 중심의 최적화 및 효과적인 채널 조합을 제공합니다. [!UICONTROL segment]

## 데이터 수집 방법 {#data-ingestion-methods}

이러한 방법 중 하나를 통해 이러한 보고서에서 사용할 데이터 [!DNL Audience Manager] 를 보낼 수 있습니다. 경우에 따라 고객은 두 가지 방법으로 데이터를 보냅니다. 이렇게 하면 보고서에 방문자에 대한 가장 포괄적이고 정확한 정보가 포함되도록 할 수 있습니다. 보고서를 [!UICONTROL Audience Optimization] 사용하려면 이벤트 호출에는 메타데이터 파일에 대한 *개요 및 매핑 설명서에 나열된* 모든 [매개 변수](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 가 포함되어야합니다. 아래 나열된 다음 방법을 통해 데이터를 전송할 수 있습니다.

* 픽셀 호출: 필요한 메타데이터 매개 변수를 전달하여 픽셀 호출을 통한 [!DNL Audience Manager] 캠페인 클릭 데이터 캡처 [및 픽셀 호출을 통해](../../../integration/media-data-integration/click-data-pixels.md) 캠페인 노출 데이터 캡처를 [참조하십시오](../../../integration/media-data-integration/impression-data-pixels.md).

* 데이터 파일: 이러한 보고서를 사용하여 데이터 또는 데이터와 통합되지 않은 소스의 데이터를 분석하려면 해당 데이터에 대한 데이터 및 메타데이터 파일 [!DNL Audience Manager]을 만들고 업로드해야 합니다. 자세한 내용은 대상 최적화 보고서용 [데이터 파일](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 및 대상 최적화 보고서용 [데이터 및 메타데이터 파일을 참조하십시오](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

볼 수 있는 보고서 유형은 할당된 [!UICONTROL RBAC] 그룹에 따라 다릅니다. 자세한 내용은 [관리](../../../features/administration/administration-overview.md) 및 [그룹](../../../features/administration/administration-overview.md#create-group) 만들기를참조하십시오.

[!UICONTROL RBAC] 보고서를 보려면 그룹에 일부 데이터 소스가 설정되어 있어야 [!UICONTROL Audience Optimization] 합니다. 컨설턴트가 이 [!DNL Audience Manager] 파일을 자동으로 [!UICONTROL data sources] 설정합니다. 각 사용자 그룹 [!UICONTROL data sources] 에서 더 많은 [!UICONTROL RBAC] 데이터가 해당 그룹 구성원이 액세스할 수 있게 됩니다. 컨설턴트는 최소 다음 중 하나를 설정할 수 있습니다 [!UICONTROL data sources].

* 광고주 [!UICONTROL data source ]
* 브랜드 [!UICONTROL data source]
* 플랫폼 [!UICONTROL data source]

둘 이상의 [!UICONTROL RBAC] 사용자 그룹에 속한 사용자는 각 그룹의 보기 간에 전환할 수 있습니다. 선택한 그룹을 존중하도록 표시된 데이터가 업데이트됩니다. 회사에서 사용하지 않는 경우 모든 사용자 [!UICONTROL RBAC]는 모든 [!UICONTROL data sources] (전환 그룹)에 대한 관리자 권한 및 액세스 권한을 가집니다.

## 전환 그룹 {#conversion-groups}

보고서에서 [!UICONTROL Audience Optimization] 는 하나 이상의 전환 특성 **[!UICONTROL Conversion Groups]** 을 포함하는 [!UICONTROL data sources] 동의어입니다. [!UICONTROL Data sources] 보고서에 하나 이상의 전환 특성이 표시되지 않는 문제가 [!UICONTROL Audience Optimization] 있습니다. 보고된 전환 트레이트 보고서에서 전환 그룹의 [전환 트레이트를 볼 수](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 있습니다.
