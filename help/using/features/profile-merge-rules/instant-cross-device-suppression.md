---
description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-title: 즉각적인 장치 간 억제
title: 즉각적인 장치 간 억제
uuid: CB 11 B 9 CB -6 D 7 D -4 AA 9-91 B 0-C 2715857 D 821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# 즉각적인 장치 간 억제 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 는 이러한 장치에서 특정 경험이 발생하는 경우 연결되어 있는 여러 장치에 걸쳐 사용자를 표시하지 않도록 하는 기능입니다. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.

## 개요 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 다음 두 가지 주요 사용 사례를 제공합니다. 사용자 경험과 미디어 효율성이 개선되었습니다.

* **향상된 사용자 경험**: 이미 제품 또는 서비스를 구입한 사용자에게는 구매하기 전과 동일한 크리에이티브 전문가가 표시되지 않습니다. 대신 구입하지 않은 제품 또는 서비스에 대한 업셀링 또는 크로스셀링 메시지를 표시할 수 있습니다.
* **미디어 효율성**: 모든 [!DNL DSP]S. 사용자가 속한 여러 장치에 대해 주파수 끝을 실시간으로 적용할 수 있습니다.

실시간 세분화에 대한 기술 세부 사항은 [프로필 병합 규칙 및 장치 해제-세그멘테이션 프로세스에서](../../features/profile-merge-rules/merge-rule-unsegment.md)설명됩니다. 위에서 설명한 사용 사례의 실질적인 구현을 읽어 보십시오.

## 전환된 후에는 타깃팅하지 않음 {#do-not-target-once}

이미 전환된 사용자 (제품 구매, 구독 획득 등) 는 전환 전의 동일한 메시징은 표시되지 않습니다. 다음과 같이 [!UICONTROL AND NOT] 로직을 사용하여 얻을 수 있습니다.

1. 아래 이미지에서와 같이 두 가지 특성을 사용하여 세그먼트를 만들고 [!UICONTROL AND NOT] 로직을 사용합니다. 규칙 기반 트레이트를 사용하여 실시간 트리거가 트리거되도록 전환 이벤트를 정의해야 합니다. 규칙 기반의 트레이트를 [만드는](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)방법에 대한 자세한 내용을 살펴보십시오.
1. 세그먼트를 실시간 서버 대 서버 대상에 매핑합니다. [서버-서버 대상에 세그먼트를 추가하는 방법을 읽어](../../features/destinations/add-edit-segments.md)보십시오.

방문자는 세그먼트가 변환되지 않는 한 해당 세그먼트를 사용할 수 있습니다. 전환 트레이트를 적용받을 수 있는 즉시 세그먼트 규칙을 따르지 않고 세그먼트에서 즉시 제거됩니다.

![](assets/and_not_use_case.png)

## X 노출 후 타깃팅 안 함 {#do-not-target-after-x}

최근 및 빈도 컨트롤을 설정하여 동일한 크리에이티브를 사용하여 사용자를 범람하지 않도록 할 수 있습니다. 이 시나리오에서 아래 단계에 설명된 대로 두 가지 트레이트가 있는 세그먼트를 만듭니다.

1. 아래 이미지에서와 같이 두 가지 특성을 사용하여 세그먼트를 만들고 [!UICONTROL AND] 로직을 사용합니다. 규칙 기반 트레이트를 사용하여 비세그먼트에 대한 노출 이벤트를 정의하여 실시간으로 트리거해야 합니다. 규칙 기반의 트레이트를 [만드는](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)방법에 대한 자세한 내용을 살펴보십시오.
   >[!NOTE]
   >
   >사용자 노출 횟수를 기반으로 트레이트를 [!UICONTROL Actionable Log Files] 사용하거나 [!UICONTROL Pixel Calls] 만들 수 있습니다. [실행 가능한 로그 파일](../../integration/media-data-integration/actionable-log-files.md) 및 [픽셀 호출에](../../integration/media-data-integration/impression-data-pixels.md)대해 자세히 알아보십시오.
1. 주파수 컨트롤을 두 번째 트레이트에 적용합니다. 원하는 경우 최근 컨트롤을 추가할 수도 있습니다. 최근 및 빈도 제어를 [적용하는](../../features/segments/recency-and-frequency.md)방법에 대해 자세히 알아보십시오.
1. 세그먼트를 실시간 서버 대 서버 대상에 매핑합니다. [서버-서버 대상에 세그먼트를 추가하는 방법을 읽어](../../features/destinations/add-edit-segments.md)보십시오.

이 시나리오에서 사용자가 노출 횟수를 3 회 이상 누적한 후에는 이 세그먼트에서 제거되고 이 특정 크리에이티브가 더 이상 표시되지 않습니다.

![](assets/impressions_use_case.png)

## 중요 정보 - 처리 과정 {#processing-notes}

처리와 관련된 다음과 같은 측면을 염두에 두십시오.

* 실시간으로 세그먼트 해제 기능을 사용하려면 원하는 세그먼트를 realtime server-to-server 대상에 매핑해야 합니다.
* [장치 그래프로](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)장치에 연결된 장치의 경우, 평가 및 세그먼테이션과 관련하여 4 장치 제한이 적용됩니다. 이 제한 사항은 [장치 그래프 옵션 및 장치 세분화에 설명되어](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation)있습니다.
* 세그먼트 해제 명령은 장치 그래프로 연결된 여러 장치에 대해 24 시간마다 대상에 전송되는 일괄 처리 파일에 포함됩니다.
* 세그먼트 평가를 프롬프팅하려면 [장치를](../../reference/system-components/components-edge.md)실시간으로 봐야 합니다. [!UICONTROL time-to-live (TTL)] 값이 있는 트레이트에 대해, 트레이트 [!DNL TTL] 충족 경우에도 *장치가* 다음에 표시될 때까지 장치가 자동으로 분할되지 않습니다. 특성 만료 간격을 [설정하는 방법에 대해 자세히](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)알아보십시오.
* 실시간 규칙 기반 [!UICONTROL DCS API] 트레이트를 실시간으로 사용하는 경우 [!UICONTROL AND NOT] 로직을 사용하여 세그먼트를 트리거할 수 있습니다. DCS API로 데이터 [전송에 대한 자세한](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)내용을 참조하십시오.

## 중요한 참고 사항 - 타이밍 {#timing-notes}

타이밍과 관련된 이러한 측면을 염두에 두십시오.

* 세그먼트는 마지막 실시간 상호 작용 이후 14 일 동안 장치 프로필과 동일한 기간 동안 [가장자리에](../../reference/system-components/components-edge.md) [!UICONTROL Edge]저장됩니다. 데이터 유지 FAQ에 대한 자세한 내용은 데이터 [유지 FAQ](../../faq/faq-privacy.md#data-retention-faq)를 참조하십시오.
* 세그먼트 해제 작업이 지역 간에 [!UICONTROL DCS] 전파되는 데에는 약 24 시간이 소요됩니다. 여기에서 [!UICONTROL DCS] Adobe 지역 [정보를](../../reference/system-components/components-data-collection.md) [](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)자세히 살펴보십시오.