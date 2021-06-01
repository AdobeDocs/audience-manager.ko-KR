---
description: Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe Experience Platform Launch을 위해 더 이상 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.
seo-description: Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe Experience Platform Launch을 위해 더 이상 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.
seo-title: 태그 관리 구성 요소
solution: Audience Manager
title: 태그 관리 구성 요소
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 시스템 구성 요소
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 4%

---

# 태그 관리 구성 요소{#tag-management-components}

Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe Experience Platform Launch을 위해 더 이상 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.

<!-- 

c_comptag.xml

 -->

Audience Manager에는 다음 구성 요소가 포함되어 있습니다.

* [클라이언트 포털](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM 컨테이너](../../reference/system-components/components-tag-management.md#dil-tim)
* [데이터 정보 라이브러리(DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [컨트롤 데이터베이스](../../reference/system-components/components-tag-management.md#control-database)

## 클라이언트 포털 {#client-portal}

클라이언트 포털은 태그 및 데이터 관리를 위한 기본 사용자 인터페이스(UI)입니다. 고객은 포털을 사용하여 태그를 사용하고, 트레이트 및 세그먼트를 작성하고, 대상을 설정하고, 보고서를 사용하여 캠페인 성과를 모니터링합니다.

## DIL/TIM 컨테이너 {#dil-tim}

[!UICONTROL DIL] 컨테이너는 [!DNL Audience Manager] 데이터 수집 코드를 웹 사이트에 배포하는 데 도움이 됩니다. [!UICONTROL TIM] 는 사용되지 않는 태그 삽입 관리자입니다. 이 함수는 더 이상 [!DNL Audience Manager]에서 사용되지 않습니다. 대신 [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html)에서 [!DNL Audience Manager] 확장을 사용하여 인벤토리의 페이지에 배치하는 컨테이너 코드를 구성하고 생성할 수 있습니다.

## DIL(데이터 통합 라이브러리) {#dil}

[데이터 정보 라이브러리](../../dil/dil-overview.md)(DIL)은 웹 사이트에서 데이터를 수집하는 자체 포함된 API 모듈입니다. [!UICONTROL DIL] 는 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구에 대한 특수 코드를 작성할 필요가 없는 데 도움이 됩니다. [!UICONTROL DIL] 에서는 이러한 작업을 자동으로 수행합니다. 또한 [!UICONTROL DIL]은 컴팩트합니다. 정보를 수집하는 데 필요한 코드 양을 줄이는 데 도움이 되는 자체 포함된 코드 라이브러리입니다. 마지막으로 [!UICONTROL DIL]은 [!DNL Adobe] Experience Cloud의 다른 제품과 [!DNL Audience Manager]을 통합하는 데 도움이 됩니다.

## Akamai {#akamai}

[!DNL Audience Manager] 는  [](https://www.akamai.com/us/en/about/) Akamaito를 호스팅하고 라는 자체 태그 관리 플랫폼에서 컨테이너 코드를 전달합니다  [!UICONTROL TIM (Tag Insertion Manager)]. 그러나 [!UICONTROL TIM]을(를) 사용하는 코드 배포는 [!DNL Adobe Experience Platform Launch]을(를) 위해 단계적으로 중단되었습니다.

## 컨트롤 데이터베이스 {#control-database}

컨트롤 데이터베이스:

* 포털에서 클라이언트 입력을 처리합니다(예: 트레이트 및 대상 만들기).
* 컨테이너 템플릿 및 대상 게시 iFrame을 작성하는 데 사용되는 데이터가 포함된 데이터를 Akamai에 전송합니다.
* UI 보고 시스템에 대한 데이터를 반환합니다.
