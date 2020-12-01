---
description: GPT(Google Publisher Tags)를 사용하여 Google Ad Manager를 통합하는 방법에 대한 개요입니다.
seo-description: Adobe Audience Manager(AAM)에서 Google Publisher Tags(GPT)를 사용하여 Google Ad Manager를 통합하는 방법에 대한 개요입니다.
seo-title: Adobe Audience Manager(AAM)에서 Google Publisher Tags(GPT)를 사용하여 Google Ad Manager 통합
title: Google Publisher Tags(GPT)를 사용하여 Google Ad Manager 통합
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Google Publisher Tags(GPT)를 사용하여 [!DNL Google Ad Manager](이전 DFP) 통합

아래 기술문서는 Google Publisher Tags(GPT)를 사용하여 [!DNL Google Ad Manager]을(를) 통합하는 방법에 대한 개요를 제공합니다. 서버측 통합을 사용하거나 GPT를 대상으로 설정하여 Audience Manager 세그먼트 데이터를 [!DNL Google Ad Manager]에 보낼 수 있습니다. Audience Manager에서 보고를 위해 [!DNL Google Ad Manager] 로그 파일을 인제스트하는 데 필요한 단계도 학습합니다.

* [Google Publisher Tags(GPT)를 사용하여 Google Ad Manager로 세그먼트를 전송하는 요구 사항 및 방법](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   클라이언트측 또는 서버측 통합을 통해 자격이 있는 세그먼트를 [!DNL Google Ad Manager]으로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보는 아래에 나와 있습니다.

* [GPT 대상 만들기](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   클라이언트측(브라우저 측) 통합 또는 서버측 통합을 통해 자격이 있는 세그먼트를 [!DNL Google Ad Manager]으로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google 게시자 태그의 쿠키 기반 대상을 만들어야 합니다.

* [GPT setTargeting API 호출 수정](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Google 게시자 태그 .setTargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인하기 위한 if 문을 추가합니다.

* [Google Publisher Tag용 Audience Manager 코드](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 Google 게시자 태그로 보내는 JavaScript 함수입니다.
