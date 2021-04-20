---
description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-description: 즉각적인 장치 간 억제는 이러한 장치에서 특정 환경에서 특정 경험이 발생할 때 연결되어 있는 여러 장치에 있는 사용자를 억제하는 기능입니다. 여러 장치 간에 일관된 경험을 사용자에게 제공하려면 즉각적인 장치 간 억제 기능을 사용하십시오. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.
seo-title: 즉각적인 장치 간 억제
title: 즉각적인 장치 간 억제
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# 즉각적인 장치 간 억제 {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] 는 특정 경험이 이러한 장치에서 발생할 때 연결된 여러 장치에서 사용자를 억제하는 기능입니다. [!UICONTROL Instant Cross-Device Suppression] 기능을 사용하여 모든 장치에서 사용자에게 일관된 경험을 제공할 수 있습니다. 이 경험은 Audience Manager의 실시간 세그먼트 해제 기능으로 가능해집니다.

## 개요 {#overview}

[!UICONTROL Instant Cross-Device Suppression] 2가지 주요 사용 사례를 소개합니다.사용자 경험 및 미디어 효율성 향상

* **향상된 사용자 경험**:이미 제품 또는 서비스를 구매한 사용자에게 구매 전과 동일한 크리에이티브가 표시되지 않습니다. 대신, 고객이 구매하지 않은 제품 또는 서비스에 대해 업셀링 또는 크로스셀링 메시지를 표시할 수 있습니다.
* **미디어 효율성**:전체 빈도에 글로벌 주파수 한도를 적용하여 캠페인 지출을 최적화할 수  [!DNL DSP]있습니다.한 사용자에 속한 여러 장치에 대해 주파수 대체를 실시간으로 기록할 수 있습니다.

실시간 세분화에 대한 기술 세부 사항은 [프로필 병합 규칙 및 장치 분리 세그먼테이션 프로세스](merge-rule-unsegment.md)에 길이 설명되어 있습니다. 위에서 설명한 사용 사례를 실제로 구현하려면 를 읽어 보십시오.

## {#do-not-target-once} 변환한 후 Target 안 함

이미 전환한(제품 구매, 구독 취득 등) 사용자 확인 전환 전과 동일한 메시지가 표시되지 않습니다. 다음과 같이 [!UICONTROL AND NOT] 로직을 사용하여 이 항목을 얻을 수 있습니다.

1. 두 가지 트레이트를 사용하여 세그먼트를 만들고 아래 이미지에 표시된 것처럼 [!UICONTROL AND NOT] 논리를 사용합니다. 실시간으로 세그먼트화되지 않은 이벤트를 트리거할 전환 이벤트를 정의하려면 규칙 기반 트레이트를 사용해야 합니다. [규칙 기반 트레이트](../traits/create-onboarded-rule-based-traits.md)를 만드는 방법에 대해 자세히 알아보십시오.
2. 실시간 서버 간 대상에 세그먼트를 매핑합니다. [서버 간 대상](../destinations/add-edit-segments.md)에 세그먼트를 추가하는 방법에 대해 읽어보십시오.

방문자가 전환되지 않은 경우 세그먼트에 자격이 부여됩니다. 전환 트레이트를 사용할 자격이 부여되면 세그먼트 규칙을 따르지 않고 세그먼트에서 즉시 제거됩니다.

![](assets/and_not_use_case.png)

## x 노출 횟수 {#do-not-target-after-x} 이후 Target 안 함

최근 및 빈도 컨트롤을 설정하여 사용자가 동일한 크리에이티브하게 작업하지 않도록 할 수 있습니다. 이 시나리오에서는 아래 단계에 설명된 대로 두 가지 트레이트로 세그먼트를 만듭니다.

