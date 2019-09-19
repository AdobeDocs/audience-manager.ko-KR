---
description: 파트너별 DIL 인스턴스를 검색합니다.
keywords: audience manager api;aam api;audience manager api;aam apis
seo-description: 파트너별 DIL 인스턴스를 검색합니다.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

파트너별 DIL 인스턴스를 검색합니다.

**** 함수 서명: `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 매개 변수

| 이름 | 유형 | 설명 |
|---|---|---|
| `partner` | 문자열 | 검색할 파트너 이름입니다. |
| `containerNSID` | 정수 | 기본값은 `0`입니다. 검색할 컨테이너의 NSID입니다. 선택 사항입니다. |

## 응답

성공적인 파트너 및 컨테이너 NSID 검색은 파트너별 [!UICONTROL DIL] 인스턴스를 반환합니다. 일치하는 항목이 없으면 API에서 " `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## 샘플 코드

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>);
DIL.getDil('<i>partner</i>');</code></pre>
