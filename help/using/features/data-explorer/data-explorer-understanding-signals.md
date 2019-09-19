---
description: 신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 온라인 속성에서 사용자 상호 작용 또는 사용자 활동을 나타내며 Audience Manager로 전달되어 트레이트 규칙에 사용됩니다.
seo-description: 신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 온라인 속성에서 사용자 상호 작용 또는 사용자 활동을 나타내며 Audience Manager로 전달되어 트레이트 규칙에 사용됩니다.
seo-title: 신호 이해
title: 신호 이해
uuid: 04a0554e-95 파섹
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 신호 이해

신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 온라인 속성에서 사용자 상호 작용 또는 사용자 활동을 나타내며 Audience Manager로 전달되어 트레이트 규칙에 사용됩니다.

[!DNL Audience Manager] 는 키-값 쌍을 사용하여 신호를 나타냅니다. 예를 들어, 다음 신호는 방문자가 전자 제품을 포함하는 웹 페이지에 도달했음을 나타낼 수 있습니다.

* `page = electronics`

신호 [대시보드에는](../../features/data-explorer/data-explorer-signals-dashboard.md) 새 트레이트를 만드는 데 사용할 수 있는 여러 유형의 신호 속성이 표시됩니다. 다음은 사용 가능한 신호 속성에 대한 자세한 보기입니다.

* *키-값 쌍은* 수신한 신호의 키-값 쌍을 보여줍니다 [!DNL Audience Manager].
* *신호 유형은* 각 신호의 카테고리를 설명합니다. 신호는 다음 카테고리 중 하나로 분류됩니다.
   * [실행 가능한 로그 파일](/help/using/integration/media-data-integration/actionable-log-files.md):미디어 성능 로그 파일에서 수신되는 실시간 신호
   * [!DNL Adobe Analytics]:귀하의 [!DNL Adobe Analytics] 계정에서 받은 실시간 신호
   * 일반 온라인 데이터:고객 활동에 의해 생성된 실시간 데이터로서 실행 가능한 로그 파일 및 [!DNL Adobe Analytics]파일에 포함되지 않은 데이터
   * 온보드 레코드:데이터 일괄 전송을 통해 수신된 데이터
* *신호* 소스는 신호 유형에 따라 다릅니다.
   * 온보드 신호의 경우 신호 소스는 데이터 소스 이름입니다.
   * 발신 신호의 경우 데이터 [!DNL Adobe Analytics]소스는 항상 보고서 세트가 됩니다.
   * 실행 가능한 로그 파일과 일반 온라인 데이터의 경우 신호 소스 정보가 표시되지 않습니다.
* *총* [!DNL Audience Manager] 수는 지난 7일 동안 실시간 신호가 수신된 총 횟수를 보여줍니다.
* *트레이트에 포함된* 트레이트는 신호가 트레이트의 일부인지 여부를 표시합니다. 화살표를 클릭하여 해당 신호가 포함된 트레이트를 봅니다. 트레이트에 속하지 않는 신호의 경우 열 값이 [!UICONTROL Create Onboarded Trait] 또는 으로 [!UICONTROL Create Rule-Based Trait]변경됩니다.

## 신호 데이터 새로 고침 빈도

Audience Manager가 매일 처리하는 많은 양의 데이터로 인해 신호 유형에 따라 [!UICONTROL Data Explorer] 정해진 시간 간격으로 표시된 신호 데이터를 새로 고칩니다.

* 실시간 신호 데이터(실행 가능한 로그 파일, [!DNL Adobe Analytics] 데이터 및 일반 온라인 데이터)는 4-6시간마다 새로 고쳐집니다.
* 온보드 신호 데이터는 24시간마다 새로 고쳐집니다.

## 관련 개념

[신호, 트레이트 및 세그먼트](/help/using/reference/signal-trait-segment.md)