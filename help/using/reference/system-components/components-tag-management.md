---
description: Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe Experience Platform Launch을 위해 더 이상 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: 태그 관리 구성 요소
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# 태그 관리 구성 요소{#tag-management-components}

Audience Manager 태그 관리 구성 요소에는 클라이언트 포털, Adobe Tag Manager(Adobe Experience Platform 태그를 위해 더 이상 사용되지 않음), DIL, Akamai 및 제어 데이터베이스가 포함됩니다.

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

다음 [!UICONTROL DIL] 컨테이너 배포 [!DNL Audience Manager] 웹 사이트에 데이터 수집 코드를 추가합니다. [!UICONTROL TIM] 는 사용되지 않는 태그 삽입 관리자입니다. 다음에서 더 이상 사용하지 않습니다. [!DNL Audience Manager]. 대신 를 사용합니다 [!DNL Audience Manager] 확장 [Adobe Experience Platform 태그](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) 를 입력하여 인벤토리의 페이지에 배치하는 컨테이너 코드를 구성하고 생성합니다.

## DIL(데이터 통합 라이브러리) {#dil}

다음 [데이터 정보 라이브러리](../../dil/dil-overview.md) (DIL)은 웹 사이트에서 데이터를 수집하는 자체 포함된 API 모듈입니다. [!UICONTROL DIL] 는 데이터 수집, 통합, 쿠키 값 읽기 및 페이지 데이터 복구에 대한 특수 코드를 작성할 필요가 없는 데 도움이 됩니다. [!UICONTROL DIL] 에서는 이러한 작업을 자동으로 수행합니다. 또한, [!UICONTROL DIL] 콤팩트합니다. 정보를 수집하는 데 필요한 코드 양을 줄이는 데 도움이 되는 자체 포함된 코드 라이브러리입니다. 마지막으로 [!UICONTROL DIL] 을 통합하면 [!DNL Audience Manager] 의 다른 제품과 함께 [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] 사용 [Akamai](https://www.akamai.com/us/en/about/) 라는 고유한 태그 관리 플랫폼에서 컨테이너 코드를 호스팅하고 전달합니다 [!UICONTROL TIM (Tag Insertion Manager)]. 그러나 코드 배포 시 [!UICONTROL TIM] 우리는 [!DNL Adobe Experience Platform Tags].

## 컨트롤 데이터베이스 {#control-database}

컨트롤 데이터베이스:

* 포털에서 클라이언트 입력을 처리합니다(예: 트레이트 및 대상 만들기).
* 컨테이너 템플릿 및 대상 게시 iFrame을 작성하는 데 사용되는 데이터가 포함된 데이터를 Akamai에 전송합니다.
* UI 보고 시스템에 대한 데이터를 반환합니다.
