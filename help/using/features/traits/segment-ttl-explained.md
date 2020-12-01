---
description: TTL(특성 시간 유지) 간격이 세그먼트 멤버십에 영향을 주는 방법입니다.
seo-description: TTL(특성 시간 유지) 간격이 세그먼트 멤버십에 영향을 주는 방법입니다.
seo-title: 세그먼트 및 라이브 시간 설명
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

특성 [!UICONTROL time-to-live]([!DNL TTL]) 간격이 세그먼트 멤버십에 영향을 주는 방식입니다.

<!-- segment-ttl-explained.xml -->

## 라이브할 시간

[!DNL TTL] 마지막 트레이트 자격 이벤트 이후 사이트 방문자가 세그먼트에 남아 있는 기간을 정의합니다. [!DNL TTL] 는 세그먼트가 아닌 트레이트에 설정됩니다. 방문자가 [!DNL TTL] 간격이 끝나기 전에 트레이트를 사용할 수 없는 경우 세그먼트에서 벗어납니다. 새 트레이트의 기본 [!DNL TTL]은 120일입니다. 0일로 설정하면 트레이트가 만료되지 않습니다. [트레이트 생성 인터페이스 ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 섹션에서 트레이트를 만들거나 편집할 때 TTL  [!UICONTROL Advanced Options] 값을 설정합니다.

### 1일 TTL 설명

[!DNL TTL]을 1일로 설정할 때 TTL 타이머는 트레이트 구현 날짜에 남은 시간을 계산하지 않고 트레이트 구현 종료 후 다음 날에 시작됩니다.

Audience Manager은 다음 공식을 기준으로 1일이 [!DNL TTL]인 트레이트에 대해 [!DNL TTL] 만료 기간을 계산합니다.

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **예 1**:한 가지 특징이 1시 [!DNL UTC]에 1일 만에 나타났다 [!DNL TTL]. [!DNL TTL] 24 + 24 - 1 = 47시간 후에 만료됩니다.
* **예 2**:한 가지 특징이 23시 [!DNL UTC]에 하루 만에 나타났다 [!DNL TTL]. [!DNL TTL] 24 + 24 - 23 = 25시간 후에 만료됩니다.

## [!DNL TTL] 세그먼트 삭제

사용자가 [!DNL TTL] 간격 내에 트레이트를 사용할 수 없는 경우 세그먼트에서 벗어납니다. 예를 들어 30일 [!DNL TTL]에 해당하는 1개의 트레이트 세그먼트가 있는 경우, 다음 30일 이내에 트레이트를 다시 사용할 수 없는 경우 사용자는 해당 세그먼트에서 제외됩니다.

![](assets/ttl-explained.png)

## [!DNL TTL] 및 세그먼트 갱신

[!DNL TTL]이(가) 재설정되고 사용자가 [!DNL TTL] 기간 내에 해당 세그먼트의 트레이트를 자격을 얻을 경우 세그먼트에 남아 있습니다. 또한 대부분의 세그먼트에는 고유한 [!DNL TTL] 간격의 여러 트레이트가 포함되어 있으므로 사용자는 세그먼트에 남아 있고 세그먼트와 연관된 트레이트에 대한 자격이 유지된다면 [!DNL TTL] 간격을 재설정할 수 있습니다.

예를 들어 특성 A(30일 [!DNL TTL])와 특성 B(15일 [!DNL TTL])로 구성된 세그먼트 1이 있다고 가정합니다. 방문자가 각 트레이트에 대해 한 번만 자격이 있다고 가정할 경우, 아래 그림에서는 [!DNL TTL] 갱신 프로세스와 총 세그먼트 내 기간에 대한 개요를 제공합니다.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL은 타사 TTL 설정과 독립적입니다.

[!DNL Audience Manager] 픽셀에 설정된 [!DNL TTL]은 제3자가 사용하는 다른 픽셀([!DNL DSP]s, 광고 네트워크 등)에 대해 [!DNL TTL] 세트와 독립적으로 작동합니다.

>[!MORELIKETHIS]
>
>* [특성 만료 간격 설정](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

