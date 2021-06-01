---
description: GPT(Google Publisher Tags)를 사용하여 Google Ad Manager를 통합하는 방법에 대한 개요입니다.
seo-description: Adobe Audience Manager(AAM)에서 GPT(Google Publisher Tags)를 사용하여 Google Ad Manager를 통합하는 방법에 대한 개요입니다.
seo-title: Adobe Audience Manager(AAM)에서 GPT(Google Publisher Tags)를 사용하여 Google Ad Manager 통합
title: GPT(Google Publisher Tags)를 사용하여 Google Ad Manager 통합
feature: 타사 통합
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Google 게시자 태그(GPT)를 사용하여 [!DNL Google Ad Manager](이전 DFP)를 통합합니다.

아래 나열된 문서에서는 GPT(Google Publisher Tags)를 사용하여 [!DNL Google Ad Manager]을 통합하는 방법에 대한 개요를 제공합니다. 서버측 통합을 사용하거나 GPT를 대상으로 설정하여 Audience Manager 세그먼트 데이터를 [!DNL Google Ad Manager]에 보낼 수 있습니다. 또한 Audience Manager에서 보고를 위해 [!DNL Google Ad Manager] 로그 파일을 수집하는 데 필요한 단계를 배웁니다.

* [Google 게시자 태그(GPT)를 사용하여 Google Ad Manager에 세그먼트를 보내기 위한 요구 사항 및 방법](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   클라이언트측 또는 서버측 통합을 통해 정규화된 세그먼트를 [!DNL Google Ad Manager]에 보낼 수 있습니다. 두 가지 방법에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.

* [GPT 대상 만들기](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 정규화된 세그먼트를 [!DNL Google Ad Manager]에 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우, Audience Manager에서 Google Publisher Tags에 대한 쿠키 기반 대상을 만들어야 합니다.

* [GPT setTargeting API 호출 수정](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Google Publisher Tag .setTargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인하는 if 문을 추가합니다.

* [Google Publisher Tag용 Audience Manager 코드](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt는 Audience Manager 쿠키 데이터를 읽고 Google Publisher Tags에 해당 정보를 전송하는 JavaScript 함수입니다.
