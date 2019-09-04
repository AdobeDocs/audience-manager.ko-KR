---
description: 광고 서버에서 특정 값을 검색합니다.
seo-description: 광고 서버에서 특정 값을 검색합니다.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Dexgetqsvars{#dexgetqsvars}

광고 서버에서 특정 값을 검색합니다.

**함수 서명:**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**매개 변수**

| 이름 | 유형 | 설명 |
|---|---|---|
| `variableName` | 문자열 | 값을 가져올 변수의 이름. |
| `partner` | 문자열 | 검색할 파트너 이름. |
| `containerNSID` | 정수 | 검색할 [!DNL NSID] 컨테이너의 이름입니다. 기본값은 `0`입니다. |

**응답**

인스턴스에 대한 변수 값을 [!UICONTROL DIL] 반환합니다.

**샘플 코드**

<pre class="java"><code>var value = dil. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>);</code></pre>
