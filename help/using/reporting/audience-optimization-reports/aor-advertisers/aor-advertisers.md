---
description: 광고업체를 위한 고객 최적화는 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 됩니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터와 Audience Manager 세그먼트 지표를 결합하여 세그먼트 중심의 최적화와 효과적인 채널 조합을 제공합니다.
seo-description: 광고업체를 위한 고객 최적화는 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 됩니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터와 Audience Manager 세그먼트 지표를 결합하여 세그먼트 중심의 최적화와 효과적인 채널 조합을 제공합니다.
seo-title: 광고업체를 위한 고객 최적화
solution: Audience Manager
title: 광고업체를 위한 고객 최적화
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

광고업체를 위한 고객 최적화는 유료 미디어 캠페인에서 Audience Manager 세그먼트에 대한 잠재적인 성과 기회를 식별하는 데 도움이 됩니다. 이러한 보고서는 로그 수준 캠페인 성과 데이터와 Audience Manager 세그먼트 지표를 결합하여 세그먼트 중심의 최적화와 효과적인 채널 조합을 제공합니다.

## 데이터 통합 방법 {#data-ingestion-methods}

이러한 방법 중 하나를 사용하여 이 보고서에서 사용할 수 [!DNL Audience Manager] 있도록 데이터를 보낼 수 있습니다. 경우에 따라 고객은 두 가지 방법으로 데이터를 보냅니다. 이렇게 하면 보고서에 방문자에 대한 가장 포괄적이고 정확한 정보가 포함되도록 할 수 있습니다. 보고서를 사용하려면 이벤트 호출에 메타데이터 파일에 대한 개요 및 매핑 [!UICONTROL Audience Optimization] 설명서에 나열된 모든 *매개 변수가* 포함되어야 합니다 [](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) . 아래 나열된 다음 방법을 통해 데이터를 전송할 수 있습니다.

* 픽셀 호출:필요한 메타데이터 매개 변수를 전달하여 픽셀 호출을 통해 캠페인 클릭 [!DNL Audience Manager] 데이터 캡처 [및 픽셀 호출을 통해 캠페인 노출](../../../integration/media-data-integration/click-data-pixels.md) 데이터 캡처를 [참조하십시오](../../../integration/media-data-integration/impression-data-pixels.md).

* 데이터 파일:이러한 보고서를 사용하여 통합되지 않은 소스의 자체 데이터 또는 데이터를 분석하려는 [!DNL Audience Manager]경우 해당 데이터에 대한 데이터 및 메타데이터 파일을 만들고 업로드해야 합니다. 자세한 내용은 대상 [최적화 보고서용 데이터 파일 및 대상](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) 최적화 [보고서용 데이터 및 메타데이터 파일을 참조하십시오](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## 역할 기반 액세스 제어(RBAC) {#rbac}

볼 수 있는 보고서 유형은 할당된 [!UICONTROL RBAC] 그룹에 따라 다릅니다. 자세한 [내용은](../../../features/administration/administration-overview.md) 관리 [및](../../../features/administration/administration-overview.md#create-group) 그룹만들기를 참조하십시오.

[!UICONTROL RBAC] 그룹에는 [!UICONTROL Audience Optimization] 보고서를 보려면 일부 데이터 소스가 설정되어 있어야 합니다. 컨설턴트가 이러한 데이터 소스를 자동으로 설정할 [!DNL Audience Manager] 것입니다. 각 [!UICONTROL RBAC] 사용자 그룹의 데이터 소스가 많을수록 해당 그룹 구성원이 액세스할 수 있는 데이터가 많아집니다. 컨설턴트는 최소 다음 데이터 소스 중 하나를 설정합니다.

* 광고주 데이터 소스
* 브랜드 데이터 소스
* 플랫폼 데이터 소스

둘 이상의 [!UICONTROL RBAC] 사용자 그룹에 속한 사용자는 각 그룹의 보기 사이를 전환할 수 있습니다. 선택한 그룹을 존중하도록 표시된 데이터가 업데이트됩니다. 회사가 사용하지 않는 [!UICONTROL RBAC]경우 모든 사용자는 관리자 권한과 모든 데이터 소스(전환 그룹)에 대한 액세스 권한을 갖습니다.

## 전환 그룹 {#conversion-groups}

보고서에서 [!UICONTROL Audience Optimization] 는 **[!UICONTROL Conversion Groups]** 하나 이상의 전환 트레이트가 포함된 데이터 소스와 비슷합니다. 하나 이상의 전환 특성이 포함되지 않은 데이터 소스는 [!UICONTROL Audience Optimization] 보고서에 나타나지 않습니다. 보고된 전환 트레이트 보고서에서 전환 그룹의 전환 트레이트를 볼 [수](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) 있습니다.
