---
description: 대상 빌더에서 구성 섹션에는 쿠키 도메인이 포함되고 필드에 데이터가 게시됩니다. 이를 통해 대상이 쿠키를 설정하거나 쿠키를 반환할 것인지를 결정하는 규칙을 만들 수 있습니다. 쿠키 도메인을 만들고 데이터를 게시하면 서로 독립적으로 작동합니다. 쿠키 대상을 사용하지 않고 쿠키 대상을 만들 수 있습니다.
seo-description: 대상 빌더에서 구성 섹션에는 쿠키 도메인이 포함되고 필드에 데이터가 게시됩니다. 이를 통해 대상이 쿠키를 설정하거나 쿠키를 반환할 것인지를 결정하는 규칙을 만들 수 있습니다. 쿠키 도메인을 만들고 데이터를 게시하면 서로 독립적으로 작동합니다. 쿠키 대상을 사용하지 않고 쿠키 대상을 만들 수 있습니다.
seo-title: 쿠키 대상에 대한 선택적 설정
solution: Audience Manager
title: 쿠키 대상에 대한 선택적 설정
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---


# 쿠키 대상에 대한 선택적 설정 {#optional-settings-cookies}

에서 [!UICONTROL Destination Builder]에 [!UICONTROL Configuration section][!UICONTROL Cookie Domain] AND [!UICONTROL Publish Data To] 필드를 포함합니다. 이를 통해 대상이 쿠키를 설정하거나 쿠키를 반환할 것인지를 결정하는 규칙을 만들 수 있습니다. [!UICONTROL Cookie Domain] 서로 독립적으로 [!UICONTROL Publish Data To] 작업할 수 있으며 선택 사항입니다. 쿠키 대상을 사용하지 않고 쿠키 대상을 만들 수 있습니다.

## 쿠키 도메인: 구문 및 예제 {#cookie-domain-syntax}

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
   <td colname="col2"> <p><span class="wintitle"> 쿠키 도메인</span> 필드는 지정된 도메인 또는 모든 도메인에서 쿠키를 설정할 수 있는 간단한 텍스트 문자열을 수락합니다. 이 기능을 사용할 때: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">각 쿠키 대상에 대해 하나의 도메인만 설정합니다. <span class="wintitle"> [쿠키 도메인</span> ] 필드에 여러 도메인을 입력하지 마십시오. 다른 <span class="wintitle"> 대상을</span> 대신 만듭니다. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">와일드카드 문자는 사용하지 마십시오. </li> 
     </ul> </p> <p> 모든 도메인에서 쿠키를 설정하려면 <span class="wintitle"> 쿠키 도메인</span> 필드를 비워 두십시오. 기본 설정입니다. </p> <p>특정 도메인 및 하위 도메인에서 쿠키를 설정하려면: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C"><span class="wintitle"> 쿠키 도메인</span> 필드에 도메인 이름을 입력합니다. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">마침표로 도메인 이름을 시작합니다. 예를 들면 <code> .somedomain.com</code>입니다. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0"><code> https://www</code> 접두사는 필요하지 않습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>예</b> </p> </td> 
   <td colname="col2"> <p>간단한 예로 Sports. com 이라는 가상의 사이트가 있습니다. Sports.com 에는 골프, 야구 및 미식축구를 위한 도메인이 있습니다. 모든 스포츠 도메인의 쿠키를 설정하려면, 아래와 같이 <span class="wintitle"> 쿠키 도메인</span> 상자에 쿠키를 입력합니다. </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>그러면 <span class="keyword"> Audience Manager</span> 에서 something. sports. com 패턴이 <code><i>포함된 모든 도메인에 쿠키를 설정하도록 합니다</i></code>. 보다 복잡한 예는 아래를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 복잡한 쿠키 도메인 예제

이러한 예에서는 옵션이 구성되는 방법에 따라 쿠키를 설정할 것인지 [!DNL Audience Manager][!UICONTROL Cookie Domain] 여부를 보여줍니다.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 웹 사이트 </th> 
   <th colname="col2" class="entry">쿠키 도메인: .sports.com <p>쿠키 세트 </p> </th> 
   <th colname="col3" class="entry">쿠키 도메인: .golf.sports.com <p>쿠키 세트 </p> </th> 
   <th colname="col4" class="entry">쿠키 도메인: blank <p>쿠키 세트 </p> </th> 
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

## 데이터 게시 대상 {#publish-data-to}

도메인이 선택한 옵션에 의해 설정된 기준을 충족하는 경우 [!UICONTROL Publish Data To] 설정이 쿠키를 반환합니다. 옵션은 다음과 같습니다.

* **[!UICONTROL All of our domains]**: (기본값) 모든 도메인에 [!DNL cookie] 대해 A를 반환합니다.
* **[!UICONTROL Only the selected domains]**: 도메인 목록에서 선택한 도메인에 대해서만 쿠키를 반환합니다.
* **[!UICONTROL All of our domains except the selected domains]**: 선택한 도메인이 A [!DNL cookie]를 받지 못하게 합니다. 다른 모든 도메인은 A [!DNL cookie]를 받을 수 있습니다.

>[!MORE_ like_ this]
>
>* [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md)