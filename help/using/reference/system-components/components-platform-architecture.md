---
description: 이 지도에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 내, 외부 및 간 데이터 흐름 방식을 시각적으로 나타냅니다.
seo-description: 이 지도에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 내, 외부 및 간 데이터 흐름 방식을 시각적으로 나타냅니다.
seo-title: 플랫폼 아키텍처 데이터 흐름 맵
solution: Audience Manager
title: 플랫폼 아키텍처 데이터 흐름 맵
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: 시스템 구성 요소
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---

# 플랫폼 아키텍처: 데이터 흐름 맵{#platform-architecture-data-flow-map}

이 지도에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 내, 외부 및 간 데이터 흐름 방식을 시각적으로 나타냅니다.

## 이 지도를 읽는 방법 {#compmap}

<!-- 

c_compmap.xml

 -->

맵에서 회색 상자에는 [!DNL Audience Manager] 시스템이 포함됩니다. 일부 구성 요소는 완전히 내부적이고 다른 구성 요소는 [!DNL Audience Manager] 과 외부 세계 사이의 경계에 있습니다. [!DNL Audience Manager] 고객으로서 내부 구성 요소는 종종 투명하거나 액세스할 수 없습니다. 그러나 경우에 따라 사용자 인터페이스 또는 데이터 통합을 통해 이러한 시스템과 참여할 수 있습니다. 상자 가장자리에 있는 시스템은 [!DNL Audience Manager] 과 외부 세계 간에 데이터를 수집하고 전송합니다.

색상은 [!DNL Audience Manager]에서 들어오고 나가는 데이터 유형을 정의합니다. 녹색은 클라이언트 데이터이고, 파란색은 고객 데이터(사이트를 방문하는 사람)이고, 주황색은 보고에 사용되는 데이터입니다.

시스템 설명 및 요약은 데이터 [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [처리](../../reference/system-components/components-data-processing.md) 및 [태그 관리](../../reference/system-components/components-tag-management.md) 섹션을 참조하십시오.

![](assets/flowmap.png)
