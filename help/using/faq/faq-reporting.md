---
description: 일반적인 보고 관련 질문 및 문제
seo-description: 일반적인 보고 관련 질문 및 문제
seo-title: 보고 FAQ
solution: Audience Manager
title: 보고 FAQ
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 보고 FAQ{#reporting-faq}

일반적인 보고 관련 질문 및 문제

<br> 

<!-- 

faq_reports.xml

 -->

**새로운 온보드 트레이트의 경우, 왜[!UICONTROL Trait Graph]가끔씩 예상 수치나 0보다 낮게 표시됩니까?**

경우에 따라 트레이트를 업로드한 후에는 결과가 표시되지 [!UICONTROL Trait Graph] 않거나 예상 수치보다 낮은 결과가 표시됩니다. 이는 우리가 받는 데이터 볼륨이 너무 커서 해당 날짜에 대한 보고 마감일 이후까지 인바운드 처리 작업이 이 정보 인제스트를 완료할 수 없을 때 발생합니다.

따라서 이 데이터는 보고 시스템으로 늦게 보내지며 이 데이터를 플로팅하는 데 사용되는 1일 보고 간격에 표시되지 않습니다 [!UICONTROL Trait Graph]. 그러나 이 데이터는 7일, 14일, 30일 및 60일 보고서 간격으로 다음 날 트렌드 [또는](../reporting/trend-reports.md#trend-report-overview) 일반 [보고서에서](../reporting/general-reports.md#general-reports-overview) 볼수있습니다.

<br> 

**일부 세그먼트가[!UICONTROL Overlap]보고서에서 누락되었습니다. 어디 있어?**

계산 수요를 줄이기 위해 이러한 보고서는 통계적으로 중요하지 않은 데이터를 결과에서 생략합니다. 세그먼트가 누락되지 않고 의미 있는 결과나 타깃팅할 수 있는 유용한 사용자 풀을 제공하지 않기 때문에 삭제됩니다. 다음을 참조하십시오.

* [보고서 및 데이터 샘플링 방법론](../reporting/report-sampling.md)
* [겹치기 및 일반 보고서에서 고유 사용자 수](../reporting/unique-user-counts.md).

<br> 

**이메일 마케팅 캠페인을 실행하는 경우 리디렉션된 사용자가 해당 캠페인이나 다른 소스에서 내 사이트로 오는지 어떻게 확인할 수 있습니까?**

모니터링할 사이트 섹션의 URL에 캠페인별 쿼리 문자열을 추가합니다. 다음으로 이 변수를 캡처하려면 트레이트 규칙을 설정합니다. 예를 들어 URL이 이와 같은 캠페인 ID로 전달되면 `www.test123.com/electronics?campaign=123`트레이트 규칙을 만들어 헤더와 같은 헤더를 찾는 트레이트 규칙을 사용하여 `h_referer` 변수에서 해당 데이터를 캡처합니다 `h_referer = 'campaign=123'`.

<br> 

**실시간 및 총 세그먼트 인구 수의 차이는 무엇입니까?**

* **** 실시간:일정 기간 동안 속성에 대해 활성화된 세그먼트의 고유 사용자 수(즉, 특정 기간 동안 해당 사용자에 대한 활동을 기록해야 [!DNL Audience Manager] 함).

* **** 총 세그먼트 모집단:해당 세그먼트에서 현재 분류된 모든 사용자의 집합입니다.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**하나의 트레이트로 구성된 세그먼트가 있습니다. 보고 지표를 볼 때 해당 카운트가 일치하지 않습니다. 이유가 무엇입니까?**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**I Inbound a file and my Inbound receipt shows a high number of successfully processed records, but reporting shows shows much lower number. 왜 그런 것입니까?**

백엔드에서 온보드 데이터는 AAM에서 여전히 활성 상태인 사용자에게만 첨부됩니다(사용자가 지난 120일 동안 최근 [!UICONTROL DCS] 활동을 가졌어야 함). 따라서 에 이미 만료된 사용자에 대해 데이터를 [!DNL Audience Manager]온보드 관리하는 경우 특정 수의 사용자 레코드가 온보드 상태임을 [!UICONTROL Inbound] 알 수 있지만 해당 사용자가 최근 활동을 하지 않은 경우 데이터가 Adobe에 도달하면 데이터가 삭제되고 [!UICONTROL User Profile Store] 보고서가 표시됩니다.

<br> 

**크로스 디바이스 온보드 트레이트가 전체 온보딩 레코드 수보다 훨씬 높은 이유는 무엇입니까?**

고객 ID에서 키잉된 크로스 디바이스 데이터 공급자에 대한 파일을 전송하는 경우 Audience Manager는 조회를 수행하여 각 온보드 고객 ID와 연결된 모든 장치 ID를 가져옵니다. 그런 다음 Audience Manager는 고객 ID와 연결된 장치 ID에 온보드 트레이트를 할당합니다.

예를 들어 100개의 레코드를 업로드했다고 가정합니다. 이러한 고객 ID에 대해 AAM은 평균적으로 세 개의 장치 ID를 연결했습니다. 그 결과 온보드 트레이트는 300개의 장치 ID에 할당됩니다.

단일 크로스 장치 고객 ID가 여러 장치 ID와 연결될 수 있는 이유는 다음과 같습니다.

* 사용자가 여러 컴퓨터/브라우저에서 동일한 크로스 디바이스 계정에 로그인하고 있습니다.
* 사용자가 쿠키를 지우고 있습니다. 참고:"포기" 쿠키는 120일 동안 사용자 활동이 없는 경우 삭제됩니다.

<br> 

**왜 내[!UICONTROL Total Trait Realizations]모습이 항상 0인 트레이트가 있을까?**

[!UICONTROL Total Trait Realizations] 페이지 로드에 해당합니다. [!UICONTROL Total Trait Realizations] 특정 트레이트가 실시간으로 발생한 횟수를 제공합니다. 이 숫자는 규칙 기반 트레이트에 대해서만 계산됩니다. 온보드 트레이트는 항상 [!UICONTROL Total Trait Realizations] 0으로 표시됩니다.

<br> 

**제가 트레이트를 만들었는데[!UICONTROL Trait Graph]그 수가 그[!UICONTROL Unique Trait Realizations]것보다 더 많이[!UICONTROL Total Trait Population]나오네요. 정상인가요?**

이것은 실시간 지표이므로 [!UICONTROL Unique Trait Realizations] 표시되지만, 계산하기 위해 수행하는 보고 작업은 [!UICONTROL Total Trait Population] 실시간이 아닙니다. 그것은 [!UICONTROL Total Trait Population] 며칠 내에 그것보다 [!UICONTROL Unique Trait Realizations] 클 것이다.
