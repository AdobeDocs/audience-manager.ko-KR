---
description: 대상 랜딩 페이지에는 모든 URL, 쿠키 및 서버 대 서버 대상이 나열됩니다. 이 콘솔에서는 대상을 만들고, 편집하고, 검색하고, 보고할 수 있는 기능을 제공합니다. 랜딩 페이지는 대상 데이터 > 대상에 있습니다.
seo-description: 대상 랜딩 페이지에는 모든 URL, 쿠키 및 서버 대 서버 대상이 나열됩니다. 이 콘솔에서는 대상을 만들고, 편집하고, 검색하고, 보고할 수 있는 기능을 제공합니다. 랜딩 페이지는 대상 데이터 > 대상에 있습니다.
seo-title: 대상 관리
solution: Audience Manager
title: 대상 관리
uuid: 6 b 66 FF 42-0075-49 A 7-A 58 F -7 F 8 EA 2295 FDC
translation-type: tm+mt
source-git-commit: 1d516c49a16c38adcc22827dc254da1ebada0734

---


# Manage Destinations {#manage-destinations}

[!UICONTROL Destination] 랜딩 페이지에는 모든 [!DNL URL]쿠키, 쿠키 및 서버 간 대상이 나열됩니다. 이 콘솔에서는 대상을 만들고, 편집하고, 검색하고, 보고할 수 있는 기능을 제공합니다. The landing page is located in **[!UICONTROL Audience Data > Destinations]**.

## Default Landing Page {#default-landing-page}

<!-- destinations-home.xml -->

기본 랜딩 페이지에는 유형에 따라 대상이 나열됩니다. 다음 네 개의 사용 가능한 탭을 사용하여 대상을 필터링할 수 있습니다.

* **** 모두: 모든 유형의 대상을 표시합니다.
* **Adobe Experience Cloud**: 다른 Adobe Experience Cloud 솔루션에 데이터를 전송하는 대상을 보여줍니다. 현재 유일하게 지원되는 옵션은 Adobe Analytics 입니다. See [Configure an Analytics Destination](/help/using/features/destinations/create-analytics-destination.md).
* **통합 플랫폼**: 사용자 기반 및 장치 기반 대상 (서버간 대상) 를 표시합니다. 현재 사용자 기반 대상은 선택한 고객에게만 사용할 수 있는 베타 기능입니다.
* **사용자** 정의: 쿠키 및 URL 대상을 표시합니다.


![](assets/destinations-landing.png)

## Addressable Audiences Landing Page {#audiences-landing-page}

To see audience data and match rates for your server-to-server destination, select **[!UICONTROL Integrated Platforms > Device-Based]**.

