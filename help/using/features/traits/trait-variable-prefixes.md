---
description: 이 문서에서는 특성 규칙을 만들 때 키 변수에 연결해야 하는 접두사에 대해 설명합니다.
seo-description: 이 문서에서는 특성 규칙을 만들 때 키 변수에 연결해야 하는 접두사에 대해 설명합니다.
seo-title: 주요 변수의 접두사 요구 사항
solution: Audience Manager
title: 주요 변수의 접두사 요구 사항
uuid: df2ef9c8-606a-45f9-a836-859f856a7d4b
translation-type: tm+mt
source-git-commit: 2206b5e40f7024084953fed52bb02fcc46ea36f1

---


# 주요 변수의 접두사 요구 사항 {#prefix-requirements-for-key-variables}

이 문서에서는 특성 규칙을 만들 때 키 변수에 연결해야 하는 접두사에 대해 설명합니다.

<!-- r_tb_variable_prefixes.xml -->

## 키 변수 접두사 목적

규칙을 만들 때 권장 접두사를 사용하여 키 변수의 서문을 작성해야 합니다. [!UICONTROL Trait Builder] 이러한 접두사는 전달된 데이터 유형을 식별하여 네임스페이스 충돌을 방지합니다 [!DNL Audience Manager]. 일반적으로 변수에 이름을 지정할 수 있지만, 키 변수 이름이 이벤트 호출의 변수 이름과 일치하지 않으면 규칙에 대한 데이터가 처리되지 않습니다.

## 키 변수의 접두사

다음 표는 에서 사용하는 일반적인 접두사를 정의합니다 [!UICONTROL Trait Builder].

<table id="table_CFEFA1DBDF904736B6EA2640B7AD26E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 키 변수 접두사 </th> 
   <th colname="col2" class="entry"> 변수 식별 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><code> c_</code> </td> 
   <td colname="col2"> <p>고객별 이 데이터는 자체 속성에서 전송된 주요 데이터입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> d_</code> </td> 
   <td colname="col2"> <p>Audience Manager <span class="keyword"> 수준에서</span> . 이 데이터는 Audience Manager 에코시스템에서 <span class="keyword"> 동일합니다</span> . 자세한 <a href="../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> 목록은 DCS API 호출에</a> 대해 지원되는 속성을 참조하십시오. <p>이 접두사를 사용하는 신호는 신호 검색에서 <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">표시되지 않습니다</a>.</p></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"><code> h_</code> </td> 
   <td colname="col2"> <p>여기에는 HTTP <a href="https://en.wikipedia.org/wiki/List_of_HTTP_header_fields" scope="external" format="html"> 헤더</a> 정보가 포함되어 있습니다. 헤더 매개 변수(예: <code> referer</code>,<code> IP</code><code> accept-language</code>, 등)를 포함합니다. </p> <p> <p>참고:9.0 이전 버전의 DIL을 사용하는 고객의 경우 <code> h_referer</code> 신호를 사용한 데이터 수집은 Safari 브라우저에서 작동하지 않습니다. ITP 2.0 <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> 이</a>도입되어 Safari 브라우저는 demdex.net 도메인을 추적기로 분류할 수 있으며 전체 URL이 아닌 원본을 포함하도록 데이터 수집 요청에서 레퍼러를 자를 자를 자를 자를 자를 자를 자를 자를 수도 있습니다. 최신 <a href="../../dil/dil-overview.md#get-implement-dil-code">DIL 버전에 대한 DIL 코드</a> 가져오기 및 구현을 참조하십시오.<p>이 접두사를 사용하는 신호는 신호 검색에서 <a href="../data-explorer/data-explorer-signals-search/data-explorer-signals-search.md">표시되지 않습니다</a>.</p></p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code> p_</code> </td> 
   <td colname="col2"> <p>데이터 수집 <span class="wintitle"> 서버를</span> 통해 개인 매개 변수를 전달할 수 있습니다. 기본적으로, 다음으로 시작하는 매개 변수는 특성 평가에 <code> p_</code> 사용되지만 다운스트림으로 기록되거나 저장되지 않습니다. </p> <p>예:이와 같은 트레이트가 <code> /event?p_age=23</code> 주어지면 <code> YoungPeople = p_age &lt; 25</code>트레이트가 실현되지만 <code> p_age=23</code> 키-값 쌍은 요청 후 삭제되며 기록되지 않습니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [기본 정보 개요](../../features/traits/create-onboarded-rule-based-traits.md)
>* [특성 규칙 관리](../../features/traits/manage-trait-rules.md#managing-trait-rules)

