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
source-wordcount: '699'
ht-degree: 1%

---

# 구성 [!DNL Twitter Custom Audiences] 셀프서비스 장치 기반 대상 {#configure-twitter}

이 문서에서는 통합 구성 방법을 설명합니다. [사용자 지정 대상 twitter](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## 사전 요구 사항 {#prerequisites}

을(를) 구성하기 전에 [!DNL Twitter Custom Audiences] 대상, 다음 전제 조건을 충족하는지 확인하십시오.

* 사용자 [!DNL Twitter Ads] 계정은 광고를 할 자격이 있어야 합니다. 신규 [!DNL Twitter Ads] 계정은 생성 후 처음 2주 동안은 광고할 수 없습니다.
* 사용자 [!DNL Twitter] Audience Manager에서 액세스 권한을 부여한 사용자 계정에는 [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 사용 권한이 활성화되었습니다.
* 첫 번째 [!DNL Twitter Custom Audiences] Audience Manager 인스턴스의 대상을 활성화하려면 Adobe 컨설팅 또는 고객 지원 센터에 문의하십시오. [!DNL Twitter] 계정에 대한 ID 동기화(데이터 소스 ID = 1123). Audience Manager과 간의 올바른 동기화를 위해 필요합니다. [!DNL Twitter].

## 새 항목 추가 [!DNL Twitter Custom Audiences] 대상 {#add-new-twitter-destination}

이 절에서는 새 장치 기반 대상을 구성할 때 따라야 할 단계에 대해 설명합니다 [!DNL Twitter Custom Audiences]. 이 시나리오에서는 사용자가 존재하지 않는다고 가정합니다. [!DNL Twitter Custom Audiences] Adobe 컨설턴트나 고객 지원 센터를 통해 구성된 대상.

### 1단계. 다음으로 인증 [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

장치 기반 대상을 추가하려면 먼저 Audience Manager과 [!DNL Twitter Custom Audiences] 계정입니다. 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 다음으로 이동 **[!DNL Administration > Integrated Accounts]**. 대상 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
1. 클릭 **[!DNL Add Account]**.
1. 선택 [!DNL Twitter Custom Audiences] 및 클릭 **[!DNL Confirm]** 인증 페이지로 리디렉션됩니다.

   ![통합 플랫폼](assets/dbd-integrated-platforms.png)

1. 인증을 완료하면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!DNL Confirm]**.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager 및 을(를) 연결한 후 [!DNL Twitter Custom Audiences], 새 대상을 만들 수 있습니다. 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름을 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 입력해야 합니다.

1. Audience Manager 계정에 로그인하고 다음으로 이동 **[!DNL Audience Data > Destinations]**, 및 클릭 **[!DNL Create Destination]**.
1. 다음에서 **[!DNL Basic Information]** 섹션, 입력 **[!DNL Name]** 및 **[!DNL Description]** 새 대상에 대해 아래 설정을 사용하십시오. ![설정](assets/dbd-new-basic.png)
1. 클릭 **[!DNL Next]**.
1. 다음을 선택합니다. [데이터 내보내기 레이블](/help/using/features/data-export-controls.md#controls-labels) 이 대상에 대해 설정할 수 있습니다.
1. 클릭 **[!DNL Save]**.
1. 다음에서 **[!DNL Segment Mappings]** 섹션에서 이 대상으로 전송할 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.

## 세그먼트 매핑 고려 사항 {#segment-mapping-considerations}

대상 세그먼트를에 매핑할 때 [!UICONTROL Twitter], 다음 세그먼트 이름 지정 요구 사항을 충족해야 합니다.

* 사람이 읽을 수 있는 세그먼트 매핑 이름을 제공합니다. Audience Manager 세그먼트에 사용한 것과 동일한 이름을 사용하는 것이 좋습니다.
* 특수 문자 사용 안 함(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`)을 클릭하여 제품에서 사용할 수 있습니다. Audience Manager 세그먼트 이름에 이러한 문자가 포함되어 있는 경우 세그먼트를 다음에 매핑하기 전에 제거하십시오. [!UICONTROL Twitter] 대상.

### 예

* 올바른 세그먼트 또는 매핑 이름: &quot;미국 및 유럽 쇼핑객&quot;;
* 잘못된 세그먼트 또는 매핑 이름: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>이미 매핑된 세그먼트의 이름은 변경할 수 없습니다. Audience Manager은 세그먼트 이름을 사용하여 통합에서 세그먼트를 올바르게 식별합니다.

## 일치율 고려 사항 {#match-rates-considerations}

* Audience Manager과 간의 통합 [!UICONTROL Twitter Custom Audiences] 는 과거 대상자 채우기를 지원합니다. 모든 세그먼트 자격 요건이 (으)로 전송됩니다. [!UICONTROL Twitter] 대상을 만들 때

## 문제 해결 {#troubleshooting}

사용자 지정 대상 Twitter을 구성하거나 이 대상으로 데이터를 보낼 때 아래에 설명된 오류가 발생할 수 있습니다. 이 섹션에서는 오류를 일으킬 수 있는 원인과 오류를 수정하는 방법에 대해 설명합니다.

| 오류 메시지 | 발생 횟수 / 이유 | 해결 방법 |
|---|---|---|
| `Internal server error` | 이 오류 메시지는 새 항목을 추가하려고 할 때 Audience Manager UI에 표시됩니다 [!DNL Twitter] twitter API의 오래된 버전을 사용하는 계정입니다. | Adobe 고객 지원 문의. |
| `Twitter Error: This request is not properly authenticated` | 지원되지 않는 세그먼트 이름을 가진 세그먼트를 대상에 매핑하려고 하면 Audience Manager UI에 이 오류 메시지가 표시됩니다. | 매핑된 세그먼트 이름을 검토하고 이름에 지원되지 않는 문자가 포함되어 있지 않은지 확인하십시오. 다음을 참조하십시오 [세그먼트 매핑 고려 사항](#segment-mapping-considerations) 지원되지 않는 문자 목록입니다. |
| `Twitter Error: Account XXXXXXXXX was not found` | 이 오류 메시지는 대상에 대해 구성된 자격 증명이 해당 Twitter 광고 계정에 액세스할 수 있는 권한이 없는 경우 Audience Manager UI에 표시됩니다. | <ul><li>사용 중인 계정 자격 증명이 [전제 조건](#prerequisites).</li><li>동일한 자격 증명을 사용하여 Twitter 광고 UI로 이동한 다음 해당하는 아래에 올바른 대상이 표시되는지 확인합니다 `XXXXXXXXX` 계정입니다. </li></ul> |