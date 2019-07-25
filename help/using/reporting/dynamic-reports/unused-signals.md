---
description: 이 보고서는 인벤토리에 수집된 후 Audience Manager로 보낸 모든 사용되지 않은 정보의 빈도를 반환합니다.
seo-description: 이 보고서는 인벤토리에 수집된 후 Audience Manager로 보낸 모든 사용되지 않은 정보의 빈도를 반환합니다.
seo-title: 사용되지 않는 신호 보고서
solution: Audience Manager
title: 사용되지 않는 신호 보고서
uuid: 04334 A 5 C -3 E 21-44 DB-B 971-0 B 4457685 E 9 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Unused Signals Report{#unused-signals-report}

이 보고서는 인벤토리에 수집된 후 Audience Manager로 보낸 모든 사용되지 않은 정보의 빈도를 반환합니다.

<!-- 

c_unused_signals.xml

 -->

## 사용되지 않는 신호 보고서

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

사용하지 않은 신호는 수집했지만 트레이트에 매핑되지 않은 데이터로 구성됩니다. [!UICONTROL Unused Signals] 보고서에는 날짜, 키, 값 및 빈도 수에 따른 표의 데이터가 표시됩니다. Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

이 보고서를 검토하여 새로운 트레이트나 기존 트레이트에 매핑할 수 있는 고아 신호를 식별할 수 있습니다.

>[!NOTE]
>
>검색 필드에 키 또는 값 이름을 지정하여 결과를 특정 레코드로 제한합니다.

## 사용 사례

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 예 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>특성 일관성을 유지하거나 관련 값을 하나의 키에 추가</b> </p> </td> 
   <td colname="col2"> <p>보고서를 검토하여 특정 신호에 대한 다양한 값 변형을 고려합니다. </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). 또는, 보고서를 사용하여 이름을 변형할 수 있고 모든 사이트에서 동일한 값으로 바꿀 수 있습니다. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>새로운 특성 만들기</b> </p> </td> 
   <td colname="col2"> <p>보고서를 검토하여 특정 키에 전달되는 새 값이 무엇인지 확인합니다. 새 값을 기준으로 새 키-값 쌍을 만들 수 있습니다. </p> <p> <p>참고: 자주 변경되는 값의 주별 보고서 (예: 표시, 캠페인, 연예인 등) 를 확인하십시오. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>매핑되지 않은 값 찾기</b> </p> </td> 
   <td colname="col2"> <p>숫자 1에 대한 보고서를 검토합니다. <span class="wintitle"> 사용하지 않은 신호</span> 보고서의 숫자 1는 null 값을 나타냅니다. 반드시 나쁜 것은 아닙니다. 이것은 특정 키에 연관된 값 매핑이 없음을 의미합니다. 중요한 변수에 대한 1 개의 값이 많이 표시되면 사이트 팀과 함께 모든 페이지에 태그가 올바르게 지정되어 있는지 확인합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 우수 사례

Run and check the [!UICONTROL Unused Signals] report:

* 트레이트를 만들거나 트레이트 규칙을 업데이트한 후 이를 통해 트레이트와 규칙이 올바르게 설정되어 있는지 확인할 수 있습니다. 결과의 숫자 1는 새 트레이트가 올바르게 구성되지 않을 수 있음을 나타냅니다.
* 매주 또는 매월. 예약된 검토를 통해 트레이트 매핑이 최신 상태로 유지되도록 할 수 있습니다.

>[!NOTE]
>
>보고서에서 사용하지 않은 값을 검색할 때는 다음 사항을 고려하십시오. 아래 두 예 간의 표현식에 차이가 있습니다.

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let's say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you'll only obtain results in the first case because values for key were not sent AT ALL. 두 번째 경우, 23 과는 다른 값이 전송되어 키 A가 사용되지 않습니다.

## 벌크 트레이트 생성

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
