---
description: Audience Manager은 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 생성하든 API 메서드를 통해 프로그래밍 방식으로 만들어지든 이러한 항목에 제한이 적용됩니다. 사용 제한 사항은 API 또는 사용자 인터페이스를 훼손할 수 있는 자동화된 프로세스로부터 Audience Manager을 보호하는 데 도움이 됩니다.
seo-description: Audience Manager은 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 생성하든 API 메서드를 통해 프로그래밍 방식으로 만들어지든 이러한 항목에 제한이 적용됩니다. 사용 제한 사항은 API 또는 사용자 인터페이스를 훼손할 수 있는 자동화된 프로세스로부터 Audience Manager을 보호하는 데 도움이 됩니다.
seo-title: 사용 제한
solution: Audience Manager
title: 사용 제한
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 6%

---


# 사용 제한 {#usage-limits}

Audience Manager은 계정에 대해 만들 수 있는 트레이트, 세그먼트, 대상 및 알고리즘 모델의 수에 대한 최대 한도를 설정합니다. 사용자 인터페이스에서 생성되었거나 [!DNL API] 메서드를 통해 프로그래밍 방식으로 만들어졌는지에 관계없이 이러한 항목에 제한이 적용됩니다. 사용 제한 사항은 Audience Manager을 자동 프로세스로부터 보호하여 Adobe [!DNL API]s 또는 사용자 인터페이스를 손상시킬 수 있습니다.

## ID 매핑 제한 {#id-mapping-limits}

아래 표에는 장치 ID에 대한 [ID 매핑](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) 제한이 나와 있습니다. ID가 아래 제한 사항에 도달하면 Audience Manager은 가장 오래된 저장된 ID 매핑을 제거하고 새 ID 매핑을 추가하여 FIFO(처음, 최초 출력) 논리를 기반으로 새 ID 매핑을 추가합니다. Audience Manager에서 지원하는 ID에 대한 자세한 내용은 Audience Manager의 [ID의 색인](../../reference/ids-in-aam.md)을 참조하십시오.

| ID 매핑 | 최대 제한 |
|-----------|-------------- |
| 장치 광고 ID([DAID](../../reference/ids-in-aam.md))를 장치 간 ID([DPUUID](../../reference/ids-in-aam.md))로 변환 | 100개 장치 광고 ID([DAID](../../reference/ids-in-aam.md))를 1개의 상호 장치 ID([DPUUID](../../reference/ids-in-aam.md))로 |
| 장치 간 ID([DPUUID](../../reference/ids-in-aam.md)) - 장치 광고 ID([DAID](../../reference/ids-in-aam.md)) | 상호 장치 ID 10개([DPUUID](../../reference/ids-in-aam.md)) - 각 [DPID](../../reference/ids-in-aam.md)당 1개의 장치 광고 ID([DAID](../../reference/ids-in-aam.md)) |
| 쿠키/브라우저 ID - 쿠키/브라우저 ID | 1000개의 쿠키/브라우저 ID를 1개의 쿠키/브라우저 ID로 변환 |

## 항목 제한 {#item-limits}

테이블에는 항목 유형별로 현재 제한이 나열됩니다. 이러한 항목 중 하나에 대한 특정 제한에 도달하면 새 특성, 세그먼트, 대상 또는 [!UICONTROL Algorithmic Models]을 만들 수 없습니다. 한도에 도달하면 새 항목을 만들기 전에 이전 항목을 삭제해야 합니다.

### 특성 제한

| 특성 유형 | 최대 제한 |
| -------------------------- | ------------------------------------- |
| 총 특성 | 100,000 |
| 총 특성 자격 | 15만 트레이트 자격에 대한 자세한 내용은 [트레이트 자격 참조](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)의 트레이트 자격 제한을 참조하십시오. |
| 알고리즘 | 50 |
| 규칙 기반 | 100,000 |
| 온보딩 | 100,000 |
| 폴더 트레이트 | 2,000 |

### 세그먼트 제한

| 세그먼트 유형 | 최대 제한 |
| -------------- | ------------- |
| 총 세그먼트 | 20,000 |

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
| 활성 [!UICONTROL Look-Alike Models] | 20. Audience Manager은 제한과 비교하여 *active* 알고리즘 모델만 계산합니다. |
| [!UICONTROL Look-Alike Models] 최대 고객 규모 | 25,000,000  이 제한은 늘릴 수 없습니다. 모델의 데이터 소스를 적게 선택하거나 보다 짧은 뒤로 보기를 선택하여 대상 크기를 줄일 수 있습니다. |
| [!UICONTROL Look-Alike Model]에 대해 제외된 최대 트레이트 수 | 500. 알고리즘 모델링의 특성 제외[를 참조하십시오.](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md) |
| 최대 [!UICONTROL Predictive Audiences Models] | 10 |
| [!UICONTROL Predictive Audiences Models]에 대한 기준선 개인 최대 수 | 50 |

### 폴더 제한

| 항목 | 최대 제한 |
| ------------- | ------------------ |
| 특성 폴더 | 2천 명  폴더 구조는 최대 5레벨일 수 있습니다. |

### 파생된 신호 제한

| 항목 | 최대 제한 |
| --------------- | ------------- |
| 파생 신호 | 50,000. |

### 회사 사용자 계정 제한

| 항목 | 최대 제한 |
| ----------- | ------------- |
| 회사의 최대 사용자 계정 수 | 1,000. |

## 모니터 사용량 {#monitor-usage}

**[!UICONTROL Administration > Limits]**&#x200B;으로 이동하여 계정에 대한 사용 및 제한을 볼 수 있습니다. 액세스하려면 관리자 권한이 필요합니다.

![사용량 제한 이미지](assets/usage-limits.png)

## 항목 제한 증가 {#increase-item-limits}

여기에 나와 있는 기본 제한은 비즈니스 요구 사항에 적합한 용량을 제공합니다. 조직이 이러한 제한에 일관되게 도달하는 경우 계정 담당자에게 문의하여 증가분을 논의하십시오.