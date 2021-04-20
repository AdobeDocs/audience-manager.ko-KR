---
description: Audience Manager 및 Adobe Experience Platform ID 서비스는 demdex.net 도메인에서 데이터를 호출하고 받습니다. 이는 Adobe이 비정상적인 제3자 도메인과 협력하는 것처럼 보이지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-description: Audience Manager 및 Adobe Experience Platform ID 서비스는 demdex.net 도메인에서 데이터를 호출하고 받습니다. 이는 Adobe이 비정상적인 제3자 도메인과 협력하는 것처럼 보이지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-title: Demdex 도메인에 대한 호출 이해
solution: Audience Manager
title: Demdex 도메인에 대한 호출 이해
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# [!DNL Demdex] 도메인 {#understanding-calls-to-the-demdex-domain}에 대한 호출 이해

[!DNL Audience Manager] 도메인 [!DNL Adobe Experience Platform Identity Service] 에서 데이터를 호출할 수  `demdex.net` 있습니다. 이것은 [!DNL Adobe]이(가) 비정상적인 제3자 도메인과 함께 작동하는 것처럼 보이지만 그렇지 않습니다. 이 섹션에서는 `demdex.net` 호출의 요소에 대해 설명합니다.

| 호출 요소 | 설명 |
|---|---|
| `demdex.net` | 이것은 [!DNL Adobe]에 의해 제어되는 레거시 도메인입니다. 여기에는 [!DNL Audience Manager]([!DNL Demdex])의 원래 사전 획득 이름이 반영됩니다. [!DNL Adobe]는 2011년에 [!DNL Demdex]를 인수하고 회사 브랜드를 [!DNL Audience Manager]로 변경했습니다. 이 도메인은 [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] 및 설치된 사용자 기반에 깊이 입력되므로 변경하는 것이 어렵습니다. 기존 `demdex.net` 호출(예: `dcs.demdex.net`, `fast.demdex.net` 등)에 첨부된 다른 접두어가 표시될 수 있습니다. 접두어에 관계없이 `something.demdex.net` 호출은 항상 [!DNL Adobe]에 대한 호출이며 알 수 없거나 의심스러운 제3자 도메인에 대한 호출은 아닙니다. |
| `dpm` | [!DNL DPM] 의 약어입니다 [!DNL Data Provider Match]. 내부 시스템에 대해 [!DNL Adobe] 또는 [!DNL Adobe Experience Cloud ID Service]의 호출이 동기화하거나 ID를 요청하기 위해 고객 데이터를 전달하고 있음을 알립니다. [!DNL Audience Manager] 이것은 [!DNL Audience Manager] 또는 [!DNL Adobe Experience Cloud ID Service]에서 볼 수 있는 가장 일반적인 `demdex.net` 호출입니다. <br><br>[!DNL DPM] 기본 사항: <ul><li>[!DNL Audience Manager]:에서  [!DNL DPM] 호출하면  [!DNL Audience Manager] 및 [!DNL Data Collection Servers] 으로 데이터를  [!DNL Profile Cache Servers]전송합니다. [데이터 수집 구성 요소](../reference/system-components/components-data-collection.md)를 참조하십시오.</li><li>[!DNL Adobe Experience Cloud ID Service]:방문자  [!DNL DPM] ID [!DNL Adobe Experience Cloud ID Service] 에 대한 요청입니다. [쿠키 및 Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html) 및 [Adobe Experience Platform ID 서비스가 ID를 요청 및 설정하는 방법을 참조하십시오](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>참고: [!DNL Adobe Experience Cloud ID Service] 도메인 이름의  [!DNL DPM] 접두사를 변경할 수 있습니다. [audienceManager Server 및 audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html)를 참조하십시오. |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Audience Manager 쿠키](https://docs.adobe.com/content/help/ko-KR/core-services/interface/ec-cookies/cookies-am.html)

