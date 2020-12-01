---
description: 트레이트에 이미 사용된 트레이트를 비롯하여 모든 신호에서 새로운 트레이트를 생성하고 트레이트 생성 후 자격을 얻는 미래의 고객을 캡처할 수 있습니다.
seo-description: 트레이트에 이미 사용된 트레이트를 비롯하여 모든 신호에서 새로운 트레이트를 생성하고 트레이트 생성 후 자격을 얻는 미래의 고객을 캡처할 수 있습니다.
seo-title: 신호에서 트레이트 만들기
title: 신호에서 트레이트 만들기
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 3%

---


# 신호에서 트레이트 만들기

트레이트에 이미 사용된 트레이트를 비롯하여 모든 신호에서 새로운 트레이트를 생성하고 트레이트 생성 후 자격을 얻는 미래의 고객을 캡처할 수 있습니다. 간단한 데모를 보려면 비디오를 시청하거나 자세한 내용을 살펴보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## 신호 대시보드에서 트레이트 만들기 {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard]에서는 [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] 및 저장된 검색에서 새 트레이트를 만들 수 있습니다.

새 트레이트를 만들 때 트레이트 유형은 신호 유형을 기반으로 미리 설정됩니다.

* **[!UICONTROL Rule-based]** 실시간 신호, 실행 가능한 로그 파일 및  [!DNL Adobe Analytics] 신호 등의 특성

* **[!UICONTROL Onboarded]** 온보드 신호에 대한 특성입니다.

**[!UICONTROL Signal Dashboard]**&#x200B;에서 새 트레이트를 만들려면 트레이트에서 사용할 신호를 식별한 다음 해당 **[!UICONTROL Create Rule-Based Trait]** 또는 **[!UICONTROL Create Onboarded Trait]** 링크를 클릭합니다.

![](assets/signals-create-trait.png)

새 트레이트를 만들려면 **[트레이트 빌더](../../features/traits/about-trait-builder.md)**&#x200B;로 리디렉션됩니다.

## 신호 검색에서 트레이트 만들기 {#create-traits-from-signal-search}

[!UICONTROL Signal Dashboard]에 표시되지 않는 사용되거나 사용되지 않은 신호에 따라 트레이트를 만듭니다.

특정 신호를 검색하고 결과를 기반으로 규칙 기반 또는 온보드 트레이트를 생성합니다. 이 작업을 수행하는 방법은 다음과 같습니다.

1. **[!UICONTROL Audience Data > Signals > Search]**&#x200B;으로 이동하여 원하는 키-값 쌍을 기반으로 검색을 실행하거나 키-값 쌍을 입력하지 않고 **[!UICONTROL Search]**&#x200B;을 클릭하여 모든 결과를 표시합니다.
2. 결과 목록에서 트레이트에 사용할 신호를 식별합니다.
   * 한 신호로 트레이트를 만들려면 해당 **[!UICONTROL Create Rule-Based Trait]** 또는 **[!UICONTROL Create Onboarded Trait]** 링크를 클릭합니다.
   * 여러 신호로 트레이트를 만들려면 각 신호의 해당 확인란을 클릭한 다음 **[!UICONTROL Create Trait from Multiple Signals]**&#x200B;을 클릭합니다.

   >[!NOTE]
   >같은 유형의 신호에서만 트레이트를 생성할 수 있습니다. 실시간 신호와 온보드 신호의 조합을 기반으로 하여 트레이트를 만들 수 없습니다.
   >
   > ![](assets/signals-create-trait-search.png)
   >또한 사용된 신호로부터 트레이트를 생성할 수 있습니다. 트레이트에 이미 사용된 신호에 **[!UICONTROL Included in Traits]** 열에 표시된 트레이트 수가 있습니다. 화살표를 클릭하면 신호가 포함된 트레이트가 표시됩니다.
   >
   >![](assets/signals-used-traits.png)

3. **[특성 빌더](../../features/traits/about-trait-builder.md)**&#x200B;를 사용하여 새 트레이트를 만듭니다.
