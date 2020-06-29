---
description: '사용자 기반 목적지는 Audience Manager에 공유 가능한 대상을 도입합니다. 이 지표는 해시된 이메일 주소 Audience Manager이 대상 플랫폼과 공유할 수 있는 수를 파악하는 데 도움이 됩니다. '
seo-description: '사용자 기반 목적지는 Audience Manager에 공유 가능한 대상을 도입합니다. 이 지표는 해시된 이메일 주소 Audience Manager이 대상 플랫폼과 공유할 수 있는 수를 파악하는 데 도움이 됩니다. '
seo-title: 공유 가능한 대상
solution: Audience Manager
title: 공유 가능한 대상
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# 공유 가능한 대상 {#shareable-audiences}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 들어 있는 어떠한 것도 법적 권고사항이다. 법률 자문을 위해 법률 자문을 구할 수 있습니다.

[!DNL People-Based Destinations] Audience Manager의 개념을 [!DNL Shareable Audiences] 가져오다. 이 지표는 해시된 이메일 주소 Audience Manager이 대상 플랫폼과 공유할 수 있는 수를 파악하는 데 도움이 됩니다.

[!DNL Shareable Audiences] 는 대상 데이터를 컨텍스트 내에서 해석하는 데 도움이 되는 지표입니다 [!DNL People-Based Destinations]. 페이지와 페이지에서 이 지표를 볼 수 [!UICONTROL Destinations] [!UICONTROL Segment] 있습니다.

## 세그먼트 공유 가능한 대상 {#segment-shareable-audiences}

세그먼트 페이지의 [!DNL Segment Shareable Audience] 지표는 일치하는 DPUUID가 있는 데이터 소스에서 해시된 이메일 주소 수를 나타냅니다. [프로필 병합 규칙이 적용된 경우 해당 검색 기간에 정의된 세그먼트를 사용할 수 있으며 Audience Manager이 대상 플랫폼과 공유할 수 있습니다](../../reference/ids-in-aam.md).

이 지표는 1일 조회 기간이 있습니다. 이렇게 하면 특정 대상의 세그먼트에 대한 대상 범위를 이해할 수 있습니다.

## 대상 공유 가능한 대상 {#destination-shareable-audience}

사람 기반 대상 페이지의 [!DNL Destination Shareable Audience] 지표는 일치하는 [DPUUID가 있는 데이터 소스에서 해시된 이메일 주소의 총 수를 나타냅니다. Audience Manager은 해당 대상에 매핑된 모든 세그먼트에서 대상 플랫폼과 공유할 수 있습니다](../../reference/ids-in-aam.md).

![공유 가능한 대상자](assets/dest-shareable-audiences.png)

이 지표에는 라이프타임 룩백 기간이 있습니다. 이렇게 하면 해시된 이메일 주소 데이터 소스에서 도달할 수 있는 대상의 규모를 파악하는 데 도움이 됩니다.

## 예

Audience Manager 고객은 110,000개의 [DPUUID](../../reference/ids-in-aam.md) (CRM ID)가 있는 데이터 소스를 가지고 있습니다. 해시된 10만 개의 이메일 주소를 Audience Manager에 인제스트하여 여러 사람 기반 대상과 함께 사용하고, 해시된 CRM ID에 대해 10만 개의 이메일 주소에 대해 ID 동기화를 수행합니다. 고객은 병합 규칙을 사용하여 세 개의 대상 세그먼트를 만들 수 있습니다. [!DNL All Cross-Device Profiles]

* 인구 수가 10,000명인 세그먼트 A가 대상 A에 매핑됩니다.
* 인구 수가 20,000명인 세그먼트 B가 대상 A에 매핑됩니다.
* 인구 수가 50,000명인 세그먼트 C가 대상 B에 매핑됩니다.

In this scenario:

* 세그먼트 A 공유 가능한 대상자 = 10,000;
* 세그먼트 B 공유 가능한 대상 = 20,000;
* 세그먼트 C 공유 가능 대상 = 50,000;
* 대상 A 공유 가능한 대상 = 세그먼트 A 공유 가능한 대상 + 세그먼트 B 공유 가능한 대상 = 30,000;
* 대상 B 공유 가능 대상 = 세그먼트 C 공유 가능 대상 = 50,000입니다.

![shareable-audiences-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>위의 예에서, 세 개의 세그먼트에서 해시된 모든 80,000개의 이메일 주소가 대상 플랫폼의 기존 계정과 일치하지 않습니다. 이것은 Audience Manager이 세 세그먼트의 해시된 식별자를 각각의 대상으로 전송한다는 것을 의미합니다. 대상 세그먼트를 사람 기반 대상으로 보낼 때 파트너 쪽에서 대상 일치가 발생합니다. 대상 A에는 최대 30,000개의 일치하는 사용자 계정이 있을 수 있지만 대상 B에는 최대 50,000개의 일치하는 사용자 계정이 있을 수 있지만 일치율은 보장되지 않습니다. Adobe는 파트너별 지표에 액세스할 수 없습니다. 사람 [기반 대상](../../faq/faq-people-based-destinations.md#match-rates) 가시성에 대한 질문과 대답의 경우 일치율을 참조하십시오.
