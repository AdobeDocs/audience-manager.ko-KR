---
description: 열 헤더 레이블이 정의되었습니다.
seo-description: 열 헤더 레이블이 정의되었습니다.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Bulk Management Tools Glossary
uuid: 4658 A 6 BC -9515-4 D 31-9715-0084760 B 0 CEA
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Management Tools Glossary{#bulk-management-tools-glossary}

열 헤더 레이블이 정의되었습니다.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[!UICONTROL Bulk Management Tools]*는에서* 지원되지 [!DNL Audience Manager]않습니다. 이 도구는 편의를 위해 제공되며 편의를 위해 제공됩니다. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [UI에](../../features/administration/administration-overview.md) 할당된 RBAC 그룹 권한이 [!DNL Audience Manager] 에서 [!UICONTROL Bulk Management Tools]인정됩니다.

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 열 헤더 </th> 
   <th colname="col2" class="entry"> 정의 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Datasourceid</span> </p> </td> 
   <td colname="col2"> <p>The ID of a <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> data source</a> you want to return or assign in bulk. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Derivedsignalid</span> </p> </td> 
   <td colname="col2"> <p><a href="../../features/derived-signals.md"> 파생된 신호</a> ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 설명</span> </p> </td> 
   <td colname="col2"> <p>개체에 제공할 수 있는 간략하고 유용한 설명입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationid</span> </p> </td> 
   <td colname="col2"> <p>The ID of the <a href="../../features/destinations/destinations.md"> destination</a> you want to map or delete. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Destinationmappingid</span> </p> </td> 
   <td colname="col2"> <p>세그먼트에 매핑할 때 세그먼트에 지정된 특수 ID 입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Folderid</span> </p> </td> 
   <td colname="col2"> <p>세그먼트 또는 트레이트 폴더의 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> 이름</span> </p> </td> 
   <td colname="col2"> <p>작업 중인 개체의 이름입니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Parentfolderid</span> </p> </td> 
   <td colname="col2"> <p>다른 폴더가 들어 있는 세그먼트 또는 트레이트 폴더의 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> SID</span> </p> </td> 
   <td colname="col2"> <p>세그먼트 ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcekey</span> </p> </td> 
   <td colname="col2"> <p>Signals are bits of data passed in to <span class="keyword"> Audience Manager</span> based on user activity. These are transmitted as <a href="../../reference/key-value-pairs-explained.md"> key-value pairs</a>. 소스 키는 변경되지 않는 상수입니다. 변경할 수 있는 소스 값을 분류하는 데 도움이 됩니다. <a href="../../features/derived-signals.md"> 파생된 신호를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Sourcevalue</span> </p> </td> 
   <td colname="col2"> <p>The source value is a variable passed in as part a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>세그먼트를 대상으로 보낼 수 있는 시기를 나타냅니다. <tt>YYYY-MM-DD</tt> 형식을 사용합니다. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetkey</span> </p> </td> 
   <td colname="col2">파생된 신호에 사용된 키입니다. <a href="../../features/derived-signals.md"> 파생된 신호를 참조하십시오</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Targetvalue</span> </p> </td> 
   <td colname="col2"> <p>파생된 신호 키와 함께 전달된 값입니다. <a href="../../features/derived-signals.md"> 파생된 신호를 참조하십시오</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitalias</span> </p> </td> 
   <td colname="col2"> <p>비쿠키 기반 대상에 전달된 ID. For a cookie-based destination, this is the key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traitrule/segmentrule</span> </p> </td> 
   <td colname="col2"> <p>데이터를 수집하는 데 사용되는 실제 트레이트 또는 세그먼트 규칙입니다. A bulk request returns the rules created in <span class="keyword"> Audience Manager</span> with the <a href="../../features/traits/about-trait-builder.md"> trait rule builder</a> or the <a href="../../features/segments/segment-builder.md"> segment rule builder</a>. 이러한 도구를 사용하여 규칙을 작성하고 트레이트 또는 트레이트를 업데이트할 때 규칙을 일괄 적용할 수도 있습니다. </p> <p>See also, <a href="../../reference/bulk-management-tools/bulk-rules.md"> Create or Update Trait Rules and Segment Rules</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Traittype</span> </p> </td> 
   <td colname="col2"> <p>특성 유형을 식별하는 문자열입니다. 옵션은 다음과 같습니다. </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> rule_ based_ trait</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> on_ boarded_ trait </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> 세그먼트</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>사용자가 세그먼트에 대한 자격을 부여받을 때 DIL에 의해 실행된 픽셀. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> Valuealias</span> </p> </td> 
   <td colname="col2"> <p>The key in a <a href="../../reference/key-value-pairs-explained.md"> key-value pair</a> passed to a cookie destination. </p> </td> 
  </tr> 
 </tbody> 
</table>

