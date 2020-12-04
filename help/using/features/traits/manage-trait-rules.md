---
description: 특성 빌더에서 표현식 빌더를 사용하면 대상 자격 요구 사항을 설정하는 규칙을 만들고 테스트할 수 있습니다. 규칙은 "color == blue" 또는 "price > 100"과 같은 키-값 쌍으로 구성됩니다. 비교 연산자는 키와 값 간의 관계를 설정합니다. 부울 표현식으로 규칙 그룹 간의 관계가 결정됩니다.
seo-description: 특성 빌더에서 표현식 빌더를 사용하면 대상 자격 요구 사항을 설정하는 규칙을 만들고 테스트할 수 있습니다. 규칙은 "color == blue" 또는 "price > 100"과 같은 키-값 쌍으로 구성됩니다. 비교 연산자는 키와 값 간의 관계를 설정합니다. 부울 표현식으로 규칙 그룹 간의 관계가 결정됩니다.
seo-title: 트레이트 규칙 관리
solution: Audience Manager
title: 트레이트 규칙 관리
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: 14c5ac091a27d125c96d17ce750c6e25ad844856
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# 트레이트 규칙 관리 {#managing-trait-rules}

[!UICONTROL Trait Builder]에서 [!UICONTROL Expression Builder]에서는 대상 자격 요건을 설정하는 규칙을 만들고 테스트할 수 있습니다. 규칙은 `color == blue` 또는 `price > 100`과 같은 키-값 쌍으로 구성됩니다. 비교 연산자는 키와 값 간의 관계를 설정합니다. [!DNL Boolean] 표현식은 규칙 그룹 간의 관계를 결정합니다.

<!-- c_tb_rules.xml -->

## 주요 신호 규칙 기능 설명

![](assets/manage-trait-rules.png)

1. **[!UICONTROL Expression Builder]** 또는 **[!UICONTROL Code View]** 탭은 트레이트의 규칙에 대한 개요를 제공합니다. **[!UICONTROL Expression Builder]** 탭에서는 필드 및 드롭다운 메뉴가 있는 규칙을 만들 수 있습니다. **[!UICONTROL Code View]**&#x200B;에서는 이러한 표현식을 수동으로 코드로 작성하여 규칙을 만들 수 있습니다. 위의 그림은 제품 키가 특정 값과 같은 적격한 조건에 대한 데이터를 평가하는 신호로 구성된 단순한 트레이트를 보여줍니다(이 경우 `color == "blue"`).

1. 이 섹션의 필드 및 컨트롤을 사용하면 키-값 쌍에서 신호를 만들고 비교 연산자와 그 사이의 관계를 설정할 수 있습니다. 키, 연산자 및 값이 필요합니다.
1. [!UICONTROL Data Explorer Options]을 사용하면 신호에 대한 트레이트 할당을 채울 수 있습니다.

   >[!NOTE]
   >
   >이 옵션은 [!UICONTROL Data Explorer] 고객만 사용할 수 있습니다. 자세한 내용은 Adobe 컨설턴트에게 문의하십시오.

1. 이 섹션에서는 [!UICONTROL Expression Builder]에 정의된 신호에 대한 지난 7일 동안 채워진 트레이트와 채우지 않은 트레이트에 대한 트레이트 실현에 대한 추정을 보여 줍니다.

   >[!NOTE]
   >
   >이 옵션은 [!UICONTROL Data Explorer] 고객만 사용할 수 있습니다. 자세한 내용은 Adobe 컨설턴트에게 문의하십시오.

1. 테스트 필드를 사용하면 데이터를 Audience Manager으로 보낼 때 사용할 신호 규칙 또는 [!DNL URL]의 조합을 확인할 수 있습니다.

## 특성 규칙 만들기 {#create-trait-rule}

규칙(또는 표현식)은 키-값 쌍의 개별 또는 그룹으로 구성됩니다. 비교 연산자는 키-값 쌍 간의 관계를 설정합니다. 규칙을 만들려면 키, 값을 입력하고 연산자를 선택하고 **[!UICONTROL Add Rule]**&#x200B;을 클릭합니다.

<!-- t_tb_create_rules.xml -->

특성 규칙을 만들기 전에 **[!UICONTROL Basic Information]** 섹션 *에서 필요한 필드를 완료합니다.*

