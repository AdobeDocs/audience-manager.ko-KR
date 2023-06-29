---
description: 광고 서버에서 특정 값을 검색합니다.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 8%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>2023년 7월부터 Adobe은 의 개발을 중단했습니다. [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장명.
><br>
>기존 고객은 [!DNL DIL] 구현. 그러나 Adobe은 개발되지 않습니다 [!DNL DIL] 이 점을 넘어서는 것입니다. 고객은 다음을 평가하는 것이 좋습니다. [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 을 참조하십시오.
><br>
>2023년 7월 이후 새로운 데이터 수집 통합을 구현하려는 고객은 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 대신,

광고 서버에서 특정 값을 검색합니다.

**함수 서명:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `variableName` | 문자열 | 값을 가져오려는 변수의 이름입니다. |
| `partner` | 문자열 | 검색할 파트너 이름입니다. |
| `containerNSID` | 정수 | 다음 [!DNL NSID] 검색 중인 컨테이너 기본값은 입니다. `0`. |

**응답**

에 대한 변수 값 반환 [!UICONTROL DIL] 인스턴스.

**샘플 코드**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
