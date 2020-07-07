---
description: 클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 자격 조건을 갖춘 세그먼트를 Google Ad Manager로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google 게시자 태그의 쿠키 기반 대상을 만들어야 합니다.
seo-description: 클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 자격 조건을 갖춘 세그먼트를 Google Ad Manager로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google 게시자 태그의 쿠키 기반 대상을 만들어야 합니다.
seo-title: GPT 대상 만들기
solution: Audience Manager
title: GPT 대상 만들기
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# GPT 대상 만들기 {#create-a-gpt-destination}

클라이언트측(브라우저 [!DNL Google Ad Manager] 측) 통합 또는 서버측 통합을 통해 적격한 세그먼트를 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에 대한 쿠키 기반 대상을 만들어야 [!DNL Google Publisher Tags] 합니다.

## 대상

Audience Manager에서 a *`destination`* 는 다른 모든 시스템(광고 서버, [!DNL DSP]광고 네트워크 등)입니다. 입니다. [!UICONTROL Destination Builder] 는 이러한 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager 대상 기능은 *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*에 있습니다. 시작하려면 을(**[!UICONTROL Add New Destination]**를) 클릭하고 아래 단계를 따르십시오.

## 기본 정보

섹션을 완료하려면 [!UICONTROL Basic Information] 다음을 수행하십시오.

1. 대상의 이름을 지정합니다.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. 를 **[!UICONTROL Next]** 클릭하고 [!UICONTROL Configuration] 및 [!UICONTROL Segment Mappings] 섹션으로 이동합니다.

## 쿠키 구성

섹션을 완료하려면 다음을 [!UICONTROL Configuration] 제공하십시오(다른 필드는 선택 사항임).

1. **쿠키 이름:** 쿠키에 대해 간단한 설명형 이름을 제공합니다.
1. **데이터 형식:** 옵션을 **[!UICONTROL "Single Key"]** 선택합니다.
1. **키:** 키 이름을 입력합니다.
1. **일련화:** 확인란을 **[!UICONTROL Enable]** 선택합니다.
1. **직렬 구분 기호:** 쉼표만 사용하십시오.

## 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. 세그먼트 찾기: 이 [!UICONTROL Segment Mappings] 섹션에는 세그먼트를 찾는 데 도움이 되는 두 개의 검색 도구가 제공됩니다. 세그먼트를 찾으려면

   * 옵션 1: 검색 필드에 세그먼트 이름을 입력하기 시작합니다. 입력된 텍스트를 기반으로 필드가 자동으로 업데이트됩니다. 사용할 세그먼트를 찾은 **[!UICONTROL Add]** 다음 을 클릭합니다.
   * 옵션 2: 이름 또는 저장소 위치별로 세그먼트를 검색할 수 있는 창을 열려면 을 클릭합니다 **[!UICONTROL Browse All Segments]** . 완료되면 을 **[!UICONTROL Add Selected Segments]** 클릭합니다.

1. **매핑 추가:** 매핑 팝업에서 매핑 필드에 세그먼트 ID를 입력하고 을 클릭합니다 **[!UICONTROL Save]**.

1. 클릭 **[!UICONTROL Done]**.