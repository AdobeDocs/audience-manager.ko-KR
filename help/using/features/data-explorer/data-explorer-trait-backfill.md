---
description: 특성 특성을 채워 내역 고객을 캡처하고 트레이트 작성 날짜 이전에 관련 데이터가 손실되지 않도록 합니다.
seo-description: 특성 특성을 채워 내역 고객을 캡처하고 트레이트 작성 날짜 이전에 관련 데이터가 손실되지 않도록 합니다.
seo-title: 특성 특성 채우기
title: 특성 특성 채우기
uuid: 8 B 0 EF 4 E 6-D 16 A -4 D 1 D -94 F 1-B 84 EEBFFA 9 A 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

특성 특성을 채워 내역 고객을 캡처하고 트레이트 작성 날짜 이전에 관련 데이터가 손실되지 않도록 합니다.

[!UICONTROL Data Explorer Trait Backfill] 은 추가 사용 사례를 잠금 해제하여 Audience Manager 경험을 향상시키는 프리미엄 기능입니다. 채우기는 추가 처리 능력이 필요하며 모든 Audience Manager 고객이 증분 비용으로 사용할 수 있습니다. 자세한 내용은 Adobe 세일즈 담당자에게 문의하십시오.

사용하지 않은 신호에서 트레이트를 만들 때 일정 기간 동안 트레이트 사실화를 채우도록 선택할 수 있습니다. [!DNL Audience Manager] 새 트레이트를 받을 수 있는 대상자에 대한 내역 데이터를 캡처하여 해당 프로필에 저장합니다. You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>규칙 기반 트레이트와 온보드 트레이트에 대한 트레이트 리얼라이제이션을 채울 수 있습니다.

특성 실현을 위한 방법:

1. [!UICONTROL Audience Data > Signals > Search] AMD에서 신호 검색을 실행하거나 [신호 대시보드를](../../features/data-explorer/data-explorer-signals-dashboard.md) 사용하여 새로운 트레이트에서 사용할 신호를 식별합니다.
1. 원하는 신호에 따라 새 트레이트를 만듭니다.
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. 사전 정의된 채우기 간격에는 1, 7, 14 및 30 일이 포함됩니다. 최대 30 일 범위의 사용자 지정 날짜 범위를 선택할 수도 있습니다.
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >특성 다음 연산자를 사용하는 표현식의 특성에 대해서는 채우기와 추정을 사용할 수 없습니다.
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 트레이트를 만듭니다.

특성 작성을 완료하면 구현 통계에 포함된 실현된 실현이 표시됩니다.

## Trait Backfilling Latency {#trait-backfilling-latency}

새롭게 만든 트레이트는 제작한 후 2 ~ 3 시간 후에 고객을 캡처하기 시작합니다. However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 매월 최대 50 개의 트레이트를 채울 수 있으며, 채우기 카운터가 매월 1 일에 재설정됩니다.

>[!NOTE]
>
>특성 채우기 할당량은 이전 달에서 이월되지 않습니다. 예를 들어, 이번 달에 30 개의 트레이트를 채우면 다음 달의 트레이트 채우기 할당량이 70 이 아닌 50로 재설정됩니다.

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.