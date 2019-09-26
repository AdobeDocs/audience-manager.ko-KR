---
description: '사람 기반 목적지는 Audience Manager에 공유 가능한 대상이라는 개념을 도입합니다. 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소 수를 파악하는 데 도움이 됩니다. '
seo-description: '사람 기반 목적지는 Audience Manager에 공유 가능한 대상이라는 개념을 도입합니다. 이 지표는 Audience Manager가 대상 플랫폼과 공유할 수 있는 해시된 이메일 주소 수를 파악하는 데 도움이 됩니다. '
seo-title: 공유 가능한 대상
solution: Audience Manager
title: 공유 가능한 대상
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# 공유 가능한 대상 {#shareable-audiences}

>[!IMPORTANT]
>이 문서에는 이 기능의 설정 및 사용을 안내하는 제품 설명서가 포함되어 있습니다. 여기에 포함된 어떠한 것도 법적 충고는 아닙니다. 법률 자문을 위해 법률 자문을 구하십시오.

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

* Segment A Shareable Audience = 10,000;
* Segment B Shareable Audience = 20,000;
* Segment C Shareable Audience = 50,000;
* Destination A Shareable Audience = Segment A Shareable Audience + Segment B Shareable Audience = 30,000;
* Destination B Shareable Audience = Segment C Shareable Audience = 50,000.

![shareable-audiences-diagram](assets/shareable-audiences.png)

> [!NOTE]
>
> In the example above, it does not mean that all the 80,000 hashed email addresses from the three segments match existing accounts in the destination platforms. It only means that Audience Manager sends the hashed identifiers from the three segments to their respective destinations. When sending audience segments to people-based destinations, audience matching happens on the partner side. Destination A may have up to 30,000 matching user accounts, whereas Destination B may have up to 50,000 matching user accounts, but there is no guarantee of match rates. Adobe does not have access to partner-specific metrics. See Match Rates for frequently asked questions about People-Based Destinations visibility in match rates.[](../../faq/faq-people-based-destinations.md#match-rates)
