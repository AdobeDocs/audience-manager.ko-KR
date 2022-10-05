---
description: 이 절차에는 AdWords 리마케팅 목록, 픽셀 코드 및 Audience Manager URL 대상이 필요합니다. RLSA(검색 광고) 통합을 위한 리마케팅 목록이라고도 합니다. 유료 검색에만 적용됩니다.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Google 애드워즈 리마케팅 목록에 세그먼트 보내기
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Google 광고 리마케팅 목록에 세그먼트 보내기 {#send-segments-to-a-google-adwords-remarketing-list}

이 절차에는 [!DNL Google Ads] 리마케팅 목록, 픽셀 코드 및 Audience Manager [!DNL URL] [!DNL destination]. 검색 광고([!DNL RLSA]) 통합. 유료 검색에만 적용됩니다.

>[!IMPORTANT]
>이 두 시스템의 제품 통합은 아닙니다.

을(를) 설정하려면 다음을 수행하십시오 [!DNL Google Ads] 리마케팅 목록 [!DNL Audience Manager] [!DNL URL destination]:

1. 사용자 [!DNL Google Ads] account, [웹 사이트 리마케팅 목록 만들기](https://support.google.com/tagmanager/answer/6106960?hl=en) 전환 ID를 작성합니다.
1. 다음 URL을 기본 URL 및 보안 URL의 템플릿으로 사용합니다. xxxxxxxx 섹션을 전환 ID로 바꿉니다.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Audience Manager에서, [만들기 [!DNL URL destination]](../../features/destinations/create-url-destination.md) 기존 [!DNL destination]. 만들 때 다음 설정을 사용하십시오. [!DNL destination]:
   * 유형: URL
   * 정리: 활성화됨
   * 구분 기호: 세미콜론( &amp;semi;) )

1. 에서 [!UICONTROL Segment Mappings] 섹션 [!DNL URL] [!DNL destination]를 채울 때 2단계의 코드를 [!DNL URL] 및 [!DNL Secure URL] 필드. 코드 접두사로 `http:` 및 `https:` 에서 [!DNL URL] 및 [!DNL Secure URL] 필드(각각)를 반환합니다.

   >[!IMPORTANT]
   >
   >인코딩된 앰퍼샌드 바꾸기 `&` 인코딩되지 않은 앰퍼샌드 사용 `&`

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
   >여러 세그먼트를 사용하는 경우 매핑할 각 세그먼트에 대해 새 픽셀을 가져옵니다 [!DNL Google Ads] [!DNL destination]. 이렇게 하면 데이터가 적절한 리마케팅 목록에 적용됩니다.

1. 새 세그먼트를 여기에 매핑 [!DNL destination] Audience Manager에서 매핑을 (으)로 정의합니다. `aam=segmentID` 및 바꾸기 `segmentID` 세그먼트 ID로 그룹화하는 것이 좋습니다.
1. 에서 버킷을 정의할 때 [!DNL Google Ads]를 입력하여 6단계에서 정의한 매핑과 일치하는 규칙을 만듭니다.

완료된 매핑은 다음과 유사할 수 있습니다.

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [AdWords 리마케팅 목록 정보](https://support.google.com/adwords/answer/2472738)
>* [AdWords 리마케팅 작동 방식](https://support.google.com/adwords/answer/2454000)

