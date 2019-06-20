---
description: 이 섹션에는 테스트 그룹에 대한 일반 정보와 이것이 나누어진 테스트 세그먼트, 선택한 전환 트레이트 및 매핑된 대상이 표시됩니다. 또한 이 섹션에서는 테스트 그룹을 복제 또는 삭제하는 컨트롤을 제공합니다.
seo-description: 이 섹션에는 테스트 그룹에 대한 일반 정보와 이것이 나누어진 테스트 세그먼트, 선택한 전환 트레이트 및 매핑된 대상이 표시됩니다. 또한 이 섹션에서는 테스트 그룹을 복제 또는 삭제하는 컨트롤을 제공합니다.
seo-title: 테스트 그룹 정보
solution: Audience Manager
title: 테스트 그룹 정보
topic: DIL API
uuid: a 49 dfdb 3-21 e 1-4 c 3 d-b 957-4 d 445 f 890124
translation-type: tm+mt
source-git-commit: 668b8ddded63acfa3479860f878cbf84b4f74218

---


# Test Group Information {#test-group-information}

이 섹션에는 테스트 그룹에 대한 일반 정보와 이것이 나누어진 테스트 세그먼트, 선택한 전환 트레이트 및 매핑된 대상이 표시됩니다. 또한 이 섹션에서는 테스트 그룹을 복제 또는 삭제하는 컨트롤을 제공합니다.

테스트 그룹에 사용한 기준선 세그먼트와 테스트 세그먼트를 분할하는 방법에 대한 정보도 볼 수 있습니다.

The **[!UICONTROL Test Segments]** are populated randomly with users from the baseline segment you used for the test group. 개요는 각 테스트 세그먼트에 할당한 사용자의 백분율을 보여줍니다.

**[!UICONTROL Conversion Traits]** The drive for the reporting groups. To designate a trait as a conversion, when creating or editing traits in the [!UICONTROL Trait Builder], select **Conversion** as **[Event Type](../../features/traits/create-onboarded-rule-based-traits.md).**

The **[!UICONTROL Destinations]** card is collapsible. 화살표를 눌러 개별 대상을 열거나 닫고, 다음과 같이 매핑되는 대상을 기준으로 그룹화된 테스트 세그먼트에 대해 다음 정보를 얻습니다.

* 각 대상에 할당된 기본 세그먼트의 총 모집단에서의 장치 수입니다.
* 매핑 키;
* 매핑 값;
* [!DNL URL] &amp; secure [!DNL URL] for [!DNL URL] destination.

>[!NOTE]
>
>테스트 그룹을 완료한 후에는 편집할 수 없으므로 일시 중지하거나 삭제하거나 복제할 수만 있습니다.

![](assets/test-groups-information.PNG)