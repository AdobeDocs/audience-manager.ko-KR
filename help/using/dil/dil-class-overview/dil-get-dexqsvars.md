---
description: 광고 서버에서 특정 값을 검색합니다.
seo-description: 광고 서버에서 특정 값을 검색합니다.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 17%

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
| `variableName` | 문자열 | 값을 가져올 변수의 이름. |
| `partner` | 문자열 | 검색할 파트너 이름입니다. |
| `containerNSID` | 정수 | 검색하는 컨테이너의 [!DNL NSID]입니다. 기본값은 `0`입니다. |

**응답**

[!UICONTROL DIL] 인스턴스의 변수 값을 반환합니다.

**샘플 코드**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
