---
description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.
seo-description: 이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.
seo-title: 트레이트 및 세그먼트 빌더의 부울 표현식
solution: Audience Manager
title: 트레이트 및 세그먼트 빌더의 부울 표현식
uuid: 14f02d3f-4c84-41fe-bc91-b34f0d49574a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# 트레이트 및 세그먼트 빌더의 부울 표현식{#boolean-expressions-in-trait-and-segment-builder}

이 문서에서는 Audience Manager 트레이트 및 세그먼트 도구가 부울 표현식 AND, OR 및 NOT을 사용하는 방법에 대해 설명합니다.

<!-- 

c_tb_boolean.xml

 -->

**부울 표현식**

부울 논리는 몇 가지 기본 표현식(또는 연산자)을 사용하여 문이 참인지 거짓인지 확인하는 대수의 분기입니다. 가장 일반적인 연산자는 [!UICONTROL AND], [!UICONTROL OR]및 [!UICONTROL NOT]입니다. 이러한 표현식의 조합은 데이터 요구 사항에 딱 맞는 트레이트 또는 세그먼트 자격 규칙을 만드는 데 도움이 됩니다. 다음 그림은 기본 부울 표현식의 작동 방식을 보여줍니다.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>이 [!UICONTROL NOT] 연산자는 암묵적인 "and" 조건을 사용하고 경우에 따라 으로 작성되기도 [!UICONTROL AND NOT]합니다.

**트레이트 및 세그먼트 빌더에서 부울 표현식을 사용하는 방법**

부울 표현식으로 트레이트 및 세그먼트 자격 규칙을 만듭니다. 아래 표에서는 [!UICONTROL AND], [!UICONTROL OR]및 [!UICONTROL NOT]를 사용하여 자격 조건을 만드는 일반적인 우수 사례에 대해 설명합니다.

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
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>집중적인 고객 자격 요건 파악 </p> </td> 
   <td colname="col3"> <p>사용자는 <i>지정된 모든 트레이트 또는 세그먼트에 속해야</i> 합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>광범위하고 덜 집중된 고객 자격 요건 </p> </td> 
   <td colname="col3"> <p>사용자는 <i>지정된 트레이트 또는 세그먼트에 속할 수</i> 있습니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>집중적인 고객 자격 요건 파악 </p> <p>고객 자격 조건을 정의하는 것이 어렵거나 비효율적인 여러 조건이 있을 때 유용합니다. 포함이 아닌 제외되는 요구 사항에 대해 쉽게 확인할 수 있습니다. </p> </td> 
   <td colname="col3"> <p>사용자는 제외된 트레이트 또는 세그먼트에 속해서는 <i>안</i> 됩니다. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]사용 사례 예**

이 [!UICONTROL AND] 연산자는 트레이트 멤버십 요구 사항을 쉽게 열거할 때 유용합니다. 예를 들어 "고가의 카메라 쇼핑 고객"을 확보해야 한다고 가정해 봅시다. 픽셀 모델을 사용하면 카메라용 픽셀과 페이지에 숫자 가격 값을 만들어 배치해야 합니다. 반면에 트레이트를 사용하여 부울 연산자를 적용하여 두 조건(카메라 [!UICONTROL AND] 가격)을 모두 처리할 수 있습니다. 결과적으로 HTTP 호출 횟수가 줄어들어 효율적인 데이터 수집이 가능하므로 사이트의 사용자 경험을 유지할 수 있습니다.

**[!UICONTROL OR]사용 사례 예**

이 [!UICONTROL OR] 연산자는 광범위한 대상 자격 조건을 갖춘 신호를 만들 때 유용합니다. 여러 특성 또는 세그먼트 자격 요구 사항이 있는 경우 사이트 방문자가 이러한 특성을 표시할 때 [!UICONTROL OR] 연산자는 true *로 평가됩니다* . [!UICONTROL OR] 자격 조건을 갖춘 사이트 방문자로 구성된 광범위한 고객을 신속하게 만들 때 가장 유용할 수 있습니다.

**[!UICONTROL AND NOT]사용 사례 예**

이 [!UICONTROL AND NOT] 연산자는 *포함이* 아닌 *제외로*&#x200B;대상을 쉽게 정의할 때 유용합니다. 예를 들어 판매를 하고 있으며 방문자를 전체 가격 항목만을 보는 고객으로 분류하려는 경우 적격한 모든 정가 또는 판매 가격의 항목에 대한 신호 목록을 만드는 대신, 방문자가 판매 가격 항목을 보지 *않은* 경우 자격을 얻는 것이 더 쉽습니다. 정식 가격에 비해 일반적으로 판매 가격 항목이 적기 때문에 이 방법은 행정적으로 효율적입니다. 부울을 사용하는 [!UICONTROL NOT]경우 방문자는 정식 가격의 대상 멤버십을 이용할 수 있도록 판매 신호를 *표시해서는* 안됩니다. 반면, [!UICONTROL AND NOT] 는 대상자 멤버십이 포함에 의해 결정되는 방식을 보여주는 [!UICONTROL AND] 사용 사례와 반대되는 개념입니다(즉, 2개의 명시적 신호를 기반으로 자격이 있는 방문자).

>[!MORELIKETHIS]
>
>* [TraitBuilder에서 비교 연산자를 사용한 작업](../features/traits/trait-comparison-operators.md)
>* [TraitBuilder 표현식의 작업 순서](../features/traits/trait-operator-precedence.md)