1. 두 가지 트레이트를 사용하여 세그먼트를 만들고 아래 이미지에 표시된 것처럼 [!UICONTROL AND] 논리를 사용합니다. 실시간으로 세그먼트화되지 않은 이벤트를 트리거하기 위한 노출 이벤트를 정의하려면 규칙 기반 트레이트를 사용해야 합니다. [규칙 기반 트레이트](../traits/create-onboarded-rule-based-traits.md)를 만드는 방법에 대해 자세히 알아보십시오.
   >[!NOTE]
   >
   >[!UICONTROL Actionable Log Files] 또는 [!UICONTROL Pixel Calls]을 사용하여 사용자 노출 횟수를 기반으로 트레이트를 만들 수 있습니다. [실행 가능한 로그 파일](../../integration/media-data-integration/actionable-log-files.md) 및 [픽셀 호출](../../integration/media-data-integration/impression-data-pixels.md)에 대해 자세히 알아보십시오.
2. 두 번째 트레이트에 주파수 컨트롤을 적용합니다. 원할 경우 최근 컨트롤도 추가할 수 있습니다. 최근 및 빈도 컨트롤 적용 방법](../segments/recency-and-frequency.md)에 대해 자세히 알아보십시오.[
3. 실시간 서버 간 대상에 세그먼트를 매핑합니다. [서버 간 대상](../destinations/add-edit-segments.md)에 세그먼트를 추가하는 방법에 대해 읽어보십시오.

이 시나리오에서는 사용자가 3개 이상의 노출 횟수를 누적하면 이 세그먼트에서 해당 노출 수가 제거되고 이 특정 크리에이티브가 더 이상 표시되지 않습니다.

![](assets/impressions_use_case.png)

## 메모에 대한 중요 사항 - {#processing-notes} 처리

처리와 관련된 다음과 같은 측면을 염두에 두십시오.

* 실시간 세그먼트 해제 기능이 작동하려면 원하는 세그먼트를 실시간 서버 간 대상에 매핑해야 합니다.
* [장치 그래프](profile-link-use-case.md#recommendations)에 의해 장치에 연결된 장치의 경우, 평가 및 세그먼테이션에 대해 4개의 장치 제한이 적용됩니다. 이 제한은 [장치 그래프 옵션 및 장치 분리](merge-rule-unsegment.md#device-graph-options-unsegmentation)에 설명되어 &#x200B; 있습니다.
* 장치 그래프로 연결된 여러 장치에 대해 24시간마다 대상에 전송되는 일괄 처리 파일에 unsegment 명령이 포함됩니다.
* 실시간으로 세그먼트 평가를 묻는 메시지를 표시하려면 장치를 실시간([Edge](../../reference/system-components/components-edge.md)에서)으로 볼 수 있어야 합니다. 특성 [!DNL TTL]이(가) 충족될 때 [!UICONTROL time-to-live (TTL)]이(가) 있는 트레이트의 경우, 장치는 배치 파일을 통해 24시간 이내에 자동으로 분할되지 않습니다&#x200B;. [특성 만료 간격 설정 방법](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval)에 대한 자세한 내용을 참조하십시오.
* [!UICONTROL DCS API]을 사용하여 실시간으로 보드 규칙 기반 트레이트를 사용하는 경우 [!UICONTROL AND NOT] 로직을 사용하여 세그먼트 제거를 트리거할 수 있습니다. DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)로 데이터 보내기에 대한 자세한 내용을 &#x200B; 참조하십시오.[

## 메모에 대한 중요 사항 - 시간 설정 {#timing-notes}

타이밍과 관련된 다음과 같은 측면을 염두에 두십시오.

* 세그먼트는 장치 프로필이 [!UICONTROL Edge]에 저장되고 같은 기간 동안 [Edge](../../reference/system-components/components-edge.md)에 저장됩니다. 즉, 마지막 실시간 상호 작용에서 14일이 지난 것입니다. [데이터 유지 FAQ](../../faq/faq-privacy.md#data-retention-faq)에서 데이터 유지에 대한 자세한 내용을 참조하십시오.
* 세그먼트 해제 작업이 [!DNL DCS] 영역에 전파되는 데 약 24시간이 소요됩니다. [!DNL DCS] 지역 [여기](../..//reference/system-components/components-data-collection.md) 및 [여기](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)에 대해 자세히 알아보십시오.
