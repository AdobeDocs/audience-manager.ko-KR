---
description: 대상 관리 모듈을 Adobe Analytics AppMeasurement에 추가하여 Audience Manager Data Integration Library(DIL) 코드가 페이지에서 픽셀을 전송하도록 하지 않고 Analytics 데이터를 Audience Manager에 전달합니다.
keywords: audience analytics; analytics; ssf; 서버 측 전달
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: 대상 관리 모듈 구현
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# 데이터를 전달하는 방법 [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

이 자습서의 단계에 따라 다음 작업을 진행하십시오 [!DNL Analytics] 다음으로 데이터 [!DNL Audience Manager] 대신 [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) 코드가 페이지에서 픽셀을 전송합니다.

>[!TIP]
>
>을 사용하는 것이 좋습니다 [!DNL Adobe Experience Platform Tags] 앞으로 [!UICONTROL Analytics] 데이터를에 [!DNL Audience Manager]. 사용 [!UICONTROL Tags]를 채울 필요는 없습니다. [!DNL AppMeasurement]: 이 페이지에 표시된 대로,

## 사전 요구 사항 {#prereqs}

확장을 활성화하거나 이 문서에 설명된 코드를 구현하는 것 외에도 다음을 수행해야 합니다.

* 구현 [Adobe Experience Platform Identity 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* 활성화 [서버 측 전달](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) 의 보고서 세트 [!UICONTROL Adobe Analytics Admin Console].

## 구현 {#implementation}

에서 데이터 전달을 구현하는 방법에는 두 가지가 있습니다 [!DNL Adobe Analytics] to [!DNL Audience Manager]사용하는 태그 관리 솔루션에 따라 다릅니다.

### 를 사용한 구현 [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] 를 [태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 인스트루먼트 확장 [!DNL Adobe Analytics] 및 [!DNL Audience Manager] 참조하십시오. 이 경우 코드를 수동으로 복사할 필요가 없습니다. 대신, [!DNL Analytics] 확장 프로그램 을 사용하십시오. 다음을 참조하십시오. [Adobe Analytics 확장](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) 설명서.

>[!TIP]
>
>를 설치하는 경우 [!DNL Adobe Analytics] 확장, *포함하지 않음* 설치 [!DNL Audience Manager] 확장. 에서 데이터 전달 [!DNL Analytics] 확장은 를 대체합니다 [!DNL Audience Manager] 확장 기능을 사용할 수 있습니다.

![Adobe Analytics 확장에서 Audience Manager으로 데이터 공유를 활성화하는 방법](/help/using/integration/assets/analytics-to-aam.png)

## 정의된 코드 요소 {#code-elements-defined}

다음 표는 코드 샘플에서 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. 에 의해 지정된 파트너 이름입니다. [!DNL Adobe]. 그것은 때때로 &#39;당신의&#39;라고 불린다 [!UICONTROL partner ID] 또는 partner 하위 도메인.  다음 사항에 문의하십시오. [!DNL Adobe] 컨설턴트 또는 [고객 지원 센터](https://helpx.adobe.com/kr/marketing-cloud/contact-support.html) 파트너 이름을 모르는 경우 |
| `containerNSID` | 필수. 대부분의 고객은  `"containerNSID":0` . 그러나 회사에서 다른 컨테이너와 ID를 사용자 지정해야 하는 경우에는 여기에서 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항입니다. 이 구성을 사용하면 [!DNL Adobe] 쿠키를 생성할 수 있습니다. 이 [!DNL cookie] 다음 포함 [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | 필수. 다음 `namespace` 매개 변수는 [!DNL AudienceManagement] 번들로 제공되는 모듈 [!UICONTROL AppMeasurement] 버전 2.10 이상. 이 [!UICONTROL AudienceManagement] 모듈을 사용하려면 [!UICONTROL Adobe Experience Platform Identity Service] 3.3 이상 <br><br>다음 [!UICONTROL Experience Cloud Organization ID] 는 가입 시 회사가 제공하는 ID입니다 [!UICONTROL Experience Cloud]. 에서 회사의 조직 ID를 확인합니다 [조직 및 계정 연결](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## 결과: 로 데이터 전달 [!DNL Audience Manager] {#results-data-forwarding}

사용자 [!DNL Analytics] 에서 데이터를에 보냅니다. [!DNL Audience Manager] 다음을 수행합니다.

* 활성화됨 [!UICONTROL Server-Side Forwarding] (이 기능에 대해 컨설턴트에게 문의하십시오.)
* 구현됨 [!DNL Adobe Experience Platform Identity Service];
* 이 자습서의 구현 단계를 따랐습니다.

이 프로세스에서는 [!DNL Audience Manager]:

* 페이지 보기 호출 시;
* 추적된 링크에서;
* 비디오 이정표 및 하트비트 비디오 보기에서.

>[!NOTE]
>
>에 전송된 변수 [!DNL Audience Manager] 변환 전: [!DNL Analytics] 특수 접두사를 사용합니다. 작성할 때 이러한 접두사를 이해하고 고려해야 합니다 [!DNL Audience Manager] 트레이트. 이러한 접두사에 대한 자세한 내용은 [주요 변수의 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md).