1. **[!UICONTROL Trait Expression]** 섹션을 확장하고 키와 값 이름을 입력합니다. 그러면 *`signal`*&#x200B;이 만들어집니다.

   >[!NOTE]
   >
   >이벤트 호출이 해당 구문을 사용하여 [!DNL Audience Manager]로 데이터를 전송하는 경우 키 변수에 대한 `c_` 접두어(또는 다른 이름 지정 규칙)를 포함시키십시오.

1. **[!UICONTROL Operator]** 드롭다운에서 [비교 연산자](../../features/traits/trait-comparison-operators.md)를 선택합니다. 비교 연산자는 신호의 요소 사이의 관계를 평가합니다.

   >[!NOTE]
   >
   >[!DNL Boolean] [!UICONTROL OR] 연산자는 그룹 내에 *여러 신호 간의 관계를 설정하며 변경할 수 없습니다.*

1. 클릭 **[!UICONTROL Add Rule]**. 저장된 규칙은 데이터 입력 필드 위의 트레이트 작업 공간에 나타납니다.

### 예 {#example-trait-rule}

아래 예에서 사용자가 제품 ID를 기반으로 새로운 특성 규칙을 만들었습니다. 이 규칙을 빌드하기 위해 사용자는 같음 연산자( `==`)와 연결된 키 `productkey`을 값 `2093`에 제공했습니다.

![](assets/tb_sample_rule1.png)

**[!UICONTROL Add Rule]**&#x200B;을 클릭하면 트레이트가 저장되고 [!UICONTROL Expression Builder] 작업 공간으로 이동합니다.

![](assets/tb_sample_rule2.png)

## 새 규칙 그룹 {#create-rule-group} 만들기

이 절차에서는 새 규칙 그룹을 만드는 방법에 대해 설명합니다.

<!-- t_tb_new_rule_group.xml -->

새 규칙 그룹을 만들려면 트레이트에 규칙이 두 개 이상 있어야 합니다.

1. 이동할 규칙 위로 커서를 이동하여 강조 표시합니다.
1. 강조 표시된 규칙 테두리 위로 마우스를 가져갑니다.

   규칙을 현재 그룹에서 자동으로 분리하고 새 그룹으로 이동합니다.

   >[!NOTE]
   >
   >의도치 않게 규칙을 이동하면 규칙을 원래 그룹으로 다시 드래그합니다.

1. 드롭다운 메뉴에서 [!DNL Boolean] 연산자([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT])를 선택하여 규칙 그룹 간의 관계를 설정합니다.

## 그룹 간 규칙 이동 {#move-rules-between-groups}

규칙을 이동하려면 을 클릭하고 다른 그룹으로 드래그합니다.

## 특성 편집 {#edit-trait}

이 절차에서는 트레이트를 편집하는 방법에 대해 설명합니다.

<!-- t_tb_edit.xml -->

1. [!UICONTROL Traits] 대시보드에서 편집할 트레이트에 대해 **[!UICONTROL Actions]** 열 위로 마우스를 가져갑니다. 그러면 특성 관리 아이콘이 표시됩니다.
1. 연필을 클릭하여 트레이트를 편집합니다.

   ![](assets/tb_edit_trait.png)

## 특성 규칙 삭제 {#delete-trait}

이 절차에서는 특성 규칙을 삭제하는 방법을 설명합니다.

<!-- t_tb_delete_rule.xml -->

1. [!UICONTROL Traits] 대시보드에서 편집할 트레이트의 [!UICONTROL Actions] 열 위로 마우스를 가져간 다음 연필 아이콘을 클릭합니다. 그러면 특성 관리 아이콘이 표시됩니다.
1. [!UICONTROL Trait Expression] 섹션을 확장합니다.
1. 삭제할 규칙 위로 마우스를 가져간 다음 X 아이콘을 클릭합니다. 규칙은 즉시 삭제됩니다.

>[!MORELIKETHIS]
>
>* [새 규칙 그룹 만들기](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [그룹 간 규칙 이동](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [특성 규칙 만들기](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [특성 규칙 삭제](../../features/traits/manage-trait-rules.md#delete-trait)
>* [그룹 간 규칙 이동](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

