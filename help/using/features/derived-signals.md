---
description: 파생된 신호는 이미 본 트레이트를 기반으로 사이트 방문자에게 추가 트레이트를 부여합니다. 즉, 사용자가 이전에 새로운 트레이트를 본 적이 없더라도 현재 표시된 트레이트에서 추가 트레이트 자격을 도출할 수 있습니다.
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: 파생 신호
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---

# 파생 신호 {#derived-signals}

A [!UICONTROL derived signal] 이미 본 트레이트를 기반으로 하여 사이트 방문자에게 추가 트레이트를 자격을 부여합니다. 즉, 사용자가 이전에 새로운 트레이트를 본 적이 없더라도 현재 표시된 트레이트에서 추가 트레이트 자격을 도출할 수 있습니다.

<!-- c_tb_derived_signal.xml -->

## 파생 신호 목적

위치 [!DNL Audience Manager], 지정된 다른 신호 또는 트레이트에 대한 이벤트 호출 중에 전달된 신호(또는 트레이트 규칙) 간의 관계를 만들 수 있습니다. 예를 들어 이벤트 호출이 키-값으로 구성된 신호를 전달한다고 가정해 보겠습니다 [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] 를 사용하여 만든 다른 모든 장치에 해당 신호를 연결합니다. [!UICONTROL derived signals] 도구. 연결된 신호는 사용자가 지정하는 모든 키-값이 될 수 있지만 이미 로 설정된 기존 신호에 연결된 경우 가장 유용합니다. [!UICONTROL Trait Builder] 규칙. 예를 들어 아래 그림에서 사용자 작업이 신호를 실행할 때 [!DNL "product = new car"] 해당 사용자는 대상 키 및 값 신호에 의해 정의된 트레이트에 대한 자격을 얻을 수도 있습니다.

![](assets/derived_signal_example.png)

## 파생 신호 위치

만들기 및 관리 [!UICONTROL derived signals] 위치: **[!UICONTROL Tools > Derived Signals]** 를 클릭합니다.

## 파생 신호 만들기 {#create}

<!-- t_tb_create_derived.xml -->

을(를) 만들려면 [!UICONTROL derived signal]:

1. 선택 **[!UICONTROL Derived Signals]** 다음에서 [!UICONTROL Tools] 메뉴 아래의 제품에서 사용할 수 있습니다.
1. 다음을 제공합니다.
   * *(선택 사항)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 클릭 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>에 대한 문자 제한 [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key], 및 [!UICONTROL Target Value] 필드는 228자입니다.

## 파생 신호 편집 {#edit}

<!-- t_tb_edit_derived.xml -->

을(를) 편집하려면 [!UICONTROL derived signal]:

1. 신호 위로 마우스를 가져간 다음 **[!UICONTROL Edit]**.
2. 필요한 코드, 키 또는 값을 변경한 다음 **[!UICONTROL Save]**.

## 파생 신호 삭제 {#delete}

<!-- t_tb_delete_derived.xml -->

삭제 방법 [!UICONTROL derived signal]를 클릭하고 신호 위로 마우스를 가져간 다음 **[!UICONTROL Delete]**.
