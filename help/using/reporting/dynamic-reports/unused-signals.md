---
description: 이 보고서는 인벤토리에서 수집되고 Audience Manager로 전송된 모든 사용되지 않은 정보의 빈도 수를 반환합니다.
seo-description: 이 보고서는 인벤토리에서 수집되고 Audience Manager로 전송된 모든 사용되지 않은 정보의 빈도 수를 반환합니다.
seo-title: 미사용 신호 보고서
solution: Audience Manager
title: 미사용 신호 보고서
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# 미사용 신호 보고서{#unused-signals-report}

이 보고서는 인벤토리에서 수집되고 Audience Manager로 전송된 모든 사용되지 않은 정보의 빈도 수를 반환합니다.

<!-- 

c_unused_signals.xml

 -->

## 미사용 신호 보고서

신호는 [!DNL Audience Manager] 키-값 쌍 [(예:](../../reference/key-value-pairs-explained.md) `color=blue, price>100, gender=female`등)의 형태로 전달된 웹 사이트의 정보입니다.

사용하지 않은 신호는 수집하지만 트레이트에 매핑되지 않은 데이터로 구성됩니다. 이 [!UICONTROL Unused Signals] 보고서는 날짜, 키, 값 및 빈도 수 별로 표에 데이터를 보여줍니다. 하루에 100번 [!DNL Audience Manager] 이상 전달되는 매핑되지 않은 모든 신호는 보고서에 사용할 수 [!UICONTROL Unused Signals] 있습니다.

이 보고서를 검토하여 새로운 트레이트나 기존 트레이트에 매핑할 수 있는 고립된 신호를 식별합니다.

>[!NOTE]
>
>검색 필드에서 키 또는 값 이름을 지정하여 특정 레코드로 결과를 제한할 수 있습니다.

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
   <td colname="col1"> <p><b>트레이트 균일성 보장 또는 단일 키에 관련 값 추가</b> </p> </td> 
   <td colname="col2"> <p>보고서를 검토하여 특정 신호에 대한 다양한 값 변형을 고려합니다. </p> <p>예를 들어 키-값 쌍에 c_state = North Carolina로 정의된 "North Carolina" 상태에 대한 트레이트가 있다고 가정해 봅시다 <code></code>. 이 보고서는 이름 변형을 찾고 트레이트에 추가하는 데 도움이 될 수 있습니다(예: <code> c_state = North Carolina, NC, N.C., NCarolina</code>). 또는 이름 변형을 보고서와 별매하고 모든 사이트에서 동일한 값으로 바꿀 수 있습니다. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>새 트레이트 만들기</b> </p> </td> 
   <td colname="col2"> <p>보고서를 검토하여 특정 키에 전달된 새 값을 확인합니다. 이러한 새 값을 기반으로 새 키-값 쌍을 만들 수 있습니다. </p> <p> <p>참고: 주별 보고서에서 자주 변경되는 값(예: 표시, 캠페인, 연예인 등)을 확인합니다. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>매핑되지 않은 값 찾기</b> </p> </td> 
   <td colname="col2"> <p>1번 보고서를 검토합니다. 미사용 신호 보고서의 숫자 1 <span class="wintitle"> 은</span> null 값을 나타냅니다. 반드시 나쁜 것은 아니다. 즉, 특정 키에 연결된 값 매핑이 없습니다. 중요한 변수에 대한 값이 1개 많으면 사이트 팀에 문의하여 모든 페이지에 올바르게 태그가 지정되었는지 확인하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 우수 사례

보고서를 실행하고 확인합니다. [!UICONTROL Unused Signals]

* 트레이트 규칙을 만들거나 업데이트한 후 이렇게 하면 트레이트와 규칙이 제대로 설정되도록 할 수 있습니다. 결과 숫자 1은 새 트레이트가 올바르게 구성되지 않았을 수 있음을 나타냅니다.
* 주별 또는 월별 예약된 검토를 통해 트레이트 매핑이 최신 상태인지 확인할 수 있습니다.

>[!NOTE]
>
>보고서에서 사용되지 않는 값을 검색할 때 다음 특정 사항을 고려하십시오. 아래의 두 예 간에는 표현식에 차이가 있습니다.

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* 두 예제는 두 개의 키-값 쌍 v와 a를 포함하는 트레이트를 보여줍니다.첫 번째 표현식은 다음으로 변환됩니다.트레이트에는 값 1이 있는 키 v와 값이 23 [!UICONTROL AND NOT] 인 키 v가 포함되어 있습니다. 두 번째 표현식에는 값 1이 있는 키 v [!UICONTROL AND] 가 있고 키 a는 값 23이 [!UICONTROL NOT EQUAL] 있습니다.
* 위의 두 가지 다른 표현식을 고려할 때 키 a에서 전달된 값이 23이 아닌 값으로 검색될 경우 키 값이 AT ALL이 전송되지 않았기 때문에 첫 번째 [!UICONTROL Unused Signals Report] 사례에서만 결과를 얻는다고 가정해 보겠습니다. 두 번째 경우 23과 다른 값이 전송되어 키 a가 사용되지 않습니다.

## 벌크 트레이트 생성

보고서에서 얻은 데이터를 기반으로 많은 트레이트를 대량으로 만들어야 하는 경우 파트너 솔루션 담당자에게 문의하십시오. [!UICONTROL Unused Signals]
