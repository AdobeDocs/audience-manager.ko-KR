---
description: 이 문서에서는 새 통합과 기존 통합 모두에 대해 Twitter 맞춤 대상을 구성하는 방법을 설명합니다.
seo-description: 이 문서에서는 새 통합과 기존 통합 모두에 대해 Twitter 맞춤 대상을 구성하는 방법을 설명합니다.
seo-title: Twitter 맞춤 대상을 셀프 서비스 장치 기반 대상으로 구성
solution: Audience Manager
title: Twitter 맞춤 대상을 셀프 서비스 장치 기반 대상으로 구성
translation-type: tm+mt
source-git-commit: 96717384ebb82056f330312b0f99fb97086a2e05

---


# 셀프 서비스 [!DNL Twitter Tailored Audiences] 장치 기반 대상으로 구성 {#configure-twitter}

이 문서에서는 새 통합과 기존 통합 모두에 [대해 Twitter 맞춤 대상을](https://business.twitter.com/en/targeting/tailored-audiences.html) 구성하는 방법을 설명합니다.

## 전제 조건 {#prerequisites}

[!DNL Twitter Tailored Audiences] 대상을 구성하기 전에 충족해야 하는 다음 Twitter 전제 조건을 검토하십시오.

1. 귀하의 [!DNL Twitter Ads] 계정은 광고를 받을 수 있어야 합니다. 새 [!DNL Twitter Ads] 계정은 광고를 만든 후 처음 2 주 동안 사용할 수 없습니다.
2. Audience Manager에서 액세스 권한이 있는 Twitter 사용자 계정은 [파트너 Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 권한이 활성화되어 있어야 합니다.
3. 기존 Twitter 통합을 셀프 서비스 관리로 [](#update-existing-twitter-integrations)업데이트하는 경우 Twitter 사용자 계정에 [광고 관리자](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) 권한이 활성화되어 있어야 합니다.



## [!DNL Twitter Tailored Audiences] 새 대상 추가 {#add-new-twitter-destination}

이 섹션에서는 새 장치 기반 대상을 구성할 때 따라야 [!DNL Twitter Tailored Audiences]하는 단계를 설명합니다. 이 시나리오에서는 Adobe 컨설턴트나 고객 관리를 통해 구성된 기존 [!DNL Twitter Tailored Audiences] 대상이 없다고 가정합니다.

### 1단계. 인증 대상 [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

장치 기반 대상을 추가하려면 먼저 Audience Manager와 [!DNL Twitter Tailored Audiences] 계정을 연결해야 합니다. 이 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!DNL Administration > Integrated Accounts]**&#x200B;로그인합니다. 이전에 대상 플랫폼과 통합을 구성한 경우 이 페이지에 나열된 것이 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
2. 클릭 **[!DNL Add Account]**.
3. 인증 [!DNL Twitter Tailored Audiences] 페이지로 **[!DNL Confirm]** 리디렉션하려면 선택하고 클릭합니다. ![통합 플랫폼](assets/dbd-integrated-platforms.png)
4. 인증이 완료되면 연결된 광고주 계정을 볼 수 있는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고를 **[!DNL Confirm]**&#x200B;클릭합니다.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager와 사용자를 [!DNL Twitter Tailored Audiences]연결한 후 새 대상을 만들 수 있습니다. 이 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름은 변경할 수 없습니다. 대상을 정확하게 식별하는 데 도움이 되는 이름을 제공하십시오.

1. Audience Manager 계정에 로그인하고, 이동한 **[!DNL Audience Data > Destinations]****[!DNL Create Destination]**&#x200B;다음을 클릭합니다.
2. **[!DNL Basic Information]** 섹션에서 새 **[!DNL Name]** 대상을 입력하고 **[!DNL Description]** 아래 설정을 사용합니다. ![설정](assets/dbd-new-basic.png)
3. 클릭 **[!DNL Next]**.
4. 이 대상에 대해 설정할 [데이터 내보내기 레이블을](/help/using/features/data-export-controls.md#controls-labels) 선택합니다.
5. 클릭 **[!DNL Save]**.
6. **[!DNL Segment Mappings]** 섹션에서 이 대상에 보낼 대상 세그먼트를 선택합니다.
7. 대상을 저장합니다.

## 기존 Twitter 통합을 셀프 서비스 관리로 업데이트 {#update-existing-twitter-integrations}

사용자 경험을 향상시키고 구성 프로세스를 간소화하기 위해 Adobe는 Audience Manager UI에서 직접 구성을 수행할 수 있는 셀프 서비스 모델로 통합을 [!DNL Twitter Tailored Audiences] 업그레이드하고 있습니다. 이 섹션에서는 기존 Twitter 통합을 업데이트하는 데 필요한 단계를 설명합니다.

>[!IMPORTANT]
>
>아래에 설명된 단계는 대상 관리자 컨설턴트 또는 고객 지원 센터에서 [!DNL Twitter Tailored Audiences]구성한 기존 통합이 있는 경우에만 적용됩니다. 셀프 서비스 모델을 대상으로 하는 전체 업그레이드 프로세스는 영업일 기준으로 최대 5 일 정도 소요될 수 있습니다. 그 동안 대상이 계속 활성 상태이며 Audience Manager는 계속 고객을 타겟팅합니다.
> 셀프 서비스 모델로 마이그레이션하기 전에 [사전 요구](#prerequisites) 사항에서 [!DNL Twitter Tailored Audiences] 항목 번호 3를 참조하십시오.

아래 절차에 따라 기존 [!DNL Twitter Tailored Audiences] 대상을 셀프 서비스 모델로 마이그레이션하십시오.

1. Audience Manager 계정에 로그인하고 **[!DNL Administration > Integrated Accounts]**&#x200B;로그인합니다.
2. 클릭 **[!DNL Add Account]**.
3. 인증 [!DNL Twitter Tailored Audiences] 페이지로 **[!DNL Confirm]** 리디렉션하려면 선택하고 클릭합니다. ![통합 플랫폼](assets/dbd-integrated-platforms.png)
4. Twitter 계정으로 인증하면 연결된 광고주 계정을 볼 수 있는 Audience Manager로 리디렉션됩니다. 사용할 광고주 계정을 선택하고를 **[!DNL Confirm]**&#x200B;클릭합니다.

## 세그먼트 매핑 고려 사항 {#segment-mapping-considerations}

대상 세그먼트를 Twitter로 매핑할 때는 다음 세그먼트 이름 지정 요구 사항을 충족해야 합니다.

* 사람이 읽을 수 있는 세그먼트 매핑 이름을 제공합니다. Audience Manager 세그먼트에 사용한 것과 동일한 이름을 사용하는 것이 좋습니다.
* 세그먼트와 세그먼트 매핑 이름에 쉼표를 사용하지 마십시오.

**예**

* 올바른 세그먼트 또는 매핑 이름: " 미국 및 유럽 쇼핑 ";
* 잘못된 세그먼트 또는 매핑 이름: " US, European 5 H 0 PP 3 RS ".

>[!IMPORTANT]
>
>이미 매핑된 세그먼트의 이름은 변경할 수 없습니다. Audience Manager는 세그먼트 이름을 사용하여 통합의 세그먼트를 올바르게 식별합니다.