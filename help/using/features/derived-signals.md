---
description: 파생된 신호는 이미 본 트레이트에 따라 사이트 방문자가 추가 트레이트에 대한 자격을 얻습니다. 즉, 사용자가 이전에 새로운 트레이트를 본 적이 없어도 현재 표시된 트레이트에서 추가 트레이트 자격을 도출할 수 있습니다.
seo-description: 파생된 신호는 이미 본 트레이트에 따라 사이트 방문자가 추가 트레이트에 대한 자격을 얻습니다. 즉, 사용자가 이전에 새로운 트레이트를 본 적이 없어도 현재 표시된 트레이트에서 추가 트레이트 자격을 도출할 수 있습니다.
seo-title: 파생 신호
solution: Audience Manager
title: 파생 신호
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: 트레이트
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 2%

---

# 파생 신호 {#derived-signals}

[!UICONTROL derived signal]은(는) 이미 본 트레이트에 따라 사이트 방문자에게 추가 트레이트를 부여할 수 있습니다. 즉, 사용자가 이전에 새로운 트레이트를 본 적이 없어도 현재 표시된 트레이트에서 추가 트레이트 자격을 도출할 수 있습니다.

<!-- c_tb_derived_signal.xml -->

## 파생 신호의 목적

[!DNL Audience Manager]에서는 지정된 다른 신호나 트레이트에 대한 이벤트 호출 중에 전달된 신호(또는 트레이트 규칙) 간의 관계를 만들 수 있습니다. 예를 들어, 이벤트 호출이 키-값 [!DNL "product = new_car"]( `https://<domain alias>/event?product=new_car`)으로 구성된 신호를 전달한다고 가정합니다. [!DNL Audience Manager] 는 도구를 사용하여 만든 다른 모든 신호에  [!UICONTROL derived signals] 연결합니다. 연결된 신호는 사용자가 지정하는 키 값일 수 있지만, 기존 신호에 연결되어 이미 [!UICONTROL Trait Builder] 규칙으로 설정된 경우 가장 유용합니다. 예를 들어 아래 그림에서 사용자 작업이 [!DNL "product = new car"] 신호를 실행하면 사용자가 타겟 키 및 값 신호에 의해 정의된 트레이트에 대한 자격도 받을 수 있습니다.

![](assets/derived_signal_example.png)

## 파생 신호의 위치

사이드바 탐색에서 **[!UICONTROL Tools > Derived Signals]**&#x200B;에 [!UICONTROL derived signals]을 만들고 관리합니다.

## 파생 신호 만들기 {#create}

<!-- t_tb_create_derived.xml -->

[!UICONTROL derived signal]을(를) 만들려면:

1. [!UICONTROL Tools] 메뉴에서 **[!UICONTROL Derived Signals]** 을 선택합니다.
1. 다음을 제공합니다.
   * *(선택 사항)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 클릭 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>[!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] 및 [!UICONTROL Target Value] 필드의 문자 제한은 228자입니다.

## 파생 신호 편집 {#edit}

<!-- t_tb_edit_derived.xml -->

[!UICONTROL derived signal]을 편집하려면:

1. 신호 위로 마우스를 가져간 다음 **[!UICONTROL Edit]** 을 클릭합니다.
2. 필요한 코드, 키 또는 값을 변경한 다음 **[!UICONTROL Save]** 을 클릭합니다.

## 파생 신호 삭제 {#delete}

<!-- t_tb_delete_derived.xml -->

[!UICONTROL derived signal]을(를) 삭제하려면 해당 신호를 마우스로 가리킨 다음 **[!UICONTROL Delete]**&#x200B;을 클릭합니다.
