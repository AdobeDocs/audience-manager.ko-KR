---
description: 파생된 신호는 사이트 방문자가 이미 본 트레이트를 기반으로 추가 트레이트를 적용하도록 합니다. 즉, 사용자가 이전에 새 트레이트를 본 적이 없는 경우에도 추가 트레이트 자격 조건은 현재 표시된 트레이트 중에 파생될 수 있습니다.
seo-description: 파생된 신호는 사이트 방문자가 이미 본 트레이트를 기반으로 추가 트레이트를 적용하도록 합니다. 즉, 사용자가 이전에 새 트레이트를 본 적이 없는 경우에도 추가 트레이트 자격 조건은 현재 표시된 트레이트 중에 파생될 수 있습니다.
seo-title: 파생 신호
solution: Audience Manager
title: 파생 신호
uuid: E 52600 E 3-26 D 1-4607-9 B 96-AFD 6086 A 252 D
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Derived Signals {#derived-signals}

A [!UICONTROL derived signal] qualifies site visitors for additional traits based on a trait they&#39;ve already seen. 즉, 사용자가 이전에 새 트레이트를 본 적이 없는 경우에도 추가 트레이트 자격 조건은 현재 표시된 트레이트 중에 파생될 수 있습니다.

<!-- c_tb_derived_signal.xml -->

## 파생 신호의 목적

In [!DNL Audience Manager], you can create a relationship between signals (or trait rules) passed in during an event call to other, specified signals or traits. For example, assume an event call passes in a signal composed of the key-value [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] 이 신호를 [!UICONTROL derived signals] 도구로 만든 다른 사람에게 연결합니다. Although the associated signals can be any key-values you specify, they are most useful when linked to existing signals already set up as [!UICONTROL Trait Builder] rules. For example, in the illustration below, when a user action fires the signal [!DNL "product = new car"] that user can also qualify for traits defined by the target key and value signals.

![](assets/derived_signal_example.png)

## 파생된 신호 위치

Create and manage [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** from the sidebar navigation.

## Create a Derived Signal {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. **[!UICONTROL Derived Signals]** 메뉴에서 선택합니다.[!UICONTROL Tools]
1. A:
   * *(선택 사항)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 클릭 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>[!UICONTROL Source Key][!UICONTROL Source Value], [!UICONTROL Target Key]및 [!UICONTROL Target Value] 필드의 문자 제한은 228 자입니다.

## Edit a Derived Signal {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. Hover over the signal, then click **[!UICONTROL Edit]**.
2. Make the required code, key, or value changes, then click **[!UICONTROL Save]**.

## Delete a Derived Signal {#delete}

<!-- t_tb_delete_derived.xml -->

To delete a [!UICONTROL derived signal], hover over the signal, then click **[!UICONTROL Delete]**.
