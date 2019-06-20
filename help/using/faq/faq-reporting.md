---
description: 일반적인 보고 관련 질문 및 문제
seo-description: 일반적인 보고 관련 질문 및 문제
seo-title: 보고 FAQ
solution: Audience Manager
title: 보고 FAQ
uuid: 78 CD 6 C 86-8 A 4 A -4748-AB 71-B 6 E 8 D 6078 C 94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 보고 FAQ{#reporting-faq}

일반적인 보고 관련 질문 및 문제

<br> 

<!-- 

faq_reports.xml

 -->

**새로운 온보드 트레이트에 대해[!UICONTROL Trait Graph]종종 예상보다 낮은 숫자 또는 0 이 표시되는 이유는 무엇입니까?**

Sometimes, after you upload traits, the [!UICONTROL Trait Graph] doesn&#39;t show any results or shows lower than expected numbers. 받는 데이터의 볼륨이 너무 많아서 인바운드 처리 작업에서 해당 날짜에 대한 보고 마감 시간까지 이 정보를 인제스트할 수 없는 문제가 해결되었습니다.

As a result, this data is sent to the reporting system late and won&#39;t show up in the 1-day reporting interval which is used for plotting the [!UICONTROL Trait Graph]. However, you can view this data in the 7, 14, 30, and 60-day report intervals in a [Trend](../reporting/trend-reports.md#trend-report-overview) or [General Report](../reporting/general-reports.md#general-reports-overview) on the following day.

<br> 

**일부 세그먼트가[!UICONTROL Overlap]보고서에서 누락되었습니다. Where are they?**

계산 수요를 줄이기 위해 이러한 보고서는 결과에서 통계적으로 중요하지 않은 데이터를 생략합니다. 세그먼트는 누락되지 않으며, 의미 있는 결과 또는 타깃팅할 수 있는 유용한 사용자 풀을 양보하지 않기 때문에 누락됩니다. 다음을 참조하십시오.

* [보고서 및 데이터 샘플링 방법](../reporting/report-sampling.md)
* [겹침 및 일반 보고서에서](../reporting/unique-user-counts.md)고유 사용자 카운트

<br> 

**이메일 마케팅 캠페인을 실행하는 경우 리디렉션된 사용자가 해당 캠페인 또는 다른 소스에서 내 사이트로 이동하는지 어떻게 확인할 수 있습니까?**

모니터링할 사이트 섹션의 URL에 캠페인 관련 쿼리 문자열을 추가합니다. 그런 다음 이 변수를 캡처하기 위해 트레이트 규칙을 설정합니다. For example, if your URL passes in a campaign ID like this, `www.test123.com/electronics?campaign=123`, then create a trait rule to capture that data from the `h_referer` variable with a trait rule that looks for a header like `h_referer = 'campaign=123'`).

<br> 

**실시간 세그먼트와 총 세그먼트 인구의 차이점은 무엇입니까?**

* **실시간:** 설정 기간 동안 세그먼트에 속하고 속성에 활성 상태인 고유한 사용자의 수입니다 (예를 들어 특정 기간 동안 해당 사용자에 대해 기록된 활동이 [!DNL Audience Manager] 있어야 함).

* **총 세그먼트 모집수:** 해당 세그먼트에서 현재 분류되어 있는 모든 사용자의 집계입니다.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**하나의 트레이트로 구성된 세그먼트가 있습니다. 보고 지표를 보면 해당 수치가 일치하지 않습니다. 이유가 무엇입니까?**

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

**i inbound a file and my inbound receipt shows a file of successfully processed records, but reporting shows much lower numbers. 왜 그런 것입니까?**

In the backend, onboarded data gets attached only to users that are still active in AAM (user must have had recent [!UICONTROL DCS] activity in the past 120 days). Therefore, if you onboard data for users that have already expired in [!DNL Audience Manager], [!UICONTROL Inbound] might tell you that a certain number of user records were onboarded, but if these users have not had any recent activity, this data is dropped when it reaches our [!UICONTROL User Profile Store] and reporting will surface that.

<br> 

**크로스 디바이스 온보드 트레이트에 대한 트레이트 고유 수가 온보드 레코드의 총 개수보다 훨씬 높은 이유는 무엇입니까?**

고객 ID를 벗어나는 장치 간 데이터 공급자에 대한 파일을 등록한 경우 Audience Manager는 조회를 수행하여 온보딩된 고객 ID와 연관된 모든 장치 ID를 가져옵니다. 그러면 Audience Manager가 고객 ID와 연결된 장치 ID에 온보드 트레이트를 할당합니다.

예를 들어 100 개의 레코드가 온보드 상태라고 가정합니다. 평균적으로 이러한 고객 ID의 경우 AAM 에는 3 개의 장치 ID가 연결되어 있습니다. 따라서 온보드 트레이트가 300 개의 장치 ID에 할당됩니다.

단일 크로스 디바이스 고객 ID를 여러 장치 ID와 연결할 수 있는 이유는 두 가지가 있습니다.

* 사용자가 여러 컴퓨터/브라우저에서 동일한 장치 간 계정에 로그인하고 있습니다.
* 사용자가 쿠키를 지우고 있습니다. 참고: «포기됨» 쿠키는 사용자가 비활성화 후 120 일 후에 삭제됩니다.

<br> 

**항상 0로 된 특성에[!UICONTROL Total Trait Realizations]나타나는 이유는 무엇입니까?**

[!UICONTROL Total Trait Realizations] 페이지에 해당합니다. [!UICONTROL Total Trait Realizations] 특정 트레이트가 실시간으로 실행된 횟수를 제공합니다. 이 숫자는 규칙 기반의 트레이트 전용으로 계산됩니다. Onboarded traits always show [!UICONTROL Total Trait Realizations] as 0.

<br> 

**트레이트를 만들고에[!UICONTROL Trait Graph]보다 많은[!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population]수가 표시됩니다. Is this normal?**

You are seeing this because the [!UICONTROL Unique Trait Realizations] are real-time metrics, but the reporting jobs we do to calculate the [!UICONTROL Total Trait Population] are not real-time. [!UICONTROL Total Trait Population][!UICONTROL Unique Trait Realizations] 는 이틀 이내여야 합니다.
