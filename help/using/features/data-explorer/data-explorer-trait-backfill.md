---
description: 트레이트 생성 날짜 이전에 내역 고객을 캡처하고 관련 데이터를 손실하지 않도록 트레이트 재지정
seo-description: 트레이트 생성 날짜 이전에 내역 고객을 캡처하고 관련 데이터를 손실하지 않도록 트레이트 재지정
seo-title: 채우기 트레이트 재계산
title: 채우기 트레이트 재계산
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# 채우기 트레이트 재계산 {#backfill-trait-realizations}

트레이트 생성 날짜 이전에 내역 고객을 캡처하고 관련 데이터를 손실하지 않도록 트레이트 재지정

[!UICONTROL Data Explorer Trait Backfill] 는 추가 사용 사례를 발굴하여 Audience Manager 경험을 향상시키는 프리미엄 기능입니다. 채우기를 사용하려면 추가 처리 능력이 필요하며, 모든 Audience Manager 고객은 추가 비용으로 사용할 수 있습니다. 자세한 내용은 Adobe 세일즈 담당자에게 문의하십시오.

사용하지 않은 신호에서 트레이트를 생성할 때 특정 기간 동안 트레이트 재연결을 채우도록 선택할 수 있습니다. [!DNL Audience Manager] 는 새 트레이트를 적용받을 수 있는 대상에 대한 내역 데이터를 캡처하여 해당 프로필에 저장합니다. 트레이트 빌더의 **[!UICONTROL Backfill Options]** 섹션에서 [!UICONTROL Trait Expression] 을 볼 수 **[있습니다](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>규칙 기반 트레이트와 온보드 트레이트에 대한 트레이트 재지정을 채울 수 있습니다.

트레이트 실현의 역량은 다음과 같습니다.

1. 신호 검색을 실행하거나 신호 [!UICONTROL Audience Data > Signals > Search] 대시보드를 [](../../features/data-explorer/data-explorer-signals-dashboard.md) 사용하여 새 트레이트에 사용할 신호를 식별합니다.
1. 원하는 신호를 기반으로 새 트레이트를 만듭니다.
1. 섹션에서 **[!UICONTROL Backfill Options]** 을 **[!UICONTROL Trait Expression]** 사용하여 트레이트 재할당을 채울 시간 간격을 선택합니다. 미리 정의된 채우기 간격에는 1, 7, 14 및 30일이 포함됩니다. 최대 30일의 사용자 지정 날짜 범위를 선택할 수도 있습니다.

   ![특징](assets/signals-trait-backfill.png)

1. (선택 사항) **[!UICONTROL Estimate Realizations]** 섹션을 **[!UICONTROL Estimated Trait Realizations]** 클릭하여 지난 7일 동안 채워진 트레이트의 예상 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 값을 확인합니다.

   ![예상 특성](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >다음 연산자를 사용하는 표현식의 트레이트에는 트레이트 채우기 및 추정을 사용할 수 없습니다.
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 트레이트를 만듭니다.

트레이트 작성을 완료하면, 소급 적용이 실현된 통계를 확인할 수 있습니다.

트레이트를 채우는 방법에 대한 비디오 연습을 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25169/?captions=kor)

## 트레이트 채우기 대기 시간 {#trait-backfilling-latency}

새로 만든 트레이트는 생성 후 2~3시간 후에 대상 캡처를 시작합니다. 그러나 매일 [!DNL Audience Manager] 수행되는 데이터 양이 많기 때문에 채워진 모집단 이 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 그래프에 즉시 반영되지 않습니다.

Audience Manager [!UICONTROL Trait Graph] 는 트레이트 생성 후 48시간 이내에 채워진 채우기로 컨텐츠를 업데이트합니다.

## 트레이트 채우기 제한 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 매월 최대 50개의 트레이트를 채우도록 허용하며 매달 1일 동안 채우기 카운터가 재설정됩니다.

>[!NOTE]
>
>트레이트 채우기 할당량은 이전 달에서 이월되지 않습니다. 예를 들어, 이번 달에 30개의 트레이트를 채우면 다음 달의 트레이트 채우기 할당량이 70이 아닌 50으로 재설정됩니다.

## 보고에 미치는 영향 {#reporting-impact}

역채워진 트레이트 실현은 내역 신호를 트레이트 실현으로 [!UICONTROL Unique Trait Realizations] 바꿀 수 있으므로 [!UICONTROL Total Trait Population] 및 [!DNL Audience Manager] 지표에 반영됩니다.

하지만, [!UICONTROL Trait Graph]및 [!UICONTROL General Reports]는 트레이트 생성 날짜 전에 채워진 내역 지표로 소급 업데이트되지 [!UICONTROL Trend Reports] 않습니다.