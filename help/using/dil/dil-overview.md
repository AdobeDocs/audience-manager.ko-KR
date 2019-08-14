---
description: DIL 개요 및 작동 방식
seo-description: DIL 개요 및 작동 방식
seo-title: DIL (데이터 통합 라이브러리) 이해
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, DIL, '
solution: Audience Manager
title: DIL (데이터 통합 라이브러리) 이해
uuid: 77 B 12 F 35-81 E 4-4639-ADA 6-BF 982 F 27 B 36 E
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# DIL (데이터 통합 라이브러리) 이해{#understanding-the-data-integration-library-dil}

Audience Manager DIL 코드 라이브러리에서 사용할 수 있는 개요, 시작 및 코드 메서드입니다.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. ID 서비스에 ID 동기화 및 URL 대상을 사용합니다. ID 서비스가 없거나, 이전 또는 구성되지 않은 경우 오류가 발생합니다.
>
>Adobe Launch를 사용하여 DIL 및 Experience Cloud ID 서비스 라이브러리를 구현하고 관리하는 것이 좋습니다.

그러나 Github 페이지에서 최신 Experience Cloud 및 DIL 릴리스를 다운로드할 수도 있습니다. 아래 링크 다운로드 링크를 참조하십시오.

* [Experience Cloud ID 서비스 다운로드](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* [DIL 다운로드](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL의 목적 {#purpose-dil}

[!UICONTROL DIL] API 라이브러리입니다. 이것은 도움말 코드의 본문으로 생각할 [!DNL Adobe Audience Manager]수 있습니다. 사용할 [!DNL Audience Manager]필요는 없지만 메서드 및 기능을 [!UICONTROL DIL] 통해 데이터를 보낼 자체 코드를 개발할 필요가 [!DNL Audience Manager]없습니다. 또한, Experience Cloud ID 서비스에서 제공하는 API와 [!UICONTROL DIL][다릅니다](https://marketing.adobe.com/resources/help/en_US/mcvid/). 이 서비스는 [!DNL Experience Cloud] 다른 솔루션에서 방문자 ID를 관리하도록 설계되었습니다. [!UICONTROL DIL] 대조적으로,

* 이벤트 호출을 만들고 데이터 수집 서버로 [데이터를 전송합니다](../reference/system-components/components-data-collection.md).
* [대상에](../features/destinations/destinations.md)데이터 보내기

## DIL 코드 가져오기 및 구현 {#get-implement-dil-code}

[!UICONTROL DIL] 여기에서 코드를 다운로드할 **[](https://github.com/Adobe-Marketing-Cloud/dil/releases)**&#x200B;수 있습니다. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. ID 서비스에 ID 동기화 및 URL 대상을 사용합니다. ID 서비스가 없거나, 이전 또는 구성되지 않은 경우 오류가 발생합니다.

수동으로 작업하고 [!UICONTROL DIL] 설정하는 [!DNL Audience Manager] 대신 [Adobe Launch를](https://docs.adobelaunch.com/) 대신 사용하는 것이 좋습니다. [!DNL Adobe Launch] 는 코드 배포, 배치 및 버전 관리를 단순화하기 때문에 권장되는 구현 도구입니다. Adobe Launch에서 [Audience Manager 확장에](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 대한 자세한 내용을 살펴보십시오.

Adobe Launch는 [Adobe 다이내믹 태그 관리자](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]) 의 후속 버전입니다.

## 샘플 호출 {#sample-code}

[!UICONTROL DIL] 이벤트 [!DNL Audience Manager] 호출에서 데이터를 전송합니다. 이벤트 호출은 페이지의 XML HTTP 요청입니다. 요청 본문에서 데이터를 전송하는 `POST` 방법을 사용합니다.

| 이벤트 호출 요소 | 설명 |
|--- |--- |
| URL | DIL 이벤트 호출은 다음 구문을 사용합니다. `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| 본문 | 아래 예에서 보듯이 DIL는 데이터를 키-값 쌍으로 전달합니다. 특수 접두사 문자는 키-값 쌍을 Audience Manager 또는 파트너 변수로 식별합니다.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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