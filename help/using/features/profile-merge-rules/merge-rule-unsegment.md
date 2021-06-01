---
description: 세그먼테이션 해제 는 세그먼트에서 장치 프로필을 분류하고 제거하는 프로세스에 대해 설명합니다. 세그먼트에서 장치 프로필을 제거하는 기능은 프로필 병합 규칙을 만드는 데 사용되는 장치 옵션에 따라 다릅니다.
seo-description: 세그먼테이션 해제 는 세그먼트에서 장치 프로필을 분류하고 제거하는 프로세스에 대해 설명합니다. 세그먼트에서 장치 프로필을 제거하는 기능은 프로필 병합 규칙을 만드는 데 사용되는 장치 옵션에 따라 다릅니다.
seo-title: 프로필 병합 규칙 및 장치 세그먼테이션 해제 프로세스
solution: Audience Manager
title: 프로필 병합 규칙 및 장치 세그먼테이션 해제 프로세스
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: 프로필 병합
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# 프로필 병합 규칙 및 장치 세그먼테이션 해제 프로세스 {#profile-merge-rules-and-device-un-segmentation-processes}

세그먼테이션 해제 는 세그먼트에서 장치 프로필을 분류하고 제거하는 프로세스에 대해 설명합니다. 세그먼트에서 장치 프로필을 제거하는 기능은 [!UICONTROL Profile Merge Rule]을(를) 만드는 데 사용되는 장치 옵션에 따라 다릅니다.

## 사용 가능한 장치 옵션 {#device-options}

미리 알림으로 [!UICONTROL Device Options]은 [!UICONTROL Profile Merge Rule]를 만들거나 편집할 때 [!UICONTROL Profile Merge Rules Setup] 섹션에서 사용할 수 있습니다.

## 현재 장치 프로필 옵션 및 장치 세그먼테이션 해제 {#current-device-profile-options}

**[!UICONTROL Device Profile]** 는 장치에 대한 기본 장치 프로필 옵션입니다 [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] 에서는 옵션을 사용할 때 세그먼트에서 장치  [!UICONTROL Profile Merge Rule] 프로필을 제거할 수  **[!UICONTROL Device Profile]** 있습니다. 이러한 조건에서 세그먼테이션은 다음 경우에 발생합니다.

* 장치 프로필이 120일 동안 비활성 상태였습니다. 주별 데이터 정리 프로세스는 세그먼트에서 비활성 장치 프로필을 제거합니다.
* 장치 프로필을 업데이트하거나 변경하면 해당 장치가 세그먼트에 대한 자격이 취소되므로 더 이상 장치가 세그먼트에 적합하지 않습니다. 이러한 일은 세그먼트 자격 기준이 변경되거나 [!DNL AND NOT] 연산자를 세그먼트 규칙에 적용하거나, [최신성 및 빈도](../segments/recency-and-frequency.md) 설정을 보다 작거나 같은 설정을 사용하는 조건을 지정할 때 발생합니다. 사용 사례는 [즉각적인 장치 간 억제](instant-cross-device-suppression.md) 설명서에 설명되어 있습니다.

![장치 전용](assets/device-only.png)

## 장치 옵션이 없고 장치 세그먼테이션 해제 {#no-device-option}

[!DNL Audience Manager] 에서는  [!UICONTROL Profile Merge Rule] + 옵션을 사용할 때 세그먼트에서 교차 장치 ID **[!UICONTROL Current Authenticated Profiles]** 를 제거할 수  **[!UICONTROL No Device Profile]** 있습니다. 이러한 조건에서, 교차 장치 ID가 더 이상 세그먼트에 자격을 부여하지 않을 때 세그먼테이션 해제가 발생합니다. 이는 교차 장치 프로필에 대한 업데이트 또는 변경 내용이 세그먼트 자격을 잃게 되기 때문입니다. 이러한 일은 세그먼트 자격 기준이 변경되거나 [!UICONTROL AND NOT] 연산자를 세그먼트 규칙에 적용하거나, [최신성 및 빈도](../segments/recency-and-frequency.md) 설정을 보다 작거나 같은 설정을 사용하는 조건을 지정할 때 발생합니다. 사용 사례는 [즉각적인 장치 간 억제](instant-cross-device-suppression.md) 설명서에 설명되어 있습니다.

![](assets/current-no-device.png)

## 장치 그래프 옵션 및 장치 세그먼테이션 해제 {#device-graph-options-unsegmentation}

[!DNL Audience Manager] 에서는 장치 그래프 옵션을 사용할 때 세그먼트에서 여러 장치  [!UICONTROL Profile Merge Rule] 프로필을 제거할 수 있습니다. 세그먼테이션 해제는 병합된 이 프로필에 대한 업데이트 또는 변경 사항이 세그먼트에서 비활성화되므로 장치 그래프에서 장치의 병합된 프로필이 더 이상 세그먼트에 적합하지 않을 때 발생합니다. 이러한 일은 세그먼트 자격 기준이 변경되거나 [!UICONTROL AND NOT] 연산자를 세그먼트 규칙에 적용하거나, [최신성 및 빈도](../segments/recency-and-frequency.md) 설정을 보다 작거나 같은 설정을 사용하는 조건을 지정할 때 발생합니다. 사용 사례는 [즉각적인 장치 간 억제](instant-cross-device-suppression.md) 설명서에 설명되어 있습니다.

>[!NOTE]
>
>**세그먼트 평가 및 결격에 대한 100개의 장치 제한**.
>Audience Manager은 장치 그래프를 사용하는 프로필 병합 규칙으로 세그먼트를 평가할 때 최대 100개의 장치를 병합합니다. Audience Manager은 [인증된 프로필](../../reference/visitor-authentication-states.md) (교차 장치 ID)로 현재 장치 및 현재 장치에 연결된 최대 99개의 장치를 평가합니다. 세그먼트 해제 신호가 발생하면 현재 장치 및 추가 장치가 대상의 세그먼트에서 제거됩니다.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [프로필 병합 규칙 및 장치 그래프 FAQ](../../faq/faq-profile-merge.md)
* [즉각적인 장치 간 억제](instant-cross-device-suppression.md)

