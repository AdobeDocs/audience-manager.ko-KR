---
description: 이 문서에서는 트레이트 규칙을 만들 때 주요 변수에 첨부해야 하는 접두사를 설명합니다.
seo-description: 이 문서에서는 트레이트 규칙을 만들 때 주요 변수에 첨부해야 하는 접두사를 설명합니다.
seo-title: 주요 변수의 접두사 요구 사항
solution: Audience Manager
title: 주요 변수의 접두사 요구 사항
uuid: DF 2 EF 9 C 8-606 A -45 F 9-A 836-859 F 856 A 7 D 4 B
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Prefix Requirements for Key Variables {#prefix-requirements-for-key-variables}

이 문서에서는 트레이트 규칙을 만들 때 주요 변수에 첨부해야 하는 접두사를 설명합니다.

<!-- r_tb_variable_prefixes.xml -->

## 주요 변수 접두사의 목적

When you create [!UICONTROL Trait Builder] rules, it is important to preface the key variable with a recommended prefix. These prefixes identify the type of data passed in and help avoid namespace conflicts within [!DNL Audience Manager]. 일반적으로 변수를 변수에 지정할 수 있지만 키 변수 이름이 이벤트 호출의 변수 이름과 일치하지 않으면 규칙 데이터가 처리되지 않습니다.

## 주요 변수의 접두어

The following table defines the common prefixes used by [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 변수 접두사 </th> 
   <th colname="col2" class="entry"> 변수를 식별합니다. </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>고객별로 다릅니다. 이것은 고유한 속성에서 전송된 주요 데이터입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>At the <span class="keyword"> Audience Manager</span> level. This data is uniform across the <span class="keyword"> Audience Manager</span> ecosystem. See <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a> for a more complete list. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>That contains <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> HTTP header</a> information. <code> 레퍼러</code>,<code> IP</code>, <code> Accept-Language</code>등과 같은 헤더 매개 변수를 포함합니다. </p> <p> <p>Note: For customers using DIL versions older than 9.0, data collection using the <code> h_referer</code> signal will not work on Safari browsers. <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>이 도입되면 Safari 브라우저는 demdex. net 도메인을 추적기로 분류하고 데이터 수집 요청의 레퍼러를 전체 URL 대신 Origin만 포함하도록 잘릴 수 있습니다. See <a href="../../dil/dil-overview.md#get-implement-dil-code">Getting and Implementing DIL Code</a> for the latest DIL version.. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>Our <span class="wintitle"> Data Collection Servers</span> allow passing of private parameters. Basically, any parameter that starts with <code> p_</code> will be used for trait evaluation, but it will not be logged downstream, nor stored. </p> <p>Example: given <code> /event?p_age=23</code> and a trait like <code> YoungPeople = p_age &lt; 25</code>, the trait will be realized, but the <code> p_age=23</code> key-value pair will be dropped after the request and will not be logged. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [기본 정보 개요](../../features/traits/create-onboarded-rule-based-traits.md)
>* [특성 규칙 관리](../../features/traits/manage-trait-rules.md#managing-trait-rules)