For more information about the displayed information, see [Addressable Audiences Interface](/help/using/features/addressable-audiences.md#addressable-audience-interface).

![](/help/using/features/assets/addressable-audiences-landing.png)

## Destination Builder {#destination-builder}

[!UICONTROL Destination Builder] 쿠키 기반 [!DNL URL] 또는 대상을 만들 수 있습니다. You cannot create server-to-server ([!DNL S2S]) destinations with [!UICONTROL Destination Builder], but you can manage their segment mappings. [!DNL S2S] 대상을 설정하려면 컨설턴트에게 문의하십시오. [!UICONTROL Destination Builder]**[!UICONTROL Audience Data > Destinations]** 에 있습니다.

### Destination Builder Settings {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] 다음 섹션과 설정으로 구성됩니다.

| [!UICONTROL Destination Builder] 섹션 | 용도 |
|--- |--- |
| 기본 정보 | Used to name the destination, describe it, and select destination type ([!DNL URL] or [!DNL cookie]), and platform (all, [!DNL Android], browser, or [!DNL iOS]). |
| 구성 | Includes controls for: <br/><ul><li>Passing in key-value data to [!DNL URL] destinations. 데이터를 개별 또는 직렬화된 키-값 쌍으로 보낼 수 있습니다. For details see, [Destination Serialization](../../features/destinations/key-value-pairs.md#destination-serialized) and [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md). </li><li>쿠키 이름, 도메인, 크기, 만료 간격, 데이터 형식 등과 같은 쿠키 대상의 요소</li></ul> |
| 세그먼트 매핑 | 보고서에: <br/><ul><li>모든 대상 유형과 연관된 세그먼트를 검색, 추가 및 관리합니다. </li><li>Set delivery priorities on individual segments (for [!DNL cookie]-based segments only).</li></ul> |

### Data Delivery Methods {#data-delivery-methods}

[!DNL URL] 정보를 문자열을 통해 전달하거나, 브라우저에 [!DNL cookie]쓰거나, 오프라인 서버 간 데이터 전송을 통해 대상을 대상으로 전달할 수 있습니다.

* [!DNL URL] 또한 쿠키 기반의 대상은 사용자가 페이지에서 작업을 수행하면서 동기적으로 데이터를 전송합니다.
* 서버 간 데이터 전송은 비동기적이며 사용자가 페이지를 떠난 후에도 발생할 수 있습니다. 선택하는 전달 유형은 비즈니스 요구 사항과 특정 데이터 파트너가 데이터를 원하는 방법에 따라 달라집니다.

See [How to Choose a Destination Type](../../features/destinations/destinations.md) for more information.

>[!MORE_ like_ this]
>
>* [쿠키 대상 만들기](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [URL 대상 만들기](../../features/destinations/manage-destinations.md#configure-url-destination)


## Configure a Cookie Destination {#create-cookie-destination}

쿠키 대상은 사용자 브라우저의 쿠키에 데이터를 반환하고 씁니다. 쿠키에는 페이지에 대한 액세스 권한이 있는 다른 플랫폼에서 읽을 수 있는 데이터가 포함되어 있습니다. Follow these instructions to create a cookie destination with [!UICONTROL Destination Builder].

<!-- create-cookie-destination.xml -->

To create a new cookie destination, go to **[!UICONTROL Audience Data > Destinations > Create New Destination]** and complete the sections as described below.

### 기본 정보 {#basic-information}

이 섹션에는 쿠키 대상 생성 프로세스를 시작하는 필드와 옵션이 포함되어 있습니다. 이 섹션을 완료하려면:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
2. 대상의 이름을 지정합니다. 약자 및 특수 문자를 사용하지 마십시오.
3. *(선택 사항)* 대상을 설명합니다. 간결한 설명은 대상에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
4. **[!UICONTROL Category]** 목록에서 **[!UICONTROL Custom]** 를 선택합니다.
5. **[!UICONTROL Environment]** 목록에서 **[!UICONTROL Browser]** 를 선택합니다. Android 또는 iOS 앱과 같은 기본 모바일 환경의 경우 쿠키 대상을 구성할 수 없습니다.
6. **[!UICONTROL Type]** 목록에서 **[!UICONTROL Cookie]** 를 클릭합니다.
7. *(선택 사항)* **[!UICONTROL Auto-fill Destination Mapping]** 를 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL Segment ID]**: 세그먼트 ID를 자동으로 추가하여 대상에 보냅니다.
   * **[!UICONTROL Integration Code Value]**: 세그먼트 통합 코드를 자동으로 추가하고 대상 매핑에 전송합니다. 통합 코드는 고객이 생성 및 사용하는 고유한 식별자입니다. 최대 255 자로 제한됩니다.
8. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-cookies}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a cookie destination. 데이터 내보내기 컨트롤을 사용하지 않으면 이 단계를 건너뜁니다. 이 섹션을 완료하려면:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. 클릭 **[!UICONTROL Save]**.

### 구성 {#configuration}

이 섹션에는 대상에 대한 쿠키를 설정할 수 있는 필드와 옵션이 포함되어 있습니다.

>[!NOTE]
>
>[!DNL Audience Manager] 대상 쿠키에 기록된 데이터를 인코딩합니다. For example, spaces are encoded as `%20` and semicolons are encoded as `%3B`.

이 섹션을 완료하려면:

1. Click **[!UICONTROL Configuration]** to expose the controls
1. 쿠키 이름을 지정합니다. 약자 및 특수 문자를 사용하지 마십시오.
1. 데이터 형식 옵션을 선택합니다. 이러한 옵션을 사용하면 세그먼트를 대상으로 보내는 키-값 쌍에 대한 구분 기호 및 구분 기호를 선택할 수 있습니다. 형식 옵션은 다음과 같습니다.
   * **단일 키:** 키-값 쌍의 키를 설정할 수 있습니다. You&#39;ll set the value after you select a segment in the [!UICONTROL Segment Mappings] section below.
   * **Multi Key:** 키-값 쌍의 키와 값을 설정할 수 있습니다. 아래의 세그먼트 매핑 섹션에서 세그먼트를 선택한 후에 키-값 쌍을 만듭니다.
See [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md) for more information about these data elements.
1. 클릭 **[!UICONTROL Save]**.

기타 모든 설정은 선택 사항입니다. **[!UICONTROL Cookie Domain]** AND **[!UICONTROL Publish data to]** 설정에 대한 자세한 내용은 쿠키 대상에 [대한 선택적 설정을 참조하십시오](../../features/destinations/manage-destinations.md#optional-settings-cookies).

### Segment Mappings {#segments-mapping}

이 섹션에서는 세그먼트를 검색하고 대상에 추가할 수 있습니다. 이 섹션을 완료하려면:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. **[!UICONTROL Search and Add Segments]** 상자에 세그먼트 이름을 입력하거나 클릭하여 **[!UICONTROL Browse All Segments]** 사용 가능한 세그먼트 목록을 찾습니다.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. [!UICONTROL Edit Mapping] 대화 상자에서 다음을 수행합니다.
   * **[!UICONTROL Mapping]** 위의 구성 섹션에 지정된 키에 대한 값을 설정할 수 있습니다.
   * **[!UICONTROL Publish from]** 대상에 대한 시작 및 종료 날짜를 설정할 수 있습니다. 종료 날짜가 비어 있으면 대상이 절대 만료되지 않습니다.
1. 클릭 **[!UICONTROL Save]**.
1. 클릭 **[!UICONTROL Done]**.

## Configure a URL Destination {#configure-url-destination}

[!DNL URL] 대상은 페이지에서 대상으로 픽셀 호출을 만듭니다. Follow these instructions to create a [!DNL URL] destination with [!UICONTROL Destination Builder].

<!-- create-url-destination.xml -->

[!DNL URL] 새 대상을 만들려면 아래 설명된 **[!UICONTROL Audience Data > Destinations > Create New Destination]** 대로 섹션으로 이동하여 완료합니다.

### 기본 정보 {#basic-info}

이 섹션에는 URL 대상 만들기 프로세스를 시작하는 필드와 옵션이 포함되어 있습니다. 이 섹션을 완료하려면:

1. Click **[!UICONTROL Basic Information]** to expose the controls.
1. 대상의 이름을 지정합니다. 약자 및 특수 문자를 사용하지 마십시오.
1. *(선택 사항)* 대상을 설명합니다. 간결한 설명은 대상에 대한 자세한 정보를 정의하거나 제공하는 효과적인 방법입니다.
1. **[!UICONTROL Category]** 목록에서 **[!UICONTROL Custom]** 를 선택합니다.
1. **[!UICONTROL Environment]** 목록에서 URL 대상을 트리거할 환경을 선택합니다.
1. **[!UICONTROL Type]** 목록에서 **[!UICONTROL URL]** 를 클릭합니다.
1. *(선택 사항)* **[!UICONTROL Auto-fill Destination Mapping]** 를 선택합니다. 옵션은 다음과 같습니다.
   * **[!UICONTROL Segment ID]**: 세그먼트 ID를 자동으로 추가하여 대상에 보냅니다.
   * **[!UICONTROL Integration Code Value]**: 세그먼트 통합 코드를 자동으로 추가하고 대상 매핑에 전송합니다. 통합 코드는 고객이 생성 및 사용하는 고유한 식별자입니다. 최대 255 자로 제한됩니다.
1. Click **[!UICONTROL Next]** to go to the [!UICONTROL Configuration] settings or click **[!UICONTROL Data Export Labels]** to apply export controls to the destination.

### Data Export Labels {#data-export-labels-dest}

This section contains options that apply [data export controls](../../features/data-export-controls.md) to a [!DNL URL] destination. 데이터 내보내기 컨트롤을 사용하지 않으면 이 단계를 건너뜁니다. 이 섹션을 완료하려면:

1. Click **[!UICONTROL Data Export Labels]** to expose the controls.
2. Select a label that corresponds to the data export control applied to the destination (see [Add Export Labels to a Destination](../../features/destinations/manage-destinations.md#add-data-export-labels) for details).
3. 클릭 **[!UICONTROL Save]**.

### 구성 {#configure-base-data}

This section contains options that let you set a base [!DNL URL] and data delimiters passed in by the [!DNL URL] string. 이 섹션은 선택 사항입니다. 이 섹션을 완료하려면:

1. Click **[!UICONTROL Configuration]** to expose the controls.
1. *(선택 사항)* 확인란을 **[!UICONTROL Serialize]** 선택합니다.
이렇게 하면 각 세그먼트에 대해 별도의 호출을 만들지 않고 세그먼트를 대상에 순차적으로 보낼 수 있습니다. 직렬화를 사용하면 데이터 전송을 효율적으로 수행할 수 있습니다. 이 확인란을 선택하면 URL 및 구분 기호 필드가 표시됩니다. For more information, see [Standard and Serial Key-Value Pairs](../../features/destinations/key-value-pairs.md).
1. If you select **[!UICONTROL Serialize]**, then you must also configure the URL and delimiter fields described below.

| 필드 | 설명 |
|--- |--- |
| 기본 URL | The base part of a standard `HTTP` [!DNL URL] that does not change. `%ALIAS%`[또한 자리 표시자 매크로를 기본 URL](../../features/destinations/destination-macros.md#destination-macros-defined) 에 추가해야 합니다. 예: `https://www.myCompany.com/%alias%...` |
| 보안 URL | The base part of a secure `HTTPS` [!DNL URL] that does not change. `%ALIAS%`[또한 자리 표시자 매크로를 기본 URL](../../features/destinations/destination-macros.md#destination-macros-defined) 에 추가해야 합니다. 예: `https://www.myCompany.com/%alias%...` |
| 구분 기호 | The symbol that separates the segment variables in the [!DNL URL] string. 일반적으로 쉼표 또는 세미콜론을 사용합니다. 이 정보를 대상 파트너로부터 얻습니다. |

### Segment Mappings {#segment-mappings}

이 섹션에서는 세그먼트를 검색하고 대상에 추가할 수 있습니다. 이 섹션을 완료하려면:

1. Click **[!UICONTROL Segment Mappings]** to expose the controls.
1. **[!UICONTROL Search and Add Segments]** 상자에 세그먼트 이름을 입력하거나 사용 가능한 세그먼트 **[!UICONTROL Browse All Segments]** 목록 찾아보기를 클릭합니다.
1. Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
1. [!UICONTROL Edit Mapping]:
   * **[!UICONTROL Mappings]**: 세그먼트에 사용되는 키-값 쌍을 제공합니다.
   * **[!UICONTROL Start Date]****[!UICONTROL End Date]** And: 대상에 대한 시작 날짜와 종료 날짜를 선택합니다. 종료 날짜가 비어 있으면 대상이 절대 만료되지 않습니다.
1. 클릭 **[!UICONTROL Done]**.

### Optional Settings for Cookie Destinations {#optional-settings-cookies}

In [!UICONTROL Destination Builder], the [!UICONTROL Configuration section] contains the [!UICONTROL Cookie Domain] and [!UICONTROL Publish Data To] fields. 이를 통해 대상이 쿠키를 설정하거나 쿠키를 반환할 것인지를 결정하는 규칙을 만들 수 있습니다. [!UICONTROL Cookie Domain] 서로 독립적으로 [!UICONTROL Publish Data To] 작업할 수 있으며 선택 사항입니다. 쿠키 대상을 사용하지 않고 쿠키 대상을 만들 수 있습니다.

## Cookie Domain: Syntax and Examples {#cookie-domain-syntax}

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
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">각 쿠키 대상에 대해 하나의 도메인만 설정합니다. <span class="wintitle"> [쿠키 도메인</span> ] 필드에 여러 도메인을 입력하지 마십시오. Create another <span class="wintitle"> Destination</span> instead. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">와일드카드 문자는 사용하지 마십시오. </li> 
     </ul> </p> <p> Leave the <span class="wintitle"> Cookie Domain</span> field blank to set a cookie on all domains. 기본 설정입니다. </p> <p>특정 도메인 및 하위 도메인에서 쿠키를 설정하려면: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C"><span class="wintitle"> 쿠키 도메인</span> 필드에 도메인 이름을 입력합니다. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">마침표로 도메인 이름을 시작합니다. For example, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0"><code> https://www</code> 접두사는 필요하지 않습니다. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>예</b> </p> </td> 
   <td colname="col2"> <p>간단한 예로 Sports. com 이라는 가상의 사이트가 있습니다. Sports.com 에는 골프, 야구 및 미식축구를 위한 도메인이 있습니다. To set a cookie in all the sports domains, you would type that in the <span class="wintitle"> Cookie Domain</span> box as shown below: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>This tells <span class="keyword"> Audience Manager</span> to set a cookie in any domain that contains the pattern <code><i>something</i></code>.sports.com. 보다 복잡한 예는 아래를 참조하십시오. </p> </td> 
  </tr> 
 </tbody> 
</table>

### 복잡한 쿠키 도메인 예제

These examples show you if [!DNL Audience Manager] will set a cookie based on how the [!UICONTROL Cookie Domain] option is configured.

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

## Publish Data To {#publish-data-to}

The [!UICONTROL Publish Data To] settings return a cookie if the domain meets the criteria set by the options you select. 옵션은 다음과 같습니다.

* **[!UICONTROL All of our domains]**: (기본값) 모든 도메인에 [!DNL cookie] 대해 A를 반환합니다.
* **[!UICONTROL Only the selected domains]**: 도메인 목록에서 선택한 도메인에 대해서만 쿠키를 반환합니다.
* **[!UICONTROL All of our domains except the selected domains]**: 선택한 도메인이 A [!DNL cookie]를 받지 못하게 합니다. All other domains can receive a [!DNL cookie].

>[!MORE_ like_ this]
>
>* [쿠키 대상 만들기](../../features/destinations/manage-destinations.md#create-cookie-destination)


## Add or Edit Segments for Server-to-Server Destinations {#add-edit-segments}

You can only add or edit segments for a server-to-server ([!DNL S2S]) destination. You cannot create [!DNL S2S] destinations with [!UICONTROL Destination Builder]. [!DNL S2S] 대상을 설정하려면 컨설턴트에게 문의하십시오. Follow these instructions to add or edit segments for an [!DNL S2S] destination.

<!-- destination-s2s-edit.xml -->

To add or edit segment mappings for an [!DNL S2S] destination:

1. **[!UICONTROL Audience Data > Destinations]** 이동. **통합된 플랫폼 &gt; 장치 기반을 선택하고** 작업할 [!DNL S2S] 대상을 찾습니다.
1. [!UICONTROL Action] 열에서 연필 아이콘을 클릭하여 대상을 편집합니다.
   * **[!UICONTROL Search and Add Segments]** 상자에 세그먼트 이름을 입력하거나 사용 가능한 세그먼트 **[!UICONTROL Browse All Segments]** 목록 찾아보기를 클릭합니다.
   * Click **[!UICONTROL Add Selected Segments]** when you find the segment you want to use. Adding a segment opens the [!UICONTROL Edit Mapping] window.
   *  [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: 이 대상에 사용되는 [키-값 쌍에](../../features/destinations/key-value-pairs.md) 대한 값을 설정합니다.
      * **[!UICONTROL Start Date]****[!UICONTROL End Date]** And: 대상에 대한 시작 날짜와 종료 날짜를 선택합니다. 종료 날짜가 비어 있으면 대상이 절대 만료되지 않습니다.
1. **[!UICONTROL Save]****[!UICONTROL Done]** 을 클릭하고를 클릭합니다.

## Add Data Export Labels to a Destination {#add-data-export-labels}

[!DNL Data Export Labels] 데이터 소스에 [!DNL Export Controls] 설정한 대로 작업합니다. [!DNL Data Export Labels] 세그먼트에 제한된 특성을 추가하고 세그먼트 데이터를 대상에 보내지 않도록 합니다. You can set multiple export labels to a new or existing [!DNL cookie] or [!DNL URL] destination.

>[!NOTE]
>
>To add an export label, you need administrator permissions *or* sufficient privileges to create or edit a destination.

<!-- t_export_labels.xml -->

대상에 내보내기 레이블을 추가하려면 다음을 수행하십시오.

1. 클릭 **[!UICONTROL Audience Data]**:
   * For new destinations: Click **[!UICONTROL Create New Destination]**. Complete the [!UICONTROL Basic Information] section before you select a data export label. See [Create a Cookie Destination](../../features/destinations/manage-destinations.md#create-cookie-destination) or [Create a URL Destination](../../features/destinations/manage-destinations.md#configure-url-destination) for information.
   * For existing destinations: Use the [!DNL Search] box to find your destination or scroll through the list and click on the destination name to open it.
1. Select a [!DNL Data Export Label]. 내보내기 제한을 설정하지 않으려면 이 확인란을 비워 두십시오. 내보내기 레이블에는 다음 옵션이 포함됩니다.
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Export restrictions will not work unless you set a [matching export control](../../features/data-export-controls.md) on a data source.
1. 클릭 **[!UICONTROL Save]**.

>[!MORE_ like_ this]
>
>* [데이터 소스 만들기](../../features/manage-datasources.md#create-data-source)

