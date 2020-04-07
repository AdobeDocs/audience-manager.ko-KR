---
description: Audience Manager는 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 생성하든 API 메서드를 통해 프로그래밍 방식으로 만들어졌든 이러한 항목에 제한이 적용됩니다. 사용 제한은 Audience Manager를 API 또는 사용자 인터페이스 손상 시도를 위한 자동화된 프로세스로부터 보호합니다.
seo-description: Audience Manager는 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 생성하든 API 메서드를 통해 프로그래밍 방식으로 만들어졌든 이러한 항목에 제한이 적용됩니다. 사용 제한은 Audience Manager를 API 또는 사용자 인터페이스 손상 시도를 위한 자동화된 프로세스로부터 보호합니다.
seo-title: 사용 제한
solution: Audience Manager
title: 사용 제한
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# 사용 제한 {#usage-limits}

Audience Manager는 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 생성하든 프로그래밍 방식으로 만들어지든 이러한 항목에 제한이 적용됩니다. [!DNL API] 사용 제한 사항은 Adobe [!DNL API]또는 사용자 인터페이스를 훼손할 수 있는 자동화된 프로세스로부터 Audience Manager를 보호하는 데 도움이 됩니다.

## ID 매핑 제한 {#id-mapping-limits}

아래 표에는 장치 ID [에 대한 ID 매핑](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) 제한이 나와 있습니다. ID가 아래 제한에 도달하면 Audience Manager는 가장 오래된 저장된 ID 매핑을 제거하고 새 ID를 추가하여 [!DNL FIFO] (첫 번째, 첫 번째, 종료) 로직을 기반으로 새 ID 매핑을 추가합니다. Audience [Manager에서](../../reference/ids-in-aam.md) 지원되는 ID에 대한 자세한 내용은 Audience Manager의 ID 인덱스를 참조하십시오.

| ID 매핑 | 최대 제한 |
|-----------|-------------- |
| 장치 광고 ID([DAID](../../reference/ids-in-aam.md))를 장치 간 ID([DPUUID](../../reference/ids-in-aam.md))로 변환 | 100개의 장치 광고 ID([DAID](../../reference/ids-in-aam.md))에서 1개의 장치 간 ID([DPUUID](../../reference/ids-in-aam.md)) |
| 장치 간 ID([DPUUID](../../reference/ids-in-aam.md))를 장치 광고 ID([DAID](../../reference/ids-in-aam.md))로 | 각 DPID당 10개의[DPUUID](../../reference/ids-in-aam.md)(Cross-Device Advertising[ID](../../reference/ids-in-aam.md))- [1개의DPID](../../reference/ids-in-aam.md) |
| 쿠키/브라우저 ID - 쿠키/브라우저 ID | 1000 쿠키/브라우저 ID를 1개의 쿠키/브라우저 ID로 변환 |

## 항목 제한 {#item-limits}

표에는 항목 유형별로 현재 제한이 나열됩니다. 새 트레이트, 세그먼트, 대상을 만들거나 이러한 항목 중 하나에 대한 특정 제한에 도달한 [!UICONTROL Algorithmic Models] 경우에는 만들 수 없습니다. 제한에 도달하는 경우, 새 항목을 만들기 전에 이전 항목을 삭제해야 합니다.

### 특성 제한

| 특성 유형 | 최대 제한 |
| -------------------------- | ------------------------------------- |
| 총 트레이트 수 | 100,000 |
| 총 트레이트 자격 | 150,000. 트레이트 자격에 대한 자세한 내용은 트레이트 자격 참조에서 트레이트 자격 [제한을 참조하십시오](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| 알고리즘 | 50 |
| 규칙 기반 | 100,000 |
| 온보드 | 100,000 |
| 폴더 트레이트 | 2,000 |

### 세그먼트 제한

| 세그먼트 유형 | 최대 제한 |
| -------------- | ------------- |
| 총 세그먼트 수 | 20,000 |

### 대상 제한

| 대상 유형 | 최대 제한 |
| ------------------ | ------------- |
| 총 대상 | 1,000 |
| 쿠키 | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 알고리즘 모델 제한

| 항목 | 최대 제한 |
| -------- | ----- |
| 활성 알고리즘 모델 | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| 알고리즘 모델 최대 고객 규모 | 25,000,000.  이 제한은 늘릴 수 없습니다. 모델의 데이터 소스를 적게 선택하거나 보다 짧은 룩백 창을 선택하여 대상 크기를 줄일 수 있습니다. |
| 모델에 대해 제외된 최대 트레이트 수 | 500.알고리즘 [모델링의 특성 제외를 참조하십시오](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### 폴더 제한

| 항목 | 최대 제한 |
| ------------- | ------------------ |
| 특성 폴더 | 2,000.  폴더 구조는 최대 5개 수준이 될 수 있습니다. |

### 파생된 신호 제한

| 항목 | 최대 제한 |
| --------------- | ------------- |
| 파생 신호 | 50,000. |

### 회사 사용자 계정 제한

| 항목 | 최대 제한 |
| ----------- | ------------- |
| 회사의 최대 사용자 계정 수 | 1,000. |

## 사용량 모니터링 {#monitor-usage}

로 이동하여 계정에 대한 사용 및 제한을 볼 수 **[!UICONTROL Administration > Limits]**&#x200B;있습니다. 액세스를 위해서는 관리자 권한이 필요합니다.

![사용량 제한 이미지](assets/usage-limits.png)

## 항목 제한 증가 {#increase-item-limits}

여기에 나열된 기본 제한은 비즈니스 요구 사항에 적합한 용량을 제공합니다. 조직이 이러한 제한에 지속적으로 도달하는 경우 계정 담당자에게 문의하여 증가율에 대해 상담하십시오.