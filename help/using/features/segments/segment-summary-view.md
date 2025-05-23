---
description: 세그먼트 요약 페이지에는 이름, 세그먼트의 트레이트, 규칙, 성능 데이터 및 대상 매핑 정보와 같은 세부 정보가 표시됩니다.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: 세그먼트 세부 정보 페이지
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: id 유형 분류, id 분류, 대상 id 보고, 교차 장치, 교차 장치 ID, 장치 ID
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# 세그먼트 세부 정보 페이지 {#segment-summary-view}

개별 세그먼트에 대한 세부 정보 페이지에서는 세그먼트 이름, ID, 성능 지표, 세그먼트를 정의하는 규칙 및 대상 매핑과 같은 세그먼트 세부 정보에 대한 개요를 제공합니다. 이러한 세부 정보를 보려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]**(으)로 이동하여 작업할 세그먼트 이름을 클릭합니다.

## 세그먼트 관리 도구 {#segment-management-tools}

세그먼트 세부 정보 페이지의 상단에는 세그먼트를 관리하는 데 사용할 수 있는 도구가 호스팅됩니다.

1. **[!UICONTROL Add New]**: 이 옵션을 사용하여 [!UICONTROL Segment Builder]을(를) 활성화하고 새 세그먼트를 만드십시오.
2. **[!UICONTROL Edit]**: 현재 세그먼트의 구성을 변경하려면 이 옵션을 사용합니다.
3. **[!UICONTROL Duplicate]**: 현재 세그먼트의 복사본을 만들려면 이 옵션을 사용합니다.
4. **[!UICONTROL Delete]**: 이 옵션을 사용하여 Audience Manager 계정에서 현재 세그먼트를 제거합니다.
5. **[!UICONTROL Marketplace Recommendations]**: 이 옵션을 사용하여 구독하지 않은 [!UICONTROL Audience Marketplace] 데이터 피드에서 보고 있는 세그먼트와 유사한 세그먼트를 찾습니다. 마켓플레이스를 탐색하고 유사한 세그먼트를 찾는 방법에 대해 알아보려면 [데이터 구매자용 Audience Marketplace](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)을 참조하세요.

![basic-segment-information](assets/basic-segment-information.png)

## 세그먼트 정보 {#basics}

세그먼트 관리 도구 아래에서 다음 세그먼트 정보를 찾을 수 있습니다.

1. **[!UICONTROL Basic Information]:** 세그먼트를 만들 때 지정된 필수 및 선택적 세부 정보를 표시합니다. 이러한 필드의 의미에 대한 자세한 개요는 [세그먼트 빌더](segment-builder.md)를 참조하십시오.
2. **[!UICONTROL Segment Graph]:** 고정된 1, 7, 14, 30, 60 및 90일 간격에 대한 성능 데이터를 그래픽으로 표시합니다. [개별 문서](../../features/segments/segment-builder-data.md)의 세그먼트 모집단 수에 대해 설명합니다.

   ![segments-graph](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown]:** 보고서는 세그먼트를 사용할 수 있는 장치([!UICONTROL Total Segment Population])에 연결된 교차 장치 ID 및/또는 외부 장치 그래프 ID의 수를 계산하여 세그먼트를 사용할 수 있는 사람 또는 가구 수를 표시합니다. 이 보고서에 표시된 교차 장치 ID 및 외부 장치 그래프 ID는 세그먼트가 사용 중인 프로필 병합 규칙과 프로필을 병합하는 데 사용됩니다. 이 보고서는 세그먼트가 사용 중인 프로필 병합 규칙에서 교차 장치 데이터 소스 또는 외부 장치 그래프를 선택한 경우에만 표시됩니다.

   ![segments-graph](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager은 세그먼트에 적합한 교차 장치 ID가 있는 경우에만 [!UICONTROL Identity Type Breakdown] 보고서를 표시합니다.

   [!UICONTROL Identity Type Breakdown]에 대한 개요를 보려면 아래 비디오를 시청하십시오.
   >[!VIDEO](https://video.tv.adobe.com/v/32080?captions=kor)

4. **[!UICONTROL Segment Rules]:**&#x200B;은(는) 선별 규칙과 함께 세그먼트의 특성을 나열합니다.
5. **[!UICONTROL Destination Mappings]:** 세그먼트에 대한 대상 매핑을 나열합니다.
6. 세그먼트를 만들고, 편집하고, 복제하고, 삭제할 수 있는 **[!UICONTROL Management Tools]:** 컨트롤입니다.
