---
description: 클라이언트측 또는 서버측 통합을 통해 자격이 있는 세그먼트를 Google 광고 관리자로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.
seo-description: 클라이언트측 또는 서버측 통합을 통해 자격이 있는 세그먼트를 Google 광고 관리자로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.
seo-title: Google 게시자 태그(GPT)를 사용하여 Google 광고 관리자에게 세그먼트를 전송하는 요구 사항 및 방법
solution: Audience Manager
title: Google 게시자 태그(GPT)를 사용하여 Google 광고 관리자에게 세그먼트를 전송하는 요구 사항 및 방법
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: 타사 통합
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 0%

---

# Google 게시자 태그(GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}를 사용하여 Google 광고 관리자에게 세그먼트를 전송하는 요구 사항 및 방법

클라이언트측 또는 서버측 통합을 통해 자격이 있는 세그먼트를 [!DNL Google Ad Manager](이전 DFP)로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.

## 클라이언트측 통합 {#client-side-integration}

클라이언트측 통합의 경우 Audience Manager에서 [!DNL GPT] 대상을 설정해야 합니다. [!DNL GPT]을(를) Audience Manager 대상으로 설정할 때는 다음 사항을 고려하십시오.

* **추가  [!UICONTROL DIL]:** 타깃팅할  [!UICONTROL Data Integration Library (DIL)] 모든 페이지에 코드를 배포합니다. [!UICONTROL DIL] 타깃팅을 위해 사용되는 쿠키에 Audience Manager 세그먼트 데이터 및 사용자 ID를  [!DNL GPT] 씁니다.

* **만들기  [!UICONTROL Cookie Destination]:Audience Manager에서 쿠키 기반 대상으로** [!DNL GPT] 설정해야 합니다.

* **쿠키 확인 코드 구현:** 권장  [!DNL GPT] `.setTargeting` 쿠키 확인 코드에서  [API 메서드를 래핑합니다](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). 이 코드는 `.setTargeting` 메서드가 호출되기 전에 유효한 AAM 쿠키를 검색하여 오류를 방지하는 데 도움이 됩니다.

* **함수 추가:  `AamGpt` 코드** 는  `AamGpt` Audience Manager 쿠키의 데이터를 캡처하여  [!DNL GPT]전송합니다. 페이지 상단 또는 `<head>` 코드 블록 내에 [Google Publisher 태그](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)( `AamGpt`)용 Audience Manager 코드를 배치합니다.

   >[!NOTE]
   >
   >자체 코드를 사용하여 Audience Manager 쿠키 데이터를 읽는 경우 `AamGpt` 함수가 필요하지 않습니다.

* **Audience Manager에 배달 로그 보내기:** 세그먼트 배달 보고서를 원하는 경우(선택 사항) 노출 수준 배달 데이터가 포함된 일별 로그를 Audience Manager에 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager `UUID`이(가) 포함되어야 합니다. Audience Manager은 [!DNL FTP]을 통해 이러한 항목을 선택하거나 받을 수 있습니다.

### 자격이 있는 세그먼트만 GPT로 전송됩니다.

[!DNL GPT]에 전달된 데이터의 양은 특정 사용자가 등록한 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정했다고 가정해 보십시오. 사이트 방문자가 5개 중 5개 세그먼트에 자격을 부여하면 이 5개 세그먼트만 [!DNL GPT]으로 전송됩니다(100개 세그먼트 전체가 아님).

>[!NOTE]
>
>보낼 수 있는 키-값 수에는 제한이 없지만 [!DNL Google] 요청 [!DNL URL]은 허용할 수 있는 문자 수에 제한이 있습니다. [GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)로 타깃팅 및 크기 설정을 참조하십시오.

## 서버측 통합 {#server-side-integration}

[!DNL GPT]을(를) 사용하여 [!DNL Google Ad Manager]과(와) 서버측 통합을 설정하려면 Audience Manager 컨설턴트나 고객 지원 센터에 문의하십시오. [!DNL Google Ad Manager] 계정 네트워크 ID 및 대상 링크 ID를 제공해야 합니다.

>[!IMPORTANT]
>
>웹 페이지에서 [가속화된 미디어 페이지](https://www.ampproject.org/)([!DNL AMP]) 라이브러리를 실행하는 경우 서버측 통합을 Audience Manager과 사용해야 합니다. [!DNL AMP]에 있고 [!DNL AMP]과(와) 클라이언트측 통합이 있는 경우 서버측 통합으로 마이그레이션해야 합니다. 마이그레이션 문제를 해결하려면 Audience Manager 컨설턴트 또는 고객 지원 센터에 문의하십시오.

>[!MORELIKETHIS]
>
>* [GPT API 참조 안내서](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

