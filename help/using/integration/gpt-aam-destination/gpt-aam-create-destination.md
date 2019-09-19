---
description: 클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 적격한 세그먼트를 DFP로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google 게시자 태그의 쿠키 기반 대상을 만들어야 합니다.
seo-description: 클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 적격한 세그먼트를 DFP로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google 게시자 태그의 쿠키 기반 대상을 만들어야 합니다.
seo-title: GPT 대상 만들기
solution: Audience Manager
title: GPT 대상 만들기
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# GPT 대상 만들기 {#create-a-gpt-destination}

클라이언트측(브라우저 측) 통합 또는 서버측 통합을 [!DNL DFP] 통해 적격한 세그먼트를 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 쿠키 기반 대상을 만들어야 [!DNL Google Publisher Tags] 합니다.

## 대상

Audience Manager *`destination`* 에서 는 다른 모든 시스템(광고 서버, [!DNL DSP]광고 네트워크 등)입니다. 데이터를 공유할 수 있습니다. [!UICONTROL Destination Builder] 에서는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은 *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*&#x200B;에 있습니다. 시작하려면 을 클릭하고 아래 단계를 **[!UICONTROL Add New Destination]** 따르십시오.

## 기본 정보

섹션을 완료하려면 [!UICONTROL Basic Information] 다음을 수행하십시오.

1. 대상의 이름을 지정합니다.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 을 **[!UICONTROL Next]** 클릭하고 [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션으로 이동합니다.

## 쿠키 구성

다음을 제공하여 [!UICONTROL Configuration] 섹션을 완료합니다(다른 필드는 선택 사항).

1. **** 쿠키 이름:쿠키에 사용할 간단한 설명 이름을 제공합니다.
1. **** 데이터 형식:옵션을 **[!UICONTROL "Single Key"]** 선택합니다.
1. **** 키:키 이름을 입력합니다.
1. **** 일련화:확인란을 **[!UICONTROL Enable]** 선택합니다.
1. **** 직렬 구분 기호:쉼표만 사용하십시오.

## 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. 세그먼트 찾기:이 [!UICONTROL Segment Mappings] 섹션에서는 세그먼트를 찾는 데 도움이 되는 두 개의 검색 도구를 제공합니다. 세그먼트를 찾으려면

   * 옵션 1:검색 필드에 세그먼트 이름을 입력합니다. 입력된 텍스트를 기반으로 필드가 자동으로 업데이트됩니다. 사용할 세그먼트를 **[!UICONTROL Add]** 찾으면 클릭합니다.
   * 옵션 2:이름이나 저장소 위치별로 세그먼트를 검색할 수 있는 창을 **[!UICONTROL Browse All Segments]** 열려면 을 클릭합니다. Click **[!UICONTROL Add Selected Segments]** when done.

1. **** 매핑 추가:매핑 팝업에서 매핑 필드에 세그먼트 ID를 입력하고 을 **[!UICONTROL Save]**&#x200B;클릭합니다.

1. 클릭 **[!UICONTROL Done]**.