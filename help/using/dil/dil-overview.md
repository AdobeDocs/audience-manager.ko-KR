---
description: DIL 및 작동 방식에 대한 개요입니다.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, l, dil, l, dil, l, dil, l, l, dil, l, l, l, dil, l, l '
solution: Audience Manager
title: DIL(데이터 통합 라이브러리) 이해
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# 이해 [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

에서 사용할 수 있는 개요, 시작 및 코드 메서드 [!DNL Audience Manager DIL] 코드 라이브러리.

>[!IMPORTANT]
>
>버전 8.0(2018년 8월 릴리스)부터 [!UICONTROL DIL] 에 대한 강한 의존성이 있습니다. [Adobe Experience Platform Identity 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html), 버전 3.3 이상 이것은 [!DNL ID Service] 를 입력하여 ID 동기화 및 URL 대상을 실행합니다. 오류가 발생하는 경우 [!DNL ID Service] 가 없거나, 오래되었거나, 구성되지 않았습니다.
>
>을 사용하는 것이 좋습니다 [!DNL Adobe Experience Platform Tags] 를 구현하고 관리합니다 [!DNL DIL] 및 [!DNL Adobe Experience Platform Identity Service] 라이브러리.

그러나 최신 Experience Cloud 및 [!DNL DIL] gitHub 페이지에서 릴리스합니다. 아래의 다운로드 링크를 참조하십시오.

* 다운로드 [Adobe Experience Platform Identity 서비스](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 다운로드 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL 목적 {#purpose-dil}

[!UICONTROL DIL] 는 API 라이브러리입니다. 이것을 을 위한 도우미 코드의 본문으로 생각할 수 있습니다 [!DNL Adobe Audience Manager]. 사용할 필요는 없습니다 [!DNL Audience Manager], 그러나 메서드 및 함수 [!UICONTROL DIL] 는 에 데이터를 보내기 위해 자체 코드를 개발할 필요가 없음을 의미합니다 [!DNL Audience Manager]. 또한, [!UICONTROL DIL] 는 [Adobe Experience Platform Identity 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html). 이 서비스는 다른 곳에서 방문자 ID를 관리하도록 설계되었습니다 [!DNL Experience Cloud] 솔루션. 반대로, [!UICONTROL DIL] 는 다음과 같은 용도로 설계되었습니다.

* 이벤트를 호출하고 데이터를 [데이터 수집 서버](../reference/system-components/components-data-collection.md).
* 에 데이터 보내기 [대상](../features/destinations/destinations.md).

## DIL 코드 가져오기 및 구현 {#get-implement-dil-code}

[!UICONTROL DIL] 코드를 다운로드할 수 있습니다 **[여기](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 버전 8.0(2018년 8월 릴리스)부터 [!UICONTROL DIL] 에 대한 강한 의존성이 있습니다. [Adobe Experience Platform Identity 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html), 버전 3.3 이상 이것은 [!DNL ID Service] ID 동기화 및 [!DNL URL destinations]. 오류가 발생하는 경우 [!DNL ID Service] 가 없거나, 오래되었거나, 구성되지 않았습니다.

일을 하는 것보다 [!UICONTROL DIL] 설정 [!DNL Audience Manager] 수동으로 [Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 을 가리키도록 업데이트하는 것이 좋습니다. [!DNL Adobe Experience Platform Tags] 는 코드 배포, 배치 및 버전 관리를 간소화하므로 권장되는 구현 도구입니다. 자세한 내용 [Audience Manager 확장](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## 샘플 호출 {#sample-code}

[!UICONTROL DIL] 에 데이터 보내기 [!DNL Audience Manager] 를 반환합니다. 이벤트 호출은 페이지의 XML HTTP 요청입니다. 이 템플릿은 `POST` 요청 본문에 데이터를 전송하는 방법입니다.

| 이벤트 호출 요소 | 설명 |
|--- |--- |
| URL | DIL 이벤트 호출은 다음 구문을 사용합니다. `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 본문 | 아래 샘플에 표시된 대로 DIL은 데이터를 키-값 쌍으로 전달합니다. 특수 접두사 문자는 키-값 쌍을 Audience Manager 또는 파트너 변수로 식별합니다.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

다음을 참조하십시오.
* [주요 변수의 접두사 요구 사항](../features/traits/trait-variable-prefixes.md)
* [DCS API 호출에 지원되는 특성](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## 관련 링크

* [DIL 사용 사례 및 코드 샘플](/help/using/dil/dil-use-cases.md)
* [클래스 수준 DIL 메서드](/help/using/dil/dil-class-overview/dil-start.md)
* [인스턴스 수준 DIL 메서드](/help/using/dil/dil-instance-methods.md)
* [DIL 모듈](/help/using/dil/dil-modules.md)
* [DIL 도구](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
