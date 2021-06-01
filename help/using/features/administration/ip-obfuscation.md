---
description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
seo-description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
solution: Audience Manager
title: IP 주소 난독화
feature: 데이터 거버넌스 및 개인 정보
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# IP 주소 난독화 {#ip-obfuscation}

Audience Manager에 수집된 IP 주소를 난독화하려면 이 기능을 사용하십시오.

## 개요 및 방법론 {#overview-and-methodology}

회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.

### IP 난독화 방법론

&quot;계획적 개인 정보 보호&quot;(Privacy By Design)라는 원칙에 따라 Adobe Audience Manager에서는 고객이 전 세계 모든 지역 간에 또는 특정 국가에 대해 UI에서 IP 난독화를 사용할 수 있도록 허용합니다. 이 설정을 사용하면 IP 주소를 Audience Manager으로 수집할 때 IP 주소의 마지막 8진수(마지막 부분)가 즉시 삭제됩니다. Audience Manager은 처리 전에(IP 주소의 선택적 지역 조회 또는 로깅 전 포함) IP 주소에서 이 부분을 삭제합니다. 예:

* 난독화 전:`255.255.255.255`
* 난독화 후:`255.255.255.0`

[데이터 개인 정보 보호 섹션](/help/using/overview/data-security-and-privacy/data-privacy.md)에서 IP 주소 수집 및 IP 주소 난독화 도 참조하십시오.

## IP 주소 난독화 요구 사항 {#ip-obfuscation-requirements}

IP 주소 난독화는 Audience Manager 관리자 계정에만 사용할 수 있습니다. 사용자에 대한 관리자 권한을 할당하는 방법을 알려면 [사용자 만들기](/help/using/features/administration/administration-overview.md#create-users) 를 참조하십시오.

>[!NOTE]
>
> Audience Manager에서 처리한 많은 양의 데이터로 인해, IP 난독화 변경 사항은 설정을 업데이트하는 시점부터 최대 4시간이 걸릴 수 있습니다.

## IP 주소 난독화 구성 {#configure-ip-obfuscation}

아래 절차에 따라 IP 주소 난독화를 구성하십시오.

1. 관리자 계정으로 Audience Manager에 로그인하고 **관리 > 개인 정보 보호**&#x200B;로 이동합니다.
2. 사용하려는 IP 난독화 유형을 선택합니다.
   1. **모든 IP 주소 난독화:** 이 IP 주소가 발생한 지역에 관계없이 모든 방문자 IP 주소의 마지막 8진수를 Audience Manager으로 난독화하도록 하려면 이 옵션을 선택합니다.
   2. **특정 국가의 IP 주소 난독화:** Audience Manager이 특정 국가의 방문자 IP 주소 마지막 8진수를 난독화하도록 하려면 이 옵션을 선택합니다. **국가 목록** 또는 해당 **검색** 필드를 사용하여 IP 난독화를 활성화할 국가를 찾고, + 아이콘을 클릭하여 **난독화에 대해 선택됨** 목록에 추가합니다. **난독화에 대해 선택됨** 목록에 필요한 모든 국가를 추가한 후에는 **저장**&#x200B;을 클릭합니다.

![](assets/ip-obfuscation.png)

## IP 주소 난독화 비활성화 {#disable-ip-obfuscation}

IP 주소 난독화를 전체적으로 비활성화하려면 **관리 > 개인 정보**&#x200B;로 이동한 다음 **IP 주소 난독화 안함**&#x200B;을 선택하고 **저장**&#x200B;을 클릭합니다.

특정 국가에 대해 IP 주소 난독화를 사용하지 않으려면 **난독화에 대해 선택됨** 목록에서 해당 국가를 찾은 다음 해당 **X** 아이콘을 클릭합니다. 완료되면 **저장**&#x200B;을 클릭합니다.

## 관련 개념 {#related-concepts}

* [데이터 개인 정보](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP 주소 난독화 비디오 데모
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
