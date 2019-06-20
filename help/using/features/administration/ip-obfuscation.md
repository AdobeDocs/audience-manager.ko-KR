---
description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
seo-description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
solution: Audience Manager
title: IP 주소 난독화
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP 주소 난독화 {#ip-obfuscation}

이 기능을 사용하여 Audience Manager에서 수집한 IP 주소를 난독화할 수 있습니다.

## Overview and Methodology {#overview-and-methodology}

회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.

### IP 난독화 방법론

&quot; 개인 정보 보호 중심의 설계 &quot;의 원칙을 따르는 Adobe Audience Manager를 사용하면 모든 지리적 지역 또는 특정 국가에서 전 세계적으로 IP 난독화를 활성화할 수 있습니다. 이 설정을 활성화하면 IP 주소가 Audience Manager로 인제스트되면 IP 주소의 마지막 옥텟 (마지막 부분) 이 즉시 무시됩니다. Audience Manager는 처리하기 전에 IP 주소의 이 부분을 삭제합니다 (선택 사항인 지리적 조회 또는 IP 주소의 기록 전). 예:

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

IP 주소 난독화는 Audience Manager 관리자 계정에서만 사용할 수 있습니다. See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> Audience Manager에서 처리하는 많은 양의 데이터로 인해, IP 난독화 변경 사항이 설정을 업데이트하면 즉시 시행되는 데 최대 4 시간이 걸릴 수 있습니다.

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

아래 절차에 따라 난독화를 구성합니다.

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. 사용할 IP 난독화의 유형을 선택합니다.
   1. **모든 IP 주소 난독화:** 이 옵션을 선택하면 Audience Manager가 원본 위치에 관계없이 모든 방문자 IP 주소의 마지막 옥텟을 난독화할 수 있습니다.
   2. **특정 국가의 IP 주소 난독화:** Audience Manager가 특정 국가의 방문자 IP 주소 중 마지막 옥텟을 난독화하도록 하려면 이 옵션을 선택합니다. Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you&#39;ve added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you&#39;re done.

## 관련 개념 {#related-concepts}

* [데이터 개인 정보](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP 주소 난독화 비디오 데모
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=kor)

