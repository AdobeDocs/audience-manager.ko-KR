---
description: 대상 빌더에서 구성 섹션에는 쿠키 도메인 및 데이터 게시 대상 필드가 포함되어 있습니다. 규칙을 만들어 대상이 쿠키를 설정하거나 쿠키를 반환하는지 결정할 수 있습니다. 쿠키 도메인 및 데이터 게시 서로 독립적으로 작동하며 선택 사항입니다. 둘 중 하나를 사용하지 않고 쿠키 대상을 만들 수 있습니다.
seo-description: 대상 빌더에서 구성 섹션에는 쿠키 도메인 및 데이터 게시 대상 필드가 포함되어 있습니다. 규칙을 만들어 대상이 쿠키를 설정하거나 쿠키를 반환하는지 결정할 수 있습니다. 쿠키 도메인 및 데이터 게시 서로 독립적으로 작동하며 선택 사항입니다. 둘 중 하나를 사용하지 않고 쿠키 대상을 만들 수 있습니다.
seo-title: 쿠키 대상에 대한 옵션 설정
solution: Audience Manager
title: 쿠키 대상에 대한 옵션 설정
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 7%

---


# 쿠키 대상에 대한 옵션 설정 {#optional-settings-cookies}

[!UICONTROL Destination Builder]에서 [!UICONTROL Configuration section]에는 [!UICONTROL Cookie Domain] 및 [!UICONTROL Publish Data To] 필드가 포함되어 있습니다. 규칙을 만들어 대상이 쿠키를 설정하거나 쿠키를 반환하는지 결정할 수 있습니다. [!UICONTROL Cookie Domain] 서로 독립적으로  [!UICONTROL Publish Data To] 작업하며 선택 사항입니다. 둘 중 하나를 사용하지 않고 쿠키 대상을 만들 수 있습니다.

## 쿠키 도메인:구문 및 예 {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 쿠키 도메인 </th> 
   <th colname="col2" class="entry"> 설명 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>구문</b> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> 쿠키 도메인</span> 필드는 지정된 도메인 또는 모든 도메인에서 쿠키를 설정할 수 있는 간단한 텍스트 문자열을 허용합니다. 이 기능을 사용하는 경우: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">각 쿠키 대상에 대해 하나의 도메인만 설정합니다. <span class="wintitle"> 쿠키 도메인</span> 필드에 여러 도메인을 입력하지 마십시오. 다른 <span class="wintitle"> 대상</span>을(를) 대신 만듭니다. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">와일드카드 문자를 사용하지 마십시오. </li> 
     </ul> </p> <p> 모든 도메인에 쿠키를 설정하려면 <span class="wintitle"> 쿠키 도메인</span> 필드를 비워 두십시오. 기본 설정입니다. </p> <p>특정 도메인 및 하위 도메인에서 쿠키를 설정하려면 </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C"><span class="wintitle"> 쿠키 도메인</span> 필드에 도메인 이름을 입력합니다. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">마침표로 도메인 이름을 시작합니다. 예, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0"><code> https://www</code> 접두사는 필수가 아닙니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>예</b> </p> </td> 
   <td colname="col2"> <p>예를 들어 sports.com이라는 가상 사이트가 있다고 가정해 보겠습니다. Sports.com에는 골프, 야구 및 축구 분야의 도메인이 있습니다. 모든 스포츠 도메인에서 쿠키를 설정하려면 아래와 같이 <span class="wintitle"> 쿠키 도메인</span> 상자에 쿠키를 입력합니다. </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>이는 <span class="keyword"> Audience Manager</span>이 <code><i>something</i></code>.sports.com 패턴이 포함된 모든 도메인에 쿠키를 설정하도록 지시합니다. 보다 복잡한 예는 아래를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 복잡한 쿠키 도메인 예

이러한 예는 [!DNL Audience Manager]이(가) [!UICONTROL Cookie Domain] 옵션이 구성되는 방식을 기반으로 쿠키를 설정하는지 여부를 보여 줍니다.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 웹 사이트 </th> 
   <th colname="col2" class="entry">쿠키 도메인:.sports.com <p>쿠키 집합 </p> </th> 
   <th colname="col3" class="entry">쿠키 도메인:.golf.sports.com <p>쿠키 집합 </p> </th> 
   <th colname="col4" class="entry">쿠키 도메인:비어 있음 <p>쿠키 집합 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> 예 </td> 
   <td colname="col3"> 아니요 </td> 
   <td colname="col4"> 예 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> 예 </td> 
   <td colname="col3"> 예 </td> 
   <td colname="col4"> 예 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> 예 </td> 
   <td colname="col3"> 아니요 </td> 
   <td colname="col4"> 예 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> 아니요 </td> 
   <td colname="col3"> 아니요 </td> 
   <td colname="col4"> 예 </td> 
  </tr> 
 </tbody> 
</table>

## {#publish-data-to}에 데이터 게시

도메인이 선택한 옵션에 의해 설정된 기준을 충족하는 경우 [!UICONTROL Publish Data To] 설정은 쿠키를 반환합니다. 옵션은 다음과 같습니다.

* **[!UICONTROL All of our domains]**:(기본값) 모든 도메인 [!DNL cookie] 에 대한 값을 반환합니다.
* **[!UICONTROL Only the selected domains]**:도메인 목록에서 선택한 도메인에 대해서만 쿠키를 반환합니다.
* **[!UICONTROL All of our domains except the selected domains]**:선택한 도메인이 수신되지 않도록  [!DNL cookie]합니다. 다른 모든 도메인은 [!DNL cookie]을 받을 수 있습니다.

>[!MORELIKETHIS]
>
>* [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md)