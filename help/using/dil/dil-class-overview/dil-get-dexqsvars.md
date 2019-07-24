---
description: 광고 서버에서 특정 값을 검색합니다.
seo-description: 광고 서버에서 특정 값을 검색합니다.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# dexGetQSVars{#dexgetqsvars}

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
| `containerNSID` | 정수 | The [!DNL NSID] of the container you're searching for. Defaults is `0`. |

**응답**

Returns the variable value for a [!UICONTROL DIL] instance.

**샘플 코드**

<pre class="java"><code>var value = dil. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>);</code>
</pre>
