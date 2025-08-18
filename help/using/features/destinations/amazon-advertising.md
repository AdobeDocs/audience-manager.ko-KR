---
description: 이 문서에서는 새 통합과 기존 통합 모두를 위해 Amazon Advertising을 구성하는 방법에 대해 설명합니다.
solution: Audience Manager
title: Amazon Advertising을 셀프서비스 장치 기반 대상으로 구성
exl-id: 049af52a-b425-493d-9e77-9ced7ba6d168
source-git-commit: bac3167927af0957e7081e1ea653464101affcb8
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# [!DNL Amazon Advertising]을(를) 셀프 서비스 장치 기반 대상으로 구성 {#configure-amazon}

이 문서에서는 [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us)과의 통합을 구성하는 방법에 대해 설명합니다.

## 사전 요구 사항 {#prerequisites}

[!DNL Amazon Advertising] 대상을 구성하기 전에 다음 전제 조건을 충족하는지 확인하십시오.

* [!DNL Amazon] 계정은 광고를 할 수 있어야 합니다.
* Audience Manager 인스턴스에 첫 번째 [!DNL Amazon Advertising] 대상을 만들 때 계정에 대해 [!DNL Amazon] ID 동기화(데이터 Source ID = 139200)를 활성화하려면 Adobe Consulting 또는 고객 지원 센터에 문의하십시오. Audience Manager과 [!DNL Amazon] 간의 올바른 동기화를 위해 필요합니다.
* 새 데이터 공급자 대상이 만들어지면 [해당 메타데이터를 업데이트](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put)하고 **[!DNL audience fees]**&#x200B;을(를) 추가해야 합니다. 이 작업의 경우 [Amazon 광고 API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) 또는 [Amazon Advertising UI](https://advertising.amazon.com/)를 사용할 수 있습니다.

## 새 [!DNL Amazon Advertising] 대상 추가 {#add-new-amazon-destination}

이 섹션에서는 [!DNL Amazon Advertising]에 대한 새 장치 기반 대상을 구성할 때 따라야 하는 단계에 대해 설명합니다. 이 시나리오에서는 Adobe 컨설턴트나 고객 지원 센터를 통해 구성된 기존 [!DNL Amazon Advertising] 대상이 없다고 가정합니다.

### 1단계. [!DNL Amazon Advertising]&#x200B;(으)로 인증 {#step1-authenticate-with-amazon}

장치 기반 대상을 추가하려면 먼저 Audience Manager과 [!DNL Amazon Advertising] 계정을 연결해야 합니다. 방법은 다음과 같습니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Administration > Integrated Accounts]**(으)로 이동합니다. 대상 플랫폼과 이전에 구성한 통합이 있는 경우 이 페이지에 표시됩니다. 그렇지 않으면 페이지가 비어 있습니다.
1. **[!UICONTROL Add Account]**&#x200B;을(를) 선택합니다.
1. [!UICONTROL Amazon Data Provider]을(를) 선택합니다.

   ![통합 플랫폼](assets/dbd-amazon-without-options.png)

1. **[!UICONTROL Amazon Data Provider]** 계정이 만들어진 지역(북미, 유럽 또는 극동)에 따라 [!DNL Amazon Ads] 옵션 중 하나를 선택하고 **[!DNL Confirm]**&#x200B;을(를) 클릭하여 인증 페이지로 리디렉션합니다.

   ![통합 플랫폼](assets/dbd-amazon-with-options.png)

1. 인증되면 연결된 광고주 계정이 표시되는 Audience Manager으로 리디렉션됩니다. 사용할 광고주 계정을 선택하고 **[!UICONTROL Confirm]**&#x200B;을(를) 클릭합니다. 이를 통해 Audience Manager에 대한 액세스 권한을 부여하여 대상에 대한 업데이트를 전송합니다.

### 2단계. 새 장치 기반 대상 만들기 {#step2-create-new-destination}

Audience Manager과 [!DNL Amazon Advertising] 계정을 연결한 후 새 대상을 만들 수 있습니다. 방법은 다음과 같습니다.

>[!NOTE]
>
>기존 장치 기반 대상의 이름을 변경할 수 없습니다. 대상을 올바르게 식별하는 데 도움이 되는 이름을 입력해야 합니다.

1. Audience Manager 계정에 로그인하고 **[!UICONTROL Audience Data > Destinations]**(으)로 이동한 다음 **[!UICONTROL Create Destination]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Basic Information]** 섹션에서 새 대상에 대한 **[!UICONTROL Name]** 및 **[!UICONTROL Description]**&#x200B;을(를) 입력하고 아래 설정을 사용하십시오.

   ![설정](assets/dbd-new-account-amazon.png)

1. **[!UICONTROL Next]**&#x200B;을(를) 선택합니다.
1. 이 대상에 대해 설정할 [데이터 내보내기 레이블](/help/using/features/data-export-controls.md#controls-labels)을 선택하십시오.
1. **[!UICONTROL Save]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Segment Mappings]** 섹션에서 이 대상으로 보낼 대상 세그먼트를 선택합니다.
1. 대상을 저장합니다.

## 일치율 고려 사항 {#match-rates-considerations}

Audience Manager과 [!DNL Amazon Advertising] 간의 통합은 과거 대상 다시 채우기를 지원합니다. 대상을 만들면 모든 세그먼트 자격이 [!DNL Amazon]&#x200B;(으)로 전송됩니다.

## 문제 해결 {#troubleshooting}

데이터를 구성하거나 [!DNL Amazon Advertising] 대상으로 보낼 때 아래에 설명된 오류가 발생할 수 있습니다. 이 섹션에서는 오류를 일으킬 수 있는 원인과 오류를 수정하는 방법에 대해 설명합니다.

| 오류 메시지 | 발생 횟수 / 이유 | 해결 방법 |
|---|---|---|
| `Internal server error` | 이 오류 메시지는 오래된 버전의 Amazon API를 사용하여 새 [!DNL Amazon] 계정을 추가하려고 할 때 Audience Manager UI에 표시됩니다. | Adobe 고객 지원 센터에 문의하십시오. |
| `Amazon Error: Account XXXXXXXXX was not found` | 이 오류 메시지는 대상에 대해 구성된 자격 증명이 해당 Amazon Ads 계정에 액세스할 수 있는 권한이 없는 경우 Audience Manager UI에 표시됩니다. | <ul><li>사용 중인 계정 자격 증명이 [필수 구성 요소](#prerequisites)를 충족하는지 확인하십시오.</li><li>동일한 자격 증명을 사용하여 Amazon Ads UI로 이동한 다음 해당 계정 아래에 올바른 대상이 표시되는지 확인합니다. </li></ul> |
