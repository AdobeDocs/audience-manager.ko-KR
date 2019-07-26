---
description: 클라이언트측 (브라우저 측) 통합 또는 서버측 통합을 통해 적격 세그먼트를 DFP로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google Publisher 태그용 쿠키 기반 대상을 만들어야 합니다.
seo-description: 클라이언트측 (브라우저 측) 통합 또는 서버측 통합을 통해 적격 세그먼트를 DFP로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google Publisher 태그용 쿠키 기반 대상을 만들어야 합니다.
seo-title: GPT 대상 만들기
solution: Audience Manager
title: GPT 대상 만들기
uuid: e 3 bbf 327-a 7 e 0-48 da-bc 84-8 f 531 b 7 f 6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## 대상

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) 로 데이터를 공유할 수 있습니다. [!UICONTROL Destination Builder] 이 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager destination features are located in *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## 기본 정보

To complete the [!UICONTROL Basic Information] section:

1. 대상의 이름을 지정합니다.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## 쿠키 구성

[!UICONTROL Configuration] 섹션을 완료하려면 다음을 입력합니다 (다른 필드는 선택 사항임).

1. **쿠키 이름:** 쿠키를 설명하는 간단한 설명을 입력합니다.
1. **데이터 형식:** **[!UICONTROL "Single Key"]** 옵션을 선택합니다.
1. **키:** 키 이름을 입력합니다.
1. **일련화:** **[!UICONTROL Enable]** 확인란을 선택합니다.
1. **일련 구분 기호:** 쉼표를 사용합니다.

## 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. 세그먼트를 찾으려면:

   * 옵션 1: 검색 필드에 세그먼트 이름을 입력합니다. 입력한 텍스트를 기반으로 필드가 자동으로 업데이트됩니다. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **매핑 추가:** 매핑 팝업에 매핑 필드에 세그먼트 ID를 입력하고를 클릭합니다 **[!UICONTROL Save]**.

1. 클릭 **[!UICONTROL Done]**.