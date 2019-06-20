---
description: 서버-서버 (S 2 S) API는 DCS 사용자 데이터를 보내고 받을 수 있고 자체 시스템이나 애플리케이션에서 이 정보를 사용할 수 있도록 해주는 코드 및 메서드를 제공합니다.
seo-description: 서버-서버 (S 2 S) API는 DCS 사용자 데이터를 보내고 받을 수 있고 자체 시스템이나 애플리케이션에서 이 정보를 사용할 수 있도록 해주는 코드 및 메서드를 제공합니다.
seo-title: 서버-서버 데이터 전송을 위한 DCS API
solution: Audience Manager
title: 서버-서버 데이터 전송을 위한 DCS API
uuid: 8 C 369166-C 8 A 7-46 B 0-9913-4 C 027 F 5 B 1 DF 9
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# DCS APIs for Server-to-Server Data Transfers{#dcs-apis-for-server-to-server-data-transfers}

Server-to-server ([!UICONTROL S2S]) [!DNL API]s provide code and methods that let you send and receive [!UICONTROL DCS] user data and work with this information in your own systems or applications.

## Common Use Cases {#common-use-cases}

[!UICONTROL Server-to-server] 전송을 통해 방문자의 관심사에 따라 랜딩 페이지 또는 기타 상호 작용을 사용자 지정할 수 있습니다. 일반적인 사용 사례는 다음과 같습니다.

* 온사이트 개인화: 고객이 속한 세그먼트에 따라 관련 컨텐츠 및 클릭 유도 문안을 동적으로 추가하여 사이트에서 방문자의 경험을 맞춤화할 수 있습니다.
* Improve customer service: Import [!DNL Audience Manager] segments into a [!DNL CRM] or other system through a server-to-server data transfer. 이 데이터는 고객에 대한 연관성 있고 개인화된 정보를 전화 서비스 또는 온라인 채팅 운영자에게 제공할 수 있습니다.

## Requirements: User IDs and Regional Server Names {#requirements}

The [!UICONTROL DCS API] requires user IDs and region IDs to validate and make data requests.

* 사용자 ID는 데이터를 특정 방문자와 연결해야 하기 때문에 필요합니다.
* 지역 ID는 호출을 서버 이름으로 다시 연결하는 데 필요하며 사용자 데이터는 사이트 방문자와 지리적으로 가장 가까운 데이터 센터에 저장되어 있으므로

## 시작하기 {#getting-started}

현재 이 안내서에서는 다음 방법을 다룹니다.

* Get the user and region IDs from the [!UICONTROL DCS] files you may already receive as an [!DNL Audience Manager] customer.

* Get the user and region IDs if you use the [!DNL Visitor ID Service].
* Make calls to the [!UICONTROL DCS] after you have the user and region ID.

새 메서드를 출시와 동시에 추가합니다. 시작하려면 다음 섹션을 참조하십시오.

* [DCS 응답에서 사용자 ID 및 지역 가져오기](dcs-aam-ids.md)
* [Experience Cloud ID를 통해 사용자 ID 및 지역 가져오기...](dcs-mcid-ids.md)
* [서버 간 DCS API 호출 만들기](dcs-s2s-calls.md)

>[!MORE_ like_ this]
>
>* [DCS API 참조](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)

