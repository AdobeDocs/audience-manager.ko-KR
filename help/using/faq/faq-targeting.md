---
description: 일반적인 타깃팅 관련 질문 및 문제
seo-description: 일반적인 타깃팅 관련 질문 및 문제
seo-title: 타깃팅 FAQ
solution: Audience Manager
title: 타깃팅 FAQ
uuid: EE 96 EF 71-B 903-4953-AFC 4-8 EC 8 E 48 BD 49 E
translation-type: tm+mt
source-git-commit: f9a12cf38833cf243edf4bc4c4f4e91f83ee0ca2

---


# Targeting FAQ{#targeting-faq}

일반적인 타깃팅 관련 질문 및 문제

<br> 

<!-- 

faq_targeting.xml

 -->

**Audience Manager에서 지원하는 타사 데이터 공급자의 전체 목록은 어디에서 찾을 수 있습니까?**

See the [Adobe Exchange Marketplace](https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) (https://marketing.adobe.com/resources/content/resources/en/exchange/marketplace/audience.html) for a complete list of third-party data providers that [!DNL Audience Manager] supports.

<br> 

**타사 데이터를 사용하여 사이트에서 본 적이 없는 사용자를 대상으로 Audience Manager 또는 DSP에서 타사 데이터를 사용해야 합니까?**

답변은 목표에 따라 다릅니다. 예를 들어, 캠페인이 제 3 자 데이터로 새 클라이언트를 찾도록 만들어진 다음, DSP를 사용하여 직접 작업하도록 설계되었습니다. Adobe Audience Manager는 사용자가 해당 사용자를 볼 때에만 데이터를 타사 데이터 공급자와 동기화합니다. 이전에 사용자를 본 적이 없는 경우 시스템에 해당 사이트 방문자에 대한 정보가 없습니다. 타사 데이터를 사용하여 속성을 방문한 적이 없는 사용자를 타깃팅한 캠페인의 경우 DSP를 통해 세그먼트를 만듭니다.

<br> 

**개인 사용자에게 마케팅할 수 있습니까?**

Audience Manager를 사용하면 공유된 특성 또는 트레이트에 따라 사용자를 집계하고 마케팅 팀에 마케팅을 할 수 있습니다. However, to comply with industry regulations, [!DNL Audience Manager] customers may not send personally identifiable information (PII) to our systems. 따라서 이메일 주소, 개별 이름, 실제 주소 등을 사용할 수 없습니다. 타깃팅을 위해.

<br> 

**데이터를 안전하게 재타깃팅하려면 어떻게 해야 합니까?**

선호하는 리타겟팅 플랫폼과 데이터를 교환하려면 서버 간 연결을 사용하는 것이 좋습니다. Audience Manager는 서버 간 연결을 통해 대부분의 주요 DSP와 데이터를 교환합니다. 서버 간 데이터 전송을 통해 다른 배우가 데이터를 가로채서 해당 고객 정보를 다시 판매하는 것을 방지할 수 있습니다.

<br> 

**Audience Manager 고유 사용자 ID (UUID) 가 페이지에서 직접 동기화함으로써 광고 서버의 고유 사용자 ID와 연결되어 있습니까?**

아니요. ID 동기화는 페이지에서 발행자 또는 서버에 대해 수행되지 않습니다. The Audience Manager UUID is inserted into the `u=` field of the ad server log files. 이것은 타깃팅을 위해 세그먼트가 전달된 경우 발생합니다. DIL 코드 모듈은 이 기능을 수행합니다. 이 메커니즘은 세그먼트 성능 보고를 위해 서버의 사용자 ID를 Audience Manager 사용자에게 매핑할 수 있도록 해주는 메커니즘입니다. 그러나 사이트에 광고 서버가 있는 경우에는 페이지에서 직접 ID를 동기화합니다.

<br> 

**Audience Manager는 다른 장치에서 로그인한 사용자를 하나의 고유 사용자 또는 다른 고유 사용자로 카운트합니까?**

[선언된 ID 타깃팅을](../features/declared-ids.md#declared-id-targeting) 통해 Audience Manager는 단일 고유 식별자를 사용하여 여러 장치에서 방문자를 식별할 수 있습니다. 하지만 타깃팅 또는 대상 관점에서 볼 때 DSP는 이러한 여러 ID를 조정할 수 없기 때문에 여전히 2 (또는 이상) 사용자입니다.

<br> 

**Audience Manager에서 디스플레이 및 모바일 장치에서 사용자를 식별할 수 있습니다.**

예. [선언된 ID 타게팅을 참조하십시오](../features/declared-ids.md#declared-id-targeting).

<br> 

**온라인으로 수집한 데이터를 사용하여 사용자를 점수를 매기고 이 모델 점수를 기반으로 재타깃팅할 수 있습니까?**

예. Audience Manager는 사용자를 점수 매기기 위해 데이터 파일을 제공할 수 있지만, 이 정보를 분석 및 평가하기 위해서는 다른 공급업체 또는 소프트웨어와 함께 작업해야 합니다. 이 데이터를 키-값 쌍의 형태로 Audience Manager로 보냅니다. 이러한 정보를 가져와 기존 사용자 프로파일에 추가할 수 있습니다. 이 과정을 검토하려면 파트너 솔루션 담당자에게 문의하십시오.

<br> 

**지정된 1 - 2 개월 동안 쿠키 삭제 비율은 얼마입니까?**

쿠키 삭제는 측정하기 어렵습니다. 대부분의 쿠키 삭제는 쿠키를 자주 삭제하는 소수의 방문자로부터 옵니다. 그러나 대부분의 브라우저 쿠키는 제한된 수명이 있더라도 최소 30 일 동안 안정적입니다. 일부 연구 조사에 따르면 30 일 이상인 상위 단계 타깃팅은 30 일 동안 브라우저 대상 대상의 7%를 효과적으로 제거할 것으로 나타났습니다. 아시다시피 해당 크리에이티브 메시지의 30 일 캠페인은 업계 표준입니다. 지금까지 본 바로는 7%의 하락이 정확하다는 것을 알 수 있습니다.

쿠키 삭제는 도달 및 빈도 계산에 역효과가 있습니다. 따라서 디스플레이 캠페인 계획에 대한 소비자 트렌드의 진정한 특성을 이해하려고 할 때 행동 데이터의 가치를 강조합니다. 클라이언트는 Adobe Audience Manager 세그먼트 겹침 보고서, 최적의 노출 빈도 보고서 및 특정 날짜 범위에 대한 고유한 사용자 트렌드를 활용하여 캠페인 계획 및 캠페인 실행을 위한 최적의 날짜 범위에 대해 사이언스 작업을 수행할 수 있습니다.

<br> 

**Audience Manager 쿠키의 만료 기간은 언제입니까?**

사용자 인터페이스를 통해 쿠키 만료 간격을 결정할 수 있습니다. You can set cookies to expire after *n* number of days or never.

<br> 

**이벤트 콜에서 캠페인 크리에이티브를 구현하면 더 많은 비용이 들까요?**

다릅니다. 비용은 고유 사용자를 기반으로 합니다. 캠페인이 순 신규 사용자로 표시되는 경우 예. 캠페인이 이미 데이터를 수집하고 있는 위치에 도달하면 추가 비용이 들지 않습니다. 캠페인이 상당한 겹치는 사이트에서 실행되는 경우, 신규 고유 사용자에게 표시되는 추가 비용이 발생합니다.

<br> 

**Audience Manager는[!UICONTROL Addressable Audiences]지표와[!UICONTROL Server-to-Server]대상에 대한 일치 비율을 표시합니다. Can you explain why we don't see these figures for Cookie and URL destinations?**

ID 동기화로 분류됩니다. For [!UICONTROL Server-to-Server] destinations, we transfer data offline (either real-time or batch) and we need to send the ID that the destination partner understands, so they can map it back to the browser. 세그먼트 어드레서블 숫자는 총 세그먼트 인구의 하위 집합입니다.

In the case of Cookie and URL destinations, the user is already on the browser, and what [!DNL Audience Manager] sends is just the segments that the user qualified for. 대상 파트너는 세그먼트 매핑을 선택하고 해당 정보를 사용할 수 있습니다. 따라서 쿠키 및 URL 대상에 대한 일치 비율은 항상 100% 고려하십시오.
