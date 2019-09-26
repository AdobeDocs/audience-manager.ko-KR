---
description: 이 문서에서는 신규 및 기존 통합 모두에 대해 Twitter 맞춤 대상을 구성하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 신규 및 기존 통합 모두에 대해 Twitter 맞춤 대상을 구성하는 방법에 대해 설명합니다.
seo-title: Twitter 맞춤 대상을 셀프 서비스 장치 기반 대상으로 구성
solution: Audience Manager
title: Twitter 맞춤 대상을 셀프 서비스 장치 기반 대상으로 구성
translation-type: tm+mt
source-git-commit: 2bf825e083c81edb8c03cb8dcef99088b1958452

---


# 셀프 서비스 [!DNL Twitter Tailored Audiences] 장치 기반 대상으로 구성 {#configure-twitter}

이 문서에서는 새로운 통합 및 기존 통합 모두에 [대해 Twitter](https://business.twitter.com/en/targeting/tailored-audiences.html) 맞춤 대상을 구성하는 방법에 대해 설명합니다.

## 전제 조건 {#prerequisites}

대상을 구성하려면 먼저 다음 Twitter 사전 요구 사항을 검토하십시오. [!DNL Twitter Tailored Audiences]

1. 귀하의 [!DNL Twitter Ads] 계정은 광고 자격이 있어야 합니다. 새 [!DNL Twitter Ads] 계정은 만든 후 처음 2주 이내에 광고를 할 수 없습니다.
1. Audience Manager에서 액세스를 인증한 Twitter 사용자 계정에는 Partner [Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 권한이 활성화되어 있어야 합니다.
1. 기존 Twitter 통합을 셀프 서비스 관리로 [](#update-existing-twitter-integrations)업데이트하는 경우 Twitter 사용자 계정에 [광고 관리자](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 권한이 활성화되어 있어야 합니다.
1. Audience Manager 인스턴스에서 첫 번째 [!DNL Twitter Tailored Audiences] 대상을 만들 때는 Adobe Consulting 또는 고객 지원 센터에 연락하여 계정에 대해 ID 동기화(데이터 소스 ID = 1123)를 [!DNL Twitter] 활성화하십시오. Audience Manager와 Audience Manager 간의 올바른 동기화를 위해 필요합니다 [!DNL Twitter].

## 새 대상 [!DNL Twitter Tailored Audiences] 추가 {#add-new-twitter-destination}

이 섹션에서는 에 대한 새 장치 기반 대상을 구성할 때 수행해야 하는 단계를 설명합니다 [!DNL Twitter Tailored Audiences]. 이 시나리오에서는 Adobe 컨설턴트나 고객 지원 센터를 통해 구성된 기존 [!DNL Twitter Tailored Audiences] 대상이 없다고 가정합니다.

### 1단계. 인증 [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

장치 기반 대상을 추가하려면 먼저 Audience Manager와 [!DNL Twitter Tailored Audiences] 계정을 연결해야 합니다. 이 작업을 수행하는 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인한 다음 로 **[!DNL Administration > Integrated Accounts]**&#x200B;이동합니다. 대상 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 나열되는 것을 볼 수 있습니다. 그렇지 않으면 페이지가 비어 있습니다.
2. 클릭 **[!DNL Add Account]**.
3. 을 [!DNL Twitter Tailored Audiences] 선택하고 **[!DNL Confirm]** 클릭하여 인증 페이지로 리디렉션됩니다.                     ![통합 플랫폼](assets/dbd-integrated-platforms.png)
4. 인증이 완료되면 연결된 광고주 계정이 표시되는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 을 **[!DNL Confirm]**&#x200B;클릭합니다.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager와 대상을 연결한 [!DNL Twitter Tailored Audiences]후 새 대상을 만들 수 있습니다. 이 작업을 수행하는 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 제공하십시오.

1. Audience Manager 계정에 로그인한 다음 **[!DNL Audience Data > Destinations]**&#x200B;으로 이동한 다음 을 클릭합니다 **[!DNL Create Destination]**.
2. 섹션에서 새 대상에 대한 **[!DNL Basic Information]** 및 **[!DNL Name]** **[!DNL Description]** 를 입력하고 아래 설정을 사용하십시오. ![설정](assets/dbd-new-basic.png)
3. 클릭 **[!DNL Next]**.
4. 이 [대상에 대해](/help/using/features/data-export-controls.md#controls-labels) 설정할 데이터 내보내기 레이블을 선택합니다.
5. 클릭 **[!DNL Save]**.
6. 섹션에서 **[!DNL Segment Mappings]** 이 대상으로 전송할 대상 세그먼트를 선택합니다.
7. 대상을 저장합니다.

## 기존 Twitter 통합을 셀프 서비스 관리로 업데이트 {#update-existing-twitter-integrations}

사용자 경험을 개선하고 구성 프로세스를 간소화하기 위해 Adobe는 Audience Manager UI에서 직접 구성을 수행할 수 있는 셀프 서비스 모델로 통합을 업그레이드하고 있습니다. [!DNL Twitter Tailored Audiences] 이 섹션에서는 기존 Twitter 통합을 업데이트하는 데 필요한 단계를 설명합니다.

>[!IMPORTANT]
>
>아래 설명된 단계는 Audience Manager 컨설턴트나 고객 지원 센터에 의해 구성된 기존 통합 [!DNL Twitter Tailored Audiences]상태인 경우에만 적용됩니다. 대상이 셀프 서비스 모델로 업그레이드하는 데 영업일 기준 최대 5일이 소요될 수 있습니다. 그 동안 대상이 여전히 활성 상태이며 Audience Manager에서 대상을 계속 보냅니다.
> 셀프 서비스 모델로 [마이그레이션하기 전에 사전 요구](#prerequisites) 사항의 [!DNL Twitter Tailored Audiences] 항목 번호 3을 참조하십시오.

아래 절차에 따라 기존 [!DNL Twitter Tailored Audiences] 대상을 셀프 서비스 모델로 마이그레이션합니다.

1. Audience Manager 계정에 로그인한 다음 로 **[!DNL Administration > Integrated Accounts]**&#x200B;이동합니다.
1. 클릭 **[!DNL Add Account]**.
1. 을 [!DNL Twitter Tailored Audiences] 선택하고 **[!DNL Confirm]** 클릭하여 인증 페이지로 리디렉션됩니다. ![통합 플랫폼](assets/dbd-integrated-platforms.png)
1. 계정을 사용하여 인증하면 연결된 광고주 계정이 표시되는 Audience Manager로 리디렉션됩니다. [!DNL Twitter] 사용할 광고주 계정을 선택하고 을 **[!DNL Confirm]**&#x200B;클릭합니다.
1. &gt; **[!UICONTROL Audience Data]** 로 **[!UICONTROL Destinations]** 이동하여 구성해야 하는 Twitter 대상을 클릭합니다.
1. 클릭 **[!UICONTROL Edit]**. 섹션에서 **[!UICONTROL Basic Information]** 드롭다운 메뉴를 클릭하고 4단계에서 인증한 **[!UICONTROL Integrated Account]** [!DNL Twitter] 계정을 선택합니다.
1. **[!UICONTROL Save]** 대상을 선택합니다.

## 셀프 서비스 관리로의 마이그레이션 유효성 확인 {#migration-validation}

기존 통합을 셀프 서비스 [!DNL Twitter] 관리로 완벽하게 마이그레이션하는 데 최대 7일이 소요될 수 있습니다. 마이그레이션이 완료되면 Audience Manager가 UI에 알림을 표시합니다.

또한 [!DNL Twitter] 계정에 [[!DNL Adobe DMP Audience]]이(가) 접두사로 추가된 새 대상자 세트가 표시됩니다. 최대 7일 동안 고객 수를 완전히 채우십시오. 마이그레이션이 완료되면 이전 대상 대신 새 대상을 사용해야 합니다.

## 세그먼트 매핑 고려 사항 {#segment-mapping-considerations}

대상 세그먼트를 Twitter에 매핑할 때는 다음 세그먼트 이름 지정 요구 사항을 충족해야 합니다.

* 사람이 읽을 수 있는 세그먼트 매핑 이름을 제공합니다. Audience Manager 세그먼트에 사용한 것과 동일한 이름을 사용하는 것이 좋습니다.
* 세그먼트 및 세그먼트 매핑 이름에는 쉼표를 사용하지 마십시오.

### 예

* 올바른 세그먼트 또는 매핑 이름:"미국 및 유럽 구매자";
* 잘못된 세그먼트 또는 매핑 이름:"미국, 유럽 5h0pP3rs".

## 일치 비율 고려 사항 {#match-rates-considerations}

사용할 [!UICONTROL Twitter Tailored Audiences]때, 대상 페이지의 [!UICONTROL Segment Addressable Audience] 및 [!UICONTROL Segment Match Rate] 지표에는 값이 표시되지 않습니다. 이 대상에 대한 일치 비율과 함께 대상을 일치시키면 Adobe가 아니라 Adobe가 처리 및 호스팅하기 때문에 이는 정상적인 동작입니다. [!UICONTROL Twitter]

>[!IMPORTANT]
>
>이미 매핑된 세그먼트의 이름은 변경할 수 없습니다. Audience Manager는 세그먼트 이름을 사용하여 통합에서 세그먼트를 올바르게 식별합니다.
