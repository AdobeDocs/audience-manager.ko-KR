---
description: 이 절차는 AdWords 리마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. 검색 광고(RLSA) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-description: 이 절차는 AdWords 리마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. 검색 광고(RLSA) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-title: Google AdWords 리마케팅 목록에 세그먼트 보내기
solution: Audience Manager
title: Google AdWords 리마케팅 목록에 세그먼트 보내기
uuid: 5ad821c6-48b4-42c0-b912-156333e93a2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Google 광고 리마케팅 목록에 세그먼트 보내기 {#send-segments-to-a-google-adwords-remarketing-list}

이 절차는 [!DNL Google Ads] 리마케팅 목록, 픽셀 코드 및 Audience Manager [!DNL URL] 대상이 필요합니다. 검색 광고([!DNL RLSA]) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.

>[!IMPORTANT]
>이 두 시스템의 제품 통합은 아닙니다.

리마케팅 목록을 URL [!DNL Google Ads] 대상으로 설정하려면 [!DNL Audience Manager] 다음을 수행하십시오.

1. 계정에서 웹 사이트 재마케팅 목록을 [!DNL Google Ads] [](https://support.google.com/adwords/answer/2454064?hl=en) 만들고 전환 ID를 기록합니다.
1. 기본 URL 및 보안 URL에 대한 템플릿으로 다음 URL을 사용합니다. xxxxxxxx 섹션을 전환 ID로 바꿉니다.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Audience Manager에서 [URL 대상을](../../features/destinations/create-url-destination.md) 만들거나 기존 대상을 편집합니다. 대상을 만들 때는 다음 설정을 사용합니다.
   * 유형:URL
   * 일련화:활성화됨
   * 구분 기호:세미콜론(;)

1. 대상의 [!UICONTROL Segment Mappings] 섹션에서 2단계의 코드를 [!DNL URL] 및 [!DNL URL] [!DNL Secure URL] 필드에 추가합니다. 및 `http:` 필드에 각각 `https:` 및 으로 코드 접두사를 [!DNL URL] [!DNL Secure URL] 지정합니다.

   >[!IMPORTANT]
   >
   >인코딩된 앰퍼샌드를 인코딩되지 `&` 않은 앰퍼샌드로 바꾸기 `&`

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
   >여러 세그먼트로 작업하는 경우 Google 광고 대상에 매핑할 각 세그먼트에 대해 새 픽셀을 가져옵니다. 이렇게 하면 데이터가 적절한 리마케팅 목록에 적용됩니다.

1. Audience Manager에서 새 세그먼트를 이 대상에 매핑할 때에는 매핑을 `aam=segmentID` 정의한 후 세그먼트의 ID로 `segmentID` 바꿉니다.
1. 버킷을 정의할 [!DNL Google Ads]때 6단계에서 정의한 매핑과 일치하는 규칙을 만듭니다.

완료된 매핑은 다음과 비슷합니다.

![](../assets/rlsa_mapping.png)

>[!MORELIKE_THIS]
>
>* [대상](../../features/destinations/destinations.md)
>* [URL 대상 만들기](../../features/destinations/create-url-destination.md)
>* [AdWords 리마케팅 목록 정보](https://support.google.com/adwords/answer/2472738)
>* [AdWords 리마케팅 작동 방식](https://support.google.com/adwords/answer/2454000)

