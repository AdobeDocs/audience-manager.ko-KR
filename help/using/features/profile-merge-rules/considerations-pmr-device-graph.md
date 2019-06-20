---
description: 실시간 세그먼트 모집단이 거의 없는 세그먼트에 대해서는 장치 그래프와 함께 프로필 병합 규칙을 사용하지 마십시오.
seo-description: 실시간 세그먼트 모집단이 거의 없는 세그먼트에 대해서는 장치 그래프와 함께 프로필 병합 규칙을 사용하지 마십시오.
seo-title: 장치 그래프가 있는 프로필 병합 규칙에 대한 중요한 고려 사항
title: 장치 그래프가 있는 프로필 병합 규칙에 대한 중요한 고려 사항
uuid: 93 CD 8861-210 D -4 c 52-9 CB 7-6 F 2 DD 7 DC 018 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Important Considerations for Profile Merge Rules with Device Graphs {#important-considerations-for-profile-merge-rules-with-device-graphs}

Avoid using [!UICONTROL Profile Merge Rules] with a [!UICONTROL Device Graph] for segments which have little to no real-time segment population.

>[!IMPORTANT]
>
>If the [!UICONTROL Profile Merge Rule] is configured incorrectly, the segment population exported to batch destinations may be significantly lower than expected.

Segments using a [Profile Merge Rule with a Device Graph](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) are only evaluated against devices seen in real-time on [Audience Manager’s Edge Servers](../../reference/system-components/components-edge.md) after the segment has been created.

Remember, a [!UICONTROL Profile Merge Rule] with a [!UICONTROL Device Graph] has one of the following device options selected, as shown below.

![](assets/pmr-considerations-1.png)

Devices that qualify for a segment in real-time are measured by the [segment’s real-time population](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

실시간 세그먼트 모집단 수가 낮으면 세그먼트에 대한 적격한 장치가 실시간으로 표시됩니다. For best performance, segments with little to no real-time population should use a [!UICONTROL Profile Merge Rule] set to evaluate the *[!UICONTROL Current Device]*, like in the image below.

![](assets/pmr-considerations-3.png)

Setting the [!UICONTROL Profile Merge Rule] to evaluate the *[!UICONTROL Current Device]* ensures that all devices (not just those seen in real-time) are evaluated for the segment. 세그먼트에 대한 적격한 모든 장치는 아래에서 보듯이 총 세그먼트 모집단에 의해 정의됩니다.

![](assets/pmr-considerations-4.png)