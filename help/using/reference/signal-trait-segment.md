---
description: Audience Manager 세그먼트의 구성 요소, 대상 자격 기준을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.
seo-description: Audience Manager 세그먼트의 구성 요소, 대상 자격 기준을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.
seo-title: 신호, 트레이트 및 세그먼트
solution: Audience Manager
title: 신호, 트레이트 및 세그먼트
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 5%

---


# 신호, 트레이트 및 세그먼트{#signals-traits-and-segments}

세그먼트의 구성 요소, [!DNL Audience Manager] 대상 자격 기준을 설정하는 데 사용되는 표현식 및 이벤트 호출에서 데이터가 전송되는 방법을 설명합니다.

<!-- 

c_signal_trait_segment.xml

 -->

**구성 및 목적**

[!DNL Audience Manager] 데이터는 신호, 특성, 세그먼트 및 관련 자격 규칙으로 구성됩니다. 데이터 요소와 규칙이 결합하여 세그먼트를 만듭니다. 세그먼트는 사이트 방문자를 관련 그룹으로 구성합니다. 다음 표는 세그먼트에 있는 세 개의 주요 구성 요소를 [!DNL Audience Manager] 정의합니다.

<table id="table_E8373A01C3414C42B4983A59BF0F0669"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 요소 </th> 
   <th colname="col2" class="entry"> 구성 요소 </th> 
   <th colname="col3" class="entry"> 예 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>신호</b> </td> 
   <td colname="col2"> <p>Signals are the smallest data units in <span class="keyword"> Audience Manager</span> and are expressed as <a href="../reference/key-value-pairs-explained.md"> key-value pairs</a>. </p> 
    <ul id="ul_728347E325284B9FA0B4E05DE8CF4570"> 
     <li id="li_89574A3B4A734726AD43405AE6D85FF5">키는 데이터 세트(예: 성별, 색상, 가격)를 정의하는 상수입니다. </li> 
     <li id="li_D35601B33EE24EC5857F45D9577254D4">값은 상수와 관련된 변수입니다(예: 남성/여성, 녹색, 100). </li> 
    </ul> <p>비교 연산자는 키-값 쌍에 참여하고 그 사이의 관계를 설정합니다. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A6D8D30A37C94437A7BF38736C6F8556"> 
     <li id="li_74C87C34FA254783AC0DEBBC69B35AC4"><code> product=camera</code> </li> 
     <li id="li_C1727B9136024E56B60374597A7DCA00"><code> price&gt;1000</code> </li> 
     <li id="li_B2E7798768EE444AB978F3F27B0BC0B5"><code> type=digital SLR</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>트레이트</b> </td> 
   <td colname="col2"> <p>하나 이상의 신호 조합. </p> <p>부울 표현식과 비교 연산자를 사용하여 트레이트 자격 규칙을 만들 수 있습니다. </p> <p>트레이트와 트레이트 그룹을 조합하여 정확한 자격 요구 사항을 만들 수 있습니다. </p> </td> 
   <td colname="col3"> <p>사용 가능한 신호에서 "고급 카메라 브라우저" 규칙을 만들 수 있습니다. </p> <p><code> product=camera AND price&gt;1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>세그먼트</b> </td> 
   <td colname="col2"> <p>공통 속성 세트를 공유하고 관련 트레이트를 사용할 수 있는 사용자입니다. </p> <p>부울 표현식과 최근/빈도 요구 사항을 함께 사용하면 세그먼트 자격 규칙을 만들 수 있습니다. </p> <p>트레이트 및 세그먼트 규칙의 조합으로 정확한 자격 조건을 만들 수 있습니다. </p> </td> 
   <td colname="col3"> <p>사용 가능한 트레이트 및 신호에서 다음과 같이 표시되는 세그먼트 규칙을 만들 수 있습니다. </p> <p><code> (product=camera AND type=digital SLR) OR (price&gt;1000)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

아래 다이어그램을 사용하여 신호, 트레이트 및 세그먼트 간의 관계에 대한 mental 메모를 작성합니다.

![](assets/signals-traits-segments.png)

**시각적인 툴과 코드 편집기를 사용하여 트레이트 및 세그먼트 규칙 구축**

클라이언트는 사용자 인터페이스에서 시각적인 툴과 코드 편집기를 사용하여 트레이트와 세그먼트를 [!DNL Audience Manager] 관리합니다. 시각적인 도구를 사용하여 검색 기능, 팝업 옵션, 드롭다운 메뉴 및 드래그 앤 드롭 기능을 사용하여 규칙을 만들 수 있습니다. 코드 편집자는 고급 사용자에게 프로그래밍 방식으로 고객 세분화 기준을 개발할 수 있는 방법을 제공합니다.

**이벤트 호출 Audience Manager으로 데이터 보내기**

이벤트 호출은 웹 사이트의 데이터를 [!DNL Audience Manager] 호출에는 요청의 신호, 특성 및 세그먼트 데이터가 [!DNL HTTP] 포함됩니다. 이벤트 자체는 `/event` 문자열의 [!DNL URL] 부분 뒤에 오는 모든 것입니다. 아래 예에서 보듯이 이 프로세스에는 여러 변수를 전달할 단일 이벤트 호출만 필요합니다 [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [세그먼트: 목적, 구성 및 규칙](../features/segments/segments-purpose.md)

