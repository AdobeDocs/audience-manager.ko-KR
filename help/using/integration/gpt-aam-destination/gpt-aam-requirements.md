---
description: 클라이언트측 또는 서버측 통합을 통해 적격 세그먼트를 Google Ad Manager에 보낼 수 있습니다. 두 방법에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.
seo-description: You can send qualified segments to Google Ad Manager either through a client-side or through a server-side integration. Requirements and related information about both methods are listed below.
seo-title: Requirements and Methods of Sending Segments to Google Ad Manager Using Google Publisher Tags (GPT)
solution: Audience Manager
title: Google 게시자 태그(GPT)를 사용하여 Google Ad Manager에 세그먼트를 보내기 위한 요구 사항 및 방법
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third-party Integration
exl-id: 04bf6fb5-ce38-4de1-bf19-e130b7e47616
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '481'
ht-degree: 0%

---

# Google 게시자 태그(GPT)를 사용하여 Google Ad Manager에 세그먼트를 보내기 위한 요구 사항 및 방법 {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}

다음 대상에게 적격한 세그먼트를 보낼 수 있습니다. [!DNL Google Ad Manager] (이전의 DFP) 클라이언트 측 또는 서버 측 통합을 통해. 두 방법에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.

## 클라이언트측 통합 {#client-side-integration}

클라이언트측 통합을 위해 다음을 설정해야 합니다. [!DNL GPT] Audience Manager 내 대상. 설정할 때 다음 사항을 고려하십시오 [!DNL GPT] Audience Manager 대상:

* **추가 [!UICONTROL DIL]:** 배포 [!UICONTROL Data Integration Library (DIL)] 을(를) 타깃팅할 모든 페이지의 코드에 추가합니다. [!UICONTROL DIL] 에서 사용하는 쿠키에 Audience Manager 세그먼트 데이터 및 사용자 ID를 기록합니다. [!DNL GPT] 타깃팅용.

* **만들기 [!UICONTROL Cookie Destination]:** [!DNL GPT] 은(는) Audience Manager에서 쿠키 기반 대상으로 설정해야 합니다.

* **쿠키 확인 코드 구현:** 줄 바꿈 [!DNL GPT] `.setTargeting` 권장되는 의 API 메서드 [쿠키 검사 코드](../../integration/gpt-aam-destination/gpt-aam-modify-api.md). 이 코드는 올바른 AAM 쿠키를 찾기 전에 오류를 방지하는 데 도움이 됩니다. `.setTargeting` 메서드가 호출됩니다.

* **추가 `AamGpt` 함수:** 다음 `AamGpt` 코드는 Audience Manager 쿠키에서 데이터를 캡처하여 (으)로 전송합니다. [!DNL GPT]. 배치 [Google 게시자 태그에 대한 Audience Manager 코드](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md) ( `AamGpt`)를 클릭하여 제품에서 사용할 수 있습니다 `<head>` 코드 블록.

   >[!NOTE]
   >
   >다음 `AamGpt` 자체 코드를 사용하여 Audience Manager 쿠키 데이터를 읽는 경우에는 함수가 필요하지 않습니다.

* **Audience Manager에 게재 로그 보내기:** 세그먼트 게재 보고서가 필요하면 Audience Manager에게 노출 수준 게재 데이터가 포함된 일별 로그를 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager이 포함되어야 합니다 `UUID`. Audience Manager은 를 통해 이러한 파일을 받거나 받을 수 있습니다. [!DNL FTP].

### 적격 세그먼트만 GPT로 전송됩니다.

에 전달된 데이터의 양 [!DNL GPT] 특정 사용자가 사용할 수 있는 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정한다고 가정해 보겠습니다. 사이트 방문자가 이 중 5개에 대한 자격이 있는 경우 해당 5개의 세그먼트만 [!DNL GPT] (100개 중 일부만).

>[!NOTE]
>
>보낼 수 있는 키-값의 수에는 제한이 없지만 [!DNL Google] 요청 [!DNL URL] 에는 사용할 수 있는 문자 수에 제한이 있습니다. 다음을 참조하십시오 [GPT를 사용하여 타깃팅 및 크기 설정](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712).

## 서버측 통합 {#server-side-integration}

과 서버측 통합을 설정하려면 Audience Manager 컨설턴트나 고객 지원에 문의하십시오. [!DNL Google Ad Manager], 사용 [!DNL GPT]. 다음을 제공해야 합니다. [!DNL Google Ad Manager] 계정 네트워크 ID 및 대상 링크 ID.

>[!IMPORTANT]
>
>웹 페이지에서 [가속 미디어 페이지](https://www.ampproject.org/) ([!DNL AMP]) 라이브러리에서는 Audience Manager과의 서버측 통합을 사용해야 합니다. 켜진 경우 [!DNL AMP] 와 클라이언트측 통합 [!DNL AMP]를 설치한 후 서버측 통합으로 마이그레이션해야 합니다. 마이그레이션에 대해 논의하려면 Audience Manager 컨설턴트나 고객 지원에 문의하십시오.

>[!MORELIKETHIS]
>
>* [GPT API 참조 안내서](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

