---
description: 클라이언트측 또는 서버측 통합을 통해 자격 조건을 갖춘 세그먼트를 Google Ad Manager로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.
seo-description: 클라이언트측 또는 서버측 통합을 통해 자격 조건을 갖춘 세그먼트를 Google Ad Manager로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.
seo-title: Google Publisher Tags(GPT)를 사용하여 Google Ad Manager로 세그먼트를 전송하는 요구 사항 및 방법
solution: Audience Manager
title: Google Publisher Tags(GPT)를 사용하여 Google Ad Manager로 세그먼트를 전송하는 요구 사항 및 방법
uuid: 4b2ea81c-29bb-42d3-93d3-1d8e677790b6
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Google 게시자 태그(GPT) {#requirements-and-methods-of-sending-segments-to-dfp-using-google-publisher-tags-gpt}를 사용하여 세그먼트를 Google Ad Manager로 전송하는 요구 사항 및 방법

클라이언트측 또는 서버측 통합을 통해 자격 조건을 갖춘 세그먼트를 [!DNL Google Ad Manager](이전 DFP)으로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.

## 클라이언트측 통합 {#client-side-integration}

클라이언트측 통합의 경우 Audience Manager에 [!DNL GPT] 대상을 설정해야 합니다. [!DNL GPT]을(를) Audience Manager 대상으로 설정할 때는 다음 사항을 고려하십시오.

* **추가  [!UICONTROL DIL]:** 타깃팅할 모든 페이지에  [!UICONTROL Data Integration Library (DIL)] 코드를 배포합니다. [!UICONTROL DIL] 타깃팅에 사용되는 쿠키에 Audience Manager 세그먼트 데이터 및 사용자 ID를  [!DNL GPT] 씁니다.

* **만들기: [!UICONTROL Cookie Destination]는 Audience Manager에서 쿠키 기반 대상으로** [!DNL GPT] 설정되어야 합니다.

* **쿠키 확인 코드 구현: 권장** 쿠키 확인 코드 [!DNL GPT] `.setTargeting` 에서  [ ](../../integration/gpt-aam-destination/gpt-aam-modify-api.md)API 메서드를 래핑합니다. 이 코드는 `.setTargeting` 메서드를 호출하기 전에 유효한 AAM 쿠키를 찾아 오류를 방지하는 데 도움이 됩니다.

* **함수 추가:  `AamGpt` 코드** 는 Audience Manager 쿠키의 데이터를 캡처하여  `AamGpt`   [!DNL GPT]전송합니다. 페이지 상단 또는 `<head>` 코드 블록 내에 [Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)( `AamGpt`)용 Audience Manager 코드를 배치합니다.

   >[!NOTE]
   >
   >자체 코드를 사용하여 Audience Manager 쿠키 데이터를 읽는 경우 `AamGpt` 함수가 필요하지 않습니다.

* **Audience Manager으로 배달 로그 보내기: 세그먼트 배달 보고서(선택 사항)를** 원하는 경우 Audience Manager에 노출 수준 배달 데이터가 포함된 일별 로그를 제공합니다. 데이터는 원시 형식일 수 있지만 각 레코드에는 Audience Manager `UUID`이 포함되어야 합니다. Audience Manager은 [!DNL FTP]을 통해 이러한 항목을 받거나 받을 수 있습니다.

### 자격이 있는 세그먼트만 GPT로 전송

[!DNL GPT]에 전달된 데이터의 양은 특정 사용자가 적격한 세그먼트 수에 따라 다릅니다. 예를 들어 100개의 Audience Manager 세그먼트를 설정했다고 가정해 봅시다. 사이트 방문자가 5개 자격을 갖춘 경우 5개의 세그먼트만 [!DNL GPT](100개 세그먼트 모두 아님)으로 전송됩니다.

>[!NOTE]
>
>보낼 수 있는 키-값 수에는 제한이 없지만 [!DNL Google] 요청 [!DNL URL]은 허용할 수 있는 문자 수에 제한이 있습니다. GPT[로 타깃팅 및 크기 설정을 참조하십시오.](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1697712)

## 서버측 통합 {#server-side-integration}

[!DNL GPT]을(를) 사용하여 [!DNL Google Ad Manager]과(와) 서버측 통합을 설정하려면 Audience Manager 컨설턴트나 고객 지원 센터에 문의하십시오. [!DNL Google Ad Manager] 계정 네트워크 ID 및 대상 링크 ID를 제공해야 합니다.

>[!IMPORTANT]
>
>웹 페이지에서 [가속 미디어 페이지](https://www.ampproject.org/)([!DNL AMP]) 라이브러리를 실행하는 경우 서버측 통합을 Audience Manager과 사용해야 합니다. [!DNL AMP]에 있고 [!DNL AMP]과(와) 클라이언트측 통합이 있는 경우 서버측 통합으로 마이그레이션해야 합니다. 마이그레이션을 논의하려면 Audience Manager 컨설턴트 또는 고객 지원 센터에 문의하십시오.

>[!MORELIKETHIS]
>
>* [GPT API 참조 안내서](https://support.google.com/dfp_premium/bin/answer.py?hl=en&amp;answer=1650154)

