---
description: S2S(서버 간) API는 DCS 사용자 데이터를 주고 받고 자체 시스템 또는 애플리케이션에서 이러한 정보로 작업할 수 있는 코드와 메서드를 제공합니다.
seo-description: Server-to-server (S2S) APIs provide code and methods that let you send and receive DCS user data and work with this information in your own systems or applications.
seo-title: DCS APIs for Server-to-Server Data Transfers
solution: Audience Manager
title: 서버 간 데이터 전송을 위한 DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
exl-id: fd23d5e2-b74e-47ff-a4aa-3a4b2c7d39c5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# 서버 간 데이터 전송을 위한 DCS API{#dcs-apis-for-server-to-server-data-transfers}

서버 간([!UICONTROL S2S]) [!DNL API]은(는) [!DNL DCS] 사용자 데이터를 보내고 받을 수 있고 시스템 또는 응용 프로그램에서 이 정보를 사용하여 작업할 수 있는 코드와 메서드를 제공합니다.

## 일반적인 사용 사례 {#common-use-cases}

[!UICONTROL Server-to-server] 전송을 통해 방문자의 관심 분야에 따라 랜딩 페이지나 기타 상호 작용을 사용자 지정할 수 있습니다. 일반적인 사용 사례는 다음과 같습니다.

* 온사이트 개인화: 관련 콘텐츠 및 콜 투 액션을 자신이 속한 세그먼트에 따라 동적으로 추가하여 사이트에서 방문자의 경험을 맞춤화합니다.
* 고객 서비스 개선: 서버 간 데이터 전송을 통해 [!DNL Audience Manager] 세그먼트를 [!DNL CRM] 또는 다른 시스템으로 가져옵니다. 이 데이터는 콜 서비스 또는 온라인 채팅 운영자에게 고객에 대한 연관성 있고 개인화된 정보를 제공할 수 있습니다.

## 요구 사항: 사용자 ID 및 지역 서버 이름 {#requirements}

[!UICONTROL DCS API]을(를) 사용하려면 유효성을 검사하고 데이터 요청을 수행하려면 사용자 ID와 지역 ID가 필요합니다.

* 데이터를 특정 방문자와 연결해야 하므로 사용자 ID가 필요합니다.
* 지역 ID는 호출을 서버 이름에 다시 연결하는 데 필요하며 사용자 데이터는 사이트 방문자에게 지리적으로 가장 가까운 데이터 센터에 저장됩니다.

## 시작하기 {#getting-started}

현재 이 안내서에서는 다음 방법을 다룹니다.

* [!DNL DCS] 고객으로 이미 받은 [!DNL Audience Manager] 파일에서 사용자 및 지역 ID를 가져옵니다.

* [!DNL Visitor ID Service]을(를) 사용하는 경우 사용자 및 지역 ID를 가져옵니다.
* 사용자 및 지역 ID가 있으면 [!DNL DCS]을(를) 호출합니다.

새로운 메서드를 사용할 수 있게 되면 추가하겠습니다. 시작하려면 다음 섹션을 참조하십시오.

* [DCS 응답에서 사용자 ID 및 지역 가져오기](dcs-aam-ids.md)
* [Experience Cloud ID를 통해 사용자 ID 및 지역 가져오기...](dcs-mcid-ids.md)
* [서버 간 DCS API 호출 만들기](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API 참조](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)
