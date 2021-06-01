---
description: 트레이트 실현을 채우기 통해 이전 대상을 캡처하고 트레이트 생성 날짜 이전에 관련 데이터가 손실되지 않도록 합니다.
seo-description: 트레이트 실현을 채우기 통해 이전 대상을 캡처하고 트레이트 생성 날짜 이전에 관련 데이터가 손실되지 않도록 합니다.
seo-title: 특성 실현 채우기
title: 특성 실현 채우기
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: 데이터 탐색기
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 2%

---

# 특성 실현 채우기 {#backfill-trait-realizations}

트레이트 실현을 채우기 통해 이전 대상을 캡처하고 트레이트 생성 날짜 이전에 관련 데이터가 손실되지 않도록 합니다.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] 는 추가 사용 사례를 잠금 해제하여 Audience Manager 경험을 향상시키는 프리미엄 기능입니다. 채우기 기능을 사용하려면 추가 처리 능력이 필요하며, 모든 Audience Manager 고객은 증분 비용으로 사용할 수 있습니다. 자세한 내용은 Adobe 영업 담당자에게 문의하십시오.

사용하지 않은 신호에서 트레이트를 만들 때 특정 기간 동안 트레이트 실현을 채우기 위해 선택할 수 있습니다. [!DNL Audience Manager] 은(는) 새 트레이트에 대한 자격이 되는 대상에 대한 이전 데이터를 캡처하여 해당 프로필에 저장합니다. **[트레이트 빌더](../../features/traits/about-trait-builder.md)**&#x200B;의 [!UICONTROL Trait Expression] 섹션에서 **[!UICONTROL Backfill Options]**&#x200B;을 볼 수 있습니다.

>[!NOTE]
>
>규칙 기반 트레이트와 온보딩된 트레이트에 대한 트레이트 실현을 채울 수 있습니다.

트레이트 실현을 채우는 방법은 다음과 같습니다.

1. [!UICONTROL Audience Data > Signals > Search] 로 이동하여 신호 검색을 실행하거나 [신호 대시보드](../../features/data-explorer/data-explorer-signals-dashboard.md)를 사용하여 새 트레이트에 사용할 신호를 식별합니다.
1. 원하는 신호를 기반으로 새 트레이트를 만듭니다.
1. **[!UICONTROL Trait Expression]** 섹션의 **[!UICONTROL Backfill Options]**&#x200B;을 사용하여 트레이트 실현을 채울 시간 간격을 선택합니다. 사전 정의된 채우기 간격에는 1, 7, 14 및 30일이 포함됩니다. 최대 30일의 사용자 지정 날짜 범위를 선택할 수도 있습니다.

   ![트레이트 채우기](assets/signals-trait-backfill.png)

1. (선택 사항) 지난 7일 동안 채우기 트레이트에 대한 예상 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 값을 보려면 **[!UICONTROL Estimated Trait Realizations]** 섹션에서 **[!UICONTROL Estimate Realizations]** 을 클릭하십시오.

   ![예상 트레이트 실현](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >다음 연산자를 사용하는 표현식이 있는 트레이트에 트레이트 채우기 및 추정을 사용할 수 없습니다.
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. 트레이트를 만듭니다.

트레이트 만들기를 완료하면 실현 통계에 포함된 트레이트의 채우기 실현이 표시됩니다.

트레이트 채우기 방법에 대한 비디오 연습을 보려면 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 트레이트 채우기 지연 {#trait-backfilling-latency}

새로 만든 트레이트는 만든 후 2~3시간 후에 대상 캡처를 시작합니다. 그러나 [!DNL Audience Manager] 가 매일 수행하는 대량의 데이터가 있기 때문에 채워진 모집단은 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 그래프에 즉시 반영되지 않습니다.

Audience Manager은 트레이트를 만든 후 48시간 이내에 [!UICONTROL Trait Graph]을 다시 채워진 모집단으로 업데이트합니다.

## 트레이트 채우기 제한 {#trait-backfilling-limit}

[!UICONTROL Data Explorer] 매월 최대 50개의 트레이트를 채울 수 있도록 하며 매월 1일에 채우기 카운터가 재설정됩니다.

>[!NOTE]
>
>트레이트 채우기 쿼터는 이전 달에서 이월되지 않습니다. 예를 들어, 이 달에 30개의 트레이트를 채우는 경우, 다음 달의 트레이트 채우기 쿼터는 70이 아니라 50으로 재설정됩니다.

## 보고에 미치는 영향 {#reporting-impact}

[!DNL Audience Manager] 는 내역 신호를 트레이트 실현으로 전환하므로, 채워진 트레이트 실현은 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 지표에 반영됩니다.

그러나 [!UICONTROL Trait Graph], [!UICONTROL General Reports] 및 [!UICONTROL Trend Reports]는 트레이트 생성 날짜 이전에 백채워진 내역 지표로 소급하여 업데이트되지 않습니다.
