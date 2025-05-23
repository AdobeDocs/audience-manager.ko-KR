---
description: 이 보고서는 인벤토리에서 수집되어 Audience Manager으로 전송된 사용되지 않은 모든 정보의 빈도 수를 반환합니다.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: 사용되지 않은 신호 보고서
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# 사용되지 않은 신호 보고서{#unused-signals-report}

이 보고서는 인벤토리에서 수집되어 Audience Manager으로 전송된 사용되지 않은 모든 정보의 빈도 수를 반환합니다. 이 보고서에 액세스하려면 **분석 > 대상 보고서 > 기타 보고서 > 사용되지 않은 신호**&#x200B;로 이동합니다.

>[!NOTE]
>
>&quot;대상 보고서에 대한 액세스 권한이 없습니다&quot;라는 메시지가 표시되면 Audience Manager 컨설턴트나 고객 지원에 연락하여 보고서를 프로비저닝하십시오.

![사용되지 않은 신호 보고서의 스크린샷](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## 개요

신호는 [키-값 쌍](../../reference/key-value-pairs-explained.md)(예: `color=blue, price>100, gender=female` 등)의 형태로 [!DNL Audience Manager]에 전달된 웹 사이트의 정보입니다.

사용되지 않은 신호는 수집하지만 트레이트에 매핑되지 않은 데이터로 구성됩니다. [!UICONTROL Unused Signals] 보고서는 날짜, 키, 값 및 빈도 수를 기준으로 표에 있는 데이터를 표시합니다. 하루에 100번 이상 [!DNL Audience Manager]에 전달된 매핑되지 않은 신호는 [!UICONTROL Unused Signals] 보고서에 사용할 수 있습니다.

사용되지 않은 신호는 45일 동안 저장된 후 폐기됩니다. 사용되지 않은 신호 보고서에는 지난 10일 동안의 데이터가 표시됩니다.

이 보고서를 검토하여 새 특성 또는 기존 특성에 매핑할 수 있는 분리된 신호를 식별하십시오.

>[!NOTE]
>
>검색 필드에 키 또는 값 이름을 지정하여 결과를 특정 레코드로 제한합니다.

## 사용 사례

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 예시 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>특성 일관성을 확인하거나 관련 값을 단일 키에 추가</b> </p> </td> 
   <td colname="col2"> <p>보고서를 검토하여 특정 신호에 대한 다양한 값 변형을 고려하십시오. </p> <p>예를 들어 키-값 쌍에 <code> c_state = North Carolina</code>(으)로 정의된 "North Carolina" 주에 대한 트레이트가 있다고 가정해 보겠습니다. 이 보고서를 통해 이름 변형을 찾아 트레이트(예: <code> c_state = North Carolina, NC, N.C., NCarolina</code>)에 추가할 수 있습니다. 또는 이름 변형을 보고서로 찾아 모든 사이트에서 동일한 값으로 바꿀 수 있습니다. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>새 특성 만들기</b> </p> </td> 
   <td colname="col2"> <p>보고서를 검토하여 특정 키에 어떤 새 값이 전달되는지 확인하십시오. 이러한 새 값을 기반으로 새 키-값 쌍을 만들 수 있습니다. </p> <p> <p>참고: 격주로 보고서를 확인하여 자주 변경되는 값(예: 쇼, 캠페인, 유명 인사 등)을 확인하십시오. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>매핑되지 않은 값 찾기</b> </p> </td> 
   <td colname="col2"> <p>1번에 대한 보고서를 검토하십시오. <span class="wintitle">개의 미사용 신호</span> 보고서의 숫자 1은 null 값을 나타냅니다. 꼭 나쁜 것만은 아니다. 이는 단순히 특정 키에 연관된 값 매핑이 없음을 의미합니다. 중요한 변수에 대해 1개의 값이 많이 표시되면 사이트 팀에 확인하여 모든 페이지에 올바르게 태그가 지정되었는지 확인하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

## 우수 사례

[!UICONTROL Unused Signals] 보고서 실행 및 확인:

* 트레이트를 만들거나 트레이트 규칙을 업데이트한 후. 이렇게 하면 트레이트와 규칙이 제대로 설정되었는지 확인할 수 있습니다. 결과의 숫자 1은 새 트레이트가 올바르게 구성되지 않았을 수 있음을 나타냅니다.
* 격주 또는 월별 예약된 검토는 트레이트 매핑이 최신 상태인지 확인하는 데 도움이 됩니다.

>[!NOTE]
>
>보고서에서 사용하지 않은 값을 검색할 때 다음 특수성을 고려하십시오. 아래 두 예제 사이에는 표현식에 차이가 있습니다.

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* 두 예제 모두 두 개의 키-값 쌍 v와 a가 포함된 트레이트를 보여 줍니다. 첫 번째 표현식은 로 해석됩니다. 트레이트에 값 1이 있는 키 v [!UICONTROL AND NOT]이(가) 있고 키 a에 값 23이 있습니다. 두 번째 식에 값 1이 [!UICONTROL AND]인 키 v와 값 [!UICONTROL NOT EQUAL]이(가) 23인 키 a가 있습니다.
* 위의 두 가지 다른 표현식을 고려하여 23이 아닌 값을 가진 키 a에 전달되는 값을 [!UICONTROL Unused Signals Report]에서 검색한다고 가정해 보겠습니다. 키에 대한 값이 전혀 전송되지 않았기 때문에 첫 번째 경우에만 결과가 나옵니다. 두 번째 경우는 23과 다른 값이 전송되었기 때문에 a 키는 사용되지 않습니다.

## 벌크 트레이트 만들기

[!UICONTROL Unused Signals] 보고서에서 얻은 데이터를 기반으로 많은 특성을 대량으로 만들어야 하는 경우 파트너 솔루션 담당자에게 문의하십시오.
