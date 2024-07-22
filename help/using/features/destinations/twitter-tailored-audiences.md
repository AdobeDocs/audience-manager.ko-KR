---
description: 이 문서에서는 새 통합과 기존 통합 모두에 대해 Twitter 사용자 지정 대상을 구성하는 방법을 설명합니다.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: twitter 사용자 지정 대상을 셀프서비스 장치 기반 대상으로 구성
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# [!DNL Twitter Custom Audiences]을(를) 셀프 서비스 장치 기반 대상으로 구성 {#configure-twitter}

이 문서에서는 [사용자 지정 대상 Twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html)와의 통합을 구성하는 방법에 대해 설명합니다.

## 전제 조건 {#prerequisites}

[!DNL Twitter Custom Audiences] 대상을 구성하기 전에 다음 전제 조건을 충족하는지 확인하십시오.

* [!DNL Twitter Ads] 계정은 광고를 할 수 있어야 합니다. 새 [!DNL Twitter Ads] 계정은 계정을 만든 후 처음 2주 동안은 광고할 수 없습니다.
* Audience Manager에서 액세스 권한을 부여한 [!DNL Twitter] 사용자 계정에는 [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 권한이 활성화되어 있어야 합니다.
* Audience Manager 인스턴스에 첫 번째 [!DNL Twitter Custom Audiences] 대상을 만들 때 계정에 대해 [!DNL Twitter] ID 동기화(데이터 Source ID = 1123)를 활성화하려면 Adobe Consulting 또는 고객 지원 센터에 문의하십시오. Audience Manager과 [!DNL Twitter] 간의 올바른 동기화를 위해 필요합니다.

## 새 [!DNL Twitter Custom Audiences] 대상 추가 {#add-new-twitter-destination}

이 섹션에서는 [!DNL Twitter Custom Audiences]에 대한 새 장치 기반 대상을 구성할 때 따라야 하는 단계에 대해 설명합니다. 이 시나리오에서는 Adobe 컨설턴트나 고객 지원 센터를 통해 구성된 기존 [!DNL Twitter Custom Audiences] 대상이 없다고 가정합니다.

### 1단계. [!DNL Twitter Custom Audiences](으)로 인증 {#step1-authenticate-with-twitter}

장치 기반 대상을 추가하려면 먼저 Audience Manager과 [!DNL Twitter Custom Audiences] 계정을 연결해야 합니다. 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!DNL Administration > Integrated Accounts]**(으)로 이동합니다. 대상 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
1. **[!DNL Add Account]** 아이콘을 클릭합니다.
1. 인증 페이지로 리디렉션하려면 [!DNL Twitter Custom Audiences]을(를) 선택하고 **[!DNL Confirm]**&#x200B;을(를) 클릭하십시오.

   ![통합 플랫폼](assets/dbd-integrated-platforms.png)

1. 인증을 완료하면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!DNL Confirm]**&#x200B;을(를) 클릭합니다.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager과 [!DNL Twitter Custom Audiences]을(를) 연결한 후에는 새 대상을 만들 수 있습니다. 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름을 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 입력해야 합니다.

1. Audience Manager 계정에 로그인하고 **[!DNL Audience Data > Destinations]**(으)로 이동한 다음 **[!DNL Create Destination]**&#x200B;을(를) 클릭합니다.
1. **[!DNL Basic Information]** 섹션에서 새 대상에 대한 **[!DNL Name]** 및 **[!DNL Description]**&#x200B;을(를) 입력하고 아래 설정을 사용하십시오. ![설정](assets/dbd-new-basic.png)
1. **[!DNL Next]** 아이콘을 클릭합니다.
1. 이 대상에 대해 설정할 [데이터 내보내기 레이블](/help/using/features/data-export-controls.md#controls-labels)을 선택하십시오.
1. **[!DNL Save]** 아이콘을 클릭합니다.
1. **[!DNL Segment Mappings]** 섹션에서 이 대상으로 보낼 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.

## 세그먼트 매핑 고려 사항 {#segment-mapping-considerations}

대상 세그먼트를 [!UICONTROL Twitter]에 매핑할 때 다음 세그먼트 이름 지정 요구 사항을 충족하는지 확인하십시오.

* 사람이 읽을 수 있는 세그먼트 매핑 이름을 제공합니다. Audience Manager 세그먼트에 사용한 것과 동일한 이름을 사용하는 것이 좋습니다.
* 세그먼트 및 세그먼트 매핑 이름에 특수 문자(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)를 사용하지 마십시오. Audience Manager 세그먼트 이름에 이러한 문자가 포함되어 있는 경우 세그먼트를 [!UICONTROL Twitter] 대상에 매핑하기 전에 해당 문자를 제거하십시오.

### 예

* 올바른 세그먼트 또는 매핑 이름: &quot;미국 및 유럽 쇼핑객&quot;;
* 잘못된 세그먼트 또는 매핑 이름: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>이미 매핑된 세그먼트의 이름은 변경할 수 없습니다. Audience Manager은 세그먼트 이름을 사용하여 통합에서 세그먼트를 올바르게 식별합니다.

## 일치율 고려 사항 {#match-rates-considerations}

* Audience Manager과 [!UICONTROL Twitter Custom Audiences] 간의 통합은 과거 대상 다시 채우기를 지원합니다. 대상을 만들면 모든 세그먼트 자격이 [!UICONTROL Twitter](으)로 전송됩니다.

## 문제 해결 {#troubleshooting}

사용자 지정 대상 Twitter을 구성하거나 이 대상으로 데이터를 보낼 때 아래에 설명된 오류가 발생할 수 있습니다. 이 섹션에서는 오류를 일으킬 수 있는 원인과 오류를 수정하는 방법에 대해 설명합니다.

| 오류 메시지 | 발생 횟수 / 이유 | 해결 방법 |
|---|---|---|
| `Internal server error` | 이 오류 메시지는 오래된 버전의 Twitter API를 사용하여 새 [!DNL Twitter] 계정을 추가하려고 할 때 Audience Manager UI에 표시됩니다. | Adobe 고객 지원 센터에 문의하십시오. |
| `Twitter Error: This request is not properly authenticated` | 지원되지 않는 세그먼트 이름을 가진 세그먼트를 대상에 매핑하려고 하면 Audience Manager UI에 이 오류 메시지가 표시됩니다. | 매핑된 세그먼트 이름을 검토하고 이름에 지원되지 않는 문자가 포함되어 있지 않은지 확인하십시오. 지원되지 않는 문자 목록은 [세그먼트 매핑 고려 사항](#segment-mapping-considerations)을 참조하십시오. |
| `Twitter Error: Account XXXXXXXXX was not found` | 이 오류 메시지는 대상에 대해 구성된 자격 증명이 해당 Twitter 광고 계정에 액세스할 수 있는 권한이 없는 경우 Audience Manager UI에 표시됩니다. | <ul><li>사용 중인 계정 자격 증명이 [필수 구성 요소](#prerequisites)를 충족하는지 확인하십시오.</li><li>동일한 자격 증명을 사용하여 Twitter 광고 UI로 이동한 다음 해당 `XXXXXXXXX` 계정에 올바른 대상이 표시되는지 확인하십시오. </li></ul> |