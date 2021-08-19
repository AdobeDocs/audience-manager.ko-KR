---
description: 대상 관리 모듈을 Adobe Analytics AppMeasurement에 추가하여 Audience Manager Data Integration Library(DIL) 코드가 페이지에서 픽셀을 전송하도록 하지 않고 Analytics 데이터를 Audience Manager에 전달합니다.
keywords: audience analytics; analytics; ssf; 서버 측 전달
seo-description: 대상 관리 모듈을 Adobe Analytics AppMeasurement에 추가하여 Audience Manager Data Integration Library(DIL) 코드가 페이지에서 픽셀을 전송하도록 하지 않고 Analytics 데이터를 Audience Manager에 전달합니다.
seo-title: 대상 관리 모듈 구현
solution: Audience Manager
title: 대상 관리 모듈 구현
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics 통합
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 2%

---

# 데이터를 [!DNL Adobe Analytics]에서 [!DNL Audience Manager](으)로 전달하는 방법 {#implement-the-audience-management-module}

이 자습서의 단계에 따라 [!DNL Audience Manager] [!UICONTROL Data Integration Library]([!DNL DIL]) 코드가 페이지에서 픽셀을 보내도록 하지 않고 [!DNL Analytics] 데이터를 [!DNL Audience Manager]에 전달합니다.

>[!TIP]
>
>[!DNL Adobe Experience Platform Launch] 을 사용하여 [!UICONTROL Analytics] 데이터를 [!DNL Audience Manager]에 전달하는 것이 좋습니다. [!UICONTROL Launch]을 사용하면 이 페이지에 표시된 대로 코드를 [!DNL AppMeasurement]에 수동으로 복사할 필요가 없습니다.

## 사전 요구 사항 {#prereqs}

확장을 활성화하거나 이 문서에 설명된 코드를 구현하는 것 외에도 다음을 수행해야 합니다.

* [Adobe Experience Platform Identity 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html)를 구현합니다.
* [!UICONTROL Adobe Analytics Admin Console]의 보고서 세트에 대해 [서버측 전달](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)을 활성화합니다.

## 구현 {#implementation}

사용하는 태그 관리 솔루션에 따라 [!DNL Adobe Analytics]에서 [!DNL Audience Manager] (으)로 데이터 전달을 구현하는 방법에는 두 가지가 있습니다.

### [!DNL Adobe Experience Platform Launch]을 사용한 구현

[!DNL Adobe] launchextension을 사용하여  [](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=en) 속성  [!DNL Adobe Analytics] 및 [!DNL Audience Manager] 에서 도구를 사용할 것을 권장합니다. 이 경우 코드를 수동으로 복사할 필요가 없습니다. 대신 아래 이미지와 같이 [!DNL Analytics Launch] 확장 프로그램에서 데이터 공유를 활성화해야 합니다. 또한 [Adobe Analytics Extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) 설명서를 참조하십시오.

>[!TIP]
>
>[!DNL Adobe Analytics] 확장을 설치하는 경우 *도 [!DNL Audience Manager] 확장을 설치하지 마십시오.* [!DNL Analytics] 확장에서 데이터를 전달하면 [!DNL Audience Manager] 확장 기능이 대체됩니다.

![Adobe Analytics 확장에서 Audience Manager으로 데이터 공유를 활성화하는 방법](/help/using/integration/assets/analytics-to-aam.png)

## 정의된 코드 요소 {#code-elements-defined}

다음 표는 코드 샘플에서 중요한 변수를 정의합니다.

| 매개 변수 | 설명 |
|--- |--- |
| `partner` | 필수. [!DNL Adobe]에 의해 지정된 파트너 이름입니다. 경우에 따라 [!UICONTROL partner ID] 또는 파트너 하위 도메인이라고도 합니다.  파트너 이름을 모르는 경우 [!DNL Adobe] 컨설턴트나 [고객 지원 센터](https://helpx.adobe.com/kr/marketing-cloud/contact-support.html)에 문의하십시오. |
| `containerNSID` | 필수. 대부분의 고객은 `"containerNSID":0` 만 설정할 수 있습니다. 그러나 회사에서 다른 컨테이너와 ID를 사용자 지정해야 하는 경우에는 여기에서 해당 컨테이너 ID를 지정할 수 있습니다. |
| `uuidCookie` | 선택 사항입니다. 이 구성을 사용하면 자사 도메인에서 [!DNL Adobe] 쿠키를 설정할 수 있습니다. 이 [!DNL cookie]에는 [UUID](../../reference/ids-in-aam.md) 가 포함되어 있습니다. |
| `visitorService` - `namespace` | 필수. [!UICONTROL AppMeasurement] 버전 2.10 이상과 함께 번들로 제공되는 [!DNL AudienceManagement] 모듈을 사용하는 경우 `namespace` 매개 변수가 필요합니다. 이 [!UICONTROL AudienceManagement] 모듈은 [!UICONTROL Adobe Experience Platform Identity Service] 3.3 이상을 사용해야 합니다. <br><br> [!UICONTROL Experience Cloud Organization ID] 은 회사에 등록할 때 제공하는 ID입니다  [!UICONTROL Experience Cloud]. [조직 및 계정 연결](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html)에서 회사의 조직 ID를 확인하십시오. |

## 결과: [!DNL Audience Manager]에 데이터 전달 {#results-data-forwarding}

[!DNL Analytics] 구현에서 다음을 수행한 후 데이터를 [!DNL Audience Manager]에 보냅니다.

* 활성화됨 [!UICONTROL Server-Side Forwarding] (이 기능에 대해 컨설턴트에게 문의);
* [!DNL Adobe Experience Platform Identity Service]; 구현됨
* 이 자습서의 구현 단계를 따랐습니다.

이 프로세스는 데이터를 [!DNL Audience Manager]에 보냅니다.

* 페이지 보기 호출 시;
* 추적된 링크에서;
* 비디오 이정표 및 하트비트 비디오 보기에서.

>[!NOTE]
>
>[!DNL Analytics]에서 [!DNL Audience Manager]으로 보낸 변수는 특수 접두사를 사용합니다. [!DNL Audience Manager] 특성을 만들 때 이러한 접두사를 이해하고 고려해야 합니다. 이러한 접두사에 대한 자세한 내용은 [키 변수에 대한 접두사 요구 사항](../../features/traits/trait-variable-prefixes.md)을 참조하십시오.
