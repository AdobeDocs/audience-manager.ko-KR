---
description: 트레이트 TTL (Time-to-Live) 간격이 세그먼트 멤버십에 미치는 영향
seo-description: 트레이트 TTL (Time-to-Live) 간격이 세그먼트 멤버십에 미치는 영향
seo-title: 세그먼트 및 트레이트 시간 설명
solution: Audience Manager
title: 세그먼트 작업 시간 설명
uuid: 5 B 2 C 6911-50 B 9-4 B 68-9 DD 4-21128 D 112 EAB
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Segment and Trait Time-to-Live Explained {#segment-time-to-live-explained}

How trait [!UICONTROL time-to-live] ([!DNL TTL]) interval affects segment membership.

<!-- segment-ttl-explained.xml -->

## 실시간 작업 시간

[!DNL TTL] 마지막 특성 수준 이벤트 이후 사이트 방문자가 세그먼트에 머무는 기간을 정의합니다. [!DNL TTL] 는 트레이트가 아니라 트레이트 위에 설정됩니다. Visitors fall out of a segment if they do not see a qualifying trait before the end of the [!DNL TTL] interval. The default [!DNL TTL] for new traits is 120 days. 0 일로 설정하면 트레이트 기간이 만료되지 않습니다. [트레이트 작성](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) 인터페이스의 [!UICONTROL Advanced Options] 섹션에서 트레이트를 만들거나 편집할 때 TTL 값을 설정합니다.

## [!DNL TTL] 세그먼트 그만두기

A user falls out of a segment if they do not see any of its traits within the [!DNL TTL] interval. For example, if you have a 1-trait segment with a 30 days [!DNL TTL], the user will drop out of that segment if they do not see the trait again within the 30 days.

![](assets/ttl_1.png)

## [!DNL TTL] 및 세그먼트 갱신

[!DNL TTL] 재설정 및 사용자가 기간 내에 해당 세그먼트의 트레이트를 보는 경우 세그먼트에 남아 [!DNL TTL] 있습니다. Also, because most segments contain multiple traits with their own [!DNL TTL] periods, a user can remain in a segment (and reset the [!DNL TTL] interval) as long as they keep seeing any traits associated with a segment. For example, say you have Segment 1 composed of Trait A (30 day [!DNL TTL]) and Trait B (15 day [!DNL TTL]). Assuming the user sees each trait only once, the illustration below outlines the [!DNL TTL] renewal process and total in-segment duration.

![](assets/ttl_2.png)

## [!DNL Audience Manager] TTLS는 타사 TTL 설정과 독립적입니다.

Remember, the [!DNL TTL] set on your [!DNL Audience Manager] pixel operates independently from the [!DNL TTL] set on other pixels used by third parties ([!DNL DSP]s, ad networks, etc.).

>[!MORE_ like_ this]
>
>* [트레이트 만료 간격 설정](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

