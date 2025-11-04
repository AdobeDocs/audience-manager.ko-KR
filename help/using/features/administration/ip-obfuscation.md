---
description: 회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP 주소 난독화
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 12%

---

# IP 주소 난독화 {#ip-obfuscation}

이 기능을 사용하여 Audience Manager에서 수집된 IP 주소를 난독화합니다.

## 개요 및 방법론 {#overview-and-methodology}

회사에서 글로벌 개인 정보 보호 규정으로 인해 여러 국가의 IP 주소를 난독 처리하려고 할 수 있습니다. Audience Manager를 사용하면 글로벌 또는 국가별로 방문자 IP 주소를 난독 처리할 수 있습니다.

### IP 난독화 방법론

&quot;계획적 개인 정보 보호&quot;(Privacy By Design)라는 원칙에 따라 Adobe Audience Manager에서는 고객이 전 세계 모든 지역 간에 또는 특정 국가에 대해 UI에서 IP 난독화를 사용할 수 있도록 허용합니다. 이 설정을 사용하면 IP 주소가 Audience Manager에 섭취될 때 IP 주소의 마지막 옥텟(마지막 부분)이 즉시 삭제됩니다. Audience Manager은 처리 전에(IP 주소의 선택적 지역 조회 또는 로깅 전 포함) IP 주소의 이 부분을 삭제합니다. 예:

* 난독화 전: `255.255.255.255`
* 난독화 후: `255.255.255.0`

[데이터 개인 정보 보호 섹션](/help/using/overview/data-security-and-privacy/data-privacy.md)에서 IP 주소 수집 및 IP 주소 난독화를 참조하십시오.

### IP 난독화 사전 요구 {#precedence}

[데이터스트림 수준 IP 난독화](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=ko#create)가 Audience Manager에 설정된 IP 난독화 옵션보다 우선하며 모든 IP 주소에 적용됩니다. Audience Manager에서 수행한 모든 지리적 위치 조회는 데이터 스트림 수준 [!UICONTROL IP obfuscation] 옵션의 영향을 받습니다. 완전히 난독화된 IP를 기반으로 하는 Audience Manager의 지리적 위치 조회를 수행하면 알 수 없는 영역이 발생하고 결과 지리적 위치 데이터를 기반으로 하는 모든 세그먼트는 실현되지 않습니다.

## IP 주소 난독화 요구 사항 {#ip-obfuscation-requirements}

IP 주소 난독화는 Audience Manager 관리자 계정만 사용할 수 있습니다. 사용자에 대한 관리자 권한을 할당하는 방법을 이해하려면 [사용자 만들기](/help/using/features/administration/administration-overview.md#create-users)를 참조하십시오.

>[!NOTE]
>
> Audience Manager에서 처리하는 대량의 데이터로 인해 IP 난독화 변경 사항은 설정을 업데이트하는 순간부터 적용되는 데 최대 4시간이 소요될 수 있습니다.

## IP 주소 난독화 구성 {#configure-ip-obfuscation}

아래 단계에 따라 IP 주소 난독화를 구성하십시오.

1. 관리자 계정으로 Audience Manager에 로그인하고 **관리 > 개인 정보**(으)로 이동합니다.
2. 사용할 IP 난독화의 유형을 선택합니다.
   1. **모든 IP 주소 난독화:** Audience Manager에서 시작된 지역에 관계없이 모든 방문자 IP 주소의 마지막 옥텟을 난독화하도록 하려면 이 옵션을 선택하십시오.
   2. **특정 국가의 IP 주소 난독화:** Audience Manager에서 특정 국가의 마지막 방문자 IP 주소 8진수를 난독화하도록 하려면 이 옵션을 선택하십시오. **국가 목록** 또는 해당 **검색** 필드를 사용하여 IP 난독화를 사용할 국가를 찾고 + 아이콘을 클릭하여 **난독화를 위해 선택됨** 목록에 추가하십시오. **난독화를 위해 선택됨** 목록에 필요한 모든 국가를 추가한 후 **저장**&#x200B;을 클릭합니다.

![](assets/ip-obfuscation.png)

## IP 주소 난독화 비활성화 {#disable-ip-obfuscation}

IP 주소 난독화를 전역적으로 사용하지 않으려면 **관리 > 개인 정보**(으)로 이동하여 **IP 주소 난독화 안 함**&#x200B;을 선택하고 **저장**&#x200B;을 클릭합니다.

특정 국가에 대해 IP 주소 난독화를 사용하지 않으려면 **난독화를 위해 선택됨** 목록에서 해당 국가를 찾은 다음 해당 **X** 아이콘을 클릭합니다. 완료되면 **저장**&#x200B;을 클릭하세요.

## 관련 개념 {#related-concepts}

* [데이터 개인 정보 보호](/help/using/overview/data-security-and-privacy/data-privacy.md)
* IP 주소 난독화 비디오 데모

>[!VIDEO](https://video.tv.adobe.com/v/34980?captions=kor)
