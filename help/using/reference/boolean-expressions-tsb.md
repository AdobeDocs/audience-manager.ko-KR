---
description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법을 설명합니다.
seo-description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법을 설명합니다.
seo-title: 트레이트 및 세그먼트 빌더의 부울 표현식
solution: Audience Manager
title: 트레이트 및 세그먼트 빌더의 부울 표현식
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: 참조
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# 트레이트 및 세그먼트 빌더의 부울 표현식{#boolean-expressions-in-trait-and-segment-builder}

이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법을 설명합니다.

<!-- 

c_tb_boolean.xml

 -->

**부울 표현식**

부울 논리는 몇 가지 기본 표현식(또는 연산자)을 사용하여 문이 true 또는 false인지를 결정하는 대수의 분기입니다. 가장 일반적인 연산자는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]입니다. 이러한 표현식의 조합은 집중 트레이트 또는 세그먼트 자격 규칙을 데이터 요구 사항에 맞게 고유하게 만드는 데 도움이 됩니다. 다음 그림은 기본적인 부울 표현식이 작동하는 방식을 보여줍니다.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] 연산자는 암시된 &quot;and&quot; 조건을 사용하고 경우에 따라 [!UICONTROL AND NOT]로 작성됩니다.

**트레이트 및 세그먼트 빌더에서 부울 표현식을 사용하는 방법**

부울 표현식으로 트레이트 및 세그먼트 자격 규칙을 만듭니다. 아래 표에서는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]를 사용하여 자격 기준을 만드는 일반적인 모범 사례에 대해 설명합니다.

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 표현식 </th> 
   <th colname="col2" class="entry"> 이를 사용하여 다음을 만듭니다 </th> 
   <th colname="col3" class="entry"> 자격 조건 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 그리고</span></b> </p> </td> 
   <td colname="col2"> <p>좁고 집중된 대상 자격 요구 사항. </p> </td> 
   <td colname="col3"> <p><i>사용자는 </i>이 지정된 모든 트레이트 또는 세그먼트에 속해야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 또는</span></b> </p> </td> 
   <td colname="col2"> <p>광범위하고 덜 집중된 대상 자격 요건. </p> </td> 
   <td colname="col3"> <p><i>사용자는 </i>이 지정된 트레이트 또는 세그먼트에 속할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>좁고 집중된 대상 자격 요구 사항. </p> <p>대상 자격 요구 사항을 정의하는 것이 어렵거나 비효율적일 때 유용합니다. 포함보다는 제외되는 요구 사항에 대해 더 쉽게 유효성 검사를 할 수 있습니다. </p> </td> 
   <td colname="col3"> <p><i>사용자는</i>이 제외된 트레이트 또는 세그먼트에 속하면 안 됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]사용 사례 예**

[!UICONTROL AND] 연산자는 트레이트 멤버십 요구 사항을 쉽게 열거한 경우 유용합니다. 예를 들어 &quot;값비싼 카메라 구매자&quot;의 대상자를 만들어야 한다고 가정해 보겠습니다. 픽셀 모델을 사용하면 카메라용 픽셀과 숫자 가격 값을 페이지에 만들어 배치해야 합니다. 그와 대조적으로 트레이트를 사용하여 부울 연산자를 적용하여 두 조건(카메라 [!UICONTROL AND] 가격)을 모두 처리할 수 있습니다. 따라서 HTTP 호출이 적을수록 데이터 수집이 효율적으로 수행되므로 사이트에서 사용자 경험을 유지하는 데 도움이 됩니다.

**[!UICONTROL OR]사용 사례 예**

[!UICONTROL OR] 연산자는 광범위한 대상 자격 요구 사항을 포함하는 신호를 만들려는 경우에 유용합니다. 트레이트 또는 세그먼트 자격 요구 사항이 여러 개 있는 경우 사이트 방문자가 해당 특성의 *any*&#x200B;를 표시하면 [!UICONTROL OR] 연산자가 true로 평가됩니다. [!UICONTROL OR] 은 자격이 있는 사이트 방문자에 대한 광범위한 대상을 빠르게 만들려는 경우에 가장 유용할 수 있습니다.

**[!UICONTROL AND NOT]사용 사례 예**

[!UICONTROL AND NOT] 연산자는 *포함*&#x200B;이 아닌 *제외*&#x200B;로 대상을 더 쉽게 정의할 때 유용합니다. 예를 들어, 판매가 있고 전체 가격 항목만을 보는 고객으로 방문자를 세그먼트화하려는 경우, 자격 있는 모든 전체 또는 판매 가격 항목에 대한 신호 목록을 만드는 대신, *not*&#x200B;에서 판매 가격 항목을 본 방문자가 있으면 자격을 더 쉽게 부여할 수 있습니다. 이렇게 하면 일반적으로 정가로 제공되는 가격보다 판매가격이 더 적기 때문에 행정적으로 효율적입니다. 부울 [!UICONTROL NOT]을 사용하는 경우, 방문자 *은(는) 완전 가격 대상 멤버십에 대한 자격이 되도록 판매 신호를 나타내지 않아야 합니다.* 그와 대조적으로, [!UICONTROL AND NOT]은 대상 멤버십이 포함에 의해 결정되는 방식을 보여주는 [!UICONTROL AND] 사용 사례의 반대입니다(즉, 방문자가 명시적으로 지정된 2개의 신호를 기반으로 자격이 있음).

>[!MORELIKETHIS]
>
>* [TraitBuilder에서 비교 연산자 사용](../features/traits/trait-comparison-operators.md)
* [TraitBuilder 표현식의 작업 순서](../features/traits/trait-operator-precedence.md)

