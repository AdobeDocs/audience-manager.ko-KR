---
description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-description: Predictive Audiences을 사용하면 데이터 과학을 사용하여 알 수 없는 대상을 실시간으로 개별 성향으로 분류할 수 있습니다.
seo-title: Predictive Audiences 관리
solution: Audience Manager
title: Predictive Audiences 시작
feature: 알고리즘 모델
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 7%

---

# Predictive Audiences 시작 {#predictive-audiences-getting-started}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떤 것도 법률적인 조언이 아닙니다. 법률 자문을 구하시려면 법률 자문을 구하십시오.

## 예측 대상 모델 만들기 {#create-predictive-audiences}

[!UICONTROL Predictive Audiences] 모델을 만들기 전에 [!UICONTROL Predictive Audiences] 트레이트 및 세그먼트를 할당할 자사 데이터 소스를 결정해야 합니다. 기존 자사 데이터 소스를 사용하거나 새 자사 데이터 소스를 만들 수 있습니다. 새 자사 데이터 소스를 만드는 방법에 대한 자세한 내용은 [데이터 소스 관리](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) 를 참조하십시오.

사용할 데이터 소스를 알고 있으면 아래 단계를 따르십시오.

1. **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**(으)로 이동합니다.
1. [!UICONTROL Predictive Audiences] 섹션에서 **[!UICONTROL Add New]** 를 클릭합니다.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. 다음으로 대상을 분류할 가상 사용자를 정의합니다. 트레이트나 세그먼트를 선택하여 가상 사용자를 생성할 수 있습니다. 트레이트와 세그먼트 카탈로그 간을 전환하려면 화면 왼쪽 위 모서리에 있는 [!UICONTROL Traits] 및 [!UICONTROL Segments] 탭을 사용하십시오. 개인으로 사용할 트레이트나 세그먼트를 식별했으면 [!UICONTROL Action] 열에서 해당 **[!UICONTROL Add]** 아이콘을 클릭합니다.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >기준선 성향에 대해 두 개 이상의 트레이트 또는 두 개의 세그먼트 중 최소 하나를 선택해야 합니다. 트레이트와 세그먼트의 조합은 사용할 수 없습니다.
1. 가상 사용자를 정의한 후 **[!UICONTROL Next]** 을 클릭합니다.
1. 그런 다음 이 대상에 대한 자사 트레이트 또는 세그먼트를 선택하여 분류할 자사 대상을 선택합니다. 화면 왼쪽 위 모서리에 있는 [!UICONTROL Traits] 및 [!UICONTROL Segments] 탭을 사용하여 트레이트와 세그먼트 카탈로그 간을 전환합니다. 대상으로 사용할 자사 트레이트 또는 세그먼트를 선택하여 모델에 추가합니다.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. 대상자를 선택한 후 **[!UICONTROL Next]** 을 클릭합니다.
1. 모델 세부 사항을 입력합니다.
   * **[!UICONTROL Model Name]**: 나중에 식별할 수 있도록 모델의 수사적 이름을 입력합니다. 모델에서 생성된 세그먼트의 이름은 모델 이름으로 시작됩니다.
   * **[!UICONTROL Description]**: 사용 사례를 식별하는 데 도움이 되는 모델에 대한 설명을 입력합니다.
   * **[!UICONTROL Data Source]**: 이 모델의 세그먼트를 할당할  [!UICONTROL Predictive Audiences] 자사 데이터 소스를 선택합니다.
   * **[!UICONTROL Profile Merge Rule]**: 이 모델 [!UICONTROL Profile Merge Rule] 에서 생성된 모든 예측 [!UICONTROL segments] 에 대해 지정할 을 선택합니다. 선택한 타겟 대상이 [!UICONTROL segment]인 경우 타겟 대상의 동일한 [!UICONTROL Profile Merge Rule]을 선택하는 것이 좋습니다.
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. 클릭 **[!UICONTROL Save]**.

## 예측 대상 모델 복제 및 편집 {#clone-predictive-audiences}

Audience Manager은 기존 [!UICONTROL Predictive Audiences] 모델 편집을 지원하지 않습니다. 모델의 구성을 변경하려면 기존 모델의 클론을 생성하고 편집할 수 있습니다. 다음을 수행할 수 있습니다.

1. **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**(으)로 이동합니다.
2. 복제할 [!UICONTROL Predictive Audiences] 모델의 이름을 클릭합니다.
3. 화면 왼쪽 상단에 있는 **[!UICONTROL Clone]** 버튼을 클릭합니다.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. 모델을 복제하면 복제된 모델의 [!DNL Save & Configure] 페이지로 이동합니다. 이 페이지에서 모델의 [!UICONTROL data source] 및 할당된[!UICONTROL Profile Merge Rule]을 변경할 수 있습니다. 복제된 모델의 개인 및 대상 대상자를 편집하려면 [!UICONTROL Back] 및 [!UICONTROL Next] 버튼을 사용하여 세 개의 탭 간을 탐색하거나 세 개의 탭 이름을 클릭합니다

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. 모델 편집이 끝나면 **[!UICONTROL Save]** 을 클릭합니다.

## 예측 대상 삭제 {#delete-predictive-audiences}

[!UICONTROL Predictive Audiences] 모델을 삭제하려면 **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** 로 이동하여 삭제할 모델을 찾은 다음 **[!UICONTROL Delete]** 아이콘을 클릭합니다.
