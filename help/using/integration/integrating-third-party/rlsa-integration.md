---
description: 이 절차를 수행하려면 Adwords 재마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. RLSA (검색 광고) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-description: 이 절차를 수행하려면 Adwords 재마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. RLSA (검색 광고) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-title: 세그먼트를 Google adwords 리마케팅 목록으로 보내기
solution: Audience Manager
title: 세그먼트를 Google adwords 리마케팅 목록으로 보내기
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. 유료 검색에만 적용됩니다.

>[!IMPORTANT]
>이 두 시스템은 프로덕션 통합이 아닙니다.

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. [!DNL Google Ads] 계정에서 [웹 사이트 재마케팅 목록을](https://support.google.com/adwords/answer/2454064?hl=en) 만들고 전환 ID를 기록합니다.
1. 기본 URL 및 보안 URL에 대한 템플릿으로 다음 URL를 사용하십시오. XXXXXXXX 섹션을 전환 ID로 바꿉니다.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager, [Create a URL destination](../../features/destinations/manage-destinations.md#configure-url-destination) or edit an existing destination. 대상을 만들 때는 다음 설정을 사용합니다.
   * 유형: URL
   * 일련화: enabled
   * 구분 기호: 세미콜론 (;)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. 클릭 **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >여러 세그먼트를 사용하는 경우 Google 광고 대상에 매핑할 각 세그먼트에 대해 새 픽셀을 가져옵니다. 이렇게 하면 데이터가 해당 리마케팅 목록에 적용됩니다.

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

완료된 매핑은 다음과 비슷합니다.

![](../assets/rlsa_mapping.png)

>[!MORE_ like_ this]
>
>* [대상](../../features/destinations/destinations.md)
>* [URL 대상 만들기](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [Adwords 리마케팅 목록](https://support.google.com/adwords/answer/2472738)
>* [Adwords 리마케팅이 작동하는 방법](https://support.google.com/adwords/answer/2454000)

