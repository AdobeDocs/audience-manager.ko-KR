---
description: 대상 빌더의 구성 섹션에는 쿠키 도메인 및 게시 데이터 필드가 포함되어 있습니다. 이를 통해 대상에서 쿠키를 설정하는지 또는 쿠키를 반환하는지 여부를 결정하는 규칙을 만들 수 있습니다. Cookie Domain 및 Publish Data To 는 서로 독립적으로 작동하며 선택 사항입니다. 둘 중 하나를 사용하지 않고 쿠키 대상을 만들 수 있습니다.
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: 쿠키 대상에 대한 옵션 설정
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 4%

---

# 쿠키 대상에 대한 옵션 설정 {#optional-settings-cookies}

[!UICONTROL Destination Builder]에서 [!UICONTROL Configuration section]에 [!UICONTROL Cookie Domain] 및 [!UICONTROL Publish Data To] 필드가 있습니다. 이를 통해 대상에서 쿠키를 설정하는지 또는 쿠키를 반환하는지 여부를 결정하는 규칙을 만들 수 있습니다. [!UICONTROL Cookie Domain] 및 [!UICONTROL Publish Data To]은(는) 서로 독립적으로 작동하며 선택 사항입니다. 둘 중 하나를 사용하지 않고 쿠키 대상을 만들 수 있습니다.

## 쿠키 도메인: 구문 및 예 {#cookie-domain-syntax}

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
   <td colname="col2"> <p><span class="wintitle"> 쿠키 도메인</span> 필드는 지정된 도메인 또는 모든 도메인에 대한 쿠키를 설정할 수 있는 간단한 텍스트 문자열을 허용합니다. 이 기능을 사용하는 경우: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">각 쿠키 대상에 대해 하나의 도메인만 설정합니다. <span class="wintitle"> 쿠키 도메인</span> 필드에 여러 도메인을 입력하지 마십시오. 대신 다른 <span class="wintitle"> 대상</span>을(를) 만듭니다. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">와일드카드 문자를 사용하지 마십시오. </li> 
     </ul> </p> <p> 모든 도메인에서 쿠키를 설정하려면 <span class="wintitle"> 쿠키 도메인</span> 필드를 비워 둡니다. 기본 설정입니다. </p> <p>특정 도메인 및 하위 도메인에 대해 쿠키를 설정하려면 다음을 수행합니다. </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C"><span class="wintitle"> 쿠키 도메인</span> 필드에 도메인 이름을 입력합니다. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">도메인 이름을 마침표로 시작합니다. 예: <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0"><code> https://www</code> 접두사는 필요하지 않습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>예</b> </p> </td> 
   <td colname="col2"> <p>간단한 예로 sports.com이라는 가상의 사이트가 있다고 가정해 보겠습니다. Sports.com 에는 골프, 야구 및 축구를 위한 도메인이 있습니다. 모든 스포츠 도메인에서 쿠키를 설정하려면 아래와 같이 <span class="wintitle"> 쿠키 도메인</span> 상자에 해당 쿠키를 입력합니다. </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>이렇게 하면 <span class="keyword"> Audience Manager</span>이(가) <code><i>something</i></code>.sports.com 패턴을 포함하는 모든 도메인에 쿠키를 설정합니다. 보다 복잡한 예제 세트는 아래를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 복잡한 쿠키 도메인 예

이러한 예는 [!DNL Audience Manager]이(가) [!UICONTROL Cookie Domain] 옵션이 구성되는 방식에 따라 쿠키를 설정하는지 여부를 보여 줍니다.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 웹 사이트 </th> 
   <th colname="col2" class="entry">쿠키 도메인: .sports.com <p>쿠키 집합 </p> </th> 
   <th colname="col3" class="entry">쿠키 도메인: .golf.sports.com <p>쿠키 집합 </p> </th> 
   <th colname="col4" class="entry">쿠키 도메인: 비어 있음 <p>쿠키 집합 </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> 예 </td> 
   <td colname="col3"> 아니오 </td> 
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
   <td colname="col3"> 아니오 </td> 
   <td colname="col4"> 예 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> 아니오 </td> 
   <td colname="col3"> 아니오 </td> 
   <td colname="col4"> 예 </td> 
  </tr> 
 </tbody> 
</table>

## 데이터 게시 위치 {#publish-data-to}

도메인이 선택한 옵션에서 설정한 기준을 충족하면 [!UICONTROL Publish Data To] 설정이 쿠키를 반환합니다. 옵션은 다음과 같습니다.

* **[!UICONTROL All of our domains]**: (기본값) 모든 도메인에 대해 [!DNL cookie]을(를) 반환합니다.
* **[!UICONTROL Only the selected domains]**: 도메인 목록에서 선택한 도메인에 대해서만 쿠키를 반환합니다.
* **[!UICONTROL All of our domains except the selected domains]**: 선택한 도메인이 [!DNL cookie]을(를) 받지 못하도록 합니다. 다른 모든 도메인은 [!DNL cookie]을(를) 받을 수 있습니다.

>[!MORELIKETHIS]
>
>* [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md)
