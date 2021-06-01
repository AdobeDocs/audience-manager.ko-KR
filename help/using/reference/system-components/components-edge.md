---
description: Audience Manager은 분산형 에지 컴퓨팅 토폴로지를 사용하여 외부 소스에서 Adobe 시스템에 부여된 요구를 충족합니다.
seo-description: Audience Manager은 분산형 에지 컴퓨팅 토폴로지를 사용하여 외부 소스에서 Adobe 시스템에 부여된 요구를 충족합니다.
seo-title: 에지 데이터 센터 이해
solution: Audience Manager
title: 에지 데이터 센터 이해
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: 시스템 구성 요소
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# 에지 데이터 센터 이해{#understanding-the-edge-data-center}

Audience Manager은 분산형 에지 컴퓨팅 토폴로지를 사용하여 외부 소스에서 Adobe 시스템에 부여된 요구를 충족합니다.

## Edge 데이터 센터 기본 사항 {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

에지 컴퓨팅은 &quot;에지&quot; 자체가 글로벌 경계이므로 확산, 인터넷 전체 수요에 응답하여 성능을 향상시킵니다. 즉, [!DNL Audience Manager]은(는) 수요 출처에 가장 가까운 처리를 동적으로 배치하고 가능한 가장 짧은 경로로 데이터를 반환합니다. 에지 컴퓨팅은 사이트 성능을 유지하는 데 도움이 되며, 따라서 웹 사이트에서 사용자 경험을 유지합니다. 에지 데이터 센터는 데이터를 [!DNL Audience Manager] 내부로 이동하는 주요 게이트웨이입니다.

[!DNL Audience Manager] 에지 데이터 센터는 다음과 같습니다.

* **핵심 서버:** 기본  [!DNL Audience Manager] 시스템입니다. Edge Server에 데이터를 업데이트하고 제공합니다.

* **Edge Server:**  일반적으로 애플리케이션 및/또는 웹 서버입니다. 그들은 [!DNL Audience Manager] 과 인터넷 사이의 경계에 앉아 있다. [!DNL DCS] 또는 Akamai 시스템과 같은 Edge Server는 일반적으로 [!DNL Audience Manager] 내부로 들어오고 나가는 데이터 및 요청을 처리합니다.

* **로드 밸런서:** 인터넷 애플리케이션에 내재된 요철 컴퓨팅/처리 수요를 관리합니다. 이러한 밸런서는 서버 클러스터가 오버로드되는 반면 다른 서버는 유휴 상태로 남아 있는 것을 방지합니다.

다음 다이어그램은 Audience Manager 에지 데이터 센터 환경을 보여 줍니다.

![](assets/edge_data_center.png)

## 지리적 배포 및 로드 밸런싱 {#geo-dist-balance}

[데이터 수집 구성 요소](../../reference/system-components/components-data-collection.md)에서 [!DNL DCS] 섹션을 참조하십시오.
