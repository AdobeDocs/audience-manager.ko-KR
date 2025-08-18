---
description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식인 AND, OR 및 NOT을 사용하는 방법을 설명합니다.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: 트레이트 및 세그먼트 빌더의 부울 표현식
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# 트레이트 및 세그먼트 빌더의 부울 표현식{#boolean-expressions-in-trait-and-segment-builder}

이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식인 AND, OR 및 NOT을 사용하는 방법을 설명합니다.

<!-- 

c_tb_boolean.xml

 -->

**부울 식**

부울 논리는 몇 가지 기본 표현식(또는 연산자)을 사용하여 명령문이 true 또는 false인지를 결정하는 대수의 분기입니다. 가장 일반적인 연산자는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]입니다. 이러한 표현식을 조합하면 집중 트레이트 또는 세그먼트 자격 규칙을 데이터 요구 사항에 맞게 고유하게 만드는 데 도움이 됩니다. 다음 그림은 기본 부울 표현식이 작동하는 방식을 보여 줍니다.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] 연산자는 암시적 &quot;and&quot; 조건을 사용하며 경우에 따라 [!UICONTROL AND NOT]&#x200B;(으)로 작성됩니다.

**트레이트 및 세그먼트 빌더에서 부울 식을 사용하는 방법**

부울 표현식을 사용하여 트레이트 및 세그먼트 자격 규칙을 만듭니다. 아래 표에서는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]을(를) 사용하여 자격 조건을 만드는 일반적인 모범 사례에 대해 설명합니다.

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 표현식 </th> 
   <th colname="col2" class="entry"> 만드는 데 사용 </th> 
   <th colname="col3" class="entry"> 선별 조건 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 및</span></b> </p> </td> 
   <td colname="col2"> <p>좁고 집중적인 대상 자격 요구 사항. </p> </td> 
   <td colname="col3"> <p>사용자 <i>must</i>이(가) 지정된 모든 트레이트 또는 세그먼트에 속합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 또는</span></b> </p> </td> 
   <td colname="col2"> <p>광범위하고 집중도가 낮은 대상 자격 요구 사항. </p> </td> 
   <td colname="col3"> <p>사용자 <i>can</i>이(가) 지정된 트레이트 또는 세그먼트에 속합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle">이(가) </span></b> 아님 </p> </td> 
   <td colname="col2"> <p>좁고 집중적인 대상 자격 요구 사항. </p> <p>대상 자격 요구 사항을 정의하기 어렵거나 비효율적인 조건이 여러 개 있는 경우 유용합니다. 경우에 따라 포함보다는 제외하는 요구 사항에 대해 유효성 검사가 더 쉽습니다. </p> </td> 
   <td colname="col3"> <p><i>명의 사용자는 제외된 트레이트 또는 세그먼트에 속할 수 없습니다</i>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]사용 사례 예**

[!UICONTROL AND] 연산자는 트레이트 멤버십 요구 사항을 쉽게 열거한 경우에 유용합니다. 예를 들어 &quot;고가 카메라 구매자&quot; 대상을 만들어야 한다고 가정합니다. 픽셀 모델을 사용하면 카메라용 픽셀과 페이지에 숫자 가격 값을 만들어 배치해야 합니다. 반대로 트레이트를 사용하면 부울 연산자를 적용하여 두 조건(카메라 [!UICONTROL AND] 가격)을 모두 처리할 수 있습니다. 그 결과 HTTP 호출이 줄어들어 효율적인 데이터 수집이 되므로 결과적으로 사이트의 사용자 경험을 유지하는 데 도움이 됩니다.

**[!UICONTROL OR]사용 사례 예**

[!UICONTROL OR] 연산자는 광범위한 대상 자격 요구 사항이 있는 신호를 만들려는 경우에 유용합니다. 트레이트 또는 세그먼트 자격 요구 사항이 여러 개 있는 경우 사이트 방문자가 해당 특성의 [!UICONTROL OR]any *을(를) 표시하면* 연산자가 true로 평가됩니다. [!UICONTROL OR]은(는) 자격을 갖춘 사이트 방문자의 광범위한 대상을 신속하게 만들려는 경우에 가장 유용할 수 있습니다.

**[!UICONTROL AND NOT]사용 사례 예**

[!UICONTROL AND NOT] 연산자는 대상자를 *포함*&#x200B;이 아닌 *제외*&#x200B;로 정의하기가 더 쉬울 때 유용합니다. 예를 들어 세일을 하고 있고 방문자를 전체 가격 항목만 보는 고객으로 분할하려고 한다고 가정해 보겠습니다. 자격을 갖춘 모든 전체 또는 판매 가격 항목에 대한 신호 목록을 만드는 대신, *판매 가격 항목이 표시되지 않음*&#x200B;이 있는 방문자의 자격을 규정하는 것이 더 쉬울 수 있습니다. 일반적으로 정가로 제공되는 항목에 비해 판매 가격 항목이 적으므로 관리 효율적입니다. 부울 [!UICONTROL NOT]을(를) 사용하는 방문자 *은(는) 정가 대상 멤버십 자격을 얻기 위해 판매 신호를 표시해서는 안 됩니다*. 반대로 [!UICONTROL AND NOT]은(는) 대상 멤버십이 포함에 의해 결정되는 방법(즉, 명시적으로 설명된 2개의 신호에 따라 자격이 부여된 방문자)을 보여 주는 [!UICONTROL AND] 사용 사례와 반대입니다.

>[!MORELIKETHIS]
>
>* [TraitBuilder에서 비교 연산자 사용](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder 식의 작업 순서](../features/traits/trait-operator-precedence.md)
