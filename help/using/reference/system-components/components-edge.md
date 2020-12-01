---
description: Audience Manager은 분산 에지 컴퓨팅 토폴로지를 사용하여 외부 소스에서 시스템에 부여된 요구 사항을 충족합니다.
seo-description: Audience Manager은 분산 에지 컴퓨팅 토폴로지를 사용하여 외부 소스에서 시스템에 부여된 요구 사항을 충족합니다.
seo-title: 에지 데이터 센터 이해
solution: Audience Manager
title: 에지 데이터 센터 이해
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# 에지 데이터 센터 이해{#understanding-the-edge-data-center}

Audience Manager은 분산 에지 컴퓨팅 토폴로지를 사용하여 외부 소스에서 시스템에 부여된 요구 사항을 충족합니다.

## Edge 데이터 센터 기본 사항 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

에지 컴퓨팅은 &quot;에지&quot; 자체가 글로벌 경계이므로 인터넷 전반의 수요 확산에 대응하여 향상된 성능을 제공합니다. 즉, [!DNL Audience Manager]은(는) 요청 소스에 가장 가까운 처리를 동적으로 배치하고 데이터를 가능한 가장 짧은 경로로 반환합니다. Edge Computing을 사용하면 사이트 성능을 유지할 수 있으며 웹 사이트에서의 사용자 경험을 그대로 유지할 수 있습니다. Edge 데이터 센터는 [!DNL Audience Manager] 안팎으로 데이터를 이동하는 주요 게이트웨이입니다.

[!DNL Audience Manager] 에지 데이터 센터에 다음이 포함됩니다.

* **핵심 서버:** 이것이 주  [!DNL Audience Manager] 시스템입니다. Edge Server에 데이터를 업데이트하고 제공합니다.

* **Edge Server:** 일반적으로 애플리케이션 및/또는 웹 서버입니다. 그들은 [!DNL Audience Manager]과 인터넷 사이에 있다. [!DNL DCS] 또는 Akamai 시스템과 같은 Edge Server는 일반적으로 [!DNL Audience Manager] 안팎으로 흐르는 데이터와 요청을 처리합니다.

* **로드 밸런서:** 인터넷 애플리케이션 고유의 고르지 않은 컴퓨팅/처리 요구를 관리합니다. 이러한 밸런서는 서버 클러스터가 과부하가 되는 반면 다른 밸런서는 유휴 상태인 경우를 방지합니다.

다음 다이어그램은 Audience Manager 에지 데이터 센터 환경을 보여줍니다.

![](assets/edge_data_center.png)

## 지리적 배포 및 부하 균형 조정 {#geo-dist-balance}

[데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)의 [!DNL DCS] 섹션을 참조하십시오.
