---
description: Audience Manager AppMeasurement(DIL) 코드가 페이지의 픽셀을 보내도록 하는 대신 Audience Management 모듈을 Adobe Analytics Audience Manager에 추가하여 Analytics 데이터를 Data Integration Library에 전달합니다.
keywords: audience analytics, analytics, ssf, 서버측 전달
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: 고객 관리 모듈 구현
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# 데이터를 [!DNL Adobe Analytics]에서 [!DNL Audience Manager]&#x200B;(으)로 전달하는 방법 {#implement-the-audience-management-module}

[!DNL Analytics] [!DNL Audience Manager]&#x200B;([!DNL Audience Manager]) 코드에서 페이지의 픽셀을 보내는 대신 [!UICONTROL Data Integration Library] 데이터를 [!DNL DIL]에 전달하려면 이 자습서의 단계를 따르십시오.

>[!TIP]
>
>[!DNL Adobe Experience Platform Tags]을(를) 사용하여 [!UICONTROL Analytics] 데이터를 [!DNL Audience Manager]&#x200B;(으)로 전달하는 것이 좋습니다. [!UICONTROL Tags]을(를) 사용하면 이 페이지에 표시된 대로 [!DNL AppMeasurement]에 코드를 수동으로 복사할 필요가 없습니다.

## 사전 요구 사항 {#prereqs}

이 문서에 설명된 확장을 활성화하거나 코드를 구현하는 작업 외에 다음 작업도 수행해야 합니다.

* [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ko)를 구현합니다.
* [의 보고서 세트에 대해 &#x200B;](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=ko)서버측 전달[!UICONTROL Adobe Analytics Admin Console]을 사용하도록 설정하십시오.

## 구현 {#implementation}

사용하는 태그 관리 솔루션에 따라 [!DNL Adobe Analytics]에서 [!DNL Audience Manager]&#x200B;(으)로 데이터 전달을 구현하는 방법에는 두 가지가 있습니다.

### [!DNL Adobe Experience Platform Tags]을(를) 사용한 구현

[!DNL Adobe]에서는 [태그](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ko) 확장을 사용하여 속성에 [!DNL Adobe Analytics] 및 [!DNL Audience Manager]을(를) 사용하는 것이 좋습니다. 이 경우 코드를 수동으로 복사할 필요가 없습니다. 대신 아래 그림과 같이 [!DNL Analytics] 확장에서 데이터 공유를 사용하도록 설정해야 합니다. [Adobe Analytics 확장](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=ko#adobe-audience-manager) 설명서도 참조하세요.

>[!TIP]
>
>[!DNL Adobe Analytics] 확장을 설치하는 경우 *하지 않음*&#x200B;도 [!DNL Audience Manager] 확장을 설치합니다. [!DNL Analytics] 확장에서 데이터를 전달하면 [!DNL Audience Manager] 확장 기능이 바뀝니다.

![Adobe Analytics 확장에서 Audience Manager으로 데이터 공유를 사용하는 방법](/help/using/integration/assets/analytics-to-aam.png)

## 정의된 코드 요소 {#code-elements-defined}

다음 표에서는 코드 샘플의 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. [!DNL Adobe]이(가) 귀하에게 할당한 파트너 이름입니다. 경우에 따라 [!UICONTROL partner ID] 또는 파트너 하위 도메인이라고도 합니다.  파트너 이름을 모르는 경우 [!DNL Adobe] 컨설턴트나 [고객 지원 센터](https://helpx.adobe.com/kr/marketing-cloud/contact-support.html)에 문의하십시오. |
| `containerNSID` | 필수. 대부분의 고객은 `"containerNSID":0`만 설정할 수 있습니다. 그러나 회사에서 ID 동기화를 다른 컨테이너와 사용자 정의해야 하는 경우 여기에서 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항. 이 구성을 사용하면 자사 도메인에서 [!DNL Adobe] 쿠키를 설정할 수 있습니다. 이 [!DNL cookie]에는 [UUID](../../reference/ids-in-aam.md) 이(가) 포함되어 있습니다. |
| `visitorService` - `namespace` | 필수. `namespace` 버전 2.10 이상과 함께 번들로 제공되는 [!DNL AudienceManagement] 모듈을 사용하는 경우 [!UICONTROL AppMeasurement] 매개 변수가 필요합니다. 이 [!UICONTROL AudienceManagement] 모듈에서는 [!UICONTROL Adobe Experience Platform Identity Service] 3.3 이상을 사용해야 합니다. <br><br>[!UICONTROL Experience Cloud Organization ID]은(는) [!UICONTROL Experience Cloud]에 등록할 때 회사에 제공되는 ID입니다. [조직 및 계정 연결](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=ko)에서 회사의 조직 ID를 확인하세요. |

## 결과: 데이터를 [!DNL Audience Manager]&#x200B;(으)로 전달 {#results-data-forwarding}

[!DNL Analytics] 구현에서는 다음을 수행한 후 데이터를 [!DNL Audience Manager]에 보냅니다.

* [!UICONTROL Server-Side Forwarding]을(를) 사용하도록 설정했습니다(이 기능에 대해 컨설턴트에게 문의하십시오).
* [!DNL Adobe Experience Platform Identity Service];
* 이 자습서의 구현 단계를 따랐습니다.

이 프로세스는 데이터를 [!DNL Audience Manager]&#x200B;(으)로 보냅니다.

* 페이지 보기 호출 시;
* 추적된 링크에서
* 비디오 이정표 및 하트비트 비디오 보기에서

>[!NOTE]
>
>[!DNL Audience Manager]에서 [!DNL Analytics]&#x200B;(으)로 보낸 변수는 특수 접두사를 사용합니다. [!DNL Audience Manager] 특성을 만들 때 이러한 접두사를 이해하고 고려해야 합니다. 이러한 접두사에 대한 자세한 내용은 [주요 변수에 대한 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)을 참조하십시오.
