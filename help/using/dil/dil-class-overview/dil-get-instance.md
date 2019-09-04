---
description: 파트너 특정 DIL 인스턴스를 검색합니다.
keywords: Audience Manager API; AAM API; Audience Manager API; AAM API
seo-description: 파트너 특정 DIL 인스턴스를 검색합니다.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Getdil{#getdil}

파트너 특정 DIL 인스턴스를 검색합니다.

**함수 서명:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 매개 변수

| 이름 | 유형 | 설명 |
|---|---|---|
| `partner` | 문자열 | 검색할 파트너 이름. |
| `containerNSID` | 정수 | 기본값은 `0`입니다. 검색할 컨테이너의 NSID 입니다. 선택 사항입니다. |

## 응답

성공적인 파트너 및 컨테이너 NSID 일치는 파트너 특정 [!UICONTROL DIL] 인스턴스를 반환합니다. 일치하는 항목이 없으면 API는 메시지와 함께 오류 메시지를 반환하지 않습니다. " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## 샘플 코드

<pre class="java"><code>dil. getdil ('<i>partner</i>', <i>containernsid</i>); 
dil. getdil ('<i>partner</i>');</code></pre>
