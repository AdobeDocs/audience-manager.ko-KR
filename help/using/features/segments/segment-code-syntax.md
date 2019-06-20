---
description: 세그먼트 빌더를 사용하면 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 작성할 수 있습니다. 이 기능에 액세스하려면 트레이트 패널에서 세그먼트 표현식 (코드 뷰) 탭을 클릭합니다.
seo-description: 세그먼트 빌더를 사용하면 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 작성할 수 있습니다. 이 기능에 액세스하려면 트레이트 패널에서 세그먼트 표현식 (코드 뷰) 탭을 클릭합니다.
seo-title: 세그먼트 표현식 편집기에서 사용된 코드 구문
solution: Audience Manager
title: 세그먼트 표현식 편집기에서 사용된 코드 구문
uuid: 7 B 4 B 06 CA -7879-4501-8 BA 7-B 2 B 6467 B 8 A 3 B
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Code Syntax Used in the Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 만들 수 있습니다. Click the **[!UICONTROL Segment Expressions (Code View)]** tab in the [!UICONTROL Traits] panel to access this feature.

## 표현식 빌더 코드 구문

드래그 앤 드롭 기능을 사용하는 대신 코드가 있는 세그먼트에 트레이트 규칙을 추가할 수 있습니다. 코딩 시 예제의 기울임꼴 요소를 실제 표현식 또는 값으로 바꿉니다. 기본 코드는 다음 구문을 사용합니다.

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>[!DNL Boolean][!UICONTROL OR] 기본적으로 조건은 표현식 *내의* 여러 트레이트에 적용됩니다.

### 부울 연산자와 세그먼트 연결

To build groups of segments, wrap the frequency function in parenthesis and set the relationship *between* each expression with a [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL NOT]).

### 매개 변수

>[!NOTE]
>
>별도의 언급이 없는 한 모든 매개 변수가 필요합니다.

| 이름 또는 변수 | 설명 |
|---|---|
| `FREQUENCY` | 표현식의 앞에 와야 하는 리터럴입니다. |
| ` [`&lt;`traitID`&gt;`T]` | An array of trait IDs followed by the letter `T`. 여러 트레이트를 쉼표로 구분합니다. 예, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(선택 사항)* 세그먼트 트레이트에 대한 최근 규칙을 설정합니다. The letter `D` indicates recency in days. |
| ` <Frequency Operator><Numeric Value>` | 세그먼트에 있는 트레이트에 대한 빈도 규칙을 설정합니다. |

### 최근 및 빈도 연산자 허용

Set [recency and frequency](../../features/segments/recency-and-frequency.md) intervals with a comparison operator and an integer. [!UICONTROL Segment Builder] &lt; (보다 작음), &gt; (보다 큼), = = (등호) 등의 표준 표현식을 사용합니다. 하지만 최근 또는 빈도를 설정할 때 허용되는 연산자 유형은 달라집니다. 아래 표에는 허용된 최근/빈도 연산자가 나와 있습니다.

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
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (크거나 같음) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt; = (작거나 같음) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (크거나 같음) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt; = (작거나 같음) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">= = (같음) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ like_ this]
>
>* [최근 및 빈도](../../features/segments/recency-and-frequency.md)
>* [트레이트 및 세그먼트 빌더에서 부울 표현식](../../reference/boolean-expressions-tsb.md)
>* [Traitbuilder에서 비교 연산자를 사용한 작업](../../features/traits/trait-comparison-operators.md)
>* [Traitbuilder 표현식의 작업 순서](../../features/traits/trait-operator-precedence.md)

