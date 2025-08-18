---
description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: 즉각적인 장치 간 억제
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# 즉각적인 장치 간 억제 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression]은(는) 이러한 장치에서 특정 경험이 발생할 때 연결된 여러 장치에서 사용자를 표시하지 않는 기능입니다. [!UICONTROL Instant Cross-Device Suppression] 기능을 사용하여 장치 간에 일관된 환경을 사용자에게 제공합니다. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.

## 개요 {#overview}

[!UICONTROL Instant Cross-Device Suppression]은(는) 향상된 사용자 경험과 미디어 효율성이라는 두 가지 주요 사용 사례를 제공합니다.

* **향상된 사용자 환경**: 제품이나 서비스를 이미 구매한 사용자에게는 구매 전과 동일한 크리에이티브가 표시되지 않습니다. 대신 구매하지 않은 제품이나 서비스에 대한 상향 판매 또는 교차 판매 메시지를 표시할 수 있습니다.
* **미디어 효율성**: 모든 [!DNL DSP]에 글로벌 빈도 상한을 적용하여 캠페인 지출을 최적화합니다. 주파수 캡은, 사용자에 속하는 복수의 디바이스에 대해 실시간으로 작동될 수 있다.

실시간 세그먼테이션 해제의 기술적 세부 정보는 [프로필 병합 규칙 및 장치 세그먼테이션 해제 프로세스](merge-rule-unsegment.md)에 자세히 설명되어 있습니다. 위에서 설명한 사용 사례를 실제로 구현하려면 계속 읽어 보십시오.

## 변환한 후에는 타깃팅하지 않음 {#do-not-target-once}

이미 전환(제품 구매, 구독 획득 등)한 사용자에게 전환 전과 동일한 메시지가 표시되지 않도록 합니다. 다음과 같이 [!UICONTROL AND NOT] 논리를 사용하여 이를 가져올 수 있습니다.

1. 아래 이미지에 표시된 대로 두 트레이트를 사용하여 세그먼트를 만들고 [!UICONTROL AND NOT] 논리를 사용합니다. 실시간으로 트리거될 세그먼트 해제에 대한 전환 이벤트를 정의하려면 규칙 기반 트레이트를 사용해야 합니다. [규칙 기반 특성을 만드는 방법](../traits/create-onboarded-rule-based-traits.md)에 대해 자세히 알아보세요.
2. 실시간 서버 간 대상에 세그먼트를 매핑합니다. [서버 간 대상](../destinations/add-edit-segments.md)에 세그먼트를 추가하는 방법에 대해 읽어 보십시오.

방문자는 전환되지 않은 한 세그먼트에 대한 자격이 있습니다. 전환 트레이트에 대한 자격이 주어지면 즉시 세그먼트 규칙을 따르는 것을 중단하고 세그먼트에서 즉시 제거됩니다.

![](assets/and_not_use_case.png)

## x 노출 후 타깃팅하지 않음 {#do-not-target-after-x}

최신성 및 빈도 컨트롤을 설정하여 사용자가 동일한 크리에이티브로 넘치는 것을 방지할 수 있습니다. 이 시나리오에서는 아래 단계에 설명된 대로 두 개의 트레이트가 있는 세그먼트를 만듭니다.

1. 아래 이미지에 표시된 대로 두 트레이트를 사용하여 세그먼트를 만들고 [!UICONTROL AND] 논리를 사용합니다. 실시간으로 트리거될 세그먼트 해제에 대한 노출 이벤트를 정의하려면 규칙 기반 트레이트를 사용해야 합니다. [규칙 기반 특성을 만드는 방법](../traits/create-onboarded-rule-based-traits.md)에 대해 자세히 알아보세요.
   >[!NOTE]
   >
   >[!UICONTROL Actionable Log Files] 또는 [!UICONTROL Pixel Calls]을(를) 사용하여 사용자 노출에 따라 트레이트를 만들 수 있습니다. [실행 가능한 로그 파일](../../integration/media-data-integration/actionable-log-files.md) 및 [픽셀 호출](../../integration/media-data-integration/impression-data-pixels.md)에 대해 자세히 알아보세요.
2. 두 번째 트레이트에 빈도 컨트롤을 적용합니다. 원하는 경우 최신성 제어도 추가할 수 있습니다. [최신성 및 빈도 컨트롤을 적용하는 방법](../segments/recency-and-frequency.md)에 대해 자세히 알아보세요.
3. 실시간 서버 간 대상에 세그먼트를 매핑합니다. [서버 간 대상](../destinations/add-edit-segments.md)에 세그먼트를 추가하는 방법에 대해 읽어 보십시오.

이 시나리오에서는 사용자가 3개 이상의 노출을 누적하면 이 세그먼트에서 제거되고 더 이상 이 특정 크리에이티브를 볼 수 없습니다.

![](assets/impressions_use_case.png)

## 중요 참고 사항 - 처리 {#processing-notes}

처리와 관련된 다음 측면을 염두에 두십시오.

* 실시간 세그먼트 해제 기능이 작동하려면 원하는 세그먼트를 실시간 서버 간 대상에 매핑해야 합니다.
* [device graph](profile-link-use-case.md#recommendations)로 장치에 연결된 장치의 경우 평가 및 세그먼테이션 해제와 관련하여 4개의 장치 제한을 적용합니다. 이 제한은 [장치 그래프 옵션 및 장치 세그먼테이션 해제](merge-rule-unsegment.md#device-graph-options-unsegmentation)에 설명되어 있습니다&#x200B;.
* 세그먼트 해제 명령은 장치 그래프로 연결된 여러 장치의 경우 24시간마다 대상으로 전송되는 배치 파일에 포함됩니다.
* 실시간으로 세그먼트 평가를 묻는 메시지를 표시하려면 장치를 실시간으로 [Edge](../../reference/system-components/components-edge.md)에서 확인해야 합니다. 트레이트 [!UICONTROL time-to-live (TTL)]이(가) 충족되면 [!DNL TTL]이(가) 있는 트레이트의 경우 일괄 처리 파일을 통해 24시간 내에 장치가 자동으로 세그먼트 해제됩니다&#x200B;. [트레이트 만료 간격을 설정](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)하는 방법에 대해 자세히 알아보세요.
* [!UICONTROL DCS API]에서 온보드 규칙 기반 트레이트를 실시간으로 사용하는 경우 [!UICONTROL AND NOT] 논리를 사용하여 세그먼트 해제를 트리거할 수 있습니다. [DCS API로 데이터 보내기](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)에 대해 자세히 알아보십시오&#x200B;.

## 중요 참고 사항 - 시간 {#timing-notes}

타이밍과 관련된 다음 측면을 염두에 두십시오.

* 세그먼트는 장치 프로필이 [에 저장되는 것과 같은 기간(즉, 마지막 실시간 상호 작용 이후 14일) 동안 ](../../reference/system-components/components-edge.md)Edge[!UICONTROL Edge]에 저장됩니다. [데이터 유지 FAQ](../../faq/faq-privacy.md#data-retention-faq)에서 데이터 유지에 대해 자세히 알아보세요.
* 세그먼트 해제 작업이 [!DNL DCS] 영역에 걸쳐 전파되는 데 약 24시간이 소요됩니다. [!DNL DCS] 지역 [여기](../../reference/system-components/components-data-collection.md) 및 [여기](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)에 대해 자세히 알아보세요.
