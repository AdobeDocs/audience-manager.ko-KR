---
description: Audience Manager은 분산된 에지 컴퓨팅 토폴로지를 사용하여 외부 소스로 시스템에 배치된 요구 사항을 충족합니다.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: 에지 데이터 센터 이해
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# 에지 데이터 센터 이해{#understanding-the-edge-data-center}

Audience Manager은 분산된 에지 컴퓨팅 토폴로지를 사용하여 외부 소스로 시스템에 배치된 요구 사항을 충족합니다.

## Edge 데이터 센터 기본 사항 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

에지 컴퓨팅은 &quot;에지&quot; 자체가 글로벌 경계이기 때문에 인터넷 전반에 걸친 광범위한 수요에 대응하여 향상된 성능을 제공합니다. 이것은 다음을 의미합니다. [!DNL Audience Manager] 동적으로 수요 출처에 가장 가까운 처리를 배치하고 가능한 가장 짧은 경로로 데이터를 반환합니다. 에지 컴퓨팅은 사이트 성능을 유지하는 데 도움이 되며, 결과적으로 웹 사이트의 사용자 경험을 유지합니다. 에지 데이터 센터는 데이터 입출력을 위한 핵심 게이트웨이입니다. [!DNL Audience Manager].

다음 [!DNL Audience Manager] 에지 데이터 센터에는 다음이 포함됩니다.

* **핵심 서버:** 이것이 바로 메인 [!DNL Audience Manager] 시스템. Edge Server를 업데이트하고 데이터를 제공합니다.

* **에지 서버:** 일반적으로 이러한 서버는 애플리케이션 및/또는 웹 서버입니다. 그들은 그 사이의 경계에 앉아 있다 [!DNL Audience Manager] 그리고 인터넷도. Edge Server(예: [!DNL DCS] 또는 Akamai 시스템은 일반적으로 들어오고 나가는 데이터 및 요청을 처리합니다 [!DNL Audience Manager].

* **로드 밸런서:** 인터넷 응용 프로그램에 내재된 고르지 못한 컴퓨팅/처리 요구를 관리합니다. 이러한 밸런서는 다른 서버가 유휴 상태로 있는 동안 서버 클러스터가 오버로드되는 것을 방지합니다.

다음 다이어그램은 Audience Manager 에지 데이터 센터 환경을 보여 줍니다.

![](assets/edge_data_center.png)

## 지리적 분포 및 로드 밸런싱 {#geo-dist-balance}

다음을 참조하십시오. [!DNL DCS] 의 섹션 [데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md).
