---
description: Audience Manager 및 Adobe Experience Platform ID 서비스는 demdex.net 도메인에서 데이터를 호출하고 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-description: Audience Manager 및 Adobe Experience Platform ID 서비스는 demdex.net 도메인에서 데이터를 호출하고 수신합니다. Adobe가 비정상적인 타사 도메인을 사용하고 있는 것처럼 보일 수 있지만 그렇지 않습니다. 이 섹션에서는 demdex.net 호출의 요소에 대해 설명합니다.
seo-title: Demdex 도메인에 대한 호출 이해
solution: Audience Manager
title: Demdex 도메인에 대한 호출 이해
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 14%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] 도메인 [!DNL Adobe Experience Platform Identity Service] 에서 데이터를 호출하고 `demdex.net` 받습니다. 이는 비정상적인 타사 도메인 [!DNL Adobe] 을 사용하는 것처럼 보이지만 그렇지 않습니다. 이 섹션에서는 `demdex.net` 호출의 요소에 대해 설명합니다.

| 호출 요소 | 설명 |
|---|---|
| `demdex.net` | This is a legacy domain controlled by [!DNL Adobe]. 여기에는 ( [!DNL Audience Manager] )의 원래 획득 전 이름이[!DNL Demdex]반영됩니다. [!DNL Adobe]는 2011년에 [!DNL Demdex]를 인수하고 회사 브랜드를 [!DNL Audience Manager]로 변경했습니다. 이 도메인은 설치된 사용자 기반과 함께 깊이 [!DNL Audience Manager]로 입력되기 때문에 [!DNL Adobe Experience Cloud ID Service]변경하는 것이 어렵습니다. 기존 `demdex.net` 호출(예:, `dcs.demdex.net`등)에 첨부된 다른 접두사가 표시될 수 `fast.demdex.net`있습니다. 접두사에 상관없이 호출은 항상 `something.demdex.net` 알 수 없거나 의심스러운 타사 도메인이 아닌 [!DNL Adobe] 호출입니다. |
| `dpm` | [!DNL DPM] 은 의 약어입니다 [!DNL Data Provider Match]. It tells internal, [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the [!DNL Adobe Experience Cloud ID Service] is passing in customer data for synchronization or requesting an ID. 이것은 당신이 볼 수 있는 가장 일반적인 `demdex.net` 전화 [!DNL Audience Manager] 의 [!DNL Adobe Experience Cloud ID Service]것입니다. <br><br>[!DNL DPM] 기본 사항: <ul><li>[!DNL Audience Manager]: 호출은 데이터 [!DNL DPM] 를 [!DNL Audience Manager] 및 [!DNL Data Collection Servers] 로 전송합니다 [!DNL Profile Cache Servers]. [데이터 수집 구성 요소](../reference/system-components/components-data-collection.md)를 참조하십시오.</li><li>[!DNL Adobe Experience Cloud ID Service]: 방문자 [!DNL DPM] ID [!DNL Adobe Experience Cloud ID Service] 에 대한 호출입니다. 쿠키 [및 Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/intro/cookies.html) 및 Adobe Experience Platform ID 서비스가 ID를 요청 및 설정하는 [방법](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html)을참조하십시오.</li></ul><br>참고: [!DNL Adobe Experience Cloud ID Service] 고객은 도메인 이름의 [!DNL DPM] 접두사를 변경할 수 있습니다. audienceManager [Server 및 audienceManagerServerSecure를 참조하십시오](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html)
>* [Audience Manager 쿠키](https://docs.adobe.com/content/help/ko-KR/core-services/interface/ec-cookies/cookies-am.html)

