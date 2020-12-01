---
description: 세그먼트 빌더를 사용하면 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 만들 수 있습니다. 이 기능에 액세스하려면 트레이트 패널에서 세그먼트 표현식(코드 보기) 탭을 클릭합니다.
seo-description: 세그먼트 빌더를 사용하면 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 만들 수 있습니다. 이 기능에 액세스하려면 트레이트 패널에서 세그먼트 표현식(코드 보기) 탭을 클릭합니다.
seo-title: 세그먼트 표현식 편집기에 사용되는 코드 구문
solution: Audience Manager
title: 세그먼트 표현식 편집기에 사용되는 코드 구문
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 11%

---


# 세그먼트 표현식 편집기에 사용되는 코드 구문 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 만들 수 있습니다. 이 기능에 액세스하려면 [!UICONTROL Traits] 패널에서 **[!UICONTROL Segment Expressions (Code View)]** 탭을 클릭합니다.

## 표현식 빌더 코드 구문

드래그 앤 드롭 기능을 사용하는 대신 코드를 사용하여 세그먼트에 트레이트 규칙을 추가할 수 있습니다. 코딩 시 예제의 기울임체 요소를 실제 표현식 또는 값으로 바꿉니다. 기본 코드에서는 다음 구문을 사용합니다.

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>기본적으로 [!DNL Boolean] [!UICONTROL OR] 조건은 표현식의 여러 특성 *에 적용됩니다.*

### 부울 연산자로 세그먼트 참여

세그먼트 그룹을 만들려면 빈도 함수를 괄호 안에 래핑하고 [!DNL Boolean] 연산자([!UICONTROL AND], [!UICONTROL OR] 및 [!UICONTROL NOT])로 각 표현식 사이의 관계 *을 설정합니다.*

### 매개 변수

>[!NOTE]
>
>별도의 설명이 없는 한 모든 매개 변수가 필요합니다.

| 이름 또는 변수 | 설명 |
|---|---|
| `FREQUENCY` | 식 앞에 와야 하는 문자 |
| ` [`&lt;`traitID`>`T]` | 특성 ID 뒤에 `T` 문자가 오는 배열. 여러 트레이트를 쉼표로 구분합니다. 예, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(선택 사항)* 세그먼트의 트레이트에 대한 최근 규칙을 설정합니다. 문자 `D`은 최근 기간(일)을 나타냅니다. |
| ` <Frequency Operator><Numeric Value>` | 세그먼트의 트레이트에 대한 빈도 규칙을 설정합니다. |

### 허용되는 최근 및 빈도 연산자

비교 연산자와 정수로 [최근 및 빈도](../../features/segments/recency-and-frequency.md) 간격을 설정합니다. [!UICONTROL Segment Builder] 는  &lt;> (보다 큼), ==(같음) 등과 같은 표준 표현식을 사용합니다. 하지만 허용되는 연산자 유형은 최근 또는 빈도를 설정할 때 달라집니다. 아래 표에는 허용되는 최근/빈도 연산자가 나와 있습니다.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 최근 연산자 </th> 
   <th colname="col2" class="entry"> 주파수 연산자 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=(보다 큼/같음) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;&gt; </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=(보다 큼/같음) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;&gt; </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">==(같음) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [최신성 및 빈도](../../features/segments/recency-and-frequency.md)
>* [트레이트 및 세그먼트 빌더의 부울 표현식](../../reference/boolean-expressions-tsb.md)
>* [TraitBuilder에서 비교 연산자 사용](../../features/traits/trait-comparison-operators.md)
>* [TraitBuilder 표현식의 작업 순서](../../features/traits/trait-operator-precedence.md)

