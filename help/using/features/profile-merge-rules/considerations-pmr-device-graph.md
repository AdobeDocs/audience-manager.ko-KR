---
description: 실시간 세그먼트 모집단에서 거의 발생하지 않는 세그먼트에 대해 장치 그래프와 프로필 병합 규칙을 사용하지 마십시오.
seo-description: 실시간 세그먼트 모집단에서 거의 발생하지 않는 세그먼트에 대해 장치 그래프와 프로필 병합 규칙을 사용하지 마십시오.
seo-title: 장치 그래프와 프로필 병합 규칙에 대한 중요 고려 사항
title: 장치 그래프와 프로필 병합 규칙에 대한 중요 고려 사항
uuid: 93cd8861-210d-4c52-9cb7-6f2dd7dc018a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 장치 그래프와 프로필 병합 규칙에 대한 중요 고려 사항 {#important-considerations-for-profile-merge-rules-with-device-graphs}

실시간 세그먼트 모집단에서 거의 발생하지 않는 세그먼트에 [!UICONTROL Profile Merge Rules] [!UICONTROL Device Graph] 대해 를 사용하지 마십시오.

>[!IMPORTANT]
>
>가 잘못 구성된 [!UICONTROL Profile Merge Rule] 경우 배치 대상으로 내보내기한 세그먼트 모집단 수가 예상보다 현저히 낮아질 수 있습니다.

장치 그래프와 [프로필 병합 규칙을 사용하는](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) 세그먼트는 세그먼트가 만들어진 후 Audience Manager의 Edge Server [에서](../../reference/system-components/components-edge.md) 실시간으로 표시되는 장치에 대해서만 평가됩니다.

A [!UICONTROL Profile Merge Rule] 가 있는 A에는 [!UICONTROL Device Graph] 아래와 같이 다음 장치 옵션 중 하나가 선택되어 있습니다.

![](assets/pmr-considerations-1.png)

실시간으로 세그먼트에 적합한 장치는 [세그먼트의 실시간 모집단으로](../../features/segments/segment-builder-data.md#segment-populations)측정됩니다.

![](assets/pmr-considerations-2.png)

실시간 세그먼트가 적으면 세그먼트에 대해 적격한 장치 중 거의 실시간으로 표시되지 않습니다. 최상의 성능을 위해 실시간 모집단에서 거의 사용되지 않는 세그먼트는 아래 이미지와 같이 [!UICONTROL Profile Merge Rule] 세트를 사용하여 *[!UICONTROL Current Device]*&#x200B;모집단화를 평가해야 합니다.

![](assets/pmr-considerations-3.png)

이 값을 [!UICONTROL Profile Merge Rule] 평가하도록 설정하면 모든 장치(실시간으로 표시되는 장치뿐만 아니라)가 세그먼트에 대해 평가됩니다 *[!UICONTROL Current Device]* . 세그먼트에 대해 자격을 부여받은 모든 장치는 아래와 같이 총 세그먼트 모집단으로 정의됩니다.

![](assets/pmr-considerations-4.png)