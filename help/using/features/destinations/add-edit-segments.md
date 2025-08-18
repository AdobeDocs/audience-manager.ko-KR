---
description: 데이터 내보내기 레이블은 데이터 소스에 설정한 내보내기 컨트롤에서 작동합니다. 데이터 내보내기 레이블을 사용하면 제한된 트레이트를 세그먼트에 추가할 수 없으며 세그먼트 데이터를 대상으로 전송할 수 없습니다. 여러 내보내기 레이블을 신규 또는 기존 쿠키 또는 URL 대상으로 설정할 수 있습니다.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: 서버 간 대상에 대한 세그먼트 추가 또는 편집
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# 서버 간 대상에 대한 세그먼트 추가 또는 편집 {#add-edit-segments}

서버 간([!DNL S2S]) 대상에 대한 세그먼트만 추가하거나 편집할 수 있습니다. [!DNL S2S]을(를) 사용하여 [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md) 대상을 만들 수 없습니다. [!DNL S2S] 대상을 설정하려면 컨설턴트에게 문의하십시오. [!DNL S2S] 대상에 대한 세그먼트를 추가하거나 편집하려면 다음 지침을 따르십시오.

<!-- destination-s2s-edit.xml -->

[!DNL S2S] 대상에 대한 세그먼트 매핑을 추가하거나 편집하려면:

1. **[!UICONTROL Audience Data > Destinations]**(으)로 이동합니다. **통합 플랫폼 > 장치 기반**&#x200B;을(를) 선택하고 작업할 [!DNL S2S] 대상을 찾습니다.
2. [!UICONTROL Action] 열에서 연필 아이콘을 클릭하여 대상을 편집합니다.
   * **[!UICONTROL Search and Add Segments]** 상자에서 세그먼트 이름을 입력하거나 **[!UICONTROL Browse All Segments]**&#x200B;을(를) 클릭하여 사용 가능한 세그먼트 목록을 찾아봅니다.
   * 사용할 세그먼트를 찾으면 **[!UICONTROL Add Selected Segments]**&#x200B;을(를) 클릭합니다. 세그먼트를 추가하면 [!UICONTROL Edit Mapping] 창이 열립니다.
   * [!UICONTROL Edit Mapping]에서:
      * **[!UICONTROL Mappings]**: 이 대상에서 사용하는 [키-값 쌍](../../features/destinations/key-value-pairs.md)의 값을 설정하십시오.
      * **[!UICONTROL Start Date]** 및 **[!UICONTROL End Date]**: 대상의 시작 및 종료 날짜를 선택하십시오. 종료 날짜가 비어 있으면 대상이 만료되지 않습니다.
3. **[!UICONTROL Save]**&#x200B;을(를) 클릭한 다음 **[!UICONTROL Done]**&#x200B;을(를) 클릭합니다.
