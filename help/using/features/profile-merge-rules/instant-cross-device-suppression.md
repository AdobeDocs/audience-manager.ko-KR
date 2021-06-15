---
description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-title: 즉각적인 장치 간 억제
title: 즉각적인 장치 간 억제
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: 프로필 병합
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# 즉각적인 장치 간 억제 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 는 이러한 장치에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에서 사용자를 억제하는 기능입니다. 장치 간에 일관된 경험을 사용자에게 제공하려면 [!UICONTROL Instant Cross-Device Suppression] 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.

## 개요 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 는 두 가지 주요 사용 사례를 제공합니다.사용자 환경 및 미디어 효율성이 개선되었습니다.

* **향상된 사용자 경험**:이미 제품이나 서비스를 구매한 사용자에게는 구매 전과 동일한 크리에이티브가 표시되지 않습니다. 대신 구매하지 않은 제품이나 서비스에 대해 업셀링 또는 크로스셀링 메시지를 표시할 수 있습니다.
* **미디어 효율성**:모든 활동에 글로벌 빈도 제한을 적용하여 캠페인 비용을  [!DNL DSP]최적화합니다.상기 주파수 캡은 사용자에게 속하는 다수의 장치에 대하여 실시간으로 동작할 수 있다.

실시간 세그먼테이션의 기술 세부 사항은 [프로필 병합 규칙 및 장치 세그먼테이션 해제 프로세스](merge-rule-unsegment.md)에 설명되어 있습니다. 위에서 설명한 사용 사례를 실제로 구현하려면 를 참조하십시오.

## 전환된 {#do-not-target-once} Target을 한 번 수행하지 마십시오.

이미 변환(제품 구매, 구독 등)한 사용자가 은 전환 전과 동일한 메시지를 보지 않습니다. 다음과 같이 [!UICONTROL AND NOT] 논리를 사용하여 이 항목을 얻을 수 있습니다.

1. 두 가지 트레이트를 사용하여 세그먼트를 만들고 아래 이미지에 표시된 대로 [!UICONTROL AND NOT] 논리를 사용합니다. 세그먼트 해제 를 실시간으로 트리거하기 위한 전환 이벤트를 정의하려면 규칙 기반 트레이트를 사용해야 합니다. [규칙 기반 특성을 만드는 방법에 대해 자세히 알아보십시오](../traits/create-onboarded-rule-based-traits.md).
2. 실시간 서버 간 대상에 세그먼트를 매핑합니다. [서버 간 대상](../destinations/add-edit-segments.md)에 세그먼트를 추가하는 방법에 대해 읽어 보십시오.

방문자가 전환되지 않은 경우 세그먼트에 대한 자격이 됩니다. 전환 트레이트에 대한 자격이 부여되면 해당 세그먼트는 세그먼트 규칙을 따르지 않으며 세그먼트에서 즉시 제거됩니다.

![](assets/and_not_use_case.png)

## x 노출 횟수 {#do-not-target-after-x} 뒤에 Target 안 함

최신성 및 빈도 제어를 설정하여 사용자에게 동일한 크리에이티브를 제공하지 않도록 할 수 있습니다. 이 시나리오에서는 아래 단계에 설명된 대로 두 가지 트레이트로 세그먼트를 만듭니다.

1. 두 가지 트레이트를 사용하여 세그먼트를 만들고 아래 이미지에 표시된 대로 [!UICONTROL AND] 논리를 사용합니다. 세그먼트 해제 이벤트를 실시간으로 트리거하기 위한 규칙 기반 트레이트를 사용해야 합니다. [규칙 기반 특성을 만드는 방법에 대해 자세히 알아보십시오](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >[!UICONTROL Actionable Log Files] 또는 [!UICONTROL Pixel Calls] 를 사용하여 사용자 노출 횟수를 기반으로 트레이트를 만들 수 있습니다. [실행 가능 로그 파일](../../integration/media-data-integration/actionable-log-files.md) 및 [픽셀 호출](../../integration/media-data-integration/impression-data-pixels.md)에 대해 자세히 알아보십시오.
2. 두 번째 트레이트에 빈도 컨트롤을 적용합니다. 원할 경우 최신성 컨트롤을 추가할 수도 있습니다. 최신성 및 빈도 컨트롤을 적용하는 방법](../segments/recency-and-frequency.md)에 대해 자세히 알아보십시오.[
3. 실시간 서버 간 대상에 세그먼트를 매핑합니다. [서버 간 대상](../destinations/add-edit-segments.md)에 세그먼트를 추가하는 방법에 대해 읽어 보십시오.

이 시나리오에서 사용자가 3개 이상의 노출을 누적하면 이 세그먼트에서 제거되고 더 이상 이 특정 크리에이티브를 볼 수 없습니다.

![](assets/impressions_use_case.png)

## 메모의 중요한 측면 - 처리 {#processing-notes}

처리와 관련된 다음 측면을 기억하십시오.

* 실시간 세그먼트 해제 기능이 작동하려면 원하는 세그먼트를 실시간 서버 간 대상에 매핑해야 합니다.
* [device graph](profile-link-use-case.md#recommendations)에 의해 장치에 연결된 장치의 경우, 평가 및 세그먼테이션 해제에 대해 4개 장치 제한을 적용합니다. 이 제한은 [장치 그래프 옵션 및 장치 세그먼테이션 해제](merge-rule-unsegment.md#device-graph-options-unsegmentation)에 설명되어 &#x200B; 있습니다.
* Device Graph에서 연결된 여러 장치에 대해 24시간마다 대상으로 전송되는 배치 파일에 세그먼트 해제 명령이 포함됩니다.
* 실시간으로 세그먼트 평가를 묻는 메시지를 표시하려면 장치를 실시간으로( [Edge](../../reference/system-components/components-edge.md)에서) 확인해야 합니다. 트레이트 [!DNL TTL]이 충족될 때 [!UICONTROL time-to-live (TTL)]이 있는 트레이트의 경우, 장치는 배치 파일을 통해 24시간 이내에 자동으로 세그먼트화되지 않습니다&#x200B;. [트레이트 만료 간격을 설정](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)하는 방법에 대해 자세히 알아보십시오.
* [!UICONTROL DCS API] 을 사용하여 실시간으로 온보드 규칙 기반 트레이트를 사용하는 경우 [!UICONTROL AND NOT] 논리를 사용하여 세그먼트 해제를 트리거할 수 있습니다. [DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)로 데이터 보내기에 대해 자세히 &#x200B; 알아보십시오.

## 메모의 중요한 측면 - 시간 {#timing-notes}

타이밍과 관련된 다음 측면을 기억하십시오.

* 세그먼트는 [Edge](../../reference/system-components/components-edge.md)에 저장되며, 장치 프로필은 [!UICONTROL Edge]에 저장됩니다. 즉, 마지막 실시간 상호 작용 이후 14일. 데이터 유지에 대한 자세한 내용은 [데이터 유지 FAQ](../../faq/faq-privacy.md#data-retention-faq)를 참조하십시오.
* 세그먼트 해제 작업이 [!DNL DCS] 영역에 걸쳐 전파되는 데 약 24시간이 걸립니다. [!DNL DCS] 지역 [여기](../../reference/system-components/components-data-collection.md) 및 [여기](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)에 대해 자세히 알아보십시오.
