---
description: 트레이트 실현을 다시 채워 내역 대상을 캡처하고 트레이트 생성 날짜 이전에 관련 데이터의 손실을 방지합니다.
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: 특성 실현 채우기
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# 특성 실현 채우기 {#backfill-trait-realizations}

트레이트 실현을 다시 채워 내역 대상을 캡처하고 트레이트 생성 날짜 이전에 관련 데이터의 손실을 방지합니다.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill]은(는) 추가 사용 사례를 잠금 해제하여 Audience Manager 환경을 향상시키는 프리미엄 기능입니다. 다시 채우려면 추가 처리 능력이 필요하며 모든 Audience Manager 고객이 추가 비용으로 사용할 수 있습니다. 자세한 내용은 Adobe 영업 담당자에게 문의하십시오.

사용되지 않은 신호에서 트레이트를 만들 때 특정 기간 동안 트레이트 실현을 채우도록 선택할 수 있습니다. [!DNL Audience Manager]은(는) 새 트레이트의 대상 내역 데이터를 캡처하여 해당 프로필에 저장합니다. **[특성 빌더](../../features/traits/about-trait-builder.md)**&#x200B;의 [!UICONTROL Trait Expression] 섹션에서 **[!UICONTROL Backfill Options]**&#x200B;을(를) 볼 수 있습니다.

>[!NOTE]
>
>규칙 기반 및 온보딩된 트레이트에 대한 트레이트 실현을 채울 수 있습니다.

다음은 트레이트 실현을 채우는 방법입니다.

1. [!UICONTROL Audience Data > Signals > Search](으)로 이동하여 신호 검색을 실행하거나 [신호 대시보드](../../features/data-explorer/data-explorer-signals-dashboard.md)를 사용하여 새 트레이트에 사용할 신호를 식별하십시오.
1. 원하는 신호를 기반으로 새 트레이트를 만듭니다.
1. **[!UICONTROL Trait Expression]** 섹션의 **[!UICONTROL Backfill Options]**&#x200B;을(를) 사용하여 특성 실현을 채울 시간 간격을 선택하십시오. 사전 정의된 채우기 간격에는 1일, 7일, 14일, 30일이 포함됩니다. 최대 30일의 사용자 지정 날짜 범위를 선택할 수도 있습니다.

   ![특성 다시 채우기](assets/signals-trait-backfill.png)

1. (선택 사항) **[!UICONTROL Estimated Trait Realizations]** 섹션에서 **[!UICONTROL Estimate Realizations]**&#x200B;을(를) 클릭하면 지난 7일 동안 채워진 트레이트에 대한 예상 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 값을 볼 수 있습니다.

   ![트레이트 실현 예상](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >다음 연산자를 사용하는 표현식이 있는 트레이트에는 트레이트 다시 채우기 및 추정을 사용할 수 없습니다.
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`
1. 트레이트를 만듭니다.

트레이트 만들기가 완료되면 채워진 실현이 실현 통계에 포함됩니다.

트레이트를 채우는 방법에 대한 비디오 설명은 아래 비디오를 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## 트레이트 채우기 지연 {#trait-backfilling-latency}

새로 만든 트레이트는 만든 후 2~3시간 후에 대상자를 캡처하기 시작합니다. 그러나 [!DNL Audience Manager]이(가) 매일 수행하는 대량의 데이터로 인해 채워진 모집단은 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 그래프에 즉시 반영되지 않습니다.

Audience Manager은 특성 생성 후 48시간 이내에 채워진 모집단으로 [!UICONTROL Trait Graph]을(를) 업데이트합니다.

## 트레이트 채우기 제한 {#trait-backfilling-limit}

[!UICONTROL Data Explorer]을(를) 사용하면 매월 최대 50개의 트레이트를 채울 수 있으며 매월 1일에 채우기 카운터가 재설정됩니다.

>[!NOTE]
>
>트레이트 채우기 할당량은 이전 달에서 이월되지 않습니다. 예를 들어, 이번 달에 30개의 트레이트를 채우면 다음 달의 트레이트 채우기 할당량은 70개가 아닌 50개로 재설정됩니다.

## 보고에 미치는 영향 {#reporting-impact}

[!DNL Audience Manager]이(가) 이전 신호를 트레이트 실현으로 전환하므로 채워진 트레이트 실현은 [!UICONTROL Unique Trait Realizations] 및 [!UICONTROL Total Trait Population] 지표에 반영됩니다.

하지만 특성 생성일 전에 채워진 기록 지표로 [!UICONTROL Trait Graph], [!UICONTROL General Reports] 및 [!UICONTROL Trend Reports]은(는) 소급하여 업데이트되지 않습니다.
