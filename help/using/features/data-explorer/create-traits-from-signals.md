---
description: 트레이트에 이미 사용된 트레이트를 포함하여 모든 신호에서 새 트레이트를 만들고 트레이트 만들기 후에 자격을 부여하는 향후 대상을 캡처합니다.
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: 신호에서 트레이트 만들기
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# 신호에서 트레이트 만들기

트레이트에 이미 사용된 트레이트를 포함하여 모든 신호에서 새 트레이트를 만들고 트레이트 만들기 후에 자격을 부여하는 향후 대상을 캡처합니다. 비디오를 시청하여 빠른 데모를 수행하거나 자세히 알아보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## 신호 대시보드에서 트레이트 만들기 {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard]을(를) 사용하면 [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] 및 저장된 검색에서 새 특성을 만들 수 있습니다.

새 트레이트를 만들 때 트레이트 유형은 신호 유형을 기반으로 미리 설정됩니다.

* 실시간 신호, 실행 가능한 로그 파일 및 [!DNL Adobe Analytics]개 신호에 대한 트레이트 **[!UICONTROL Rule-based]**&#x200B;개,

* 온보딩된 신호에 대한 트레이트 **[!UICONTROL Onboarded]**&#x200B;개.

**[!UICONTROL Signal Dashboard]**&#x200B;에서 새 트레이트를 만들려면 트레이트에 사용할 신호를 식별한 다음 해당 **[!UICONTROL Create Rule-Based Trait]** 또는 **[!UICONTROL Create Onboarded Trait]** 링크를 클릭합니다.

![](assets/signals-create-trait.png)

새 특성을 만들려면 **[특성 빌더](../../features/traits/about-trait-builder.md)**(으)로 리디렉션됩니다.

## 신호 검색에서 트레이트 만들기 {#create-traits-from-signal-search}

[!UICONTROL Signal Dashboard]에 표시되지 않는 사용되거나 사용되지 않은 신호를 기반으로 특성을 만듭니다.

특정 신호를 검색하고 결과를 기반으로 규칙 기반 또는 온보딩된 트레이트를 만듭니다. 방법은 다음과 같습니다.

1. **[!UICONTROL Audience Data > Signals > Search]**(으)로 이동하여 원하는 키-값 쌍을 기준으로 검색을 실행하거나 키-값 쌍을 입력하지 않고 **[!UICONTROL Search]**&#x200B;을(를) 클릭하여 모든 결과를 표시합니다.
2. 결과 목록에서 트레이트에 사용할 신호를 식별합니다.
   * 하나의 신호에서 트레이트를 만들려면 해당 **[!UICONTROL Create Rule-Based Trait]** 또는 **[!UICONTROL Create Onboarded Trait]** 링크를 클릭합니다.
   * 여러 신호에서 트레이트를 만들려면 각 신호의 해당 확인란을 클릭한 다음 **[!UICONTROL Create Trait from Multiple Signals]**&#x200B;을(를) 클릭합니다.

   >[!NOTE]
   >동일한 유형의 신호에서만 트레이트를 만들 수 있습니다. 실시간 신호와 온보딩된 신호의 조합을 기반으로 트레이트를 만들 수 없습니다.
   >
   > ![](assets/signals-create-trait-search.png)
   >사용한 신호로부터 트레이트를 만들 수도 있습니다. 트레이트에 이미 사용된 신호는 **[!UICONTROL Included in Traits]** 열에 표시된 트레이트 수를 가집니다. 화살표를 클릭하면 신호가 포함된 트레이트가 표시됩니다.
   >
   >![](assets/signals-used-traits.png)

3. **[트레이트 빌더](../../features/traits/about-trait-builder.md)**&#x200B;를 사용하여 새 트레이트를 만드십시오.
