---
description: 이 문서에서는 Audience Manager에서 고객 데이터가 어떻게 제어되는지 설명합니다.
seo-description: 이 문서에서는 Audience Manager에서 고객 데이터가 어떻게 제어되는지 설명합니다.
seo-title: 데이터 거버넌스
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, 개인 정보, 동의, 난독화, 거버넌스
title: 데이터 거버넌스
feature: 데이터 거버넌스 & 개인 정보 보호
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 94%

---

# 데이터 거버넌스

## 개요 {#overview}

Audience Manager의 데이터 거버넌스는 Audience Manager에서 고객 데이터의 라이프사이클을 말하며 [IP 주소 수집 및 난독화](data-governance.md#collecting-ip-addresses), [데이터 유지](data-governance.md#data-retention) 및 [국외 데이터 전송](data-governance.md#data-transfers)을 포함합니다.

## IP 주소 수집 및 IP 주소 난독화 {#collecting-ip-addresses}

고객의 웹 사이트에 대한 방문자의 [!DNL IP] 주소는 [!DNL IP] 주소가 저장되어 있을 수 있는 Adobe [!DNL DPC]([!DNL Data Processing Center])에 전송됩니다. 방문자에 대한 네트워크 구성에 따라서는, [!DNL IP] 주소가 꼭 방문자의 컴퓨터 [!DNL IP] 주소를 나타내지는 않을 수 있습니다. 예를 들어 [!DNL IP] 주소가 NAT(Network Address Translation) 방화벽, [!DNL HTTP] 프록시 또는 인터넷 게이트웨이의 외부 [!DNL IP] 주소일 수 있습니다.

**IP 난독화 방법론:** &quot;계획적 개인 정보 보호&quot;(Privacy By Design)라는 원칙에 따라 Adobe Audience Manager에서는 고객이 전 세계 모든 지역 간에 또는 특정 국가에 대해 UI에서 [!DNL IP] 난독화를 사용할 수 있도록 허용합니다. 이 설정을 활성화할 경우 [!DNL IP] 주소가 Audience Manager에 섭취될 때 [!DNL IP] 주소의 마지막 옥텟(마지막 부분)이 즉시 삭제됩니다. Audience Manager는 처리 전에([!DNL IP] 주소의 선택적 지역 조회 또는 로깅 전 포함) [!DNL IP] 주소에서 이 부분을 삭제합니다. 예:

* 전: `255.255.255.255`
* 후: `255.255.255.0`

>[!NOTE]
>
>Audience Manager 사용자 인터페이스에서 [!DNL IP] 주소 난독화를 사용하도록 설정하는 방법을 알려면 [IP 주소 난독화](../../features/administration/ip-obfuscation.md) 를 참조하십시오.

Audience Manager에서 [!DNL IP] 주소 난독화가 작동하는 방식을 이해하려면 아래 비디오를 보십시오.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**지리 특성:** [!DNL IP] 주소 난독화를 사용하는 경우 Audience Manager에서 지리 특성 및 보고에 [!DNL IP] 주소의 나머지 옥텟을 계속해서 사용할 수 있습니다. [!DNL IP] 주소 난독화를 사용하지 않는 경우에는 Audience Manager가 전체 [!DNL IP] 주소를 사용합니다. 어느 경우에나 지역으로 [!DNL IP] 위치를 식별할 수 있는 지리 특성 기능을 사용할 수 있지만 [!DNL IP] 난독화를 사용 중인 경우 약간의 정밀도 손실이 있습니다. 도시 수준의 정보를 획득하는 것은 [!DNL IP] 주소 난독화의 영향을 크게 받을 수 있습니다. 지역 및 국가 수준의 정보를 획득하는 것은 IP 주소 난독화의 영향을 약간만 받아야 합니다. 지리 특성 데이터는 개인 수준이 아니라 도시 수준이나 우편 번호 수준으로만 세분화됩니다. [지역 타겟팅](../../features/traits/trait-geotarget-keys.md) 및 지역 변수를 사용하여 트레이트를 설정하는 방법에 대해 자세히 알아보십시오.

## Audience Manager의 데이터 유지 {#data-retention}

데이터에 적절하고 안전하며시기 적절한 데이터 보존 정책을 적용하는 것은 데이터 개인 정보 규정을 준수하는 데 중요한 부분입니다. Audience Manager 고객은 필요한 TTL(Time to Live)을 정의하여 트레이트 및 세그먼트에 대한 사용자 지정 유지 기간을 설정할 수 있습니다. 유지 기간에 대한 자세한 내용은 [데이터 유지 FAQ](../../faq/faq-privacy.md)를 참조하십시오.

## 국외 데이터 전송 {#data-transfers}

Audience Manager가 국경을 넘어 고객의 개인 데이터를 전송할 때 Audience Manager는 해당 법률에 따라 전송합니다. 자세히 알려면 [Adobe 개인 정보 보호 센터](https://www.adobe.com/kr/privacy/eudatatransfers.html)를 방문하십시오.
