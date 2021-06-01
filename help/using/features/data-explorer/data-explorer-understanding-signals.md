---
description: 신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 이들은 온라인 속성에서 사용자 상호 작용이나 사용자 활동을 나타내며, 트레이트 규칙에 사용할 Audience Manager으로 전달됩니다.
seo-description: 신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 이들은 온라인 속성에서 사용자 상호 작용이나 사용자 활동을 나타내며, 트레이트 규칙에 사용할 Audience Manager으로 전달됩니다.
seo-title: 신호 이해
title: 신호 이해
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: 데이터 탐색기
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 3%

---

# 신호 이해

신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 이들은 온라인 속성에서 사용자 상호 작용이나 사용자 활동을 나타내며, 트레이트 규칙에 사용할 Audience Manager으로 전달됩니다.

[!DNL Audience Manager] 는 키-값 쌍을 사용하여 신호를 나타냅니다. 예를 들어, 다음 신호는 방문자가 전자제품이 포함된 웹 페이지에 도달했음을 나타낼 수 있습니다.

* `page = electronics`

[신호 대시보드](../../features/data-explorer/data-explorer-signals-dashboard.md)는 새 트레이트를 만드는 데 사용할 수 있는 여러 유형의 신호 속성을 표시합니다. 다음은 사용 가능한 신호 속성에 대한 세부 보기입니다.

* *키-값 쌍* 은 에서 받은 신호의 키-값 쌍을 보여  [!DNL Audience Manager]줍니다.
* *신호* 유형은 각 신호의 카테고리를 설명합니다. 신호는 다음 카테고리 중 하나로 분류됩니다.
   * [실행 가능 로그 파일](/help/using/integration/media-data-integration/actionable-log-files.md):미디어 성능 로그 파일에서 수신한 실시간 신호
   * [!DNL Adobe Analytics]:계정에서 받은 실시간  [!DNL Adobe Analytics] 신호
   * 일반 온라인 데이터:대상 활동에서 생성되었으며 실행 가능한 로그 파일 및 [!DNL Adobe Analytics];
   * 온보드 레코드:배치 데이터 전송을 통해 받은 데이터.
* *신호* 소스는 신호 유형에 따라 달라집니다.
   * 온보딩된 신호의 경우 신호 소스는 데이터 소스 이름입니다.
   * [!DNL Adobe Analytics]에서 오는 신호의 경우 데이터 소스는 항상 보고서 세트가 됩니다.
   * 실행 가능한 로그 파일 및 일반 온라인 데이터의 경우 신호 소스 정보가 표시되지 않습니다.
* *총* 카운트는 지난 7일 동안 실시간 신호가 수신된 총  [!DNL Audience Manager] 횟수를 보여줍니다.
* *트레이트에* 포함된 신호는 트레이트의 일부인지 여부를 보여줍니다. 화살표를 클릭하여 해당 신호를 포함하는 트레이트를 확인합니다. 트레이트에 포함되지 않은 신호의 경우 열 값이 [!UICONTROL Create Onboarded Trait] 또는 [!UICONTROL Create Rule-Based Trait]로 변경됩니다.

## 신호 데이터 새로 고침 빈도

Audience Manager이 매일 처리하는 많은 양의 데이터로 인해, [!UICONTROL Data Explorer]은 신호 유형에 따라 고정된 시간 간격으로 표시된 신호 데이터를 새로 고칩니다.

* 실시간 신호 데이터(실행 가능한 로그 파일, [!DNL Adobe Analytics] 데이터 및 일반 온라인 데이터)는 4~6시간마다 새로 고쳐집니다.
* 온보딩된 신호 데이터는 24시간마다 새로 고쳐집니다.

## 관련 개념

[신호, 트레이트 및 세그먼트](/help/using/reference/signal-trait-segment.md)
