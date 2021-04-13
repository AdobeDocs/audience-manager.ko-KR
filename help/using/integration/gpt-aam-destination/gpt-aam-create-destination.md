---
description: 클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 자격이 있는 세그먼트를 Google 광고 관리자로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google 게시자 태그에 대한 쿠키 기반 대상을 만들어야 합니다.
seo-description: 클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 자격이 있는 세그먼트를 Google 광고 관리자로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google 게시자 태그에 대한 쿠키 기반 대상을 만들어야 합니다.
seo-title: GPT 대상 만들기
solution: Audience Manager
title: GPT 대상 만들기
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: 타사 통합
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# GPT 대상 만들기 {#create-a-gpt-destination}

클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 자격이 있는 세그먼트를 [!DNL Google Ad Manager]으로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 [!DNL Google Publisher Tags]에 대한 쿠키 기반 대상을 만들어야 합니다.

## 대상

Audience Manager에서 *`destination`*&#x200B;은 다른 모든 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등)입니다. 입니다. [!UICONTROL Destination Builder] 는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은 *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*&#x200B;에 있습니다. 시작하려면 **[!UICONTROL Add New Destination]**&#x200B;을 클릭하고 아래 단계를 따르십시오.

## 기본 정보

[!UICONTROL Basic Information] 섹션을 완료하려면 다음을 수행하십시오.

1. 대상의 이름을 지정합니다.
1. [!UICONTROL Type] 드롭다운 목록에서 **[!UICONTROL "Cookie"]**&#x200B;을 선택합니다.
1. **[!UICONTROL Next]**&#x200B;을 클릭하고 [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션으로 이동합니다.

## 쿠키 구성

[!UICONTROL Configuration] 섹션을 완료하려면 다음을 입력합니다(다른 필드는 선택 사항임).

1. **쿠키 이름:** 쿠키에 대해 간단한 설명형 이름을 제공합니다.
1. **데이터 형식:** 옵션을  **[!UICONTROL "Single Key"]** 선택합니다.
1. **키:** 키 이름을 입력합니다.
1. **일련화:** 확인란을  **[!UICONTROL Enable]** 선택합니다.
1. **직렬 구분 기호:** 쉼표만 사용합니다.

## 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. 세그먼트 찾기:[!UICONTROL Segment Mappings] 섹션은 세그먼트를 찾는 데 도움이 되는 2개의 검색 도구를 제공합니다. 세그먼트를 찾으려면:

   * 옵션 1:검색 필드에 세그먼트 이름을 입력하기 시작합니다. 입력된 텍스트를 기반으로 필드가 자동으로 업데이트됩니다. 사용할 세그먼트를 찾으면 **[!UICONTROL Add]**&#x200B;을 클릭합니다.
   * 옵션 2:이름 또는 저장소 위치별로 세그먼트를 검색할 수 있는 창을 열려면 **[!UICONTROL Browse All Segments]**&#x200B;을 클릭합니다. 완료되면 **[!UICONTROL Add Selected Segments]**&#x200B;을 클릭합니다.

1. **매핑 추가: 매핑** 팝업에서 매핑 필드에 세그먼트 ID를 입력하고 을  **[!UICONTROL Save]**&#x200B;클릭합니다.

1. 클릭 **[!UICONTROL Done]**.
