---
description: '사용자 기반 대상에서는 Audience Manager에 공유 가능한 대상을 개념을 도입합니다. 이 지표는 해시된 이메일 주소 Audience Manager이 대상 플랫폼과 공유할 수 있는 수를 이해하는 데 도움이 됩니다. '
seo-description: '사용자 기반 대상에서는 Audience Manager에 공유 가능한 대상을 개념을 도입합니다. 이 지표는 해시된 이메일 주소 Audience Manager이 대상 플랫폼과 공유할 수 있는 수를 이해하는 데 도움이 됩니다. '
seo-title: 공유 가능한 대상
solution: Audience Manager
title: 공유 가능한 대상
feature: 사용자 기반 대상
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# 공유 가능한 대상 {#shareable-audiences}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떤 것도 법률적인 조언이 아닙니다. 법률 자문을 구하시려면 법률 자문을 구하십시오.

[!DNL People-Based Destinations] Audience Manager [!DNL Shareable Audiences] 에 개념을 주다. 이 지표는 해시된 이메일 주소 Audience Manager이 대상 플랫폼과 공유할 수 있는 수를 이해하는 데 도움이 됩니다.

[!DNL Shareable Audiences] 는 의 컨텍스트에서 대상 데이터를 해석하는 데 도움이 되는 지표입니다 [!DNL People-Based Destinations]. 이 지표는 [!UICONTROL Destinations] 페이지 및 [!UICONTROL Segment] 페이지에서 볼 수 있습니다.

## 세그먼트 공유 가능한 대상 {#segment-shareable-audiences}

세그먼트 페이지의 [!DNL Segment Shareable Audience] 지표는 일치하는 [DPUUIDs](../../reference/ids-in-aam.md)와 일치하는 데이터 소스의 해시된 이메일 주소 수를 나타내며, Audience Manager에 적용된 프로필 병합 규칙을 기준으로 볼 때 주어진 전환 기간에 정의된 세그먼트에도 적합합니다. 해당 세그먼트는 대상 플랫폼과 공유할 수 있습니다.

이 지표에는 1일 전환 확인 기간이 있습니다. 이렇게 하면 특정 대상의 세그먼트에 대한 대상 범위를 이해할 수 있습니다.

## 대상 공유 가능한 대상 {#destination-shareable-audience}

사용자 기반 대상 페이지의 [!DNL Destination Shareable Audience] 지표는 해당 Audience Manager이 해당 대상에 매핑된 모든 세그먼트에서 대상 플랫폼과 공유할 수 있는 [DPUUID](../../reference/ids-in-aam.md)와 일치하는 데이터 소스의 해시된 총 이메일 주소 수를 나타냅니다.

![공유 가능한 대상](assets/dest-shareable-audiences.png)

이 지표에는 라이프타임 전환 확인 기간이 있습니다. 이것은 해시된 이메일 주소 데이터 소스에서 전달할 수 있는 대상의 크기를 이해하는 데 도움이 됩니다.

## 예

Audience Manager 고객에게는 110,000의 [DPUUIDs](../../reference/ids-in-aam.md)(CRM ID)가 있는 데이터 소스가 있습니다. 해시된 10만 개의 이메일 주소를 Audience Manager에 수집하여 여러 사용자 기반 대상과 함께 사용하고 CRM ID에 대해 해시된 10만 개의 이메일 주소에 대한 ID 동기화를 수행합니다. 고객은 [!DNL All Cross-Device Profiles] 병합 규칙을 사용하여 세 개의 대상 세그먼트를 만들 수 있습니다.

* 모집단 수가 10,000명인 세그먼트 A가 대상 A에 매핑됩니다.
* 모집단 수가 20,000명인 세그먼트 B가 대상 A에 매핑됩니다.
* 모집단 수가 50,000명인 세그먼트 C가 대상 B에 매핑됩니다.

이 시나리오에서는

* 세그먼트 A 공유 가능한 대상 = 10,000;
* 세그먼트 B 공유 가능한 대상 = 20,000;
* 세그먼트 C 공유 가능한 대상 = 50,000;
* 대상 A 공유 가능한 대상 = 세그먼트 A 공유 가능한 대상 + 세그먼트 B 공유 가능한 대상 = 30,000;
* 대상 B 공유 가능한 대상 = 세그먼트 C 공유 가능한 대상 = 50,000입니다.

![shareable-audiences-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>위의 예에서 세 세그먼트의 해시된 이메일 주소 80,000개가 모두 대상 플랫폼의 기존 계정과 일치함을 의미하지는 않습니다. 즉, Audience Manager이 세 세그먼트의 해시된 식별자를 해당 대상으로 보냅니다. 대상 세그먼트를 사람 기반 대상에 보낼 때 파트너 측에서는 대상 일치가 발생합니다. 대상 A에는 최대 30,000개의 일치하는 사용자 계정이 있을 수 있지만 대상 B에는 최대 50,000개의 일치하는 사용자 계정이 있을 수 있지만 일치율에 대한 보장은 없습니다. Adobe은 파트너별 지표에 액세스할 수 없습니다. 일치율의 사용자 기반 대상 가시성에 대한 FAQ는 [일치율](../../faq/faq-people-based-destinations.md#match-rates)을 참조하십시오.
