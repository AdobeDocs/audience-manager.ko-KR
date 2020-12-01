---
description: 일반적인 보고 관련 질문 및 문제
seo-description: 일반적인 보고 관련 질문 및 문제
seo-title: 보고 FAQ
solution: Audience Manager
title: 보고 FAQ
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 100%

---


# 보고 FAQ{#reporting-faq}

일반적인 보고 관련 질문 및 문제

<br> 

<!-- 

faq_reports.xml

 -->

**새로운 온보딩 트레이트의 경우, 왜 [!UICONTROL Trait Graph]가 가끔씩 예상 수치나 0보다 낮게 표시됩니까?**

경우에 따라 트레이트를 업로드하면 [!UICONTROL Trait Graph]에 결과가 표시되지 않거나 예상 수치보다 낮은 결과가 표시됩니다. 이런 일은 우리가 받는 데이터의 양이 너무 커서 인바운드 처리 작업이 해당 날짜에 대한 보고 최종 기한 이후까지 이 정보의 섭취를 완료할 수 없을 때 발생합니다.

그 결과 이 데이터는 보고 시스템에 늦게 보내지고 [!UICONTROL Trait Graph] 플로팅에 사용되는 1일 보고 간격에 나타나지 않습니다. 하지만 이 데이터는 다음 날 [트렌드](../reporting/trend-reports.md#trend-report-overview) 또는 [일반 보고서](../reporting/general-reports.md#general-reports-overview)에서 7일, 14일, 30일 및 60일 보고서 간격으로 볼 수 있습니다.

<br> 

**일부 세그먼트가 [!UICONTROL Overlap] 보고서에서 누락되었습니다. 해당 세그먼트는 어디 있습니까?**

컴퓨터 부담을 줄이기 위해 이 보고서에서는 통계적으로 중요하지 않은 데이터를 결과에서 생략합니다. 해당 세그먼트는 누락되지 않았고 의미 있는 결과나 타겟팅할 수 있는 유용한 사용자 풀을 내놓지 않기 때문에 뺐을 뿐입니다. 다음을 참조하십시오.

* [보고서 및 데이터 샘플링 방법론](../reporting/report-sampling.md)
* [Overlap Reports 및 일반 보고서의 고유 사용자 수 계산](../reporting/unique-user-counts.md)

<br> 

**이메일 마케팅 캠페인을 실행하는 경우 리디렉션된 사용자가 해당 캠페인이나 다른 소스에서 내 사이트로 오는지 어떻게 판단할 수 있습니까?**

모니터링하려는 사이트 섹션의 URL에 캠페인 관련 쿼리 문자열을 추가하십시오. 그런 다음 이 변수를 캡처하도록 트레이트 규칙을 설정합니다. 예를 들어 URL이 `www.test123.com/electronics?campaign=123`과 같이 캠페인 ID를 전달한다면 `h_referer = 'campaign=123'`과 같은 헤더를 찾는 트레이트 규칙이 있는 `h_referer` 변수에서 해당 데이터를 캡처합니다.

<br> 

**실시간 및 총 세그먼트 인구수 간의 차이는 무엇입니까?**

* **실시간:** 일정 시간 동안 세그먼트의 일부이면서 귀하의 자산에서 활성 상태인(즉, [!DNL Audience Manager]가 특정 시간 동안 해당 사용자에 대해 활동을 기록해야 함) 고유 사용자의 수입니다.

* **총 세그먼트 인구:** 해당 세그먼트에서 현재 분류된 모든 사용자의 집계입니다.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**한 가지 트레이트만으로 구성된 세그먼트가 있습니다. 보고 지표를 보면 보고서 카운트가 일치하지 않습니다. 이유가 무엇입니까?**

[세그먼트 빌더의 트레이트 및 세그먼트 인구 데이터](../features/segments/segment-builder-data.md)를 참조하십시오.

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**파일 하나를 인바운드하고 인바운드 수령증을 보면 성공적으로 처리된 레코드 수가 많지만 보고에 따르면 숫자가 훨씬 적습니다. 왜 그런 것입니까?**

백엔드에서, 온보딩된 데이터는 AAM에서 여전히 활성 상태인 사용자에게만 첨부됩니다(사용자에게 지난 120일 동안 최근 [!DNL DCS] 활동이 있어야 함). 따라서 [!DNL Audience Manager]에서 이미 만료된 사용자에 대해 데이터를 온보딩하는 경우 [!UICONTROL Inbound]를 통해 특정 수의 사용자 레코드가 온보딩되었음을 알 수 있지만 이러한 사용자에게 최근 활동이 없을 경우 이 데이터는 [!UICONTROL User Profile Store]에 도달하면 삭제되고 보고에 그 내용이 표시됩니다.

<br> 

**내 교차 장치 온보딩된 트레이트의 트레이트 고유성이 총 온보드 레코드 수보다 훨씬 큰 이유는 무엇입니까?**

고객 ID를 키로 사용하는 교차 장치 데이터 공급자의 파일을 온보딩하는 경우 Audience Manager는 조회를 수행하여 온보딩된 각 고객 ID와 관련된 모든 장치 ID를 가져옵니다. 그런 다음 Audience Manager는 고객 ID와 관련된 장치 ID에 온보딩된 트레이트를 지정합니다.

예를 들어 100개의 레코드를 온보딩했다고 가정합니다. AAM은 이러한 각 고객 ID에 대해 평균적으로 3개의 장치 ID를 연결했습니다. 그 결과 온보딩된 트레이트가 300개 장치 ID에 지정됩니다.

단일 교차 장치 고객 ID를 여러 장치 ID와 연결할 수 있는 이유는 두 가지가 있습니다.

* 사용자가 여러 컴퓨터/브라우저에서 동일한 교차 장치 계정에 로그인하고 있습니다.
* 사용자가 쿠키를 지우고 있습니다. 참고로, &quot;포기&quot; 쿠키는 사용자가 120일 동안 활동하지 않으면 삭제됩니다.

<br> 

**온보딩된 트레이트에 대해 [!UICONTROL Total Trait Realizations]이 왜 항상 0입니까?**

[!UICONTROL Total Trait Realizations]은 페이지 로드에 해당합니다. [!UICONTROL Total Trait Realizations]은 특정 트레이트가 실시간으로 실행된 횟수를 제공합니다. 이 숫자는 규칙 기반 트레이트에 대해서만 계산됩니다. 온보딩된 트레이트는 항상 [!UICONTROL Total Trait Realizations]을 0으로 표시됩니다.

<br> 

**트레이트 하나를 만들었는데 [!UICONTROL Trait Graph]에 [!UICONTROL Total Trait Population]보다 더 많은 [!UICONTROL Unique Trait Realizations]이 표시됩니다. 이것이 정상입니까?**

[!UICONTROL Unique Trait Realizations]이 실시간 지표라서 이렇게 표시되고 있지만, [!UICONTROL Total Trait Population]를 계산하기 위해 수행하는 보고 작업은 실시간이 아닙니다. [!UICONTROL Total Trait Population]는 이틀 정도 있어야 [!UICONTROL Unique Trait Realizations]보다 커지게 됩니다.
