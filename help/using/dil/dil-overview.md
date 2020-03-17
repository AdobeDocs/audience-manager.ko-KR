---
description: DIL 및 작동 방식에 대한 개요입니다.
seo-description: DIL 및 작동 방식에 대한 개요입니다.
seo-title: DIL(데이터 통합 라이브러리) 이해
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: DIL(데이터 통합 라이브러리) 이해
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# DIL(데이터 통합 라이브러리) 이해{#understanding-the-data-integration-library-dil}

Audience Manager DIL 코드 라이브러리에서 사용할 수 있는 개요, 시작 및 코드 메서드입니다.

>[!IMPORTANT]
>
>버전 8.0(2018년 8월 릴리스)부터 [!UICONTROL DIL] 시작하여 Adobe Experience [Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), 버전 3.3 이상에 대한 종속성을 갖습니다. ID 서비스를 사용하여 ID 동기화 및 URL 대상을 실행합니다. ID 서비스가 없거나, 오래되었거나, 구성되지 않은 경우 오류가 발생합니다.
>
>Adobe Experience Platform Launch를 사용하여 DIL 및 Adobe Experience Platform Identity Service 라이브러리를 구현하고 관리하는 것이 좋습니다.

그러나 GitHub 페이지에서 최신 Experience Cloud 및 DIL 릴리스를 다운로드할 수도 있습니다. 아래 다운로드 링크를 참조하십시오.

* Adobe Experience [Platform Identity Service 다운로드](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* DIL [다운로드](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL 목적 {#purpose-dil}

[!UICONTROL DIL] 는 API 라이브러리입니다. 여러분은 그것을 헬퍼 코드의 본체로 생각할 수 [!DNL Adobe Audience Manager]있습니다. 사용할 필요는 없지만 [!DNL Audience Manager]메서드 및 함수를 [!UICONTROL DIL] 사용하면 데이터를 전송하기 위해 자체 코드를 개발할 필요가 없습니다 [!DNL Audience Manager]. 또한 [!UICONTROL DIL] 이 API는 Adobe Experience Platform Identity [Service에서 제공하는 API와 다릅니다](https://marketing.adobe.com/resources/help/en_US/mcvid/). 이 서비스는 다양한 [!DNL Experience Cloud] 솔루션에서 방문자 ID를 관리하도록 설계되었습니다. 반면, [!UICONTROL DIL] 다음과 같이 설계되었습니다.

* 이벤트 호출을 수행하고 데이터를 데이터 수집 [서버로 보냅니다](../reference/system-components/components-data-collection.md).
* 데이터를 [대상으로](../features/destinations/destinations.md)보내기

## DIL 코드 가져오기 및 구현 {#get-implement-dil-code}

[!UICONTROL DIL] 코드는 **[여기에서](https://github.com/Adobe-Marketing-Cloud/dil/releases)**다운로드할 수 있습니다. 버전 8.0(2018년 8월 릴리스)부터[!UICONTROL DIL]시작하여 Adobe Experience Platform Identity[Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), 버전 3.3 이상에 대한 강한 의존성이 있습니다. ID 서비스를 사용하여 ID 동기화 및 URL 대상을 실행합니다. ID 서비스가 없거나, 오래되었거나, 구성되지 않은 경우 오류가 발생합니다.

수동으로 작업하고 [!UICONTROL DIL] 설정하는 대신 Adobe Experience Platform [!DNL Audience Manager] Launch를 사용하는 것이 좋습니다 [](https://docs.adobelaunch.com/) . [!DNL Adobe Experience Platform Launch] 는 코드 배포, 배치 및 버전 관리를 간소화하므로 권장 구현 도구입니다. Adobe Experience Platform Launch [의 Audience Manager 익스텐션에](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 대한 자세한 내용을 살펴보십시오.

Adobe Experience Platform Launch는 Adobe Dynamic [Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM])의 후속 제품입니다.

## 샘플 호출 {#sample-code}

[!UICONTROL DIL] 이벤트 호출에서 데이터를 [!DNL Audience Manager] 전송합니다. 이벤트 호출은 페이지의 XML HTTP 요청입니다. 이 메서드는 요청 본문에 데이터를 전송하는 `POST` 방법을 사용합니다.

| 이벤트 호출 요소 | 설명 |
|--- |--- |
| URL | DIL 이벤트 호출은 다음 구문을 사용합니다. `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 본문 | 아래 샘플에서 보듯이 DIL은 데이터를 키-값 쌍으로 전달합니다. 특수 접두사 문자는 Audience Manager 또는 파트너 변수로 키-값 쌍을 식별합니다.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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