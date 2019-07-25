---
description: DIL 개요 및 작동 방식
seo-description: DIL 개요 및 작동 방식
seo-title: DIL (데이터 통합 라이브러리) 이해
solution: Audience Manager
title: DIL (데이터 통합 라이브러리) 이해
uuid: 77 B 12 F 35-81 E 4-4639-ADA 6-BF 982 F 27 B 36 E
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Audience Manager DIL 코드 라이브러리에서 사용할 수 있는 개요, 시작 및 코드 메서드입니다.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. ID 서비스에 ID 동기화 및 URL 대상을 사용합니다. ID 서비스가 없거나, 이전 또는 구성되지 않은 경우 오류가 발생합니다.
>
>Adobe Launch를 사용하여 DIL 및 Experience Cloud ID 서비스 라이브러리를 구현하고 관리하는 것이 좋습니다.

그러나 Github 페이지에서 최신 Experience Cloud 및 DIL 릴리스를 다운로드할 수도 있습니다. 아래 링크 다운로드 링크를 참조하십시오.

* [Experience Cloud ID 서비스 다운로드](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* [DIL 다운로드](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] API 라이브러리입니다. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don't have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. [!UICONTROL DIL] 대조적으로,

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* [대상에](../features/destinations/destinations.md)데이터 보내기

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] 여기에서 코드를 다운로드할 **[](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;수 있습니다. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. ID 서비스에 ID 동기화 및 URL 대상을 사용합니다. ID 서비스가 없거나, 이전 또는 구성되지 않은 경우 오류가 발생합니다.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] 는 코드 배포, 배치 및 버전 관리를 단순화하기 때문에 권장되는 구현 도구입니다. Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] 이벤트 [!DNL Audience Manager] 호출에서 데이터를 전송합니다. 이벤트 호출은 페이지의 XML HTTP 요청입니다. It uses a `POST` method to send data in the body of the request.

| 이벤트 호출 요소 | 설명 |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 본문 | 아래 예에서 보듯이 DIL는 데이터를 키-값 쌍으로 전달합니다. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

다음을 참조하십시오.
* [주요 변수의 접두사 요구 사항](../features/traits/trait-variable-prefixes.md)
* [DCS API 호출에 지원되는 속성](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 관련 링크

* [DIL 사용 사례 및 코드 샘플](/help/using/dil/dil-use-cases.md)
* [클래스 수준 DIL 메서드](/help/using/dil/dil-class-overview/dil-start.md)
* [인스턴스 수준 DIL 메서드](/help/using/dil/dil-instance-methods.md)
* [DIL 모듈](/help/using/dil/dil-modules.md)
* [DIL 도구](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)