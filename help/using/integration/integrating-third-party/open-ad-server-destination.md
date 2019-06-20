---
description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼으로 전송합니다.
seo-description: Open Ad Server를 대상으로 설정하고 Audience Manager 데이터를 해당 플랫폼으로 전송합니다.
seo-title: Audience Manager 대상으로 OAS
solution: Audience Manager
title: Audience Manager 대상으로 OAS
uuid: 5891 A 063-5 A 4 B -4 EA 7-865 F-B 24 E 17 CA 735 F
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OAS as an Audience Manager Destination {#oas-as-an-audience-manager-destination}

Set up [!DNL Open Ad Server] as a destination and send Audience Manager data to that platform.

## OAS Destination Requirements {#oas-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OAS].

<!-- aam-oas-requirements.xml -->

이 대상 유형에는 다음이 필요합니다.

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] 코드는 인벤토리에 배포해야 합니다. [!UICONTROL DIL] 데이터 수집, 통합, 쿠키 값 읽기, 페이지 데이터 복구 등에 필요한 특수 코드를 작성하지 않아도 됩니다.
* **`get_aamCookie`함수:** Audience Manager 사용자 ID 및 쿠키 데이터를 캡처하는 코드입니다. [이 코드를](../../features/destinations/get-aam-cookie-code.md) 페이지 상단 또는 `<head>` 코드 블록 내에 배치합니다.
* **Audience Manager로 배달 로그 보내기:** 세그먼트 배달 보고서를 원할 경우 (옵션), 노출 수준 배달 데이터가 들어 있는 일별 로그를 Audience Manager에 제공합니다. The data can be in a raw format, but each record must contain the Audience Manager [!UICONTROL UUID]. Audience Manager can pick up or receive these via [!DNL FTP].

### 쿠키 형식 및 키 값 데이터

Audience Manager는 세그먼트 데이터를 다음과 같이 브라우저 쿠키로 보낼 수 있습니다.

* Single keys (`x=1&x=2`);
* Multiple keys (`x=1&x=2&y=3&y=4`);
* Serialized values (`x=1,2,3`);
* 개별 키-값 쌍을 구분하는 데 사용되는 표준 값 구분 기호.

### 자격 조건을 갖춘 세그먼트만 OAS로 전송됩니다.

The amount data passed in to [!DNL OAS] depends on how many segments a particular user qualifies for. 예를 들어 100 개의 고객 관리 세그먼트를 설정한다고 가정합니다. 사이트 방문자가 5 개 사이트에 자격을 부여한 경우 5 개의 세그먼트만 OAS로 전송됩니다 (모두 100 개 아님).

>[!MORE_ like_ this]
>
>* [GET_ AAMCOOKIE 코드](../../features/destinations/get-aam-cookie-code.md)
>* [키-값 쌍을 설명했습니다.](../../reference/key-value-pairs-explained.md)


## Create an OAS Destination {#oas-dest-setup}

Create a cookie-based destination for [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) 로 데이터를 공유할 수 있습니다. [!UICONTROL Destination Builder] 이 데이터 전달 프로세스를 만들고 관리할 수 있는 도구를 제공합니다. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### 1 단계: 기본 정보

To complete the [!UICONTROL Basic Information] section:

1. 대상의 이름을 지정합니다.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### 2 단계: 구성 정보

To complete the [!UICONTROL Configuration] section:

1. **쿠키 이름:** 쿠키를 설명하는 간단한 설명을 입력합니다.
1. **쿠키 도메인:** 사용자 현재 페이지의 도메인에서 쿠키를 설정하려면 비워 두십시오. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### 3 단계: 세그먼트 매핑

쿠키 대상에 세그먼트를 추가하려면:

1. **세그먼트 찾기:** 섹션에서는 [!UICONTROL Segment Mappings] 세그먼트를 찾는 데 도움이 되는 두 가지 검색 도구를 제공합니다. 세그먼트를 찾으려면:
   * 옵션 1: 검색 필드에 세그먼트 이름을 입력합니다. 텍스트를 기반으로 필드가 자동으로 업데이트됩니다. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **매핑 추가:** 매핑 팝업에 매핑 필드에 세그먼트 ID를 입력하고를 클릭합니다 **[!UICONTROL Save]**.
1. 클릭 **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Modify [!DNL OAS] settings to work with Audience Manager segment data.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Install [!UICONTROL DIL] code across your site.
* Audience Manager에서 쿠키 대상으로 OAS를 만듭니다.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` 이 코드는 여기에서 사용할 수 있습니다.[](../../features/destinations/get-aam-cookie-code.md)
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OAS] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* 광고 태그는 아래 예와 비슷합니다.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Remember to include the `u=` variable. It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.
