---
description: 트레이트 TTL(Time-to-Live) 간격이 세그먼트 멤버십에 미치는 영향
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: 세그먼트 TTL(Time to Live) 설명
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# 세그먼트 및 트레이트 유지 시간 설명 {#segment-time-to-live-explained}

트레이트 [!UICONTROL time-to-live]&#x200B;([!DNL TTL]) 간격이 세그먼트 멤버십에 미치는 영향.

<!-- segment-ttl-explained.xml -->

## TTL(Time to Live)

[!DNL TTL]은(는) 마지막 트레이트 자격 이벤트 후 사이트 방문자가 세그먼트에 남아 있는 기간을 정의합니다. [!DNL TTL]이(가) 세그먼트가 아닌 트레이트에 설정되어 있습니다. 방문자가 [!DNL TTL] 간격이 끝나기 전에 트레이트에 적합하지 않으면 세그먼트에서 이탈됩니다. 새 트레이트의 기본 [!DNL TTL]은(는) 120일입니다. 0일로 설정하면 트레이트가 만료되지 않습니다. 특성 만들기 인터페이스의 [ 섹션에서 특성을 만들거나 편집할 때 ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)TTL 값을 설정[!UICONTROL Advanced Options]합니다.

### 1일 TTL 설명

[!DNL TTL]을(를) 1일로 설정할 때 트레이트 실현 날짜의 남은 시간을 계산하지 않고 트레이트 실현 다음 날에 TTL 타이머가 시작됩니다.

Audience Manager은 다음 수식을 기반으로 하여 1일 [!DNL TTL]의 트레이트에 대한 [!DNL TTL] 만료를 계산합니다.

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **예 1**: 1:00 [!DNL UTC]에 실현된 트레이트(1일 [!DNL TTL]). [!DNL TTL]은(는) 24 + 24 - 1 = 47시간 후에 만료됩니다.
* **예 2**: 23:00 [!DNL UTC]에 실현된 트레이트(1일 [!DNL TTL]). [!DNL TTL]은(는) 24 + 24 - 23 = 25시간 후에 만료됩니다.

## [!DNL TTL] 및 세그먼트에서 드롭아웃

사용자가 [!DNL TTL] 간격 내에 트레이트에 대한 자격이 없으면 세그먼트에서 빠집니다. 예를 들어, 30일 [!DNL TTL]이(가) 있는 트레이트 1개가 있는 경우, 사용자가 향후 30일 이내에 트레이트에 대한 자격을 다시 얻지 못하면 해당 세그먼트에서 삭제됩니다.

![](assets/ttl-explained.png)

## [!DNL TTL] 및 세그먼트 갱신

[!DNL TTL]이(가) 재설정되고 사용자는 [!DNL TTL] 기간 내에 해당 세그먼트의 트레이트에 대한 자격이 있는 경우 세그먼트에 남아 있습니다. 또한 대부분의 세그먼트에는 자체 [!DNL TTL] 간격으로 여러 트레이트가 포함되어 있으므로 사용자는 세그먼트에 남아 해당 세그먼트와 관련된 모든 트레이트에 대한 자격을 유지하는 한 [!DNL TTL] 간격을 다시 설정할 수 있습니다.

예를 들어 트레이트 A(30일 [!DNL TTL])와 트레이트 B(15일 [!DNL TTL])로 구성된 세그먼트 1이 있다고 가정합니다. 방문자가 각 트레이트에 대해 한 번만 자격을 얻는다고 가정할 경우 아래 그림에서는 [!DNL TTL] 갱신 프로세스와 총 세그먼트 내 기간을 간략하게 설명합니다.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL은 타사 TTL 설정과 독립적입니다

[!DNL TTL] 픽셀에 설정된 [!DNL Audience Manager]은(는) 타사에서 사용하는 다른 픽셀([!DNL TTL], 광고 네트워크 등)에 설정된 [!DNL DSP]과(와) 독립적으로 작동합니다.

>[!MORELIKETHIS]
>
>* [트레이트 만료 간격 설정](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
