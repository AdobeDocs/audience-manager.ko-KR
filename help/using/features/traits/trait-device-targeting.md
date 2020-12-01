---
description: Audience Manager 계정의 모든 속성에 장치 관련 변수가 있는 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.
seo-description: Audience Manager 계정의 모든 속성에 장치 관련 변수가 있는 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.
seo-title: 플랫폼 수준 키로 장치 타겟팅
solution: Audience Manager
title: 플랫폼 수준 키로 장치 타겟팅
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 9%

---


# 플랫폼 수준 키로 장치 타겟팅 {#device-targeting-with-platform-level-keys}

Audience Manager 계정의 모든 속성에 장치 관련 변수가 있는 사용자를 타깃팅하는 데 사용할 수 있는 일반적인 플랫폼 수준 키-값 쌍에 대해 설명합니다.

## 플랫폼 수준 변수의 목적 {#platform-variables}

<!-- c_tb_device_targeting.xml -->

플랫폼 수준 변수를 사용하면 특정 사이트에서 전달된 데이터를 가져와서 [!DNL Audience Manager] 계정의 모든 속성에 대해 타깃팅할 수 있도록 할 수 있습니다. 이러한 변수는 `d_`이(가) 키를 접두사로 사용한 [키-값 쌍](../../reference/key-value-pairs-explained.md)에 의해 만들어집니다.

## 사용자 에이전트가 정의하는 플랫폼 수준 키 {#keys-user-agent}

[!UICONTROL Data Collection Servers]은 `HTTP` 요청의 [사용자 에이전트 헤더](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43)에서 이러한 키에 대한 값을 추출합니다. 값은 [!UICONTROL Device Atlas] 데이터베이스의 장치 수준 정보를 나타냅니다. 사용자 에이전트 예제에서 추출한 대로 아래 표의 신호를 사용할 수 있습니다. [측정에 따라 가장 일반적인 키](assets/device_keys.csv) 목록을  [!UICONTROL Device Atlas] 다운로드합니다.

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
>사용자 에이전트 헤더에서 하나 이상의 신호를 검색할 수 없는 경우에도 다른 신호는 여전히 [!UICONTROL Data Collection Servers]으로 전달됩니다.

>[!MORELIKETHIS]
>
>* [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)

