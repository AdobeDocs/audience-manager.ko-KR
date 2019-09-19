---
description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-title: 즉각적인 장치 간 억제
title: 즉각적인 장치 간 억제
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# 즉각적인 장치 간 억제 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 는 이러한 장치에서 특정 경험이 발생할 때 연결된 여러 장치에서 사용자를 억제하는 기능입니다. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.

## 개요 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 두 가지 주요 사용 사례를 소개합니다.향상된 사용자 경험과 미디어 효율성

* **향상된 사용자 경험**:이미 제품 또는 서비스를 구매한 사용자는 구매 전과 동일한 크리에이티브를 볼 수 없습니다. 대신, 구매하지 않은 제품 또는 서비스에 대해 업셀링 또는 크로스셀링 메시지를 표시할 수 있습니다.
* **미디어 효율성**:모든 [!DNL DSP]항목에 글로벌 빈도 한도를 적용하여 캠페인 지출을 최적화합니다.한 사용자에 속한 여러 장치의 경우 주파수 대문자를 실시간으로 입력할 수 있습니다.

실시간 세그멘테이션의 기술 세부 사항은 프로필 병합 규칙 및 장치 [세그멘테이션 처리 과정에 자세히 설명되어 있습니다](../../features/profile-merge-rules/merge-rule-unsegment.md). 위에 설명된 사용 사례를 실제로 구현하려면 읽어 보십시오.

## 변환된 후 타깃팅하지 않음 {#do-not-target-once}

이미 전환한(제품 구매, 구독 취득 등) 사용자에게 확인 전환 전과 동일한 메시지가 표시되지 않습니다. 다음과 같이 [!UICONTROL AND NOT] 로직을 사용하여 얻을 수 있습니다.

1. 두 가지 트레이트를 사용하여 세그먼트를 만들고 아래 이미지와 같이 [!UICONTROL AND NOT] 로직을 사용합니다. 규칙 기반 트레이트를 사용하여 실시간으로 세그먼트화되지 않도록 전환 이벤트를 정의해야 합니다. 규칙 기반 트레이트를 [만드는 방법에](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)대한 자세한 내용을 살펴보십시오.
1. 실시간 서버-서버 대상에 세그먼트를 매핑합니다. 서버 간 대상에 [](../../features/destinations/add-edit-segments.md)세그먼트를 추가하는 방법에 대해 알아봅니다.

방문자가 전환하지 않은 경우 세그먼트를 사용할 수 있습니다. 전환 트레이트에 대한 자격이 부여되면 세그먼트 규칙을 따르지 않고 세그먼트에서 즉시 제거됩니다.

![](assets/and_not_use_case.png)

## x 노출 후 타깃팅하지 않음 {#do-not-target-after-x}

최근 및 빈도 컨트롤을 설정하여 사용자가 동일한 크리에이티브한 기능을 사용하지 않도록 설정할 수 있습니다. 이 시나리오에서는 아래 단계에 설명된 대로 두 가지 트레이트로 세그먼트를 만듭니다.

1. 두 가지 트레이트를 사용하여 세그먼트를 만들고 아래 이미지와 같이 [!UICONTROL AND] 로직을 사용합니다. 규칙 기반 트레이트를 사용하여 실시간으로 세그먼트가 트리거되도록 노출 이벤트를 정의해야 합니다. 규칙 기반 트레이트를 [만드는 방법에](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)대한 자세한 내용을 살펴보십시오.
   >[!NOTE]
   >
   >사용자 노출 수를 기반으로 트레이트를 [!UICONTROL Actionable Log Files] 만들거나 만들 [!UICONTROL Pixel Calls] 수 있습니다. 실행 가능한 로그 [파일](../../integration/media-data-integration/actionable-log-files.md) 및 픽셀 호출에 대한 자세한 [내용을 살펴보십시오](../../integration/media-data-integration/impression-data-pixels.md).
1. 두 번째 트레이트에 주파수 컨트롤을 적용합니다. 원할 경우 최근 컨트롤도 추가할 수 있습니다. 최근 및 빈도 컨트롤을 [](../../features/segments/recency-and-frequency.md)적용하는 방법에 대한 자세한 내용을 살펴보십시오.
1. 실시간 서버-서버 대상에 세그먼트를 매핑합니다. 서버 간 대상에 [](../../features/destinations/add-edit-segments.md)세그먼트를 추가하는 방법에 대해 알아봅니다.

이 시나리오에서는 사용자가 3개 이상의 노출 횟수를 누적하면 이 세그먼트에서 제거되고 이 특정 크리에이티브가 더 이상 표시되지 않습니다.

![](assets/impressions_use_case.png)

## 중요한 참고 사항 - 처리 {#processing-notes}

처리와 관련된 다음 사항을 염두에 두십시오.

* 실시간 세그먼트 해제 기능이 작동하려면 원하는 세그먼트를 서버 간 실시간 대상에 매핑해야 합니다.
* 장치 그래프로 [](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)장치에 연결된 장치의 경우 평가 및 세그멘테이션에 대해 4개의 장치 제한이 적용됩니다. 이 제한 사항은 장치 그래프 옵션 [](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation)및 장치 세그먼테이션에 설명되어 &#x200B; 있습니다.
* 장치 그래프로 연결된 여러 장치에 대해 24시간마다 대상으로 전송되는 일괄 처리 파일에 제거 명령이 포함됩니다.
* 세그먼트를 평가하라는 메시지를 표시하려면 장치를 실시간으로(Edge [에서](../../reference/system-components/components-edge.md)) 확인해야 합니다. 값이 있는 트레이트의 경우, 트레이트가 [!UICONTROL time-to-live (TTL)] 충족되더라도 장치가 다음에 실시간으로 표시될 때까지 장치가 자동으로 분할되지 [!DNL TTL] 않습니다 ** . 트레이트 만료 간격을 [설정하는 방법에 대한 자세한 내용을 참조하십시오](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* 실시간으로 보드 규칙 기반 트레이트를 사용하는 [!UICONTROL DCS API] 경우 [!UICONTROL AND NOT] 로직을 사용하여 세그먼트 해제를 트리거할 수 있습니다. DCS API로 데이터 [전송에 대한 자세한 내용을 살펴보십시오](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## 중요한 참고 사항 - 타이밍 {#timing-notes}

타이밍과 관련된 다음과 같은 측면을 염두에 두십시오.

* 세그먼트는 장치 프로파일이 [에](../../reference/system-components/components-edge.md) 저장되어 있는 것과 동일한 기간 동안 Edge에 저장됩니다. 즉, [!UICONTROL Edge]이것은 마지막 실시간 상호 작용 이후 14일입니다. 데이터 유지 FAQ에서 데이터 유지에 대한 [자세한 내용을 살펴보십시오](../../faq/faq-privacy.md#data-retention-faq).
* 세그먼트 해제 작업이 여러 [!UICONTROL DCS] 영역에 전파되는 데 약 24시간이 걸립니다. Adobe의 [!UICONTROL DCS] 지역에 대한 자세한 내용은 [여기를](../../reference/system-components/components-data-collection.md) 참조하십시오 [](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).