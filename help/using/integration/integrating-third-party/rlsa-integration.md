---
description: 이 절차에는 AdWords 리마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. RLSA(검색 광고) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-description: 이 절차에는 AdWords 리마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. RLSA(검색 광고) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-title: Google 애드워즈 리마케팅 목록에 세그먼트 보내기
solution: Audience Manager
title: Google 애드워즈 리마케팅 목록에 세그먼트 보내기
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: 타사 통합
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 5%

---

# Google 광고 리마케팅 목록에 세그먼트 보내기 {#send-segments-to-a-google-adwords-remarketing-list}

이 절차에는 [!DNL Google Ads] 리마케팅 목록, 픽셀 코드 및 Audience Manager [!DNL URL] [!DNL destination]가 필요합니다. 검색 광고([!DNL RLSA]) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.

>[!IMPORTANT]
>이 두 시스템의 제품 통합은 아닙니다.

[!DNL Google Ads] 리마케팅 목록을 [!DNL Audience Manager] [!DNL URL destination] 로 설정하려면 다음을 수행하십시오.

1. [!DNL Google Ads] 계정에서 [웹 사이트 재마케팅 목록](https://support.google.com/adwords/answer/2454064?hl=en)을 만들고 전환 ID를 기록합니다.
1. 다음 URL을 기본 URL 및 보안 URL의 템플릿으로 사용합니다. xxxxxxxx 섹션을 전환 ID로 바꿉니다.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Audience Manager에서 [Create a [!DNL URL destination]](../../features/destinations/create-url-destination.md)을 만들거나 기존 [!DNL destination]을 편집합니다. [!DNL destination]을 만들 때 다음 설정을 사용하십시오.
   * 유형:URL
   * 정리:활성화됨
   * 구분 기호:세미콜론(;)

1. [!DNL URL] [!DNL destination]의 [!UICONTROL Segment Mappings] 섹션에서 2단계의 코드를 [!DNL URL] 및 [!DNL Secure URL] 필드에 추가합니다. 각각 [!DNL URL] 및 [!DNL Secure URL] 필드에 `http:` 및 `https:` 접두사로 코드를 추가합니다.

   >[!IMPORTANT]
   >
   >인코딩된 앰퍼샌드 `&`를 인코딩되지 않은 앰퍼샌드 `&`로 바꿉니다.

   보안 해제 [!DNL URL] 코드:

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
   >여러 세그먼트로 작업하는 경우 [!DNL Google Ads] [!DNL destination]에 매핑할 각 세그먼트에 대한 새 픽셀을 가져옵니다. 이렇게 하면 데이터가 적절한 리마케팅 목록에 적용됩니다.

1. 새 세그먼트를 Audience Manager의 이 [!DNL destination]에 매핑할 때 매핑을 `aam=segmentID`(으)로 정의하고 `segmentID` 를 세그먼트의 ID로 바꿉니다.
1. [!DNL Google Ads]에서 버킷을 정의할 때 6단계에서 정의한 매핑과 일치하는 규칙을 만듭니다.

완료된 매핑은 다음과 유사할 수 있습니다.

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
* [웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
* [AdWords 리마케팅 목록 정보](https://support.google.com/adwords/answer/2472738)
* [AdWords 리마케팅 작동 방식](https://support.google.com/adwords/answer/2454000)

