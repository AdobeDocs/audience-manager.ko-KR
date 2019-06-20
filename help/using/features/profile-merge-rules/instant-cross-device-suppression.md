---
description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-title: 즉각적인 장치 간 억제
title: 즉각적인 장치 간 억제
uuid: CB 11 B 9 CB -6 D 7 D -4 AA 9-91 B 0-C 2715857 D 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 즉각적인 장치 간 억제 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 는 이러한 장치에서 특정 경험이 발생하는 경우 연결되어 있는 여러 장치에 걸쳐 사용자를 표시하지 않도록 하는 기능입니다. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.

## 개요 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 다음 두 가지 주요 사용 사례를 제공합니다. 사용자 경험과 미디어 효율성이 개선되었습니다.

* **향상된 사용자 경험**: 이미 제품 또는 서비스를 구입한 사용자에게는 구매하기 전과 동일한 크리에이티브 전문가가 표시되지 않습니다. 대신 구입하지 않은 제품 또는 서비스에 대한 업셀링 또는 크로스셀링 메시지를 표시할 수 있습니다.
* **미디어 효율성**: 모든 [!DNL DSP]S. 사용자가 속한 여러 장치에 대해 주파수 끝을 실시간으로 적용할 수 있습니다.

The technical details of the real-time unsegmentation are described in length in [Profile Merge Rules and Device Un-Segmentation Processes](../../features/profile-merge-rules/merge-rule-unsegment.md). 위에서 설명한 사용 사례의 실질적인 구현을 읽어 보십시오.

## Do Not Target Once Converted {#do-not-target-once}

이미 전환된 사용자 (제품 구매, 구독 획득 등) 는 전환 전의 동일한 메시징은 표시되지 않습니다. You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. 규칙 기반 트레이트를 사용하여 실시간 트리거가 트리거되도록 전환 이벤트를 정의해야 합니다. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. 세그먼트를 실시간 서버 대 서버 대상에 매핑합니다. [서버-서버 대상에 세그먼트를 추가하는 방법을 읽어](../../features/destinations/manage-destinations.md#add-edit-segments)보십시오.

방문자는 세그먼트가 변환되지 않는 한 해당 세그먼트를 사용할 수 있습니다. 전환 트레이트를 적용받을 수 있는 즉시 세그먼트 규칙을 따르지 않고 세그먼트에서 즉시 제거됩니다.

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

최근 및 빈도 컨트롤을 설정하여 동일한 크리에이티브를 사용하여 사용자를 범람하지 않도록 할 수 있습니다. 이 시나리오에서 아래 단계에 설명된 대로 두 가지 트레이트가 있는 세그먼트를 만듭니다.

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. 규칙 기반 트레이트를 사용하여 비세그먼트에 대한 노출 이벤트를 정의하여 실시간으로 트리거해야 합니다. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. [실행 가능한 로그 파일](../../integration/media-data-integration/actionable-log-files.md) 및 [픽셀 호출에](../../integration/media-data-integration/impression-data-pixels.md)대해 자세히 알아보십시오.
1. 주파수 컨트롤을 두 번째 트레이트에 적용합니다. 원하는 경우 최근 컨트롤을 추가할 수도 있습니다. Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. 세그먼트를 실시간 서버 대 서버 대상에 매핑합니다. [서버-서버 대상에 세그먼트를 추가하는 방법을 읽어](../../features/destinations/manage-destinations.md#add-edit-segments)보십시오.

이 시나리오에서 사용자가 노출 횟수를 3 회 이상 누적한 후에는 이 세그먼트에서 제거되고 이 특정 크리에이티브가 더 이상 표시되지 않습니다.

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

처리와 관련된 다음과 같은 측면을 염두에 두십시오.

* 실시간으로 세그먼트 해제 기능을 사용하려면 원하는 세그먼트를 realtime server-to-server 대상에 매핑해야 합니다.
* [장치 그래프로](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)장치에 연결된 장치의 경우, 평가 및 세그먼테이션과 관련하여 4 장치 제한이 적용됩니다. This limitation is described in [Device Graph Options and Device Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).​
* 세그먼트 해제 명령은 장치 그래프로 연결된 여러 장치에 대해 24 시간마다 대상에 전송되는 일괄 처리 파일에 포함됩니다.
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. [!UICONTROL time-to-live (TTL)] 값이 있는 트레이트에 대해, 트레이트 [!DNL TTL] 충족 경우에도 *장치가* 다음에 표시될 때까지 장치가 자동으로 분할되지 않습니다. Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).​

## Important Aspects to Note - Timing {#timing-notes}

타이밍과 관련된 이러한 측면을 염두에 두십시오.

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).