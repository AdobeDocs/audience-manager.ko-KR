---
description: 파트너별 DIL 인스턴스를 검색합니다.
keywords: audience manager api;aam api;audience manager api;aam api
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
TQID: https://experienceleague.adobe.com/C4wUrtnwE8WXsgDzXSTJQ1qUf-aB-RNWoBDbDFCNeZ8
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2:
  - id: d7e573ad-4eda-46ec-90c4-239e75362af9
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 143
ht-degree: 6%

---

# getDil{#getdil}

>[!WARNING]
>
>2023년 7월부터 Adobe은 [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장 개발을 중단했습니다.
>
>기존 고객은 [!DNL DIL] 구현을 계속 사용할 수 있습니다. 그러나 Adobe은 이 시점 이후에는 [!DNL DIL]을(를) 개발하지 않습니다. 고객은 장기 데이터 수집 전략에 대해 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)을(를) 평가하는 것이 좋습니다.
>
>2023년 7월 이후에 새로운 데이터 수집 통합을 구현하려는 고객은 대신 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=ko)을 사용해야 합니다.

파트너별 DIL 인스턴스를 검색합니다.

**함수 서명:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## 매개변수

| 이름 | 유형 | 설명 |
|---|---|---|
| `partner` | 문자열 | 검색할 파트너 이름입니다. |
| `containerNSID` | 정수 | 기본값은 `0`입니다. 검색 중인 컨테이너의 NSID입니다. 선택 사항입니다. |

## 응답

성공적인 파트너 및 컨테이너 NSID 일치가 파트너 관련 [!UICONTROL DIL] 인스턴스를 반환합니다. 일치하는 항목이 없으면 API에서 &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot; 메시지와 함께 오류를 반환합니다(throw하지 않음).

## 샘플 코드

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
