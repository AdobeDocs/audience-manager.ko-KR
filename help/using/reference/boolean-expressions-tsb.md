---
description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식인 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.
seo-description: This article explains how the Audience Manager trait and segment tools use the Boolean expressions AND, OR, and NOT.
seo-title: Boolean Expressions in Trait and Segment Builder
solution: Audience Manager
title: 트레이트 및 세그먼트 빌더의 부울 표현식
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# 트레이트 및 세그먼트 빌더의 부울 표현식{#boolean-expressions-in-trait-and-segment-builder}

이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식인 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.

<!-- 

c_tb_boolean.xml

 -->

**부울 표현식**

부울 논리는 몇 가지 기본 표현식(또는 연산자)을 사용하여 명령문이 true 또는 false인지를 결정하는 대수의 분기입니다. 가장 일반적인 연산자는 다음과 같습니다 [!UICONTROL AND], [!UICONTROL OR], 및 [!UICONTROL NOT]. 이러한 표현식을 조합하면 집중 트레이트 또는 세그먼트 자격 규칙을 데이터 요구 사항에 맞게 고유하게 만드는 데 도움이 됩니다. 다음 그림은 기본 부울 표현식이 작동하는 방식을 보여 줍니다.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>다음 [!UICONTROL NOT] 연산자는 암시적 &quot;and&quot; 조건을 사용하며 때로는 다음과 같이 기록됩니다. [!UICONTROL AND NOT].

**트레이트 및 세그먼트 빌더에서 부울 표현식을 사용하는 방법**

부울 표현식을 사용하여 트레이트 및 세그먼트 자격 규칙을 만듭니다. 아래 표에서는 를 사용하여 자격 기준을 만드는 일반적인 모범 사례를 설명합니다. [!UICONTROL AND], [!UICONTROL OR], 및 [!UICONTROL NOT].

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
   <td colname="col1"> <p><b><span class="wintitle"> 그리고</span></b> </p> </td> 
   <td colname="col2"> <p>좁고 집중적인 대상 자격 요구 사항. </p> </td> 
   <td colname="col3"> <p>사용자 <i>필수</i> 지정된 모든 트레이트 또는 세그먼트에 속합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 또는</span></b> </p> </td> 
   <td colname="col2"> <p>광범위하고 집중도가 낮은 대상 자격 요구 사항. </p> </td> 
   <td colname="col3"> <p>사용자 <i>can</i> 는 지정된 트레이트 또는 세그먼트에 속합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>좁고 집중적인 대상 자격 요구 사항. </p> <p>대상 자격 요구 사항을 정의하기 어렵거나 비효율적인 조건이 여러 개 있는 경우 유용합니다. 경우에 따라 포함보다는 제외하는 요구 사항에 대해 유효성 검사가 더 쉽습니다. </p> </td> 
   <td colname="col3"> <p>사용자 <i>은(는) 해서는 안 됨</i> 제외된 트레이트 또는 세그먼트에 속합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]사용 사례 예**

다음 [!UICONTROL AND] 연산자는 트레이트 멤버십 요구 사항을 쉽게 열거한 경우에 유용합니다. 예를 들어 &quot;고가 카메라 구매자&quot; 대상을 만들어야 한다고 가정합니다. 픽셀 모델을 사용하면 카메라용 픽셀과 페이지에 숫자 가격 값을 만들어 배치해야 합니다. 반대로 트레이트를 사용하면 부울 연산자를 적용하여 두 조건(카메라)을 모두 처리할 수 있습니다 [!UICONTROL AND] 가격). 그 결과 HTTP 호출이 줄어들어 효율적인 데이터 수집이 되므로 결과적으로 사이트의 사용자 경험을 유지하는 데 도움이 됩니다.

**[!UICONTROL OR]사용 사례 예**

다음 [!UICONTROL OR] 연산자는 광범위한 대상 자격 요구 사항이 있는 신호를 만들려는 경우에 유용합니다. 트레이트 또는 세그먼트 자격 요구 사항이 여러 개 있는 경우 [!UICONTROL OR] 연산자는 사이트 방문자가 를 표시하면 true로 평가됩니다. *임의* 그러한 특성들 중. [!UICONTROL OR] 는 자격을 갖춘 사이트 방문자의 광범위한 대상을 신속하게 만들려는 경우에 가장 유용할 수 있습니다.

**[!UICONTROL AND NOT]사용 사례 예**

다음 [!UICONTROL AND NOT] 연산자는 대상자를 정의하는 것이 더 쉬울 때 유용합니다. *제외* 보다 *포함*. 예를 들어 세일을 하고 있고 방문자를 전체 가격 항목만 보는 고객으로 분할하려고 한다고 가정해 보겠습니다. 자격을 갖춘 모든 전체 또는 판매 가격 항목에 대한 신호 목록을 만드는 것보다, 방문자가 다음을 보유한 경우 방문자의 자격을 평가하는 것이 더 쉬울 수 있습니다. *아님* 판매 가격 항목을 확인했습니다. 일반적으로 정가로 제공되는 항목에 비해 판매 가격 항목이 적으므로 관리 효율적입니다. 부울 사용 [!UICONTROL NOT], 방문자 수 *은(는) 해서는 안 됨* 정가 대상 멤버십의 자격을 얻기 위한 판매 신호를 표시합니다. 대조적으로, [!UICONTROL AND NOT] 의 반대입니다. [!UICONTROL AND] 대상 멤버십이 포함에 의해 결정되는 방법을 보여 주는 사용 사례(즉, 명시적으로 설명된 2개의 신호에 따라 방문자가 자격을 부여받음).

>[!MORELIKETHIS]
>
>* [TraitBuilder에서 비교 연산자 사용](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder 표현식의 작업 순서](../features/traits/trait-operator-precedence.md)

