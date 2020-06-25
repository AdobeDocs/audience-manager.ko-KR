---
description: 이 지도에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 간에 데이터가 어떻게 유입되는지 시각적으로 나타냅니다.
seo-description: 이 지도에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 간에 데이터가 어떻게 유입되는지 시각적으로 나타냅니다.
seo-title: Platform 아키텍처 데이터 흐름 맵
solution: Audience Manager
title: Platform 아키텍처 데이터 흐름 맵
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 2%

---


# 플랫폼 아키텍처: 데이터 흐름 맵{#platform-architecture-data-flow-map}

이 지도에는 주요 Audience Manager 시스템이 포함되어 있습니다. Audience Manager 구성 요소 간에 데이터가 어떻게 유입되는지 시각적으로 나타냅니다.

## How to read this map {#compmap}

<!-- 

c_compmap.xml

 -->

맵에서 회색 상자는 시스템을 [!DNL Audience Manager] 포함합니다. 일부 구성 요소는 완전히 내부 구성 요소이고 다른 구성 요소는 외부 [!DNL Audience Manager] 와 바깥의 경계 상에 위치합니다. 고객인 경우 내부 구성 요소는 [!DNL Audience Manager] 투명하거나 액세스할 수 없는 경우가 많습니다. 그러나 경우에 따라 사용자 인터페이스 또는 데이터 통합을 통해 이러한 시스템과 연계할 수 있습니다. 최신 시스템은 데이터와 외부 간에 데이터를 수집하고 전송할 수 [!DNL Audience Manager] 있습니다.

색상은 들어오는 데이터의 유형을 정의합니다 [!DNL Audience Manager]. 녹색은 클라이언트 데이터, 파란색은 고객 데이터(사이트를 방문한 사람)이고 주황색은 보고에 사용되는 데이터입니다.

시스템 및 요약은 데이터 작업 [,](../../reference/system-components/components-data-action.md)수집 [,](../../reference/system-components/components-data-collection.md)처리 [및](../../reference/system-components/components-data-processing.md)태그 관리 섹션 설명 [을 참조하십시오](../../reference/system-components/components-tag-management.md) .

![](assets/flowmap.png)

