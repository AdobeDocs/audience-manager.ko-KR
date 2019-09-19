---
description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
seo-description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
solution: Audience Manager
title: IP 주소 난독화
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP 주소 난독화 {#ip-obfuscation}

이 기능을 사용하여 Audience Manager에서 수집한 IP 주소를 난독화합니다.

## 개요 및 방법론 {#overview-and-methodology}

회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.

### IP 난독화 방법론

"Privacy By Design"의 원칙에 따라, Adobe Audience Manager를 사용하면 모든 지리적 지역 또는 특정 국가에서 UI의 IP 난독화를 활성화할 수 있습니다. 이 설정을 활성화하면 IP 주소가 Audience Manager로 인제스트되면 IP 주소의 마지막 8진수(마지막 부분)가 즉시 삭제됩니다. Audience Manager는 처리하기 전에 IP 주소의 이 부분을 삭제합니다(IP 주소의 지리적 조회 또는 로깅 전에 포함). 예:

* 난독화 전: `255.255.255.255`
* 난독화 후: `255.255.255.0`

데이터 개인 정보 섹션에서 IP 주소 및 IP 주소 난독화를 [참조하십시오](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP 주소 난독화 요구 사항 {#ip-obfuscation-requirements}

IP 주소 난독화는 Audience Manager 관리자 계정에서만 사용할 수 있습니다. 사용자에 [대한 관리자](/help/using/features/administration/administration-overview.md#create-users) 권한을 할당하는 방법을 이해하려면 사용자 만들기를 참조하십시오.

>[!NOTE]
>
> Audience Manager에서 처리하는 많은 양의 데이터로 인해 IP 난독화 변경 사항이 적용되려면 설정을 업데이트한 시점부터 최대 4시간이 걸릴 수 있습니다.

## IP 주소 난독화 구성 {#configure-ip-obfuscation}

아래 절차에 따라 IP 주소 난독화를 구성합니다.

1. 관리자 계정으로 Audience Manager에 로그인한 다음 관리 &gt; 개인 **정보로 이동합니다**.
2. 사용할 IP 난독화의 유형을 선택합니다.
   1. **** 모든 IP 주소 난독화:Audience Manager가 모든 방문자 IP 주소의 마지막 8진수를 난독화하도록 하려면 이 옵션을 선택합니다.
   2. **** 특정 국가의 IP 주소 난독화:Audience Manager가 특정 국가의 방문자 IP 주소의 마지막 8진수를 난독화하도록 하려면 이 옵션을 선택합니다. 국가 **목록** 또는 해당 **검색** 필드를 사용하여 IP 난독화를 활성화할 국가를 찾고 + 아이콘을 클릭하여 난독화를 위해 선택됨 **목록에 추가합니다** . 난독화를 위해 선택됨 목록에 필요한 모든 국가를 추가한 **후** 저장을 **클릭합니다**.

![](assets/ip-obfuscation.png)

## IP 주소 난독화 비활성화 {#disable-ip-obfuscation}

IP 주소 난독화를 전역적으로 비활성화하려면 [관리] &gt; [ **개인 정보**] **로 이동하여 [IP 주소 난독화**&#x200B;안 함]을 선택한 다음 [저장]을 **클릭합니다**.

특정 국가의 IP 주소 난독화를 비활성화하려면 난독화를 위해 선택됨 **목록에서** 국가를 찾은 다음 해당 X **아이콘을 클릭합니다** . Click **Save** when you're done.

## 관련 개념 {#related-concepts}

* [데이터 개인 정보](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP 주소 난독화 비디오 데모
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=kor)

