---
description: Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe 태그 관리자 (Adobe 다이내믹 태그 관리자 및 Adobe Launch에 대해 권장되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.
seo-description: Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe 태그 관리자 (Adobe 다이내믹 태그 관리자 및 Adobe Launch에 대해 권장되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.
seo-title: 태그 관리 구성 요소
solution: Audience Manager
title: 태그 관리 구성 요소
uuid: e 5059478-6 ba 7-4 e 1 a-afec-e 41 ad 7 a 27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe 태그 관리자 (Adobe 다이내믹 태그 관리자 및 Adobe Launch에 대해 권장되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.

<!-- 

c_comptag.xml

 -->

Audience Manager 에는 다음 구성 요소가 포함되어 있습니다.

* [클라이언트 포털](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM 컨테이너](../../reference/system-components/components-tag-management.md#dil-tim)
* [DIL (데이터 정보 라이브러리)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [데이터베이스 제어](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

클라이언트 포털은 태그 및 데이터 관리를 위한 기본 유저 인터페이스 (UI) 입니다. 고객은 포털을 사용하여 태그와 함께 작업하고, 트레이트와 세그먼트를 만들고, 대상을 설정하고, 보고서를 사용하여 캠페인 성과를 모니터링합니다.

## DIL/TIM Container {#dil-tim}

[!UICONTROL DIL] 컨테이너는 웹 사이트에 [!DNL Audience Manager] 데이터 수집 코드를 배포하는 데 도움이 됩니다. [!UICONTROL TIM] 는 더 이상 사용되지 않는 태그 삽입 관리자입니다. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. [!UICONTROL DTM] 컨테이너는 사이트에서 데이터를 수집하고 전송하는 [!UICONTROL Data Information Library (DIL)] 과 함께 사용할 [!DNL Audience Manager]수 있습니다.

## DIL(데이터 통합 라이브러리) {#dil}

The [Data Information Library](../../dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] 데이터 수집, 통합, 쿠키 값 읽기, 페이지 데이터 복구 등에 필요한 특수 코드를 작성하지 않아도 됩니다. [!UICONTROL DIL] 이 작업을 자동으로 수행합니다. Additionally, [!UICONTROL DIL] is compact. 정보를 수집하는 데 필요한 코드의 양을 줄이는 데 도움이 되는 독립된 코드 라이브러리입니다. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager][Akamai](https://www.akamai.com/html/about/index.html)[!UICONTROL TIM (Tag Insertion Manager)]를 사용하여 However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

컨트롤 데이터베이스:

* 포털에서 클라이언트 입력을 처리합니다 (예: 트레이트 및 대상 만들기).
* 컨테이너 템플릿 및 대상 게시 iframe를 만드는 데 사용되는 데이터를 포함하는 데이터를 Akamai로 전송합니다.
* UI 보고 시스템에 대한 데이터를 반환합니다.

