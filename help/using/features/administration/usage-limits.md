---
description: Audience Manager는 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 만들었는지 또는 프로그래밍 방식으로 API 메서드를 통해 만들었는지 여부에 관계없이 이러한 항목에 제한이 적용됩니다. 사용 제한으로 인해 Adobe API 또는 유저 인터페이스를 손상시키려는 자동화된 프로세스를 통해 Audience Manager를 보호할 수 있습니다.
seo-description: Audience Manager는 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 만들었는지 또는 프로그래밍 방식으로 API 메서드를 통해 만들었는지 여부에 관계없이 이러한 항목에 제한이 적용됩니다. 사용 제한으로 인해 Adobe API 또는 유저 인터페이스를 손상시키려는 자동화된 프로세스를 통해 Audience Manager를 보호할 수 있습니다.
seo-title: 사용 제한
solution: Audience Manager
title: 사용 제한
topic: DIL API
uuid: 50 CA 4647-0 B 5 C -409 C -89 FA -4 FA 1799 B 3222
translation-type: tm+mt
source-git-commit: a9550d71bbc6adf939539df05cd38a9d22ef261b

---


# Usage Limits {#usage-limits}

Audience Manager는 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## ID 매핑 제한 {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adds the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

| ID 매핑 | 최대 제한 |
|-----------|-------------- |
| 장치 간 ID (CRM ID) 에 대한 장치 광고 ID (Daid) | 100 개의 장치 광고 ID (DAIDS) 와 1 개의 장치 간 ID (CRM ID) |
| 장치 광고 ID (Daid) 에 대한 장치 간 ID (CRM ID) | 10 개의 크로스 디바이스 ID (CRM ID) 와 1 개의 디바이스 광고 ID (daid) |
| 쿠키/브라우저 ID에 대한 쿠키/브라우저 ID | 쿠키/브라우저 ID로 1000 개의 쿠키/브라우저 ID |

## Item Limits {#item-limits}

표에는 항목 유형별 현재 제한이 나열됩니다. You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. 한도에 도달하는 경우 새 항목을 만들려면 먼저 이전 항목을 삭제해야 합니다.

### 트레이트 제한

| 트레이트 유형 | 최대 제한 |
| -------------------------- | ------------------------------------- |
| 총 특성 | 100,000 |
| 총 특성 자격 조건 | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
| Algorithmic | 50 |
| 규칙 기반 | 100,000 |
| 온보딩 | 100,000 |
| 폴더 특징 | 2,000 |

### 세그먼트 제한

| 세그먼트 유형 | 최대 제한 |
| -------------- | ------------- |
| 총 세그먼트 수 | 20,000 |

### 대상 제한

| 대상 유형 | 최대 제한 |
| ------------------ | ------------- |
| 총 목표 수 | 1,000 |
| 쿠키 | 1,000 |
| URL | 1,000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### 알고리즘 모델 제한

| 항목 | 최대 제한 |
| -------- | ----- |
| 활성 알고리즘 모델 | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| 알고리즘 모델 최대 대상 규모 | 25,000,000.  이 제한은 늘릴 수 없습니다. 모델의 데이터 소스를 줄이거나 더 짧은 룩백 창을 선택하여 대상 크기를 줄일 수 있습니다. |
| 모델에 대해 제외된 최대 트레이트 수 | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### 폴더 제한

| 항목 | 최대 제한 |
| ------------- | ------------------ |
| 특성 폴더 | 2,000.  폴더 구조는 최대 5 개 수준이 될 수 있습니다. |

### 파생 신호 제한

| 항목 | 최대 제한 |
| --------------- | ------------- |
| 파생 신호 | 50,000. |

### 회사 사용자 계정 제한

| 항목 | 최대 제한 |
| ----------- | ------------- |
| 회사에 대한 최대 사용자 계정 수 | 1,000. |

## Monitor Usage {#monitor-usage}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. 액세스하려면 관리자 권한이 필요합니다.

![사용 제한 이미지](assets/usage-limits.png)

## Increase Item Limits {#increase-item-limits}

여기에 나열된 기본 제한은 비즈니스 요구 사항에 충분한 용량을 제공해야 합니다. 조직이 이러한 제한에 지속적으로 도달하는 경우 계정 담당자에게 연락하여 증가에 대해 논의합니다.