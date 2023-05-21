---
description: Audience Manager 및 Adobe Experience Platform Identity 서비스는 demdex.net 도메인을 호출하고 해당 도메인에서 데이터를 받습니다. 이는 Adobe이 비정상적인 타사 도메인과 작동하는 것처럼 보일 수 있지만, 실제로 작동하는 것은 아닙니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Demdex 도메인에 대한 호출 이해
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 8%

---

# 에 대한 호출 이해 [!DNL Demdex] 도메인 {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 및 [!DNL Adobe Experience Platform Identity Service] 을(를) 호출하고 에서 데이터를 받습니다. `demdex.net` 도메인. 다음과 같습니다. [!DNL Adobe] 는 비정상적인 타사 도메인을 사용하여 작동하지만, 실제로 작동하지 않습니다. 이 섹션에서는 `demdex.net` 호출합니다.

| 호출 요소 | 설명 |
|---|---|
| `demdex.net` | 이 도메인은에서 제어하는 기존 도메인입니다 [!DNL Adobe]. 원래의, 인수 이전 이름을 반영합니다. [!DNL Audience Manager] ([!DNL Demdex]). [!DNL Adobe]는 2011년에 [!DNL Demdex]를 인수하고 회사 브랜드를 [!DNL Audience Manager]로 변경했습니다. 이 도메인은 와(과) 깊게 연결되어 있으므로 변경하기가 어렵습니다. [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service]및 설치된 사용자 기반입니다. 다른 접두사가 기존 접두사에 첨부되어 있을 수 있습니다 `demdex.net` 호출 (예: `dcs.demdex.net`, `fast.demdex.net`등). 접두사에 관계없이 `something.demdex.net` 은(는) 항상 을 호출합니다. [!DNL Adobe] 알 수 없거나 의심스러운 타사 도메인은 허용되지 않습니다. |
| `dpm` | [!DNL DPM] 는 의 약어입니다. [!DNL Data Provider Match]. 내부적으로는 [!DNL Adobe] 에서 호출을 수행하는 시스템 [!DNL Audience Manager] 또는 [!DNL Adobe Experience Cloud ID Service] 은(는) 동기화 또는 ID 요청을 위해 고객 데이터를 전달합니다. 가장 일반적인 항목 `demdex.net` 다음에서 보게 될 전화: [!DNL Audience Manager] 또는 [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] 호출 기본 사항: <ul><li>[!DNL Audience Manager]: A [!DNL DPM] 다음에서 호출: [!DNL Audience Manager] 에 데이터 전송 [!DNL Data Collection Servers] 및 [!DNL Profile Cache Servers]. [데이터 수집 구성 요소](../reference/system-components/components-data-collection.md)를 참조하십시오.</li><li>[!DNL Adobe Experience Cloud ID Service]: A [!DNL DPM] 에서 호출 [!DNL Adobe Experience Cloud ID Service] 는 방문자 ID에 대한 요청입니다. 다음을 참조하십시오 [쿠키 및 Adobe Experience Platform Identity 서비스](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) 및 [Adobe Experience Platform Identity 서비스에서 ID를 요청하고 설정하는 방법](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>참고: [!DNL Adobe Experience Cloud ID Service] 고객은 [!DNL DPM] 도메인 이름에 접두사를 추가합니다. 다음을 참조하십시오 [audienceManager Server 및 audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager 쿠키](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)

