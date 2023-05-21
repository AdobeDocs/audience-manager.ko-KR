---
description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP 주소 난독화
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 16%

---

# IP 주소 난독화 {#ip-obfuscation}

이 기능을 사용하여 Audience Manager에서 수집된 IP 주소를 난독화합니다.

## 개요 및 방법론 {#overview-and-methodology}

회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.

### IP 난독화 방법론

&quot;계획적 개인 정보 보호&quot;(Privacy By Design)라는 원칙에 따라 Adobe Audience Manager에서는 고객이 전 세계 모든 지역 간에 또는 특정 국가에 대해 UI에서 IP 난독화를 사용할 수 있도록 허용합니다. 이 설정을 사용하면 IP 주소를 Audience Manager으로 수집할 때 IP 주소의 마지막 옥텟(마지막 부분)이 즉시 삭제됩니다. Audience Manager은 처리 전에(IP 주소의 선택적 지역 조회 또는 로깅 전 포함) IP 주소의 이 부분을 삭제합니다. 예:

* 난독화 전: `255.255.255.255`
* 난독화 후: `255.255.255.0`

에서 IP 주소 수집 및 IP 주소 난독화 를 참조하십시오. [데이터 개인 정보 보호 섹션](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP 주소 난독화 요구 사항 {#ip-obfuscation-requirements}

IP 주소 난독화는 Audience Manager 관리자 계정에만 사용할 수 있습니다. 다음을 참조하십시오 [사용자 만들기](/help/using/features/administration/administration-overview.md#create-users) 를 사용하여 사용자에 대한 관리자 권한을 할당하는 방법을 이해할 수 있습니다.

>[!NOTE]
>
> Audience Manager에서 처리하는 대량의 데이터로 인해 IP 난독화 변경 사항은 설정을 업데이트하는 순간부터 적용되는 데 최대 4시간이 소요될 수 있습니다.

## IP 주소 난독화 구성 {#configure-ip-obfuscation}

아래 단계에 따라 IP 주소 난독화를 구성하십시오.

1. 관리자 계정으로 Audience Manager에 로그인하고 다음으로 이동 **관리 > 개인 정보**.
2. 사용할 IP 난독화의 유형을 선택합니다.
   1. **모든 IP 주소 난독화:** 이 옵션을 선택하면 Audience Manager은 자신이 속한 지역에 관계없이 모든 방문자 IP 주소의 마지막 옥텟을 난독화합니다.
   2. **특정 국가의 IP 주소 난독화:** Audience Manager이 특정 국가에 대한 방문자 IP 주소의 마지막 옥텟을 난독화하도록 하려면 이 옵션을 선택합니다. 사용 **국가 목록** 또는 해당 **검색** 필드를 사용하여 IP 난독화를 사용할 국가를 찾고 + 아이콘을 클릭하여 해당 국가를 **난독화를 위해 선택됨** 목록을 표시합니다. 필요한 모든 국가를 **난독화를 위해 선택됨** 목록, 클릭 **저장**.

![](assets/ip-obfuscation.png)

## IP 주소 난독화 비활성화 {#disable-ip-obfuscation}

IP 주소 난독화를 전역적으로 비활성화하려면 **관리 > 개인 정보**, 선택 **IP 주소 난독화 안 함**, 및 클릭 **저장**.

특정 국가에 대해 IP 주소 난독화를 비활성화하려면 **난독화를 위해 선택됨** 목록을 작성한 다음 해당하는 을 클릭합니다 **X** 아이콘. 클릭 **저장** 다 끝나면.

## 관련 개념 {#related-concepts}

* [데이터 개인 정보](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP 주소 난독화 비디오 데모
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
