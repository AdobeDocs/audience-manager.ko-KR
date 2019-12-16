---
description: 이 문서에서는 Audience Manager에서 고객 데이터를 관리하는 방법을 설명합니다.
seo-description: 이 문서에서는 Audience Manager에서 고객 데이터를 관리하는 방법을 설명합니다.
seo-title: 데이터 거버넌스
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: 데이터 거버넌스
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# 데이터 거버넌스

## 개요 {#overview}

Audience Manager의 데이터 거버넌스는 Audience Manager의 고객 데이터 라이프사이클을 의미하며, IP 주소 수집 및 난독화, [데이터 유지](data-governance.md#collecting-ip-addresses)및 [국경을](data-governance.md#data-retention)통한 데이터 [전송을](data-governance.md#data-transfers)포함합니다.

## IP 주소 및 IP 주소 난독화 수집 {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP 난독화 방법론:"Privacy By Design"의 원칙에 따라 Adobe Audience Manager를 사용하면 모든 지리적 지역 또는 특정 국가에서 UI [!DNL IP] 의 난독화를 활성화할 수 있습니다. 이 설정을 활성화하면 Audience Manager로 주소를 인제스트할 때 [!DNL IP] 주소의 마지막 8진수(마지막 부분) [!DNL IP] 가 즉시 삭제됩니다. Audience Manager는 처리 전(선택 사항인 지리적 조회 또는 주소의 로깅 전에 포함) 주소의 이 부분을 [!DNL IP] [!DNL IP] 삭제합니다. 예:

* : `255.255.255.255`
* 후: `255.255.255.0`

>[!NOTE]
>
>Audience [Manager UI에서 주소 난독화를](../../features/administration/ip-obfuscation.md) 활성화하는 방법은 IP 주소 난독화를 [!DNL IP] 참조하십시오.

Audience Manager에서 주소 난독화가 작동하는 방식을 이해하려면 아래 비디오를 [!DNL IP] 시청하십시오.

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=kor)

**** 지리 특성:주소 난독화를 활성화하면 주소의 나머지 [!DNL IP] [!DNL IP] 주소를 여전히 Audience Manager의 지리 특성 및 보고에 사용할 수 있습니다. 주소 난독화를 활성화하지 않으면 Audience Manager에서 전체 [!DNL IP] [!DNL IP] 주소를 사용합니다. 두 경우 모두 지리적 영역별로 [!DNL IP] 위치를 식별할 수 있지만, 난독화를 사용하는 경우 약간의 정밀도가 손실되는 지리적 세그멘테이션 기능을 사용할 [!DNL IP] 수 있습니다. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. 지역 및 국가 수준 정보를 획득하는 것은 약간 영향을 받아야 합니다. 지리적 세그멘테이션 데이터는 도시 수준이나 우편 번호 수준에만 세분화되며 개별 수준에는 해당되지 않습니다. 지리적 [타깃팅](../../features/traits/trait-geotarget-keys.md) 및 지리적 변수를 사용하여 트레이트를 설정하는 방법에 대한 자세한 내용을 살펴보십시오.

## Audience Manager의 데이터 유지 {#data-retention}

데이터에 적절하고 안전하며 시기 적절한 데이터 보존 정책을 적용하는 것은 데이터 개인 정보 보호 규정을 준수하기 위한 중요한 부분입니다. Audience Manager 고객은 필요한 TTL(Time to Live)을 정의하여 트레이트 및 세그먼트에 사용자 지정 유지 기간을 설정할 수 있습니다. 유지 [기간에 대한 자세한 내용은 데이터](../../faq/faq-privacy.md) 유지 FAQ를 참조하십시오.

## 국경을 통한 데이터 전송 {#data-transfers}

Audience Manager가 고객의 개인 데이터를 국경을 넘어 전송하는 경우 Audience Manager는 해당 법률을 준수합니다. 자세한 내용은 [Adobe](https://www.adobe.com/privacy/eudatatransfers.html) 개인 정보 보호 센터를 참조하십시오.