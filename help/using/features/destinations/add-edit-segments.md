---
description: 데이터 내보내기 레이블은 데이터 소스에 설정한 내보내기 컨트롤과 함께 작동합니다. 데이터 내보내기 레이블 을 사용하면 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 못합니다. 여러 내보내기 레이블을 새 또는 기존 쿠키 또는 URL 대상에 설정할 수 있습니다.
seo-description: 데이터 내보내기 레이블은 데이터 소스에 설정한 내보내기 컨트롤과 함께 작동합니다. 데이터 내보내기 레이블 을 사용하면 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 못합니다. 여러 내보내기 레이블을 새 또는 기존 쿠키 또는 URL 대상에 설정할 수 있습니다.
seo-title: 서버 간 대상에 대한 세그먼트 추가 또는 편집
solution: Audience Manager
title: 서버 간 대상에 대한 세그먼트 추가 또는 편집
feature: 대상 기본 사항
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 8%

---

# 서버 간 대상에 대한 세그먼트 추가 또는 편집 {#add-edit-segments}

서버 간([!DNL S2S]) 대상에 대해서만 세그먼트를 추가하거나 편집할 수 있습니다. [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md) 를 사용하여 [!DNL S2S] 대상을 만들 수 없습니다. 컨설턴트에게 [!DNL S2S] 대상을 설정합니다. 다음 지침에 따라 [!DNL S2S] 대상에 대한 세그먼트를 추가하거나 편집합니다.

<!-- destination-s2s-edit.xml -->

[!DNL S2S] 대상에 대한 세그먼트 매핑을 추가하거나 편집하려면:

1. **[!UICONTROL Audience Data > Destinations]**(으)로 이동합니다. **통합 플랫폼 > 장치 기반**&#x200B;을 선택하고 작업할 [!DNL S2S] 대상을 찾습니다.
2. [!UICONTROL Action] 열에서 연필 아이콘을 클릭하여 대상을 편집합니다.
   * **[!UICONTROL Search and Add Segments]** 상자에서 세그먼트 이름을 입력하거나 **[!UICONTROL Browse All Segments]** 를 클릭하여 사용 가능한 세그먼트 목록을 찾습니다.
   * 사용할 세그먼트를 찾으면 **[!UICONTROL Add Selected Segments]** 을 클릭합니다. 세그먼트를 추가하면 [!UICONTROL Edit Mapping] 창이 열립니다.
   *  [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**:이 대상에서  [사용하는 키 값](../../features/destinations/key-value-pairs.md) 에 대한 값을 설정합니다.
      * **[!UICONTROL Start Date]** 및  **[!UICONTROL End Date]**:대상에 대한 시작 및 종료 날짜를 선택합니다. 종료 날짜가 비어 있으면 대상이 만료되지 않습니다.
3. **[!UICONTROL Save]** 을 클릭한 다음 **[!UICONTROL Done]** 를 클릭합니다.
