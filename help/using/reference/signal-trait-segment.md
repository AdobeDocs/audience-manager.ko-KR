---
description: Audience Manager 세그먼트의 구성 요소, 대상자 자격 조건을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.
seo-description: Audience Manager 세그먼트의 구성 요소, 대상자 자격 조건을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.
seo-title: 신호, 트레이트 및 세그먼트
solution: Audience Manager
title: 신호, 트레이트 및 세그먼트
uuid: 485 FCC 5 C-B 289-463 B-A 610-0 D 727 DF 90 F 3 C
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signals, Traits, and Segments{#signals-traits-and-segments}

Audience Manager 세그먼트의 구성 요소, 대상자 자격 조건을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.

<!-- 

c_signal_trait_segment.xml

 -->

**컴포지션 및 목적**

[!DNL Audience Manager] 데이터는 신호, 특성, 세그먼트 및 관련 자격 규칙으로 구성됩니다. 데이터 요소와 규칙이 결합하여 세그먼트를 만듭니다. 세그먼트는 사이트 방문자를 관련 그룹으로 구성합니다. The following table defines the three principal components in an [!DNL Audience Manager] segment.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 요소 </th> 
   <th colname="col2" class="entry"> 다음으로 구성 </th> 
   <th colname="col3" class="entry"> 예 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>신호</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">키는 데이터 세트를 정의하는 상수 (예: 성별, 색상, 가격) 입니다. </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">이 값은 상수 관련 변수 (예: 남성/여성, 녹색, 100) 입니다. </li> 
    </ul> <p>비교 연산자는 키-값 쌍에 참여하고 이러한 쌍 간의 관계를 설정합니다. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product = camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> 가격 &gt; 1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type = Digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>특성</b> </td> 
   <td colname="col2"> <p>하나 이상의 신호 조합. </p> <p>부울 표현식 및 비교 연산자를 사용하여 트레이트 자격 조건을 만들 수 있습니다. </p> <p>트레이트와 트레이트 그룹의 조합을 통해 정확한 자격 조건을 만들 수 있습니다. </p> </td> 
   <td colname="col3"> <p>사용 가능한 신호에서 다음과 같이 표현된 "고급 카메라 브라우저" 규칙을 만들 수 있습니다. </p> <p><code> 제품 = 카메라 및 가격 &gt; 1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>세그먼트</b> </td> 
   <td colname="col2"> <p>공통 속성 세트를 공유하고 관련 트레이트를 적용받을 수 있는 사용자 </p> <p>최근/빈도 요구 사항과 함께 부울 표현식을 사용하여 세그먼트 자격 조건을 만들 수 있습니다. </p> <p>특성 및 세그먼트 규칙의 조합을 통해 정확한 자격 조건을 만들 수 있습니다. </p> </td> 
   <td colname="col3"> <p>사용 가능한 트레이트와 신호에서 다음과 같이 표현된 세그먼트 규칙을 만들 수 있습니다. </p> <p><code> (product = Camera and Type = Digital SLR) OR (price &gt; 1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

아래 다이어그램을 사용하여 신호, 특성 및 세그먼트 간의 관계를 명확하게 메모해 두십시오.

![](assets/signals-traits-segments.png)

**시각적 툴과 코드 편집기를 사용하여 트레이트와 세그먼트 규칙 제작**

Clients manage traits and segments with visual tools and code editors in the [!DNL Audience Manager] user interface. 시각적 도구를 사용하면 검색 기능, 팝업 옵션, 드롭다운 메뉴 및 드래그 앤 드롭 기능을 사용하여 규칙을 만들 수 있습니다. 코드 편집기는 고급 사용자에게 프로그래밍 방식으로 대상 세그멘테이션 기준을 개발할 수 있는 방법을 제공합니다.

**이벤트 호출 데이터를 Audience Manager로 보내기**

An event call sends data from your website to [!DNL Audience Manager]. 호출에는 HTTP 요청에서 신호, 특성 및 세그먼트 데이터가 포함됩니다. The event itself is everything after the `/event` part of a URL string. As shown in the example below, this process requires only a single event call to pass in multiple variables to [!DNL Audience Manager].

```
https://<domain>/event?product=camera&price>100
```

>[!MORE_ like_ this]
>
>* [세그먼트: 목적, 컴포지션 및 규칙](../features/segments/segments-purpose.md)

