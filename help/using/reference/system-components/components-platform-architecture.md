---
description: 이 맵에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 간에 데이터가 이동되는 방식을 시각적으로 나타냅니다.
seo-description: 이 맵에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 간에 데이터가 이동되는 방식을 시각적으로 나타냅니다.
seo-title: 플랫폼 아키텍처 데이터 흐름 맵
solution: Audience Manager
title: 플랫폼 아키텍처 데이터 흐름 맵
uuid: D 845 AF 1 D-F 448-4 F 4 C -948 E-B 2 C 89 F 125086
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Platform Architecture: Data Flow Map{#platform-architecture-data-flow-map}

이 맵에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 간에 데이터가 이동되는 방식을 시각적으로 나타냅니다.

## How to read this map {#compmap}

<!-- 

c_compmap.xml

 -->

In the map, the gray box contains [!DNL Audience Manager] systems. Some components are completely internal and others sit on the boundary between [!DNL Audience Manager] and the outside world. [!DNL Audience Manager] 고객으로서 내부 구성 요소는 투명하거나 액세스할 수 없는 경우가 많습니다. 그러나 경우에 따라 사용자는 사용자 인터페이스 또는 데이터 통합을 통해 이러한 시스템과 상호 작용할 수 있습니다. Systems on the edge of the box collect and send data between [!DNL Audience Manager] and the outside world.

Colors define the type of data that flows in and out of [!DNL Audience Manager]. 녹색은 클라이언트 데이터이고 파란색은 고객 데이터 (사이트를 방문하는 사람) 이고 주황색은 보고에 사용되는 데이터입니다.

For system descriptions and summaries see the data [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [processing](../../reference/system-components/components-data-processing.md), and [tag management](../../reference/system-components/components-tag-management.md) sections.

![](assets/flowmap.png)

