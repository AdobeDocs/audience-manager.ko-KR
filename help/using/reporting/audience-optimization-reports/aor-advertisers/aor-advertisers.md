---
description: 광고업체를 위한 고객 최적화를 통해 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성능 기회를 식별할 수 있습니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심 최적화 및 효과적인 채널 조합을 알려줍니다.
seo-description: 광고업체를 위한 고객 최적화를 통해 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성능 기회를 식별할 수 있습니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심 최적화 및 효과적인 채널 조합을 알려줍니다.
seo-title: 광고업체를 위한 고객 최적화
solution: Audience Manager
title: 광고업체를 위한 고객 최적화
uuid: 852 D 550 E -3 C 7 F -4750-9 ABC -365 C 3 A 6 F 7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

광고업체를 위한 고객 최적화를 통해 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성능 기회를 식별할 수 있습니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터를 Audience Manager 세그먼트 지표와 결합하여 세그먼트 중심 최적화 및 효과적인 채널 조합을 알려줍니다.

## Data Ingestion Methods {#data-ingestion-methods}

You can send data to [!DNL Audience Manager] for use in these reports by either of these methods. 경우에 따라 고객은 두 방법 모두에서 데이터를 보냅니다. 이렇게 하면 보고서에 방문자에 대한 가장 포괄적이고 정확한 정보가 들어 있는지 확인할 수 있습니다. [!UICONTROL Audience Optimization] 보고서를 사용하려면 이벤트 호출에 *메타데이터* [파일](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) 설명서의 개요 및 매핑에 나열된 모든 매개 변수가 포함되어야 합니다. 아래 나열된 방법을 통해 데이터를 보낼 수 있습니다.

* Pixel calls: To pass the required metadata parameters to [!DNL Audience Manager] see [Capturing Campaign Click Data via Pixel Calls](../../../integration/media-data-integration/click-data-pixels.md) and [Capturing Campaign Impression Data via Pixel Calls](../../../integration/media-data-integration/impression-data-pixels.md).

* Data files: If you want to use these reports to analyze your own data or data from a source that is not integrated with [!DNL Audience Manager], you need to create and upload data and metadata files for that data. For more information, see [Data Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) and [Data and Metadata Files for Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Role-Based Access Controls (RBAC) {#rbac}

The type of reports you can view depend on the [!UICONTROL RBAC] group you&#39;re assigned to. See [Administration](../../../features/administration/administration-overview.md) and [Create a Group](../../../features/administration/administration-overview.md#create-group) for more information.

[!UICONTROL RBAC] 보고서를 보려면 그룹에 일부 Data Sources 설정이 [!UICONTROL Audience Optimization] 설정되어 있어야 합니다. [!DNL Audience Manager] 컨설턴트가 이러한 데이터 소스를 설정합니다. The more data sources in each [!UICONTROL RBAC] user group, the more data those group members will have access to. 컨설턴트는 최소한 최소한 다음과 같은 Data Sources 중 하나를 설정합니다.

* 광고주 데이터 소스
* 브랜드 데이터 소스
* 플랫폼 데이터 소스

Users that belong to more than one [!UICONTROL RBAC] user group can switch between each group&#39;s view. 표시된 데이터가 선택한 그룹을 고려하여 업데이트됩니다. If your company does not use [!UICONTROL RBAC], all users will have admin privileges and access to all the data sources (conversion groups).

## Conversion Groups {#conversion-groups}

In the [!UICONTROL Audience Optimization] reports, **[!UICONTROL Conversion Groups]** are synonymous with data sources that contain at least one conversion trait. Data sources which do not contain at least one conversion trait do not appear in the [!UICONTROL Audience Optimization] reports. [보고된 전환 특성](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 보고서에서 전환 그룹에 대한 전환 트레이트를 볼 수 있습니다.
