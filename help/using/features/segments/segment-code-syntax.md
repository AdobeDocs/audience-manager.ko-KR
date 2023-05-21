---
description: 세그먼트 빌더를 사용하면 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 작성할 수 있습니다. 이 기능에 액세스하려면 트레이트 패널에서 세그먼트 표현식(코드 보기) 탭을 클릭합니다.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: 세그먼트 표현식 편집기에 사용되는 코드 구문
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 10%

---

# 세그먼트 표현식 편집기에 사용되는 코드 구문 {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] 코드 편집기를 사용하여 세그먼트에 대한 트레이트 규칙을 작성할 수 있습니다. 다음을 클릭합니다. **[!UICONTROL Segment Expressions (Code View)]** 의 탭 [!UICONTROL Traits] 패널 을 클릭하여 이 기능에 액세스합니다.

## 표현식 빌더 코드 구문

끌어다 놓기 기능을 사용하는 대신 코드로 세그먼트에 트레이트 규칙을 추가할 수 있습니다. 코딩할 때 예제의 기울임꼴 요소를 실제 표현식 또는 값으로 바꿉니다. 기본 코드에서는 다음 구문을 사용합니다.

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>기본적으로, [!DNL Boolean] [!UICONTROL OR] 조건이 여러 트레이트에 적용됨 *다음 범위 내* 표현식.

### 부울 연산자로 세그먼트 조인

세그먼트 그룹을 작성하려면 빈도함수를 괄호로 묶고 관계를 설정합니다 *사이* 각 표현식에 [!DNL Boolean] 연산자 ([!UICONTROL AND], [!UICONTROL OR], 및 [!UICONTROL NOT]).

### 매개 변수

>[!NOTE]
>
>별도로 명시되지 않는 한 모든 매개 변수가 필요합니다.

| 이름 또는 변수 | 설명 |
|---|---|
| `FREQUENCY` | 표현식 앞에 와야 하는 리터럴입니다. |
| ` [`&lt;`traitID`>`T]` | 문자 뒤에 오는 트레이트 ID의 배열 `T`. 여러 트레이트는 쉼표로 구분하십시오. 예, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(선택 사항)* 세그먼트의 트레이트에 대한 최신성 규칙을 설정합니다. 편지 `D` 최신성을 일 단위로 나타냅니다. |
| ` <Frequency Operator><Numeric Value>` | 세그먼트의 트레이트에 대한 빈도 규칙을 설정합니다. |

### 허용된 최신성 및 빈도 연산자

설정 [최신성 및 빈도](../../features/segments/recency-and-frequency.md) 비교 연산자 및 정수가 포함된 간격. [!UICONTROL Segment Builder] &lt;(작음), >(큼), ==(같음) 등과 같은 표준 표현식을 사용합니다. 그러나 최신성이나 빈도를 설정할 때는 허용된 연산자 유형이 달라집니다. 아래 표에는 허용되는 최신성/빈도 연산자가 나와 있습니다.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 최신성 연산자 </th> 
   <th colname="col2" class="entry"> 빈도 연산자 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;=(크거나 같음) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (보다 작거나 같음) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;=(크거나 같음) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (보다 작거나 같음) </li> 
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

