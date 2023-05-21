---
description: 광고 서버에서 특정 값을 검색합니다.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 18%

---

# dexGetQSVars{#dexgetqsvars}

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
