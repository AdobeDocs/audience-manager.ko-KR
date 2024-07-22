---
description: 신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 이는 온라인 속성에 대한 사용자 상호 작용 또는 사용자 활동을 나타내며 트레이트 규칙에 사용할 Audience Manager에 전달됩니다.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: 신호 이해
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# 신호 이해

신호는 Audience Manager 내에서 가장 작은 정보 단위입니다. 이 매개 변수는 온라인 속성에서의 사용자 상호 작용 또는 사용자 활동을 나타내며, 트레이트 규칙에 사용할 Audience Manager에 전달됩니다.

[!DNL Audience Manager]은(는) 키-값 쌍을 사용하여 신호를 나타냅니다. 예를 들어, 다음 신호는 방문자가 전자 장치가 포함된 웹 페이지에 도달했음을 나타낼 수 있습니다.

* `page = electronics`

[신호 대시보드](../../features/data-explorer/data-explorer-signals-dashboard.md)에는 새 특성을 만드는 데 사용할 수 있는 여러 유형의 신호 특성이 표시됩니다. 다음은 사용 가능한 신호 속성에 대한 세부 보기입니다.

* *키-값 쌍*&#x200B;은(는) [!DNL Audience Manager]이(가) 받은 신호의 키-값 쌍을 표시합니다.
* *신호 형식*&#x200B;은(는) 각 신호의 범주를 설명합니다. 신호는 다음 범주 중 하나에 속합니다.
   * [실행 가능한 로그 파일](/help/using/integration/media-data-integration/actionable-log-files.md): 미디어 성능 로그 파일에서 수신한 실시간 신호입니다.
   * [!DNL Adobe Analytics]: [!DNL Adobe Analytics] 계정에서 받은 실시간 신호;
   * 일반 온라인 데이터: 대상 활동으로 생성된 실시간 데이터이며 실행 가능한 로그 파일 및 [!DNL Adobe Analytics]에 포함되지 않습니다.
   * 온보딩된 레코드: 배치 데이터 전송을 통해 받은 데이터.
* *신호 Source*&#x200B;은(는) 신호 유형에 따라 다릅니다.
   * 온보딩된 신호의 경우 신호 소스는 데이터 소스 이름입니다.
   * [!DNL Adobe Analytics]에서 보낸 신호의 경우 데이터 원본은 항상 보고서 세트입니다.
   * 실행 가능한 로그 파일 및 일반 온라인 데이터의 경우 신호 소스 정보가 표시되지 않습니다.
* *총 개수*&#x200B;는 지난 7일 동안 [!DNL Audience Manager]에서 실시간 신호를 받은 총 횟수를 보여줍니다.
* *트레이트에 포함됨*&#x200B;은(는) 신호가 어떤 트레이트에 속하는지 여부를 보여 줍니다. 해당 신호를 포함하는 트레이트를 보려면 화살표를 클릭합니다. 어떤 특성에도 속하지 않는 신호의 경우 열 값이 [!UICONTROL Create Onboarded Trait] 또는 [!UICONTROL Create Rule-Based Trait](으)로 변경됩니다.

## 신호 데이터 새로 고침 빈도

Audience Manager이 매일 처리하는 대량의 데이터로 인해 [!UICONTROL Data Explorer]은(는) 신호 유형에 따라 고정된 시간 간격으로 표시된 신호 데이터를 새로 고칩니다.

* 실시간 신호 데이터(실행 가능한 로그 파일, [!DNL Adobe Analytics] 데이터 및 일반 온라인 데이터)는 4~6시간마다 새로 고쳐집니다.
* 온보딩된 신호 데이터는 24시간마다 새로 고쳐집니다.

## 관련 개념

[신호, 트레이트 및 세그먼트](/help/using/reference/signal-trait-segment.md)
