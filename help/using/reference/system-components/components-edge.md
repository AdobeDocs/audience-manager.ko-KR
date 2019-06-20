---
description: Audience Manager는 외부 소스에서 Adobe 시스템에 배치된 요구 사항을 충족하기 위해 분산 컴퓨팅 토폴로지를 사용합니다.
seo-description: Audience Manager는 외부 소스에서 Adobe 시스템에 배치된 요구 사항을 충족하기 위해 분산 컴퓨팅 토폴로지를 사용합니다.
seo-title: Edge 데이터 센터 이해
solution: Audience Manager
title: Edge 데이터 센터 이해
uuid: 4177 E 666-99 F 4-453 D -94 DD -058 C 6182 C 8 D 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

Audience Manager는 외부 소스에서 Adobe 시스템에 배치된 요구 사항을 충족하기 위해 분산 컴퓨팅 토폴로지를 사용합니다.

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge Computing는 &quot;에지 (edge)&quot; 자체가 글로벌 경계이므로 인터넷 보급률에 대한 향상된 성능을 제공합니다. This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. Edge Computing를 사용하면 사이트 성능을 유지할 수 있으므로 웹 사이트에서 사용자 경험을 그대로 유지할 수 있습니다. The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

[!DNL Audience Manager] Edge 데이터 센터에는 다음이 포함됩니다.

* **코어 서버:** 기본 [!DNL Audience Manager] 시스템입니다. Edge Server에 데이터를 업데이트하고 제공합니다.

* **Edge Server:** 일반적으로 응용 프로그램 및/또는 웹 서버입니다. [!DNL Audience Manager] 인터넷과 인터넷 경계에 앉아 있습니다. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **로드 밸런서:** 인터넷 애플리케이션에서 발생하는 불규칙한 컴퓨팅/처리 요구 사항을 관리합니다. 이러한 밸런서는 서버 클러스터가 오버로드되는 것을 방지하고 다른 서버는 유휴 상태를 유지합니다.

다음 다이어그램은 Audience Manager Edge 데이터 센터 환경을 보여줍니다.

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
