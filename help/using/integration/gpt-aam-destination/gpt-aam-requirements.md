---
description: 클라이언트 측 또는 서버측 통합을 통해 적격 세그먼트를 DFP로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보가 아래에 나와 있습니다.
seo-description: 클라이언트 측 또는 서버측 통합을 통해 적격 세그먼트를 DFP로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보가 아래에 나와 있습니다.
seo-title: Google 게시자 태그(GPT)를 사용하여 DFP에 세그먼트를 보내기 위한 요구 사항 및 방법
solution: Audience Manager
title: Google 게시자 태그(GPT)를 사용하여 DFP에 세그먼트를 보내기 위한 요구 사항 및 방법
uuid: 4 B 2 EA 81 C -29 BB -42 D 3-93 D 3-1 D 8 E 677790 B 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Google 게시자 태그(GPT)를 사용하여 DFP에 세그먼트를 보내기 위한 요구 사항 및 방법{#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

You can send qualified segments to [!DNL DFP] either through a client-side or through a server-side integration. 두 방법 모두에 대한 요구 사항 및 관련 정보가 아래에 나와 있습니다.

## Client-Side Integration {#client-side-integration}

For a client-side integration, you need to set up a [!DNL GPT] destination in Audience Manager. Consider the following points when you want to set up [!DNL GPT] as an Audience Manager destination:

* **[!UICONTROL DIL]추가:** 타깃팅할 모든 페이지에 [!UICONTROL Data Integration Library (DIL)] 코드를 배포합니다. [!UICONTROL DIL] 타깃팅용으로 사용되는 [!DNL GPT] 쿠키에 Audience Manager 세그먼트 데이터 및 사용자 ID를 기록합니다.

* **A[!UICONTROL Cookie Destination]:**[!DNL GPT] Audience Manager에서 쿠키 기반 대상으로 설정해야 합니다.

* **쿠키 검사 코드 구현:** 권장 [!DNL GPT]`.setTargeting`[쿠키 확인 코드에서 API 메서드를](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)래핑합니다. This code helps prevent errors by looking for valid AAM cookies before the `.setTargeting` method gets invoked.

* **`AamGpt`함수를 추가합니다.** `AamGpt` 이 코드는 Audience Manager 쿠키의 데이터를 캡처하여 전송합니다 [!DNL GPT]. Place the [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`) at the top of the page or inside the `<head>` code block.

   >[!NOTE]
   >
   >The `AamGpt` function is not required if you use your own code to read Audience Manager cookie data.

* **Audience Manager로 배달 로그 보내기:** 세그먼트 배달 보고서를 원할 경우 (옵션), 노출 수준 배달 데이터가 들어 있는 일별 로그를 Audience Manager에 제공합니다. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### 정규화된 세그먼트만 GPT로 전송됩니다.

The amount of data passed in to [!DNL GPT] depends on how many segments a particular user qualifies for. 예를 들어 100 개의 Audience Manager 세그먼트를 설정한다고 가정합니다. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL GPT] (not all 100).

>[!NOTE]
>
>There are no limits to the number of key-values you can send, but the [!DNL Google] request [!DNL URL] does have limits to the number of characters it can accept. See [Setting targeting and sizes with GPT](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1697712).

## Server-Side Integration {#server-side-integration}

Talk to your Audience Manager consultant or Customer Care if you want to set up a server-side integration with [!DNL DFP], using [!DNL GPT]. [!DNL DFP] 계정 네트워크 ID와 대상 링크 ID를 제공해야 합니다.

>[!IMPORTANT]
>
>If your web pages are running the [Accelerated Media Pages](https://www.ampproject.org/) ([!DNL AMP]) library, you must use the server-side integration with Audience Manager. If you are on [!DNL AMP] and have a client-side integration with [!DNL AMP], you must migrate to the server-side integration. 마이그레이션에 대해 논의하려면 Audience Manager 컨설턴트 또는 고객 지원 센터에 문의하십시오.

>[!MORE_ like_ this]
>
>* [GPT API 참조 안내서](https://support.google.com/dfp_premium/bin/answer.py?hl=en&answer=1650154)

