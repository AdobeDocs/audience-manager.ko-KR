---
description: 트레이트 TTL(time-to-live) 간격이 세그먼트 멤버십에 미치는 영향.
seo-description: 트레이트 TTL(time-to-live) 간격이 세그먼트 멤버십에 미치는 영향.
seo-title: 세그먼트 및 트레이트 유지 시간 설명
solution: Audience Manager
title: 세그먼트 사용 시간 설명
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: 트레이트
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# 세그먼트 및 트레이트 유지 시간 설명 {#segment-time-to-live-explained}

트레이트 [!UICONTROL time-to-live]([!DNL TTL]) 간격이 세그먼트 멤버십에 미치는 영향

<!-- segment-ttl-explained.xml -->

## Time to Live

[!DNL TTL] 마지막 트레이트 자격 이벤트 후 사이트 방문자가 세그먼트에 남아 있는 시간을 정의합니다. [!DNL TTL] 는 세그먼트가 아니라 트레이트에 대해 설정됩니다. 방문자가 [!DNL TTL] 간격이 끝나기 전에 트레이트에 대한 자격이 없으면 세그먼트에서 이탈됩니다. 새 트레이트에 대한 기본 [!DNL TTL]은 120일입니다. 0일로 설정하면 트레이트가 만료되지 않습니다. [트레이트 만들기 인터페이스](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 의 섹션에서 트레이트를 만들거나 편집할  [!UICONTROL Advanced Options] 때 TTL 값을 설정합니다.

### 1일 TTL 설명

[!DNL TTL]을 1일로 설정할 때 TTL 타이머는 트레이트 실현일에 남은 시간을 계산하지 않고, 트레이트 실현 다음 날 시작합니다.

Audience Manager은 다음 공식을 기준으로 1일 [!DNL TTL]이 있는 트레이트에 대해 [!DNL TTL] 만료를 계산합니다.

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **예제 1**:1일 [!DNL UTC]로 1시에 실현되는 트레이트  [!DNL TTL]. [!DNL TTL] 은 24 + 24 - 1 = 47시간 후에 만료됩니다.
* **예제 2**:한 트레이트가 23:00 [!DNL UTC]에 실현되었으며, 하루  [!DNL TTL]. [!DNL TTL] 은 24 + 24 - 23 = 25시간 후에 만료됩니다.

## [!DNL TTL] 세그먼트에서 삭제

사용자가 [!DNL TTL] 간격 내에 트레이트에 대한 자격이 없는 경우 세그먼트에서 이탈됩니다. 예를 들어 30일 [!DNL TTL]에 1개의 트레이트 세그먼트가 있는 경우, 다음 30일 이내에 트레이트에 대한 자격이 다시 부여되지 않으면 사용자가 해당 세그먼트에서 제외됩니다.

![](assets/ttl-explained.png)

## [!DNL TTL] 및 세그먼트 갱신

[!DNL TTL] 은 재설정되고, 사용자가 [!DNL TTL] 기간 내에 해당 세그먼트의 트레이트에 대한 자격이 있는 경우 세그먼트에 남아 있습니다. 또한 대부분의 세그먼트에는 고유한 [!DNL TTL] 간격이 있는 여러 트레이트가 포함되어 있으므로 사용자가 세그먼트에 남아 있고 세그먼트와 연관된 트레이트에 대해 자격이 계속 되는 한 [!DNL TTL] 간격을 재설정할 수 있습니다.

예를 들어, 트레이트 A(30일 [!DNL TTL])와 트레이트 B(15일 [!DNL TTL])로 구성된 세그먼트 1이 있다고 가정해 보겠습니다. 방문자가 각 트레이트에 대해 한 번만 자격이 있다고 가정할 경우 아래 그림에서는 [!DNL TTL] 갱신 프로세스와 총 세그먼트 내 기간을 간략하게 설명합니다.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL은 타사 TTL 설정과 독립적입니다

[!DNL Audience Manager] 픽셀에 설정된 [!DNL TTL] 픽셀은 타사에서 사용하는 다른 픽셀([!DNL DSP]s, 광고 네트워크 등)에 설정된 [!DNL TTL]와는 독립적으로 작동합니다.

>[!MORELIKETHIS]
>
>* [트레이트 만료 간격 설정](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

