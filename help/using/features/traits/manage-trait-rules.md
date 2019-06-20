---
description: 특성 빌더에서 표현식 빌더를 사용하면 대상 자격 조건을 설정하는 규칙을 만들고 테스트할 수 있습니다. 규칙은 "color = = blue" 또는 "price > 100" 와 같은 키-값 쌍으로 구성됩니다. 비교 연산자는 키와 값 간의 관계를 설정합니다. 부울 표현식은 규칙 그룹 사이의 관계를 결정합니다.
seo-description: 특성 빌더에서 표현식 빌더를 사용하면 대상 자격 조건을 설정하는 규칙을 만들고 테스트할 수 있습니다. 규칙은 "color = = blue" 또는 "price > 100" 와 같은 키-값 쌍으로 구성됩니다. 비교 연산자는 키와 값 간의 관계를 설정합니다. 부울 표현식은 규칙 그룹 사이의 관계를 결정합니다.
seo-title: 특성 규칙 관리
solution: Audience Manager
title: 특성 규칙 관리
uuid: 827 D 4567-2 B 6 F -411 E-BD 5 C -9735 C 916291 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Managing Trait Rules {#managing-trait-rules}

In [!UICONTROL Trait Builder], the [!UICONTROL Expression Builder] lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as `color == blue` or `price > 100`. 비교 연산자는 키와 값 간의 관계를 설정합니다. [!DNL Boolean] 표현식은 규칙 그룹 간의 관계를 결정합니다.

<!-- c_tb_rules.xml -->

## 기본 신호 규칙 기능 설명

![](assets/manage-trait-rules.png)

1. **[!UICONTROL Expression Builder]** OR **[!UICONTROL Code View]** 탭은 트레이트 규칙에 대한 개요를 제공합니다. **[!UICONTROL Expression Builder]** 이 탭에서는 필드와 드롭다운 메뉴가 있는 규칙을 만들 수 있습니다. The **[!UICONTROL Code View]** lets you create rules by manually writing those expressions as code. The illustration above shows a simple trait composed of a signal that evaluates data for a qualifying condition where a product key equals a specific value, in this case `color == "blue"`.

1. 이 섹션의 필드 및 컨트롤을 사용하면 키-값 쌍의 신호를 만들고 이러한 쌍을 비교 연산자와 설정할 수 있습니다. 키, 연산자 및 값이 필요합니다.
1. The [!UICONTROL Data Explorer Options] allow you to backfill trait realizations for your signals.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. 자세한 내용은 Adobe 컨설턴트에게 문의하십시오.
1. This section shows you an estimation of trait realizations for the past 7 days, for the signals defined in the [!UICONTROL Expression Builder], for backfilled and non-backfilled traits.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. 자세한 내용은 Adobe 컨설턴트에게 문의하십시오.
1. The test fields let you validate combinations of signal rules or the [!DNL URL]s that you want to use when sending data to Audience Manager.

## Create a Trait Rule {#create-trait-rule}

규칙 (또는 표현식) 는 키-값 쌍의 개별 또는 그룹으로 구성됩니다. 비교 연산자는 키-값 쌍 간의 관계를 설정합니다. To create a rule,provide a key, a value, select an operator, and click **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete the required fields in the **[!UICONTROL Basic Information]** section *before* creating trait rules.

1. **[!UICONTROL Trait Expression]** 섹션을 확장하고 키와 값 이름을 입력합니다. This creates a *`signal`*.
   >[!NOTE]
   >
   >Include the `c_` prefix (or any other naming convention) for key variable if your event calls send data to [!DNL Audience Manager] using that syntax.
1. Select a [comparison operator](../../features/traits/trait-comparison-operators.md) from the **[!UICONTROL Operator]** dropdown. 비교 연산자는 신호에서 요소 간의 관계를 평가합니다.
   >[!NOTE]
   >
   >[!DNL Boolean][!UICONTROL OR] 연산자는 그룹 *내의* 여러 신호 간의 관계를 설정하고 변경할 수 없습니다.
1. 클릭 **[!UICONTROL Add Rule]**. 저장된 규칙이 데이터 입력 필드 위의 트레이트 작업 영역에 나타납니다.

### 예 {#example-trait-rule}

아래 예에서 사용자는 제품 ID를 기반으로 새 트레이트 규칙을 만들었습니다. To build this rule, the user provided the key `productkey` linked with an equals operator ( `==`) to the value `2093`.
![](assets/tb_sample_rule1.png)

Clicking **[!UICONTROL Add Rule]** saves and moves the trait into the [!UICONTROL Expression Builder] workspace.

![](assets/tb_sample_rule2.png)

>[!MORE_ like_ this]
>
>* [새 규칙 그룹 만들기](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [그룹 간 규칙 이동](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [트레이트 규칙 삭제](../../features/traits/manage-trait-rules.md#delete-trait)


## Create a New Rule Group {#create-rule-group}

이 절차에서는 새 규칙 그룹을 만드는 방법에 대해 설명합니다.

<!-- t_tb_new_rule_group.xml -->

새 규칙 그룹을 만들려면 트레이트에 최소 두 개의 규칙이 있어야 합니다.

1. 이동할 규칙 위로 커서를 이동하면 강조 표시됩니다.
1. 강조 표시된 규칙 테두리 위로 마우스를 가져갑니다.
이렇게 하면 규칙이 현재 그룹에서 자동으로 분리되고 새 그룹으로 이동합니다.
   >[!NOTE]
   >
   >의도하지 않게 이동하는 경우 규칙을 원래 그룹으로 다시 드래그합니다.
1. Select a [!DNL Boolean] operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) from the drop-down menu to set the relationship between the rule groups.

>[!MORE_ like_ this]
>
>* [트레이트 규칙 만들기](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [그룹 간 규칙 이동](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [트레이트 규칙 삭제](../../features/traits/manage-trait-rules.md#delete-trait)


## Move Rules Between Groups {#move-rules-between-groups}

규칙을 이동하려면을 클릭하고 다른 그룹으로 드래그합니다.

>[!MORE_ like_ this]
>
>* [트레이트 규칙 만들기](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [새 규칙 그룹 만들기](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [트레이트 규칙 삭제](../../features/traits/manage-trait-rules.md#delete-trait)


## Edit a Trait {#edit-trait}

이 절차에서는 트레이트를 편집하는 방법에 대해 설명합니다.

<!-- t_tb_edit.xml -->

1. [!UICONTROL Traits] 대시보드에서 편집할 트레이트 **[!UICONTROL Actions]** 열로 마우스를 가져갑니다. 특성 관리 아이콘이 표시됩니다.
1. 연필을 클릭하여 트레이트를 편집합니다.

   ![](assets/tb_edit_trait.png)

## Delete a Trait Rule {#delete-trait}

이 절차에서는 트레이트 규칙을 삭제하는 방법에 대해 설명합니다.

<!-- t_tb_delete_rule.xml -->

1. [!UICONTROL Traits] 대시보드에서 편집할 트레이트 [!UICONTROL Actions] 열로 마우스를 가져간 다음 연필 아이콘을 클릭합니다. 특성 관리 아이콘이 표시됩니다.
1. [!UICONTROL Trait Expression] 섹션을 확장합니다.
1. 삭제할 규칙 위로 마우스를 가져간 다음 X 아이콘을 클릭합니다. 규칙이 즉시 삭제됩니다.