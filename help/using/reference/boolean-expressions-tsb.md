---
description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 및 OR, NOT을 사용하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 및 OR, NOT을 사용하는 방법에 대해 설명합니다.
seo-title: 트레이트 및 세그먼트 빌더의 부울 표현식
solution: Audience Manager
title: 트레이트 및 세그먼트 빌더의 부울 표현식
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
feature: Reference
exl-id: 44bc0385-2cce-4173-9833-b9a30fb6edae
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# 트레이트 및 세그먼트 빌더의 부울 표현식{#boolean-expressions-in-trait-and-segment-builder}

이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 및 OR, NOT을 사용하는 방법에 대해 설명합니다.

<!-- 

c_tb_boolean.xml

 -->

**부울 표현식**

부울 논리는 몇 가지 기본 표현식(또는 연산자)을 사용하여 명령문이 true 또는 false인지 확인하는 대수의 분기입니다. 가장 일반적인 연산자는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]입니다. 이러한 표현식의 조합을 사용하면 데이터 요구 사항에 맞게 트레이트 또는 세그먼트 자격 규칙을 고유하게 적용할 수 있습니다. 다음 그림은 기본적인 부울 표현식의 작동 방식을 보여줍니다.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] 연산자는 암시적 &quot;and&quot; 조건을 사용하며 경우에 따라 [!UICONTROL AND NOT]로 기록됩니다.

**트레이트 및 세그먼트 빌더에서 부울 표현식을 사용하는 방법**

부울 표현식으로 트레이트 및 세그먼트 자격 규칙을 만듭니다. 아래 표에서는 [!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT]로 자격 조건을 만드는 일반적인 우수 사례에 대해 설명합니다.

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 표현식 </th> 
   <th colname="col2" class="entry"> Flash Player를 사용하여 </th> 
   <th colname="col3" class="entry"> 자격 조건 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 그리고</span></b> </p> </td> 
   <td colname="col2"> <p>제한된 집중적인 고객 자격 조건 </p> </td> 
   <td colname="col3"> <p><i>사용자는 </i>이(가) 지정된 모든 트레이트 또는 세그먼트에 속해야 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> 또는</span></b> </p> </td> 
   <td colname="col2"> <p>광범위하고 덜 집중된 고객 자격 조건 </p> </td> 
   <td colname="col3"> <p><i>사용자는 </i>이(가) 지정된 트레이트 또는 세그먼트에 속할 수 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>제한된 집중적인 고객 자격 조건 </p> <p>고객 자격 조건을 정의하는 것이 어렵거나 비효율적인 여러 조건이 있는 경우 유용합니다. 포함하기 보다는 제외되는 요구 사항에 대해 쉽게 확인할 수 있습니다. </p> </td> 
   <td colname="col3"> <p><i>사용자는 </i>이(가) 제외된 트레이트 또는 세그먼트에 속하지 않아야 합니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]사용 사례 예**

[!UICONTROL AND] 연산자는 트레이트 멤버십 요구 사항을 쉽게 열거할 때 유용합니다. 예를 들어 &quot;고가의 카메라 쇼핑 고객&quot;을 대상으로 하는 고객을 만들어야 합니다. 픽셀 모델을 사용하면 카메라용 픽셀과 페이지에 숫자 가격 값을 만들어 배치해야 합니다. 반대로 트레이트를 사용하여 부울 연산자를 적용하여 두 조건(카메라 [!UICONTROL AND] 가격)을 모두 처리할 수 있습니다. 그 결과 HTTP 호출 횟수가 적은 효율적인 데이터 수집이 가능하므로 사이트의 사용자 경험을 그대로 유지할 수 있습니다.

**[!UICONTROL OR]사용 사례 예**

[!UICONTROL OR] 연산자는 광범위한 대상 자격 요건을 갖춘 신호를 만들 때 유용합니다. 몇 가지 트레이트 또는 세그먼트 자격 요구 사항이 있는 경우 사이트 방문자가 해당 특성의 *임의의*&#x200B;을 표시할 때 [!UICONTROL OR] 연산자가 true로 평가됩니다. [!UICONTROL OR] 은 적격한 사이트 방문자로 구성된 광범위한 대상을 빠르게 만들려면 가장 유용합니다.

**[!UICONTROL AND NOT]사용 사례 예**

[!UICONTROL AND NOT] 연산자는 *include*&#x200B;이 아닌 *exclusion*&#x200B;로 대상을 정의하는 것이 더 쉬운 경우에 유용합니다. 예를 들어 판매를 하고 있으며 정식 가격 항목만을 열람하는 고객으로 방문자를 분류하려는 경우 자격 조건을 갖춘 모든 정식 또는 판매 가격 항목에 대한 신호 목록을 만드는 대신 *이(가) 아닌*&#x200B;이(가) 판매 가격 항목을 보면 방문자의 자격을 얻는 것이 더 쉽습니다. 정품 가격에 비해 일반적으로 판매 가격 항목이 적기 때문에 이 방법은 행정적으로 효율적입니다. 부울 [!UICONTROL NOT]이 있는 경우 방문자가 *에 전체 가격의 대상 멤버십을 이용할 수 있는 판매 신호를 표시하지 않아야 합니다.* 반면 [!UICONTROL AND NOT]은(는) 대상 멤버십이 포함에 의해 결정되는 방식을 보여주는 [!UICONTROL AND] 사용 사례와 반대되는 경우입니다(즉, 2개의 명시적 신호를 기반으로 자격이 부여된 방문자).

>[!MORELIKETHIS]
>
>* [TraitBuilder에서 비교 연산자를 사용한 작업](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder 표현식의 작업 순서](../features/traits/trait-operator-precedence.md)

