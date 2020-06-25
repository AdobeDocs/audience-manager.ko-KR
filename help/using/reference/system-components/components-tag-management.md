---
description: Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe 다이내믹 태그 관리자 및 Adobe Experience Platform 실행 대신 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.
seo-description: Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe 다이내믹 태그 관리자 및 Adobe Experience Platform 실행 대신 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.
seo-title: 태그 관리 구성 요소
solution: Audience Manager
title: 태그 관리 구성 요소
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 5%

---


# 태그 관리 구성 요소{#tag-management-components}

Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe 다이내믹 태그 관리자 및 Adobe Experience Platform 실행 대신 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.

<!-- 

c_comptag.xml

 -->

Audience Manager에는 다음 구성 요소가 포함되어 있습니다.

* [클라이언트 포털](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM 컨테이너](../../reference/system-components/components-tag-management.md#dil-tim)
* [데이터 정보 라이브러리(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [제어 데이터베이스](../../reference/system-components/components-tag-management.md#control-database)

## 클라이언트 포털 {#client-portal}

클라이언트 포털은 태그 및 데이터 관리를 위한 기본 사용자 인터페이스(UI)입니다. 고객은 포털을 사용하여 태그를 사용하고, 트레이트 및 세그먼트를 만들고, 대상을 설정하고, 보고서를 사용하여 캠페인 성과를 모니터링합니다.

## DIL/TIM 컨테이너 {#dil-tim}

이 [!UICONTROL DIL] 컨테이너는 [!DNL Audience Manager] 데이터 수집 코드를 웹 사이트에 배포하는 데 도움이 됩니다. [!UICONTROL TIM] 는 더 이상 사용되지 않는 태그 삽입 관리자입니다. 더 이상 사용되지 않습니다 [!DNL Audience Manager]. 대신 [다이내믹 태그 관리](https://docs.adobe.com/content/help/ko-KR/dtm/using/dtm-home.html) 또는 Adobe Experience Platform 론치의 [!DNL Audience Manager] 확장 [을 사용하여](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) 인벤토리의 페이지에 배치할 컨테이너 코드를 구성하고 생성합니다. 컨테이너 [!UICONTROL DTM] 는 사이트에서 데이터를 수집하여 [!UICONTROL Data Information Library (DIL)] 로 전송하는 데 사용됩니다 [!DNL Audience Manager].

## DIL(데이터 통합 라이브러리) {#dil}

DIL( [Data Information Library](../../dil/dil-overview.md) )은 웹 사이트에서 데이터를 수집하는 독립적인 API 모듈입니다. [!UICONTROL DIL] 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구를 위한 특수 코드를 작성할 필요가 없습니다. [!UICONTROL DIL] 이 작업을 자동으로 수행합니다. 게다가 [!UICONTROL DIL] 크기가 작다. 정보를 수집하는 데 필요한 코드의 양을 줄이는 데 도움이 되는 자체 코드 라이브러리입니다. 마지막으로, Experience Cloud의 다른 제품 [!UICONTROL DIL] 과 통합할 수 [!DNL Audience Manager] [!DNL Adobe] 있습니다.

## Akamai {#akamai}

[!DNL Audience Manager] 에서는 [Akamai를](https://www.akamai.com/html/about/index.html) 사용하여 Adobe의 자체 태그 관리 플랫폼에서 컨테이너 코드를 호스팅하고 제공합니다 [!UICONTROL TIM (Tag Insertion Manager)]. 그러나 코드 배포는 [!UICONTROL TIM] AND에 유리한 단계적 [!DNL Adobe Dynamic Tag Management] 으로 진행되고 [!DNL Adobe Experience Platform Launch]있습니다.

## 제어 데이터베이스 {#control-database}

제어 데이터베이스:

* 포털에서 클라이언트 입력을 처리합니다(예: 트레이트 및 대상 만들기).
* 컨테이너 템플릿 및 대상 게시 iFrame을 만드는 데 사용되는 데이터가 포함된 데이터를 Akamai로 데이터를 전송합니다.
* UI 보고 시스템의 데이터를 반환합니다.

