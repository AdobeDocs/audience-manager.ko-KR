---
description: 이 문서에서는 Audience Manager 특성 및 세그먼트 도구에 부울 표현식과, 또는, 또는 이 사용되지 않는 방법을 설명합니다.
seo-description: 이 문서에서는 Audience Manager 특성 및 세그먼트 도구에 부울 표현식과, 또는, 또는 이 사용되지 않는 방법을 설명합니다.
seo-title: 트레이트 및 세그먼트 빌더에서 부울 표현식
solution: Audience Manager
title: 트레이트 및 세그먼트 빌더에서 부울 표현식
uuid: 14 F 02 D 3 F -4 C 84-41 FE-BC 91-B 34 F 0 D 49574 A
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Boolean Expressions in Trait and Segment Builder{#boolean-expressions-in-trait-and-segment-builder}

이 문서에서는 Audience Manager 특성 및 세그먼트 도구에 부울 표현식과, 또는, 또는 이 사용되지 않는 방법을 설명합니다.

<!-- 

c_tb_boolean.xml

 -->

**부울 표현식**

부울 로직은 소수의 기본 표현식 (또는 연산자) 를 사용하여 문이 true 인지 또는 false 인지를 결정하는 algebra의 분기입니다. The most common operators are [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]. 이러한 표현식의 조합을 통해 데이터 요구 사항에 맞게 고유한 특성 또는 세그먼트 자격 규칙을 만들 수 있습니다. 다음 그림은 기본적인 부울 표현식의 작동 방식을 보여줍니다.

<br> 

![](assets/BooleanOverview_small.png)

>[!NOTE]
>
>[!UICONTROL NOT] 연산자는 암시적인 "and" 조건을 사용하며 때로로 작성됩니다 [!UICONTROL AND NOT].

**트레이트 및 세그먼트 빌더에서 부울 표현식을 사용하는 방법**

부울 표현식을 사용하여 특성 및 세그먼트 자격 규칙을 만듭니다. The table below describes general best practices for creating qualification criteria with [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT].

<table id="table_C762872C98F54C4A86A2F1C840A86657"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 표현식 </th> 
   <th colname="col2" class="entry"> Use it to create </th> 
   <th colname="col3" class="entry"> 자격 조건 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> AND</span></b> </p> </td> 
   <td colname="col2"> <p>범위를 좁히고 집중한 고객 자격 요건 </p> </td> 
   <td colname="col3"> <p>Users <i>must</i> belong to all specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> OR</span></b> </p> </td> 
   <td colname="col2"> <p>보다 집중적이고 집중적인 고객 자격 요건 </p> </td> 
   <td colname="col3"> <p>Users <i>can</i> belong to any specified traits or segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="wintitle"> NOT</span></b> </p> </td> 
   <td colname="col2"> <p>범위를 좁히고 집중한 고객 자격 요건 </p> <p>고객 자격 조건을 까다롭거나 비효율적으로 정의하는 여러 조건이 있을 때 유용합니다. 경우에 따라 포함하지 않고 제외되는 요구 사항을 확인하는 것이 더 쉽습니다. </p> </td> 
   <td colname="col3"> <p>Users <i>must not</i> belong to an excluded trait or segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

**[!UICONTROL AND]사용 사례 예**

[!UICONTROL AND] 연산자는 트레이트 멤버십 요구 사항을 쉽게 열거할 때 유용합니다. 예를 들어, "비싼 카메라 쇼핑 쇼핑 대상자" 를 만들어야 한다고 가정해 봅시다. » 픽셀 모델을 사용하면 카메라 픽셀 및 페이지에 대한 숫자 가격 값을 만들어 배치해야 합니다. By contrast, with traits you can apply Boolean operators to handle both conditions (cameras [!UICONTROL AND] price). 결과적으로 HTTP 호출이 더 적은 효율적인 데이터 수집으로 사이트의 사용자 경험을 유지할 수 있습니다.

**[!UICONTROL OR]사용 사례 예**

[!UICONTROL OR] 연산자는 광범위한 대상 자격 조건을 갖춘 신호를 만들고자 할 때 유용합니다. If you have several trait or segment qualification requirements, the [!UICONTROL OR] operator will evaluate to true when your site visitors exhibit *any* of those characteristics. [!UICONTROL OR] 은 적격한 사이트 방문자의 광범위한 대상을 빠르게 만들려는 경우에 가장 유용합니다.

**[!UICONTROL AND NOT]사용 사례 예**

[!UICONTROL AND NOT] 연산자는 포함이 아닌 *제외로* 대상을 정의하는 것이 더 쉬운 경우에 *유용합니다*. 예를 들어, 세일 중이며, 방문자를 전체 가격 항목만 보는 고객으로 세그먼트화하려는 경우를 예로 들 수 있습니다. Rather than create a list of signals for all qualifying full or sale-price items, it may be easier to qualify visitors if they have *not* seen a sale price item. 이는 일반적으로 정식 가격으로 제공되는 판매와 비교하여 판매 가격 항목이 적기 때문에 관리상의 효율적입니다. With a Boolean [!UICONTROL NOT], visitors *must not* exhibit the sale signal to qualify for full-price audience membership. By contrast, [!UICONTROL AND NOT] is the opposite of the [!UICONTROL AND] use case, which showed how audience membership is determined by inclusion (i.e., the visitor qualified based on 2 explicitly stated signals).

>[!MORE_ like_ this]
>
>* [Traitbuilder에서 비교 연산자를 사용한 작업](../features/traits/trait-comparison-operators.md)
>* [Traitbuilder 표현식의 작업 순서](../features/traits/trait-operator-precedence.md)

