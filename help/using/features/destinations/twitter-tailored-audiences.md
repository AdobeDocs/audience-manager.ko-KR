---
description: 이 문서에서는 새 통합 및 기존 통합 둘 다에 대해 Twitter 사용자 지정 대상을 구성하는 방법을 설명합니다.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: twitter 사용자 지정 대상을 셀프 서비스 장치 기반 대상으로 구성
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# 구성 [!DNL Twitter Custom Audiences] 셀프서비스 장치 기반 대상으로 사용 {#configure-twitter}

이 문서에서는 [Twitter 사용자 지정 대상](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## 사전 요구 사항 {#prerequisites}

구성하기 전에 [!DNL Twitter Custom Audiences] 대상, 다음 전제 조건을 충족하는지 확인하십시오.

* 사용자 [!DNL Twitter Ads] 계정에 광고 자격이 있어야 합니다. 새로 만들기 [!DNL Twitter Ads] 계정을 만든 후 처음 2주 동안은 광고를 할 수 없습니다.
* 사용자 [!DNL Twitter] Audience Manager에서 액세스 권한을 부여한 사용자 계정에는 [파트너 대상 관리자](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 사용 권한이 활성화되어 있습니다.
* 첫 번째 [!DNL Twitter Custom Audiences] Audience Manager 인스턴스의 대상에 대해서는 Adobe 컨설팅 또는 고객 지원 센터에 문의하여 [!DNL Twitter] 계정에 대한 ID 동기화(데이터 소스 ID = 1123). Audience Manager과 간의 올바른 동기화를 위해 필요합니다 [!DNL Twitter].

## 새로 추가 [!DNL Twitter Custom Audiences] 대상 {#add-new-twitter-destination}

이 섹션에서는 다음에 대한 새 장치 기반 대상을 구성할 때 따라야 하는 절차에 대해 설명합니다 [!DNL Twitter Custom Audiences]. 이 시나리오는 기존 항목이 없다고 가정합니다 [!DNL Twitter Custom Audiences] Adobe 컨설턴트나 고객 지원을 통해 구성된 대상입니다.

### 1단계. 인증 [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

장치 기반 대상을 추가하려면 먼저 Audience Manager 및 대상을 연결해야 합니다 [!DNL Twitter Custom Audiences] 계정이 필요합니다. 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!DNL Administration > Integrated Accounts]**. 대상 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 해당 통합이 표시되어야 합니다. 그렇지 않으면 페이지가 비어 있습니다.
1. 클릭 **[!DNL Add Account]**.
1. 선택 [!DNL Twitter Custom Audiences] 을(를) 클릭합니다. **[!DNL Confirm]** 인증 페이지로 리디렉션됩니다.

   ![통합 플랫폼](assets/dbd-integrated-platforms.png)

1. 인증되면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 을(를) 클릭합니다 **[!DNL Confirm]**.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager 및 을 연결한 후 [!DNL Twitter Custom Audiences]새 대상을 만들 수 있습니다. 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 입력해야 합니다.

1. Audience Manager 계정에 로그인하고 다음 위치로 이동하십시오. **[!DNL Audience Data > Destinations]**&#x200B;를 클릭하고 **[!DNL Create Destination]**.
1. 에서 **[!DNL Basic Information]** 섹션에서 다음을 입력합니다. **[!DNL Name]** 및 **[!DNL Description]** 새 대상에 대해 아래의 설정을 사용하십시오. ![설정](assets/dbd-new-basic.png)
1. 클릭 **[!DNL Next]**.
1. 을(를) 선택합니다 [데이터 내보내기 레이블](/help/using/features/data-export-controls.md#controls-labels) 이 대상에 대해 설정할 수 있습니다.
1. 클릭 **[!DNL Save]**.
1. 에서 **[!DNL Segment Mappings]** 섹션에서 이 대상으로 전송할 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.

## 세그먼트 매핑 고려 사항 {#segment-mapping-considerations}

대상 세그먼트를 [!UICONTROL Twitter], 다음 세그먼트 이름 지정 요구 사항을 충족하는지 확인하십시오.

* 사람이 읽을 수 있는 세그먼트 매핑 이름을 제공합니다. Audience Manager 세그먼트에 사용한 것과 동일한 이름을 사용하는 것이 좋습니다.
* 특수 문자 사용 안 함(`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) 내의 아무 곳에나 삽입할 수 있습니다. Audience Manager 세그먼트 이름에 이러한 문자가 포함되어 있는 경우 세그먼트를 [!UICONTROL Twitter] 대상.

### 예

* 올바른 세그먼트 또는 매핑 이름: &quot;미국과 유럽 쇼핑객&quot;;
* 잘못된 세그먼트 또는 매핑 이름: &quot;미국, 유럽 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>이미 매핑된 세그먼트의 이름은 변경할 수 없습니다. Audience Manager은 세그먼트 이름을 사용하여 통합에서 세그먼트를 올바르게 식별합니다.

## 일치율 고려 사항 {#match-rates-considerations}

* Audience Manager과 간의 통합 [!UICONTROL Twitter Custom Audiences] 이전 대상 채우기 기능을 지원합니다. 모든 세그먼트 자격이 [!UICONTROL Twitter] 대상을 만들 때 입니다.

## 문제 해결 {#troubleshooting}

twitter 사용자 지정 대상 대상으로 데이터를 구성하거나 전송할 때 아래에 설명된 오류가 발생할 수 있습니다. 이 섹션에서는 오류를 일으킬 수 있는 대상과 이를 수정하는 방법에 대해 설명합니다.

| 오류 메시지 | 발생/이유 | 해상도 |
|---|---|---|
| `Internal server error` | 이 오류 메시지는 새로 추가하려고 할 때 Audience Manager UI에 표시됩니다 [!DNL Twitter] twitter API의 이전 버전을 사용한 계정. | Adobe 고객 지원 문의. |
| `Twitter Error: This request is not properly authenticated` | 이 오류 메시지는 지원되지 않는 세그먼트 이름이 있는 세그먼트를 대상에 매핑하려고 할 때 Audience Manager UI에 표시됩니다. | 매핑된 세그먼트 이름을 검토하고 지원되지 않는 문자가 포함되어 있지 않은지 확인하십시오. 자세한 내용은 [세그먼트 매핑 고려 사항](#segment-mapping-considerations) 지원되지 않는 문자 목록입니다. |
| `Twitter Error: Account XXXXXXXXX was not found` | 이 오류 메시지는 대상에 대해 구성된 자격 증명이 해당 Twitter 광고 계정에 액세스할 권한이 없는 경우 Audience Manager UI에 표시됩니다. | <ul><li>사용 중인 계정 자격 증명이 [전제 조건](#prerequisites).</li><li>동일한 자격 증명을 사용하여 Twitter 광고 UI로 이동하고 해당 아래에 올바른 대상이 표시되는지 확인합니다 `XXXXXXXXX` 계정이 필요합니다. </li></ul> |