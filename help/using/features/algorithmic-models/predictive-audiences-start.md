---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-title: 예측 대상자 관리
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 71e129a39cf85d5f07979ede8f3aa862f93b6512
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 8%

---


# Predictive Audiences 시작 {#predictive-audiences-getting-started}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 권고사항이다. 법률 자문을 위해 법률 자문을 구할 수 있습니다.

## 예측 대상 모델 만들기 {#create-predictive-audiences}

모델을 만들기 전에 트레이트와 세그먼트를 할당할 자사 데이터 소스 [!UICONTROL Predictive Audiences] [!UICONTROL Predictive Audiences] 를 결정해야 합니다. 기존 자사 데이터 소스를 사용하거나 새 데이터 소스를 만들 수 있습니다. 새 [퍼스트 파티 데이터 소스를 만드는 방법에 대한 자세한 내용은 데이터 소스](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) 관리를 참조하십시오.

사용할 데이터 소스를 알게 되면 아래 단계를 따르십시오.

1. > **[!UICONTROL Audience Data]** 로 **[!UICONTROL Models]**&#x200B;이동합니다.
1. 섹션에서 를 [!UICONTROL Predictive Audiences] 클릭합니다 **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 그런 다음 대상을 분류할 개인성을 정의합니다. 이를 위해서는 트레이트 또는 세그먼트를 선택하여 개인화를 만들 수 있습니다. 화면 왼쪽 상단 모서리의 [!UICONTROL Traits] 및 [!UICONTROL Segments] 탭을 사용하여 트레이트와 세그먼트 카탈로그 간을 전환할 수 있습니다. 개인으로 사용할 트레이트 또는 세그먼트를 식별했으면 열에서 해당 **[!UICONTROL Add]** 아이콘을 [!UICONTROL Action] 클릭합니다.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >기준선 성향에 대해 최소한 두 개의 특성이나 두 개의 세그먼트를 선택해야 합니다. 트레이트와 세그먼트 조합을 사용할 수 없습니다.
1. 개인 **[!UICONTROL Next]** 을 정의한 후 을 클릭합니다.
1. 그런 다음 이 대상에 대한 자사 특성 또는 세그먼트를 선택하여 분류할 자사 대상자를 선택합니다. 화면의 왼쪽 위 모서리에 있는 [!UICONTROL Traits] 및 [!UICONTROL Segments] 탭을 사용하여 트레이트와 세그먼트 카탈로그 간을 전환합니다. 대상으로 사용할 자사 특성 또는 세그먼트를 선택하여 모델에 추가합니다.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. 대상자를 선택한 **[!UICONTROL Next]** 후 을 클릭합니다.
1. 모델 세부 사항을 입력합니다.
   * **[!UICONTROL Model Name]**: 나중에 식별할 수 있도록 모델에 대해 설명형 이름을 입력합니다. 모델에서 생성된 세그먼트의 이름은 모델 이름으로 시작됩니다.
   * **[!UICONTROL Description]**: 사용 사례를 식별하는 데 도움이 되는 모델의 설명을 입력합니다.
   * **[!UICONTROL Data Source]**: 이 모델의 세그먼트를 할당할 자사 데이터 소스 [!UICONTROL Predictive Audiences] 를 선택합니다.
   * **[!UICONTROL Profile Merge Rule]**: 이 모델 [!UICONTROL Profile Merge Rule] 에 의해 생성된 모든 예측 [!UICONTROL segments] 에 대해 지정할 항목을 선택합니다. 선택한 대상 대상이 [!UICONTROL segment]같은 경우 대상 대상자와 동일한 대상 [!UICONTROL Profile Merge Rule] 을 선택하는 것이 좋습니다.
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. 클릭 **[!UICONTROL Save]**.

## 예측 대상자 편집 {#edit-predictive-audiences}

Audience Manager은 기존 [!UICONTROL Predictive Audiences] 모델 편집을 지원하지 않습니다. 모델의 구성을 변경하려면 새 모델을 생성해야 합니다. 10개 [!UICONTROL Predictive Audiences] 모델 한도에 도달하여 모델 중 하나를 편집해야 하는 경우 모델을 삭제하고 새 모델을 만들어야 합니다.

## 예측 대상 삭제 {#delete-predictive-audiences}

모델을 삭제하려면 [!UICONTROL Predictive Audiences] > **[!UICONTROL Audience Data]** 로 이동하여 삭제할 모델을 찾은 다음 **[!UICONTROL Models]****[!UICONTROL Delete]** 아이콘을 클릭합니다.
