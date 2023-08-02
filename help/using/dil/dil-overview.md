---
description: DIL 및 작동 방식에 대한 개요입니다.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: DIL(데이터 통합 라이브러리) 이해
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 10%

---

# 이해 [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>2023년 7월부터 Adobe은 의 개발을 중단했습니다. [!DNL Data Integration Library (DIL)] 및 [!DNL DIL] 확장명.
>
>기존 고객은 [!DNL DIL] 구현. 그러나 Adobe은 개발되지 않습니다 [!DNL DIL] 이 점을 넘어서는 것입니다. 고객은 다음을 평가하는 것이 좋습니다. [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 을 참조하십시오.
>
>2023년 7월 이후 새로운 데이터 수집 통합을 구현하려는 고객은 [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) 대신,

개요, 시작 및 코드에서 사용할 수 있는 [!DNL Audience Manager DIL] 코드 라이브러리.

>[!IMPORTANT]
>
>버전 8.0(2018년 8월 릴리스)부터 [!UICONTROL DIL] 은(는) 다음에 대한 엄격한 종속성을 가지고 있습니다. [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html), 버전 3.3 이상 다음에 의존합니다. [!DNL ID Service] ID 동기화 및 URL 대상을 실행하려면 다음 경우 오류가 발생합니다. [!DNL ID Service] 이(가) 누락되었거나, 오래되었거나, 구성되지 않았습니다.
>
>다음을 사용하는 것이 좋습니다. [!DNL Adobe Experience Platform Tags] 을 구현하고 관리하려면 [!DNL DIL] 및 [!DNL Adobe Experience Platform Identity Service] 라이브러리.

그러나 최신 Experience Cloud 및 [!DNL DIL] 는 GitHub 페이지에서 릴리스됩니다. 아래 다운로드 링크를 참조하십시오.

* 다운로드 [Adobe Experience Platform ID 서비스](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* 다운로드 [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## DIL 목적 {#purpose-dil}

[!UICONTROL DIL] 는 API 라이브러리입니다. 다음을 위한 도우미 코드 본문으로 생각할 수 있습니다. [!DNL Adobe Audience Manager]. 를 사용할 필요는 없습니다. [!DNL Audience Manager], 그러나 메서드 및 함수 [!UICONTROL DIL] 는 로 데이터를 전송하기 위해 자체 코드를 개발할 필요가 없음을 의미합니다 [!DNL Audience Manager]. 또한, [!UICONTROL DIL] 은(는) 이 제공한 API와 다릅니다. [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html). 해당 서비스는 여러 방문자 ID를 관리하도록 설계되었습니다 [!DNL Experience Cloud] 솔루션. 대조적으로, [!UICONTROL DIL] 설계 대상:

* 이벤트를 호출하고 데이터를 [데이터 수집 서버](../reference/system-components/components-data-collection.md).
* 데이터 보내기 대상 [대상](../features/destinations/destinations.md).

## DIL 코드 가져오기 및 구현 {#get-implement-dil-code}

[!UICONTROL DIL] 코드를 다운로드할 수 있음 **[여기](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. 버전 8.0(2018년 8월 릴리스)부터 [!UICONTROL DIL] 은(는) 다음에 대한 엄격한 종속성을 가지고 있습니다. [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html), 버전 3.3 이상 다음에 의존합니다. [!DNL ID Service] ID 동기화 및 [!DNL URL destinations]. 다음 경우 오류가 발생합니다. [!DNL ID Service] 이(가) 누락되었거나, 오래되었거나, 구성되지 않았습니다.

을 사용하여 작업하기 보다는 [!UICONTROL DIL] 및 설정 [!DNL Audience Manager] 수동으로 다음을 사용하는 것이 좋습니다. [Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) 대신, [!DNL Adobe Experience Platform Tags] 는 코드 배포, 배치 및 버전 관리를 단순화하기 때문에 권장되는 구현 도구입니다. 자세한 내용 [Audience Manager 확장](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 위치: [!DNL Adobe Experience Platform Tags].

## 샘플 호출 {#sample-code}

[!UICONTROL DIL] 에 데이터 전송 [!DNL Audience Manager] 이벤트 호출. 이벤트 호출은 페이지의 XML HTTP 요청입니다. 다음을 사용합니다. `POST` 요청 본문에서 데이터를 보내는 메서드입니다.

| 이벤트 호출 요소 | 설명 |
|--- |--- |
| URL | DIL 이벤트 호출은 다음 구문을 사용합니다. `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| 본문 | 아래 샘플에서 보듯이 DIL은 데이터를 키-값 쌍으로 전달합니다. 특수 접두사 문자는 키-값 쌍을 Audience Manager 또는 파트너 변수로 식별합니다.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
