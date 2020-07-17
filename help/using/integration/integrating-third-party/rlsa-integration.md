---
description: 이 절차는 AdWords 리마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. RLSA(Search Ads) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-description: 이 절차는 AdWords 리마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. RLSA(Search Ads) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-title: Google 애드워즈 리마케팅 목록에 세그먼트 보내기
solution: Audience Manager
title: Google 애드워즈 리마케팅 목록에 세그먼트 보내기
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

이 절차는 [!DNL Google Ads] 리마케팅 목록, 픽셀 코드 및 Audience Manager이 필요합니다 [!DNL URL] [!DNL destination]. 검색 광고([!DNL RLSA]) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.

>[!IMPORTANT]
>이 두 시스템의 제품 통합은 아닙니다.

리마케팅 [!DNL Google Ads] 목록을 다음과 같이 설정하려면 [!DNL Audience Manager] [!DNL URL destination]다음을 수행하십시오.

1. 계정에서 웹 사이트 재마케팅 목록 [!DNL Google Ads] 을 [](https://support.google.com/adwords/answer/2454064?hl=en) 만들고 전환 ID를 기록합니다.
1. 기본 URL 및 보안 URL에 대한 템플릿으로 다음 URL을 사용하십시오. xxxxxxxx 섹션을 전환 ID로 바꿉니다.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Audience Manager에서 기존 [을 [!DNL URL destination]](../../features/destinations/create-url-destination.md) 만들거나 편집합니다 [!DNL destination]. Use the following settings when creating the [!DNL destination]:
   * 유형: URL
   * 일련화: 활성화됨
   * 구분 기호: 세미콜론(;)

1. 섹션 [!UICONTROL Segment Mappings] 에서 2단계의 코드를 [!DNL URL] 및 [!DNL destination][!DNL URL] [!DNL Secure URL] 필드에 추가합니다. 코드 앞에 `http:` 및 필드 `https:` 를 [!DNL URL] 각각 붙입니다 [!DNL Secure URL] .

   >[!IMPORTANT]
   >
   >인코딩된 앰퍼샌드 `&` 를 인코딩되지 않은 앰퍼샌드 대체 `&`

   비보안 [!DNL URL] 코드:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   보안 [!DNL URL] 코드:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 클릭 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >여러 세그먼트로 작업하는 경우 매핑할 각 세그먼트에 대해 새 픽셀을 가져오십시오 [!DNL Google Ads] [!DNL destination]. 이렇게 하면 데이터가 적절한 리마케팅 목록에 적용됩니다.

1. Audience Manager에서 새 세그먼트를 이 세그먼트 [!DNL destination] 에 매핑할 때는 매핑을 다른 `aam=segmentID` 로 정의하고 세그먼트의 ID로 바꿉니다 `segmentID` .
1. 버킷을 정의할 때 6 [!DNL Google Ads]단계에서 정의된 매핑과 일치하는 규칙을 만듭니다.

완료된 매핑은 다음과 비슷합니다.

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL 대상]](../../features/destinations/destinations.md)
>* [웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [AdWords 리마케팅 목록 정보](https://support.google.com/adwords/answer/2472738)
>* [AdWords 리마케팅 작동 방식](https://support.google.com/adwords/answer/2454000)

