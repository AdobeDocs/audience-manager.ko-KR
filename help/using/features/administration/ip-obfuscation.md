---
description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
seo-description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
solution: Audience Manager
title: IP 주소 난독화
feature: 데이터 거버넌스 및 개인 정보
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 22%

---

# IP 주소 난독화 {#ip-obfuscation}

Audience Manager에서 수집한 IP 주소를 난독화하려면 이 기능을 사용합니다.

## 개요 및 방법론 {#overview-and-methodology}

회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.

### IP 난독화 방법론

&quot;Privacy By Design&quot;의 원칙을 따르는 Adobe Audience Manager을 통해 고객은 모든 지역 또는 특정 국가에서 UI의 IP 난독화를 활성화할 수 있습니다. 이 설정을 활성화하면 IP 주소가 Audience Manager으로 인제스트될 때 IP 주소의 마지막 8진수(마지막 부분)가 즉시 삭제됩니다. Audience Manager은 처리하기 전에 IP 주소의 이 부분을 삭제합니다(IP 주소의 위치 조회 또는 로깅 전후의 선택 사항 포함). 예:

* 난독화 전:`255.255.255.255`
* 난독화 후:`255.255.255.0`

자세한 내용은 [데이터 개인 정보 섹션](/help/using/overview/data-security-and-privacy/data-privacy.md)에서 IP 주소 및 IP 주소 난독화 수집을 참조하십시오.

## IP 주소 난독화 요구 사항 {#ip-obfuscation-requirements}

IP 주소 난독화는 Audience Manager 관리자 계정에서만 사용할 수 있습니다. 사용자에 대한 관리자 권한을 할당하는 방법을 이해하려면 [사용자 만들기](/help/using/features/administration/administration-overview.md#create-users)를 참조하십시오.

>[!NOTE]
>
> Audience Manager에서 처리하는 많은 양의 데이터로 인해 IP 난독화 변경 사항이 적용되기까지는 설정을 업데이트하는 시점부터 최대 4시간이 걸릴 수 있습니다.

## IP 주소 난독화 구성 {#configure-ip-obfuscation}

IP 주소 난독화를 구성하려면 아래 단계를 따르십시오.

1. 관리자 계정으로 Audience Manager에 로그인하고 **관리 > 개인 정보**&#x200B;로 이동합니다.
2. 사용할 IP 난독화 유형을 선택합니다.
   1. **모든 IP 주소 난독화: 이 옵션을** 선택하면 방문자가 가져온 지역에 상관없이 모든 방문자 IP 주소의 마지막 8진수 텍스트를 Audience Manager으로 난독화하게 됩니다.
   2. **특정 국가의 IP 주소 난독화: 특정 국가의 방문자 IP 주소의 마지막 8번째 텍스트를 Audience Manager으로 난독화하도록 하려면 이 옵션을** 선택합니다. **국가 목록** 또는 해당 **검색** 필드를 사용하여 IP 난독화를 활성화할 국가를 찾고 + 아이콘을 클릭하여 난독화를 위해 **선택됨** 목록에 추가합니다. 필요한 모든 국가를 **난독화** 목록에 추가한 후 **저장**&#x200B;을 클릭합니다.

![](assets/ip-obfuscation.png)

## IP 주소 난독화 사용 안 함 {#disable-ip-obfuscation}

IP 주소 난독화를 전체적으로 비활성화하려면 **관리 > 개인 정보**&#x200B;로 이동하고 **IP 주소 난독화 안 함**&#x200B;을 선택한 다음 **저장**&#x200B;을 클릭합니다.

특정 국가에서 IP 주소 난독화를 비활성화하려면 **난독화에 대해 선택됨** 목록에서 국가를 찾은 다음 해당 **X** 아이콘을 클릭합니다. 완료되면 **저장**&#x200B;을 클릭합니다.

## 관련 개념 {#related-concepts}

* [데이터 개인 정보](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP 주소 난독화 비디오 데모
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
