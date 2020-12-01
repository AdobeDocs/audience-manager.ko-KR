---
description: 이 문서에서는 Audience Manager 특성 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Manager 특성 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.
seo-title: 트레이트 및 세그먼트 빌더의 부울 표현식
solution: Audience Manager
title: 트레이트 및 세그먼트 빌더의 부울 표현식
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 4%

---


# 트레이트 및 세그먼트 빌더의 부울 표현식{#boolean-expressions-in-trait-and-segment-builder}

이 문서에서는 Audience Manager 특성 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.

<!-- 

c_tb_boolean.xml

 -->

**부울 표현식**

부울 로직은 몇 개의 기본 표현식(또는 연산자)을 사용하여 문이 참인지 거짓인지 확인하는 대수의 한 가지입니다. 가장 일반적인 연산자는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]입니다. 이러한 표현식의 조합은 데이터 요구 사항에 딱 맞는 트레이트 또는 세그먼트 자격 규칙을 만드는 데 도움이 됩니다. 다음 그림에서는 기본 부울 표현식의 작동 방식을 보여 줍니다.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] 연산자는 암묵적인 &quot;and&quot; 조건을 사용하고 경우에 따라 [!UICONTROL AND NOT]로 기록됩니다.

**트레이트 및 세그먼트 빌더에서 부울 표현식을 사용하는 방법**

부울 표현식으로 트레이트 및 세그먼트 자격 규칙을 만듭니다. 아래 표는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]로 자격 조건을 만들기 위한 일반적인 우수 사례에 대해 설명합니다.

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 표현식 </th> 
   <th colname="col2" class="entry"> JavaScript를 사용하여 </th> 
   <th colname="col3" class="entry"> 자격 조건 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 그리고</span></b> </p> </td> 
   <td colname="col2"> <p>한정된 집중형 고객 자격 요건 </p> </td> 
   <td colname="col3"> <p><i>사용자는 지정된 모든 트레이트 또는 세그먼트에 속해야 합니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 또는</span></b> </p> </td> 
   <td colname="col2"> <p>광범위한 고객 자격 조건 </p> </td> 
   <td colname="col3"> <p><i>사용자는 지정된 트레이트 또는 세그먼트에 속할 수 있습니다.</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>한정된 집중형 고객 자격 요건 </p> <p>고객 자격 요건 정의를 어렵거나 비효율적으로 만드는 여러 조건이 있는 경우 유용합니다. 포함이 아닌 제외되는 요구 사항에 대해 검증하는 것이 더 쉽습니다. </p> </td> 
   <td colname="col3"> <p>사용자 <i>은(는) 제외된 트레이트 또는 세그먼트에 속하지 않아야 합니다.</i> </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]사용 사례 예**

[!UICONTROL AND] 연산자는 특성 멤버십 요구 사항을 쉽게 열거할 때 유용합니다. 예를 들어 &quot;고가의 카메라 구매 전문가&quot;를 대상으로 고객을 만들어야 합니다. 픽셀 모델을 사용하면 카메라에 사용할 픽셀과 페이지에 숫자 값을 만들어 배치해야 합니다. 이와 반대로 트레이트를 사용하여 부울 연산자를 적용하여 두 조건(카메라 [!UICONTROL AND] 가격)을 모두 처리할 수 있습니다. 그 결과 HTTP 호출 횟수가 줄어들어 효율적인 데이터 수집이 가능하므로 사이트의 사용자 경험을 그대로 유지할 수 있습니다.

**[!UICONTROL OR]사용 사례 예**

[!UICONTROL OR] 연산자는 광범위한 대상 자격 조건을 가진 신호를 만들 때 유용합니다. 특성 또는 세그먼트 자격 요구 사항이 여러 개인 경우 사이트 방문자가 이러한 특성의 *임의의*&#x200B;을 표시할 때 [!UICONTROL OR] 연산자가 true로 평가됩니다. [!UICONTROL OR] 은 적격한 사이트 방문자로 구성된 광범위한 대상을 빠르게 만들려면 가장 유용합니다.

**[!UICONTROL AND NOT]사용 사례 예**

[!UICONTROL AND NOT] 연산자는 *포함*&#x200B;이 아닌 *exclusion*&#x200B;로 대상을 쉽게 정의할 때 유용합니다. 예를 들어, 현재 판매를 하고 있으며 방문자를 정식 가격 항목만을 열람하는 고객으로 분류하려는 경우 적격한 모든 정가 또는 세일 가격 항목에 대한 신호 목록을 만드는 것이 아니라, 방문자가 판매 가격 항목을 보지 않은 *이(가) 있는 경우 자격을 얻는 것이 더 쉽습니다.* 이는 정가에 비해 보통 세일 가격 품목이 적어 행정 효율적입니다. 부울 [!UICONTROL NOT]을 사용하는 방문자는 *에서 정가의 대상 멤버십을 이용할 수 있는 판매 신호를 표시하지 않아야 합니다.* 반대로, [!UICONTROL AND NOT]은 대상 멤버십이 포함에 의해 결정되는 방법을 보여주는 [!UICONTROL AND] 사용 사례와 반대입니다(즉, 2개의 명시적으로 지정된 신호를 기반으로 자격이 있는 방문자).

>[!MORELIKETHIS]
>
>* [TraitBuilder에서 비교 연산자 사용](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder 표현식의 작업 순서](../features/traits/trait-operator-precedence.md)

