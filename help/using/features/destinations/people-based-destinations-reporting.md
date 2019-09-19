---
description: '사람 기반 목적지는 Audience Manager에 공유 가능한 대상이라는 개념을 도입합니다. 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소 수를 파악하는 데 도움이 됩니다. '
seo-description: '사람 기반 목적지는 Audience Manager에 공유 가능한 대상이라는 개념을 도입합니다. 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소 수를 파악하는 데 도움이 됩니다. '
seo-title: 공유 가능한 대상
solution: Audience Manager
title: 공유 가능한 대상
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 공유 가능한 대상 {#shareable-audiences}

[!DNL People-Based Destinations] adobe Audience Manager [!DNL Shareable Audiences] 에 활용 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소 수를 파악하는 데 도움이 됩니다.

[!DNL Shareable Audiences] 는 대상 데이터를 컨텍스트 기반으로 해석하는 데 도움이 되는 지표입니다 [!DNL People-Based Destinations]. 이 지표는 [!UICONTROL Destinations] 페이지와 [!UICONTROL Segment] 페이지에서 볼 수 있습니다.

## 세그먼트 공유 가능한 대상 {#segment-shareable-audiences}

세그먼트 페이지의 [!DNL Segment Shareable Audience] 지표는 일치하는 DPUUID와 함께 데이터 소스에서 해시된 이메일 주소 수를 나타냅니다. [이](../../reference/ids-in-aam.md)지표는 지정된 룩백 기간에서 정의된 세그먼트를 자격을 가지며, 프로필 병합 규칙이 해당 지표에 적용되어 있고 Audience Manager가 대상 플랫폼과 공유할 수 있습니다.

이 지표에는 1일 조회 기간이 있습니다. 이렇게 하면 특정 대상의 세그먼트에 대한 대상 범위를 이해할 수 있습니다.

## 대상 공유 가능 대상 {#destination-shareable-audience}

사람 기반 대상 페이지의 [!DNL Destination Shareable Audience] 지표는 Audience Manager가 해당 대상에 매핑된 모든 세그먼트에서 대상 [플랫폼과 공유할 수 있는](../../reference/ids-in-aam.md)DPUUID가 있는 데이터 소스의 해시 이메일 주소의 총 수를 나타냅니다.

![공유 가능한 고객](assets/dest-shareable-audiences.png)

이 지표에는 라이프타임 룩백 기간이 있습니다. 이렇게 하면 해시된 이메일 주소 데이터 소스에서 도달할 수 있는 대상의 규모를 파악하는 데 도움이 됩니다.

## 예

Audience Manager 고객에게는 110,000개의 DPUUID(CRM ID) [가](../../reference/ids-in-aam.md) 있는 데이터 소스가 있습니다. Audience Manager에 해시된 100,000개의 이메일 주소를 인제스트하여 여러 사람 기반 대상과 함께 사용하고 CRM ID에 대해 해시된 100,000개의 이메일 주소에 대한 ID 동기화를 수행합니다. 고객은 병합 규칙을 사용하여 다음 세 개의 대상 세그먼트를 만들 수 있습니다. [!DNL All Cross-Device Profiles]

* 인구 수가 10,000명인 세그먼트 A가 대상 A에 매핑됩니다.
* 인구 수가 20,000명인 세그먼트 B가 대상 A에 매핑됩니다.
* 인구 수가 50,000명인 세그먼트 C가 대상 B에 매핑됩니다.

이 시나리오에서:

* 세그먼트 A 공유 가능한 대상자 = 10,000;
* 세그먼트 B 공유 가능한 대상자 = 20,000;
* 세그먼트 C 공유 가능한 대상자 = 50,000;
* 대상 A 공유 가능한 대상자 = 세그먼트 A 공유 가능한 대상자 + 세그먼트 B 공유 가능한 대상자 = 30,000;
* 대상 B 공유 가능한 대상자 = 세그먼트 C 공유 가능한 대상자 = 50,000입니다.

![shareable-audiences-diagram](assets/shareable-audiences.png)

> [!NOTE]
>
> 위의 예에서, 세 개의 세그먼트에서 해시된 모든 80,000개의 이메일 주소가 대상 플랫폼의 기존 계정과 일치한다는 의미는 아닙니다. 이것은 Audience Manager가 세 세그먼트의 해시된 식별자를 각각의 대상으로 전송한다는 것을 의미합니다. 고객 세그먼트를 사람 기반 대상으로 보낼 때 파트너 측에서 고객 일치를 수행합니다. 대상 A에는 최대 30,000개의 일치하는 사용자 계정이 있을 수 있지만 대상 B에는 최대 50,000개의 일치하는 사용자 계정이 있을 수 있지만 일치율은 보장되지 않습니다. Adobe는 파트너별 지표에 액세스할 수 없습니다. 일치율의 [사람](../../faq/faq-people-based-destinations.md#match-rates) 기반 대상 가시성에 대한 FAQ는 비율 일치를 참조하십시오.
