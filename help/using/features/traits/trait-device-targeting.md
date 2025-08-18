---
description: Audience Manager 계정의 모든 속성에서 장치 관련 변수를 사용하여 사용자를 타겟팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: 플랫폼 수준 키로 장치 타겟팅
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# 플랫폼 수준 키로 장치 타겟팅 {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google은 [!DNL Google Chrome] 헤더를 통해 수집된 정보를 최소화하기 위해 [!DNL Chromium] 및 모든 `User-Agent` 기반 브라우저의 기능을 업데이트했습니다.
>&#x200B;>2023년 3월부터는 Audience Manager에서 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)을 활용하여 이러한 업데이트를 지원합니다. `User-Agent` 헤더를 통해 제공되는 트레이트 정보를 계속 사용하려면 [웹 SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)를 사용하고 [높은 엔트로피 사용자 에이전트 클라이언트 힌트](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=ko)를 사용하도록 설정해야 합니다.
>&#x200B;>이러한 업데이트는 [DIL](../../../using/dil/dil-overview.md)에서 지원되지 않으므로 [!DNL DIL]을(를) 사용하는 Audience Manager 고객은 `User-Agent` 헤더를 통해 트레이트 정보를 수집할 수 없습니다.

Audience Manager 계정의 모든 속성에서 장치 관련 변수를 사용하여 사용자를 타겟팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.

## 플랫폼 수준 변수의 목적 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

플랫폼 수준 변수를 사용하면 특정 사이트에서 전달된 데이터를 가져와 [!DNL Audience Manager] 계정의 모든 속성에서 타깃팅에 사용할 수 있습니다. 이러한 변수는 아래와 같이 [이 접두사로 추가된 키를 사용하여 ](../../reference/key-value-pairs-explained.md)키-값 쌍`d_`으로 형성됩니다.

## 사용자 에이전트에서 정의한 플랫폼 수준 키 {#keys-user-agent}

[!UICONTROL Data Collection Servers]은(는) [ 요청의 ](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)사용자 에이전트 헤더`HTTP`에서 이러한 키의 값을 추출합니다. 값은 [!UICONTROL Device Atlas] 데이터베이스의 장치 수준 정보를 나타냅니다. 사용자 에이전트 예에서 추출한 대로 아래 표의 신호를 사용할 수 있습니다. [ 측정에 따라 ](assets/device_keys.csv)가장 일반적인 키 목록을 다운로드[!UICONTROL Device Atlas]합니다.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>사용자 에이전트 헤더에서 하나 이상의 신호를 검색할 수 없는 경우에도 다른 신호는 [!UICONTROL Data Collection Servers]에 전달됩니다.

>[!MORELIKETHIS]
>
>* [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)
