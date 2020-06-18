---
description: 이 문서에서는 신규 및 기존 통합 모두에 대해 Twitter 사용자 지정 대상을 구성하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 신규 및 기존 통합 모두에 대해 Twitter 사용자 지정 대상을 구성하는 방법에 대해 설명합니다.
seo-title: Twitter 맞춤 대상을 셀프서비스 장치 기반 대상으로 구성
solution: Audience Manager
title: Twitter 맞춤 대상을 셀프서비스 장치 기반 대상으로 구성
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 4%

---


# 셀프 서비스 [!DNL Twitter Tailored Audiences] 장치 기반 대상으로 구성 {#configure-twitter}

이 문서에서는 [Twitter 맞춤 대상과의 통합을 구성하는 방법에 대해 설명합니다](https://business.twitter.com/en/targeting/tailored-audiences.html).

## 사전 요구 사항 {#prerequisites}

대상을 구성하려면 먼저 충족해야 하는 다음 Twitter 사전 요구 사항을 검토하십시오. [!DNL Twitter Tailored Audiences]

1. 귀하의 [!DNL Twitter Ads] 계정은 광고를 받을 자격이 있어야 합니다. 새 [!DNL Twitter Ads] 계정은 만든 후 처음 2주 이내에 광고를 수행할 수 없습니다.
2. Audience Manager에서 액세스하도록 인증한 사용자 [!DNL Twitter] 계정에는 [Partner audience manager 권한이 활성화되어 있어야](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 합니다.
3. Audience Manager 인스턴스에서 첫 번째 [!DNL Twitter Tailored Audiences] 대상을 만들 때는 Adobe Consulting 또는 고객 지원 센터에 연락하여 계정에 대한 [!DNL Twitter] ID 동기화(데이터 소스 ID = 1123)를 활성화하십시오. Audience Manager과 간의 올바른 동기화를 위해 필요합니다 [!DNL Twitter].

## 새 대상 [!DNL Twitter Tailored Audiences] 추가 {#add-new-twitter-destination}

이 섹션에서는 에 대한 새 장치 기반 대상을 구성할 때 따라야 하는 단계를 설명합니다 [!DNL Twitter Tailored Audiences]. 이 시나리오는 Adobe 컨설턴트나 고객 지원 센터를 통해 구성된 기존 [!DNL Twitter Tailored Audiences] 대상이 없다고 가정합니다.

### 1단계. 인증 대상 [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

장치 기반 대상을 추가하려면 먼저 Audience Manager과 [!DNL Twitter Tailored Audiences] 계정을 연결해야 합니다. 이 작업을 수행하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인한 다음 로 이동합니다 **[!DNL Administration > Integrated Accounts]**. 대상 플랫폼과의 이전에 구성한 통합이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
1. 클릭 **[!DNL Add Account]**.
1. 을 선택하고 [!DNL Twitter Tailored Audiences] **[!DNL Confirm]** 클릭하여 인증 페이지로 리디렉션됩니다.                     ![통합 플랫폼](assets/dbd-integrated-platforms.png)
1. 인증하면 연결된 광고주 계정을 볼 수 있는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 을 클릭합니다 **[!DNL Confirm]**.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager과를 연결한 후 새 대상을 만들 [!DNL Twitter Tailored Audiences]수 있습니다. 이 작업을 수행하는 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 제공하십시오.

1. Audience Manager 계정에 로그인한 다음 이동 **[!DNL Audience Data > Destinations]**&#x200B;후 을 클릭합니다 **[!DNL Create Destination]**.
1. 섹션에서 **[!DNL Basic Information]** 새 대상에 대한 **[!DNL Name]** 및 **[!DNL Description]** 를 입력하고 아래 설정을 사용하십시오. ![설정](assets/dbd-new-basic.png)
1. 클릭 **[!DNL Next]**.
1. 이 대상에 대해 [설정할 데이터](/help/using/features/data-export-controls.md#controls-labels) 내보내기 레이블을 선택합니다.
1. 클릭 **[!DNL Save]**.
1. 섹션에서 **[!DNL Segment Mappings]** 이 대상으로 전송할 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.

## 세그먼트 매핑 고려 사항 {#segment-mapping-considerations}

대상 세그먼트를 매핑 대상 [!UICONTROL Twitter]으로 지정할 때는 다음 세그먼트 이름 지정 요구 사항을 충족해야 합니다.

* 사람이 읽을 수 있는 세그먼트 매핑 이름을 제공합니다. Audience Manager 세그먼트에 사용한 것과 동일한 이름을 사용하는 것이 좋습니다.
* 세그먼트 및 세그먼트 이름에 특수 문자(`,``%``:` 는 `;` 는 `@` `/` `=` `?` `$`)를 사용하지 마십시오. Audience Manager 세그먼트 이름에 이러한 문자가 포함되어 있으면 세그먼트를 [!UICONTROL Twitter] 대상에 매핑하기 전에 제거하십시오.

### 예

* 올바른 세그먼트 또는 매핑 이름: &quot;미국 및 유럽 구매자&quot;;
* 잘못된 세그먼트 또는 매핑 이름: &quot;미국, 유럽 5h0pP3rs&quot;입니다.

>[!IMPORTANT]
>
>이미 매핑된 세그먼트의 이름은 변경할 수 없습니다. Audience Manager은 세그먼트 이름을 사용하여 통합에서 세그먼트를 올바르게 식별합니다.

## 일치 비율 고려 사항 {#match-rates-considerations}

* 사용 [!UICONTROL Twitter Tailored Audiences]시 대상 페이지의 [!UICONTROL Segment Addressable Audience] 및 [!UICONTROL Segment Match Rate] 지표에 값이 표시되지 않습니다. 이 대상에 대한 일치 비율과 함께 대상을 일치시키는 것은 Adobe가 아니라 Adobe가 처리 및 호스팅하기 때문에 이러한 동작은 일반적인 [!UICONTROL Twitter]동작입니다.
* Audience Manager과 이전 대상 채우기 간의 통합을 [!UICONTROL Twitter Tailored Audiences] 지원합니다. 대상을 만들면 모든 세그먼트 자격 [!UICONTROL Twitter] 이 전송됩니다.
