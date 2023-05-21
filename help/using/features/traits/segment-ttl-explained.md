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
source-wordcount: '354'
ht-degree: 1%

---

# 세그먼트 및 트레이트 유지 시간 설명 {#segment-time-to-live-explained}

트레이트 방법 [!UICONTROL time-to-live] ([!DNL TTL]) 간격은 세그먼트 멤버십에 영향을 줍니다.

<!-- segment-ttl-explained.xml -->

## TTL(Time to Live)

[!DNL TTL] 는 마지막 트레이트 자격 이벤트 후 사이트 방문자가 세그먼트에 남아 있는 기간을 정의합니다. [!DNL TTL] 는 세그먼트가 아닌 트레이트에 대해 설정됩니다. 방문자가 종료 전에 트레이트에 대한 자격이 없으면 세그먼트에서 이탈됩니다. [!DNL TTL] 간격. 기본값 [!DNL TTL] 새 트레이트의 경우 120일입니다. 0일로 설정하면 트레이트가 만료되지 않습니다. [TTL 값 설정](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 에서 트레이트를 만들거나 편집할 때 [!UICONTROL Advanced Options] 트레이트 만들기 인터페이스의 섹션입니다.

### 1일 TTL 설명

를 설정할 때 [!DNL TTL] 1일까지 TTL 타이머는 트레이트 실현에 남은 시간을 계산하지 않고 트레이트 실현 다음 날에 시작됩니다.

Audience Manager 계산 [!DNL TTL] 1일의 트레이트 만료 [!DNL TTL] 다음 공식을 기반으로 합니다.

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **예 1**: 1시에 실현된 트레이트 [!DNL UTC], 1일 포함 [!DNL TTL]. [!DNL TTL] 은 24 + 24 - 1 = 47시간 후에 만료됩니다.
* **예제 2**: 23:00에 실현된 트레이트 [!DNL UTC], 1일 포함 [!DNL TTL]. [!DNL TTL] 은 24 + 24 - 23 = 25시간 후에 만료됩니다.

## [!DNL TTL] 및 세그먼트 드롭아웃

내의 트레이트에 대한 자격이 없는 경우 사용자가 세그먼트에서 이탈됩니다. [!DNL TTL] 간격. 예를 들어 30일이 있는 트레이트 1개가 있는 경우 [!DNL TTL], 향후 30일 이내에 트레이트에 대한 자격이 다시 주어지지 않는 경우 사용자는 해당 세그먼트에서 삭제됩니다.

![](assets/ttl-explained.png)

## [!DNL TTL] 및 세그먼트 갱신

다음 [!DNL TTL] 를 재설정하고, 사용자가 내에서 해당 세그먼트의 트레이트에 대한 자격이 있는 경우 세그먼트에 남아 있게 됩니다. [!DNL TTL] 마침표. 또한 대부분의 세그먼트에는 자체 트레이트가 있는 여러 트레이트가 포함되어 있습니다 [!DNL TTL] 간격: 사용자가 세그먼트에 남아 있을 수 있고 [!DNL TTL] 해당 세그먼트가 세그먼트와 연결된 모든 트레이트에 대해 자격이 되는 한 간격입니다.

예를 들어 세그먼트 1이 트레이트 A(30일)로 구성되어 있다고 가정해 보겠습니다 [!DNL TTL]) 및 트레이트 B (15일 [!DNL TTL]). 방문자가 각 트레이트에 대해 한 번만 자격을 얻는다고 가정할 경우 아래 그림은 다음을 간략하게 설명합니다. [!DNL TTL] 갱신 프로세스 및 총 세그먼트 내 기간.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL은 타사 TTL 설정과 독립적입니다

기억하십시오. [!DNL TTL] 설정 [!DNL Audience Manager] pixel은 [!DNL TTL] 타사에서 사용하는 다른 픽셀 설정([!DNL DSP]s, ad networks 등).

>[!MORELIKETHIS]
>
>* [트레이트 만료 간격 설정](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

