---
description: TTL(특성 시간 유지) 간격이 세그먼트 멤버십에 영향을 주는 방법입니다.
seo-description: TTL(특성 시간 유지) 간격이 세그먼트 멤버십에 영향을 주는 방법입니다.
seo-title: 세그먼트 및 트레이트 시간 설명
solution: Audience Manager
title: 세그먼트별 라이브 설명
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 1%

---


# 세그먼트 및 트레이트 유지 시간 설명 {#segment-time-to-live-explained}

특성 [!UICONTROL time-to-live] ([!DNL TTL]) 간격이 세그먼트 멤버십에 영향을 주는 방식입니다.

<!-- segment-ttl-explained.xml -->

## 라이브할 시간

[!DNL TTL] 마지막 트레이트 자격 이벤트 이후 사이트 방문자가 세그먼트에 남아 있는 기간을 정의합니다. [!DNL TTL] 는 세그먼트가 아닌 트레이트에 설정됩니다. Visitors fall out of a segment if they do not qualify for a trait before the end of the [!DNL TTL] interval. 새 트레이트의 기본값 [!DNL TTL] 은 120일입니다. 0일로 설정하면 트레이트가 만료되지 않습니다. [트레이트 생성 인터페이스 섹션에서 트레이트를 만들거나 편집할 때 TTL 값](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 을 [!UICONTROL Advanced Options] 설정합니다.

### 1일 TTL 설명

이 [!DNL TTL] 를 1일로 설정하면 TTL 타이머가 특성 구현 날짜의 남은 시간을 계산하지 않고 다음 날 트레이트 구현 종료 후에 시작됩니다.

Audience Manager은 다음 공식을 [!DNL TTL] [!DNL TTL] 기준으로 1일이 있는 트레이트의 만료를 계산합니다.

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **예 1**: 한 가지 특징이 1시 [!DNL UTC]에 1일 만에 나타났다 [!DNL TTL]. [!DNL TTL] 24 + 24 - 1 = 47시간 후에 만료됩니다.
* **예 2**: 한 가지 특징이 23시 [!DNL UTC]에 하루 만에 나타났다 [!DNL TTL]. [!DNL TTL] 24 + 24 - 23 = 25시간 후에 만료됩니다.

## [!DNL TTL] 세그먼트 삭제

사용자가 간격 내에 트레이트를 사용할 수 없는 경우 세그먼트에서 [!DNL TTL] 제외됩니다. 예를 들어 30일 [!DNL TTL]의 1트레이트 세그먼트가 있는 경우, 다음 30일 이내에 트레이트를 다시 사용할 수 없는 경우 해당 세그먼트에서 탈퇴합니다.

![](assets/ttl-explained.png)

## [!DNL TTL] 및 세그먼트 갱신

기간 [!DNL TTL] 내에 해당 세그먼트의 트레이트를 활용할 수 있는 경우 재설정되고 사용자가 세그먼트에 남아 [!DNL TTL] 있습니다. 또한 대부분의 세그먼트에는 고유한 [!DNL TTL] 간격과 여러 트레이트가 포함되어 있으므로 사용자는 세그먼트에 남아 있고 세그먼트와 연관된 트레이트에 대한 자격을 유지하는 한 [!DNL TTL] 간격을 재설정할 수 있습니다.

예를 들어 특성 A(30일)와 특성 B(15일)로 구성된 세그먼트 1이 있다고 [!DNL TTL][!DNL TTL]가정해 봅시다. 방문자가 각 트레이트에 대해 한 번만 자격이 있다고 가정할 경우 아래 그림에서는 갱신 프로세스 및 총 세그먼트 내 [!DNL TTL] 기간에 대한 개요를 설명합니다.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL은 타사 TTL 설정과 독립적입니다.

픽셀 [!DNL TTL] 의 [!DNL Audience Manager] 세트는 타사( [!DNL TTL][!DNL DSP]광고 네트워크 등)에서 사용하는 다른 픽셀에 대해 설정된 픽셀과 독립적으로 작동합니다.

>[!MORELIKETHIS]
>
>* [특성 만료 간격 설정](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

