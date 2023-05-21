---
description: 클라이언트측(브라우저측) 통합 또는 서버측 통합을 통해 적격 세그먼트를 Google Ad Manager에 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google Publisher Tags에 대한 쿠키 기반 대상을 만들어야 합니다.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: GPT 대상 만들기
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---

# GPT 대상 만들기 {#create-a-gpt-destination}

다음 대상에게 적격한 세그먼트를 보낼 수 있습니다. [!DNL Google Ad Manager] 클라이언트 측(브라우저 측) 통합 또는 서버 측 통합을 통해 생성할 수 있습니다. 클라이언트측 통합을 선택하는 경우, 다음을 위해 쿠키 기반 대상을 만들어야 합니다 [!DNL Google Publisher Tags] Audience Manager.

## 대상

Audience Manager에서 *`destination`* 다른 시스템(광고 서버, [!DNL DSP], 광고 네트워크 등) 입니다. [!UICONTROL Destination Builder] 는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은에 있습니다. *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. 시작하려면 다음을 클릭하십시오. **[!UICONTROL Add New Destination]** 을(를) 클릭하고 아래 단계를 수행합니다.

## 기본 정보

다음을 완료하려면 [!UICONTROL Basic Information] 섹션:

1. 대상 이름을 지정합니다.
1. 선택 **[!UICONTROL "Cookie"]** 다음에서 [!UICONTROL Type] 드롭다운 목록입니다.
1. 클릭 **[!UICONTROL Next]** 다음으로 이동: [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션.

## 쿠키 구성

다음을 입력하여 다음을 완료합니다 [!UICONTROL Configuration] 섹션(다른 필드는 선택 사항):

1. **쿠키 이름:** 쿠키를 설명하는 간단한 이름을 입력합니다.
1. **데이터 형식:** 다음 항목 선택 **[!UICONTROL "Single Key"]** 옵션을 선택합니다.
1. **키:** 키 이름을 입력합니다.
1. **직렬화:** 다음 항목 선택 **[!UICONTROL Enable]** 확인란.
1. **일련 구분 기호:** 쉼표만 사용하십시오.

## 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면 다음 작업을 수행하십시오.

1. 세그먼트 찾기: [!UICONTROL Segment Mappings] 섹션은 세그먼트를 찾는 데 도움이 되는 두 가지 검색 도구를 제공합니다. 세그먼트를 찾으려면

   * 옵션 1: 검색 필드에 세그먼트 이름을 입력하십시오. 필드는 입력한 텍스트를 기반으로 자동으로 업데이트됩니다. 클릭 **[!UICONTROL Add]** 사용할 세그먼트를 찾으면
   * 옵션 2: 클릭 **[!UICONTROL Browse All Segments]** 이름 또는 저장소 위치별로 세그먼트를 검색할 수 있는 창을 엽니다. 클릭 **[!UICONTROL Add Selected Segments]** 완료 시.

1. **매핑 추가:** 매핑 팝에서 매핑 필드에 세그먼트 ID를 입력하고 를 클릭합니다 **[!UICONTROL Save]**.

1. 클릭 **[!UICONTROL Done]**.
