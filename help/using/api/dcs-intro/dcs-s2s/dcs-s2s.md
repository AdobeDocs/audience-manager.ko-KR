---
description: S2S(Server-to-Server) API는 DCS 사용자 데이터를 전송 및 수신하고 자신의 시스템 또는 애플리케이션에서 이 정보를 사용하여 작업할 수 있는 코드 및 방법을 제공합니다.
seo-description: S2S(Server-to-Server) API는 DCS 사용자 데이터를 전송 및 수신하고 자신의 시스템 또는 애플리케이션에서 이 정보를 사용하여 작업할 수 있는 코드 및 방법을 제공합니다.
seo-title: 서버 간 데이터 전송을 위한 DCS API
solution: Audience Manager
title: 서버 간 데이터 전송을 위한 DCS API
uuid: 8c369166-c8a7-46b0-9913-4c027f5b1df9
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 11%

---


# 서버 간 데이터 전송을 위한 DCS API{#dcs-apis-for-server-to-server-data-transfers}

Server-to-Server([!UICONTROL S2S]) [!DNL API]s는 [!DNL DCS] 사용자 데이터를 전송 및 받고 자신의 시스템 또는 애플리케이션에서 이 정보를 사용하여 작업할 수 있는 코드 및 메서드를 제공합니다.

## 일반 사용 사례 {#common-use-cases}

[!UICONTROL Server-to-server] 전송을 사용하면 방문자의 관심사에 따라 랜딩 페이지 또는 기타 상호 작용을 사용자 정의할 수 있습니다. 다음은 일반적인 사용 사례입니다.

* 온사이트 개인화:방문자가 속한 세그먼트를 기반으로 연관성 있는 컨텐츠와 클릭 유도 문안을 동적으로 추가하여 사이트에서 방문자의 경험을 맞춤화할 수 있습니다.
* 고객 서비스 개선:서버 간 데이터 전송을 통해 [!DNL Audience Manager] 세그먼트를 [!DNL CRM] 또는 다른 시스템으로 가져옵니다. 이 데이터는 고객을 대상으로 개인화된 관련 정보를 전화 서비스 또는 온라인 채팅 운영자에게 제공할 수 있습니다.

## 요구 사항:사용자 ID 및 지역 서버 이름 {#requirements}

[!UICONTROL DCS API]에서는 데이터 요청을 확인하고 수행하려면 사용자 ID와 지역 ID가 필요합니다.

* 데이터를 특정 방문자와 연결해야 하므로 사용자 ID가 필요합니다.
* 지역 ID는 호출을 다시 서버 이름으로 연결해야 하며 사용자 데이터는 사이트 방문자에게 지리적 위치에 가장 가까운 데이터 센터에 저장되기 때문입니다.

## 시작하기 {#getting-started}

현재 이 가이드에서는 다음 방법을 다룹니다.

* 이미 [!DNL Audience Manager] 고객으로 받을 수 있는 [!DNL DCS] 파일에서 사용자 및 지역 ID를 가져옵니다.

* [!DNL Visitor ID Service]을(를) 사용하는 경우 사용자 및 지역 ID를 가져옵니다.
* 사용자 및 지역 ID가 있는 후에 [!DNL DCS]을 호출합니다.

가능한 새로운 방법을 추가할 것입니다. 시작하려면 다음 섹션을 참조하십시오.

* [DCS 응답에서 사용자 ID 및 지역 가져오기](dcs-aam-ids.md)
* [Experience Cloud ID를 통해 사용자 ID 및 지역 가져오기..](dcs-mcid-ids.md)
* [서버 간 DCS API 호출 만들기](dcs-s2s-calls.md)

>[!MORELIKETHIS]
>
>* [DCS API 참조](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

