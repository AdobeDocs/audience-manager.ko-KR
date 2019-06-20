---
description: Google Publisher 태그 (GPT) 를 사용하여 DFP를 통합하는 방법에 대한 개요입니다.
seo-description: AAM (Adobe Audience Manager) 에서 GPT (Google Publisher Tags) 를 사용하여 DFP를 통합하는 방법에 대한 개요입니다.
seo-title: AAM (Adobe Audience Manager) 에서 Google Publisher 태그 (GPT) 를 사용하여 DFP 통합
title: Google Publisher 태그 (GPT) 를 사용하여 DFP 통합
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Google Publisher 태그 (GPT) 를 사용하여 DFP 통합

아래 문서는 Google Publisher 태그 (GPT) 를 사용하여 DFP를 통합하는 방법에 대한 개요를 제공합니다. 서버측 통합을 사용하거나, GPT를 대상으로 설정하여 Audience Manager 세그먼트 데이터를 DFP로 보낼 수 있습니다. 또한 Audience Manager에서 보고를 위해 DFP 로그 파일을 인제스트하는 데 필요한 단계를 학습합니다.

* [Google 게시자 태그(GPT)를 사용하여 DFP에 세그먼트를 보내기 위한 요구 사항 및 방법](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   클라이언트 측 또는 서버측 통합을 통해 적격 세그먼트를 DFP로 보낼 수 있습니다. 두 방법 모두에 대한 요구 사항 및 관련 정보가 아래에 나와 있습니다.

* [GPT 대상 만들기](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   클라이언트측 (브라우저 측) 통합 또는 서버측 통합을 통해 적격 세그먼트를 DFP로 보낼 수 있습니다. 클라이언트측 통합을 선택하는 경우 Audience Manager에서 Google Publisher 태그용 쿠키 기반 대상을 만들어야 합니다.

* [GPT 설정 수정 API 호출 수정](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Google Publisher Tag. settargeting 메서드를 호출하기 전에 Audience Manager 쿠키를 확인하려면 if 문을 추가합니다.

* [Google Publisher 태그를 위한 Audience Manager 코드](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   Aamgpt는 Audience Manager 쿠키 데이터를 읽고 해당 정보를 Google Publisher 태그로 전송하는 JavaScript 기능입니다.
