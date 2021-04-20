---
description: 이 문서에서는 신규 및 기존 통합 모두에 대해 Twitter 맞춤 대상을 구성하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 신규 및 기존 통합 모두에 대해 Twitter 맞춤 대상을 구성하는 방법에 대해 설명합니다.
seo-title: Twitter 맞춤 대상을 셀프서비스 장치 기반 대상으로 구성
solution: Audience Manager
title: Twitter 맞춤 대상을 셀프서비스 장치 기반 대상으로 구성
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# [!DNL Twitter Tailored Audiences]을(를) 셀프 서비스 장치 기반 대상 {#configure-twitter} 구성

이 문서에서는 [Twitter 맞춤 대상자](https://business.twitter.com/en/targeting/tailored-audiences.html)와의 통합을 구성하는 방법에 대해 설명합니다.

## 사전 요구 사항 {#prerequisites}

[!DNL Twitter Tailored Audiences] 대상을 구성하려면 먼저 충족해야 하는 다음 Twitter 사전 요구 사항을 검토하십시오.

1. [!DNL Twitter Ads] 계정은 광고를 수행할 수 있어야 합니다. 새 [!DNL Twitter Ads] 계정은 만든 후 처음 2주 이내에 광고를 수행할 수 없습니다.
2. Audience Manager에서 액세스하도록 인증한 [!DNL Twitter] 사용자 계정에는 [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 권한이 활성화되어 있어야 합니다.
3. Audience Manager 인스턴스에서 첫 번째 [!DNL Twitter Tailored Audiences] 대상을 만들 때 Adobe 컨설팅 또는 고객 지원 센터에 문의하여 계정에 대해 [!DNL Twitter] ID 동기화(데이터 소스 ID = 1123)를 활성화하십시오. Audience Manager과 [!DNL Twitter] 사이의 올바른 동기화를 수행하려면 이 항목이 필요합니다.

## 새 [!DNL Twitter Tailored Audiences] 대상 {#add-new-twitter-destination} 추가

이 섹션에서는 [!DNL Twitter Tailored Audiences]에 대한 새 장치 기반 대상을 구성할 때 따라야 하는 단계를 설명합니다. 이 시나리오에서는 Adobe 컨설턴트나 고객 지원 센터를 통해 구성된 기존 [!DNL Twitter Tailored Audiences] 대상이 없다고 가정합니다.

### 1단계. [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}로 인증

장치 기반 대상을 추가하려면 먼저 Audience Manager 및 [!DNL Twitter Tailored Audiences] 계정을 연결해야 합니다. 이를 위한 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!DNL Administration > Integrated Accounts]**&#x200B;으로 이동합니다. 대상 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
1. 클릭 **[!DNL Add Account]**.
1. [!DNL Twitter Tailored Audiences]을 선택하고 **[!DNL Confirm]**&#x200B;을 클릭하여 인증 페이지로 리디렉션합니다.                     ![통합 플랫폼](assets/dbd-integrated-platforms.png)
1. 인증된 후에는 연결된 광고주 계정을 볼 수 있는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!DNL Confirm]**&#x200B;을 클릭합니다.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager과 [!DNL Twitter Tailored Audiences]을(를) 연결했으면 새 대상을 만들 수 있습니다. 이를 위한 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 제공하십시오.

1. Audience Manager 계정에 로그인하고 **[!DNL Audience Data > Destinations]**&#x200B;으로 이동한 다음 **[!DNL Create Destination]**&#x200B;을 클릭합니다.
1. **[!DNL Basic Information]** 섹션에서 새 대상에 대해 **[!DNL Name]** 및 **[!DNL Description]**&#x200B;를 입력하고 아래 설정을 사용하십시오.![설치](assets/dbd-new-basic.png)
1. 클릭 **[!DNL Next]**.
1. 이 대상에 대해 설정할 [데이터 내보내기 레이블](/help/using/features/data-export-controls.md#controls-labels)을 선택합니다.
1. 클릭 **[!DNL Save]**.
1. **[!DNL Segment Mappings]** 섹션에서 이 대상으로 보낼 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.

## 세그먼트 매핑 고려 사항 {#segment-mapping-considerations}

대상 세그먼트를 [!UICONTROL Twitter]에 매핑할 때는 다음 세그먼트 이름 지정 요구 사항을 충족해야 합니다.

* 사람이 읽을 수 있는 세그먼트 매핑 이름을 제공합니다. Audience Manager 세그먼트에 사용한 것과 동일한 이름을 사용하는 것이 좋습니다.
* 세그먼트 및 세그먼트 매핑 이름에 특수 문자(`+` `,` `%` `:` `;` `@` `/` `=` `?` `$`)를 사용하지 마십시오. `&` Audience Manager 세그먼트 이름에 이러한 문자가 포함되어 있으면 세그먼트를 [!UICONTROL Twitter] 대상에 매핑하기 전에 제거하십시오.

### 예

* 올바른 세그먼트 또는 매핑 이름:&quot;미국 및 유럽 구매자&quot;;
* 잘못된 세그먼트 또는 매핑 이름:&quot;미국, 유럽 5h0pP3rs&quot;입니다.

>[!IMPORTANT]
>
>이미 매핑된 세그먼트의 이름은 변경할 수 없습니다. Audience Manager은 세그먼트 이름을 사용하여 통합에서 세그먼트를 올바르게 식별합니다.

## 일치 비율 고려 사항 {#match-rates-considerations}

* Audience Manager과 [!UICONTROL Twitter Tailored Audiences] 간의 통합은 내역 대상 채우기 기능을 지원합니다. 대상을 만들 때 모든 세그먼트 자격 조건은 [!UICONTROL Twitter]으로 전송됩니다.
