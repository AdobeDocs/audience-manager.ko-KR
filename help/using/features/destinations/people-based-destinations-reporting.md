---
description: 'People-based destinations는 공유 가능한 대상의 개념을 Audience Manager에 도입합니다. 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소의 수를 이해하는 데 도움이 됩니다. '
seo-description: 'People-based destinations는 공유 가능한 대상의 개념을 Audience Manager에 도입합니다. 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소의 수를 이해하는 데 도움이 됩니다. '
seo-title: 공유 가능한 고객
solution: Audience Manager
title: 공유 가능한 고객
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# 공유 가능한 고객 {#shareable-audiences}

[!DNL People-Based Destinations] Adobe Audience Manager [!DNL Shareable Audiences] 의 인사이트 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소의 수를 이해하는 데 도움이 됩니다.

[!DNL Shareable Audiences] 은 컨텍스트 데이터를 해석하는 데 도움이 [!DNL People-Based Destinations]되는 지표입니다. [!UICONTROL Destinations] 페이지 및 [!UICONTROL Segment] 페이지에서 이 지표를 볼 수 있습니다.

## 공유 가능한 세그먼트 세그먼트 {#segment-shareable-audiences}

세그먼트 페이지의 [!DNL Segment Shareable Audience] 지표는 일치하는 Dpuuids가 있는 데이터 소스의 해시된 이메일 주소 수를 나타냅니다. 이 [이메일에는](../../reference/ids-in-aam.md)프로필 병합 규칙이 적용된 지정된 룩백 기간 동안 지정된 세그먼트에 대한 자격이 있으며 대상 관리자가 대상 플랫폼과 공유할 수 있습니다.

이 지표에는 1 일 룩백 기간이 있습니다. 이렇게 하면 특정 대상의 세그먼트에 대한 대상자 도달 수를 이해할 수 있습니다.

## 대상 공유 가능 대상 {#destination-shareable-audience}

사람 기반 대상 페이지의 [!DNL Destination Shareable Audience] 지표는 대상 관리자가 대상 플랫폼과 공유할 수 있는 해당 [대상 플랫폼에 대해 매핑된 모든](../../reference/ids-in-aam.md)세그먼트에서 대상 플랫폼과 공유할 수 있는 데이터 소스의 해시된 이메일 주소의 총 수를 나타냅니다.

![공유 가능한 대상](assets/dest-shareable-audiences.png)

이 지표는 라이프타임 룩백 기간을 갖습니다. 이렇게 하면 해시된 이메일에서 접근할 수 있는 대상의 규모를 이해하는 데 도움이 됩니다.

## 예

Audience Manager 고객의 데이터 소스는 110,000 [개의 DPUUID](../../reference/ids-in-aam.md) (CRM ID) 입니다. 100,000 개의 해시된 이메일 주소를 Audience Manager로 인제스트하여 여러 사람이 기반 대상에 사용하고 CRM ID에 대해 100,000 개의 해시된 이메일 주소에 대해 ID 동기화를 수행합니다. 고객은 [!DNL All Cross-Device Profiles] 병합 규칙을 사용하여 세 개의 대상 세그먼트를 만들 수 있습니다.

* 세그먼트 A가 대상 A에 매핑되는 인구 수가 10,000 인 세그먼트 A
* 인구 수가 대상 A에 매핑되는 세그먼트 B의 세그먼트 B
* 세그먼트 C가 대상 B에 매핑되고 인구 수가 50,000 인 세그먼트 C 입니다.

In this scenario:

* 공유 가능한 대상 = 10,000 세그먼트
* 세그먼트 B 공유 가능한 대상 = 20,000;
* 세그먼트 C 공유 가능한 대상 = 50,000;
* 대상 A 공유 가능한 대상 = 공유 가능한 대상 + 세그먼트 B 공유 가능한 대상 = 30,000
* 대상 B 공유 가능한 대상 = 세그먼트 C 공유 가능한 대상 = 50,000.

![shareable-audience-diagram](assets/shareable-audiences.png)

> [!NOTE]
>
> 위의 예에서, 세 세그먼트의 모든 80,000 개의 해시된 이메일 주소가 대상 플랫폼의 기존 계정과 일치하는지 의미하지는 않습니다. Audience Manager가 세 세그먼트의 해시된 식별자를 해당 대상에 보낸다는 것을 의미합니다. 대상 세그먼트를 사용자 기반 대상으로 보낼 때 파트너 측에서 대상 일치가 발생합니다. 대상 A 에는 최대 30,000 개의 일치하는 사용자 계정이 있을 수 있지만 대상 B 에는 최대 50,000 개의 일치하는 사용자 계정이 있을 수 있지만 일치 비율은 보장되지 않습니다. Adobe는 파트너 전용 지표에 액세스할 수 없습니다. 일치 비율에서 사람 기반 도착지 가시화에 대한 FAQ는 [일치 비율을](../../faq/faq-people-based-destinations.md#match-rates) 참조하십시오.
