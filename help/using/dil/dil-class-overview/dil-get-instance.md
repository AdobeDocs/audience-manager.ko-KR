---
description: 파트너 특정 DIL 인스턴스를 검색합니다.
keywords: Audience Manager API; AAM API; Audience Manager API; AAM API
seo-description: 파트너 특정 DIL 인스턴스를 검색합니다.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

파트너 특정 DIL 인스턴스를 검색합니다.

**함수 서명:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 매개 변수

| 이름 | 유형 | 설명 |
|---|---|---|
| `partner` | 문자열 | 검색할 파트너 이름. |
| `containerNSID` | 정수 | Defaults is `0`. 검색할 컨테이너의 NSID 입니다. 선택 사항입니다. |

## 응답

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## 샘플 코드

<pre class="java"><code>dil. getdil ('<i>partner</i>', <i>containernsid</i>); 
dil. getdil ('<i>partner</i>');</code>
</pre>
