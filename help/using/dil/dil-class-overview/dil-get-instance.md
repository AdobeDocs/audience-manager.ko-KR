---
description: 파트너별 DIL 인스턴스를 검색합니다.
keywords: audience manager api;aam api;audience manager api;aam api
seo-description: 파트너별 DIL 인스턴스를 검색합니다.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL 구현
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%

---

# getDil{#getdil}

파트너별 DIL 인스턴스를 검색합니다.

**함수 서명:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 매개 변수

| 이름 | 유형 | 설명 |
|---|---|---|
| `partner` | 문자열 | 검색할 파트너 이름입니다. |
| `containerNSID` | 정수 | 기본값은 `0`입니다. 검색하는 컨테이너의 NSID입니다. 선택 사항입니다. |

## 응답

성공적인 파트너 및 컨테이너 NSID 일치는 파트너별 [!UICONTROL DIL] 인스턴스를 반환합니다. 일치하는 항목이 없으면 API가 &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot; 메시지와 함께 오류를 반환(던지지 않음)합니다.

## 샘플 코드

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
