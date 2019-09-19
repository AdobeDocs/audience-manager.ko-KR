---
description: 파생된 신호는 이미 본 트레이트를 기반으로 사이트 방문자가 추가 트레이트를 받을 수 있습니다. 당시 이 트레이트를 본 적이 없어도 현재 전시되는 트레이트에서 트레이트 자격을 얻는 것이 가능하다.
seo-description: 파생된 신호는 이미 본 트레이트를 기반으로 사이트 방문자가 추가 트레이트를 받을 수 있습니다. 당시 이 트레이트를 본 적이 없어도 현재 전시되는 트레이트에서 트레이트 자격을 얻는 것이 가능하다.
seo-title: 파생 신호
solution: Audience Manager
title: 파생 신호
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# 파생 신호 {#derived-signals}

사이트 [!UICONTROL derived signal] 방문자가 이미 본 트레이트를 기반으로 추가 트레이트를 받을 수 있습니다. 당시 이 트레이트를 본 적이 없어도 현재 전시되는 트레이트에서 트레이트 자격을 얻는 것이 가능하다.

<!-- c_tb_derived_signal.xml -->

## 유도신호의 목적

에서 [!DNL Audience Manager]이벤트 호출 동안 전달된 신호(또는 특성 규칙) 간 관계를 다른 지정된 신호 또는 트레이트에 만들 수 있습니다. 예를 들어 이벤트 호출이 키 값 [!DNL "product = new_car"] `https://<domain alias>/event?product=new_car`()으로 구성된 신호에서 전달된다고 가정합니다. [!DNL Audience Manager] 를 사용하면 해당 신호를 [!UICONTROL derived signals] 도구로 만든 다른 모든 사람에게 연결할 수 있습니다. 연결된 신호는 사용자가 지정하는 모든 키 값일 수 있지만, 이미 [!UICONTROL Trait Builder] 규칙으로 설정된 기존 신호에 연결할 때 가장 유용합니다. 예를 들어, 아래 그림에서 사용자 작업이 신호를 실행할 때 사용자가 대상 키 및 값 신호에 의해 정의된 트레이트를 평가할 [!DNL "product = new car"] 수도 있습니다.

![](assets/derived_signal_example.png)

## 파생 신호 위치

사이드바 탐색에서 [!UICONTROL derived signals] 만들고 관리할 **[!UICONTROL Tools > Derived Signals]** 수 있습니다.

## 파생 신호 만들기 {#create}

<!-- t_tb_create_derived.xml -->

To create a [!UICONTROL derived signal]:

1. 메뉴에서 **[!UICONTROL Derived Signals]** 을 [!UICONTROL Tools] 선택합니다.
1. 제공:
   * *(선택 사항)*[!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. 클릭 **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>문자 제한은 [!UICONTROL Source Key]228 [!UICONTROL Source Value][!UICONTROL Target Key][!UICONTROL Target Value] 자입니다.

## 파생된 신호 편집 {#edit}

<!-- t_tb_edit_derived.xml -->

To edit a [!UICONTROL derived signal]:

1. 신호 위로 마우스를 가져간 다음 을 클릭합니다 **[!UICONTROL Edit]**.
2. 필요한 코드, 키 또는 값을 변경한 다음 을 **[!UICONTROL Save]**&#x200B;클릭합니다.

## 파생된 신호 삭제 {#delete}

<!-- t_tb_delete_derived.xml -->

을 삭제하려면 신호 [!UICONTROL derived signal]위로 마우스를 가져간 다음 을 클릭합니다 **[!UICONTROL Delete]**.
