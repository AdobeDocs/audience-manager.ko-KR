---
description: Audience Manager은 계정에 대해 생성할 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 제한을 설정합니다. 이러한 항목은 사용자 인터페이스에서 생성하든 API 메서드를 통해 프로그래밍 방식으로 생성하든 관계없이 제한이 적용됩니다. 사용 제한은 API 또는 사용자 인터페이스를 손상시키려는 자동화된 프로세스로부터 Audience Manager을 보호하는 데 도움이 됩니다.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: 사용 제한
keywords: ID 매핑, ID 매핑, 쿠키 매핑
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 3%

---

# 사용 제한 {#usage-limits}

Audience Manager은 계정에 대해 생성할 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 제한을 설정합니다. 이러한 항목은 사용자 인터페이스에 만들어졌든 프로그래밍 방식으로 [!DNL API] 메서드를 통해 만들어졌든 관계없이 제한이 적용됩니다. 사용 제한은 [!DNL API] 또는 Audience Manager 인터페이스를 손상시킬 수 있는 자동화된 프로세스로부터 사용자를 보호하는 데 도움이 됩니다.

## ID 매핑 제한 {#id-mapping-limits}

아래 표에는 장치 ID에 대한 [ID 매핑](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) 제한이 나와 있습니다. ID가 아래 제한에 도달하면 Audience Manager은 가장 오래 전에 저장된 ID 매핑을 제거하고 새 ID 매핑을 추가하여 FIFO(선입선출) 로직을 기반으로 새 ID 매핑을 추가합니다. Audience Manager에서 지원하는 ID에 대한 자세한 내용은 Audience Manager의 [ID 색인](../../reference/ids-in-aam.md)을 참조하세요.

| ID 매핑 | 최대 한도 |
|-----------|-------------- |
| 장치 Advertising ID([DAID](../../reference/ids-in-aam.md))와 장치 간 ID([DPUUID](../../reference/ids-in-aam.md)) | 장치 Advertising ID 100개([DAID](../../reference/ids-in-aam.md))와 장치 간 ID 1개([DPUUID](../../reference/ids-in-aam.md)) |
| 장치 간 ID([DPUUID](../../reference/ids-in-aam.md))와 장치 Advertising ID([DAID](../../reference/ids-in-aam.md)) | 각 [DPID](../../reference/ids-in-aam.md)당 10개의 교차 장치 ID([DPUUID](../../reference/ids-in-aam.md))와 1개의 장치 Advertising ID([DAID](../../reference/ids-in-aam.md)) |
| 쿠키/브라우저 ID와 쿠키/브라우저 ID | 1000 쿠키/브라우저 ID에서 1 쿠키/브라우저 ID로 |

## 항목 제한 {#item-limits}

테이블에는 항목 유형별 현재 제한이 나열됩니다. 이러한 항목 중 하나에 대해 특정 제한에 도달한 경우 새 트레이트, 세그먼트, 대상 또는 [!UICONTROL Algorithmic Models]을(를) 만들 수 없습니다. 제한에 도달하는 경우 새 항목을 만들려면 먼저 이전 항목을 삭제해야 합니다.

### 트레이트 제한

| 트레이트 유형 | 최대 한도 |
| -------------------------- | ------------------------------------- |
| 총 트레이트 | 100,000 |
| 총 트레이트 자격 요건 | 15만 트레이트 자격에 대한 자세한 내용은 [트레이트 자격 참조](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)에서 트레이트 자격 제한을 참조하십시오. |
| 알고리즘 | 50 |
| 규칙 기반 | 100,000 |
| 온보딩된 | 100,000 |
| 폴더 트레이트 | 2,000 |

### 세그먼트 제한

| 세그먼트 유형 | 최대 한도 |
| -------------- | ------------- |
| 총 세그먼트 수 | 20,000 |

### 대상 제한

| 대상 유형 | 최대 한도 |
| ------------------ | ------------- |
| 총 대상 | 1,000 |
| 쿠키 | 1,000 |
| URL | 1,000 |
| S2 | 100 |
| Adobe Analytics | 10 |

### 알고리즘 모델 제한

| 항목 | 최대 한도 |
| -------- | ----- |
| 활성 [!UICONTROL Look-Alike Models] | 20. Audience Manager은 한도에 대해 *활성* 알고리즘 모델만 계산합니다. |
| [!UICONTROL Look-Alike Models] 최대 대상 크기 | 2500만  이 제한은 늘릴 수 없습니다. 모델의 데이터 소스 수를 줄이거나 더 짧은 전환 확인 기간을 선택하여 대상 크기를 줄일 수 있습니다. |
| [!UICONTROL Look-Alike Model]에 대해 제외된 최대 트레이트 수 | 500. 알고리즘 모델링에서 [트레이트 제외](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md)를 참조하십시오. |
| 최대 [!UICONTROL Predictive Audiences Models] | 10 |
| [!UICONTROL Predictive Audiences Models]에 대한 최대 기준선 가상 사용자 수 | 50 |

### 폴더 제한

| 항목 | 최대 한도 |
| ------------- | ------------------ |
| 트레이트 폴더 | 2,000명  폴더 구조는 최대 5단계 깊이일 수 있습니다. |

### 파생 신호 제한

| 항목 | 최대 한도 |
| --------------- | ------------- |
| 파생 신호 | 5만 |

### 회사 사용자 계정 제한

| 항목 | 최대 한도 |
| ----------- | ------------- |
| 회사의 최대 사용자 계정 수 | 1,000명. |

## 사용 모니터링 {#monitor-usage}

**[!UICONTROL Administration > Limits]**(으)로 이동하여 계정에 대한 사용 및 제한을 볼 수 있습니다. 액세스하려면 관리자 권한이 필요합니다.

![사용 제한 이미지](assets/usage-limits.png)

## 항목 제한 늘이기 {#increase-item-limits}

여기에 나열된 기본 제한은 비즈니스 요구 사항에 충분한 용량을 제공해야 합니다. 조직에서 일관되게 이러한 제한에 도달하는 경우 계정 담당자에게 문의하여 증가에 대해 논의하십시오.
