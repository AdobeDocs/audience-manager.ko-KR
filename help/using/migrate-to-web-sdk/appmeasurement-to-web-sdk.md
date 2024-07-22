---
title: AppMeasurement JavaScript 라이브러리에서 웹 SDK JavaScript 라이브러리로 Audience Manager을 위해 데이터 수집 라이브러리를 업데이트합니다.
description: AppMeasurement JavaScript 라이브러리에서 웹 SDK JavaScript 라이브러리로 Audience Manager을 위해 데이터 수집 라이브러리를 업데이트하는 단계를 이해합니다.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# AppMeasurement JavaScript 라이브러리에서 웹 SDK JavaScript 라이브러리로 Audience Manager을 위해 데이터 수집 라이브러리 업데이트

## 의도한 대상 {#intended-audience}

이 페이지는 AppMeasurement을 사용하여 웹 수집 데이터를 Audience Manager으로 가져오는 Audience Manager 고객을 위한 것입니다. [Audience Manager 태그 확장](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview)을 사용하는 고객의 경우 [Audience Manager의 데이터 수집 라이브러리를 Audience Manager 태그 확장에서 Web SDK 태그 확장](dil-extension-to-web-sdk.md)으로 업데이트하는 방법에 대한 안내서를 참조하십시오.

## 이 구현 경로의 장단점

이러한 마이그레이션 접근 방식을 사용하면 장점과 단점이 모두 있습니다. 각 옵션을 신중히 평가하여 조직에 가장 적합한 접근 방식을 결정하십시오.

| 장점 | 단점 |
| --- | --- |
| <ul><li>**기존 구현을 사용**: 이 방법을 사용하려면 일부 구현을 변경해야 하지만 처음부터 완전히 새로운 구현이 필요하지 않습니다. 구현 논리를 최소한으로 변경하여 기존 데이터 레이어 및 코드를 사용할 수 있습니다.</li><li>**스키마가 필요하지 않습니다**: Web SDK로 마이그레이션하는 이 단계에서는 XDM 스키마가 필요하지 않습니다. 대신 Audience Manager으로 직접 데이터를 보내는 `data` 개체를 채울 수 있습니다. 웹 SDK로의 마이그레이션이 완료되면 조직에 대한 스키마를 만들고 데이터스트림 매핑을 사용하여 적용 가능한 XDM 필드를 채울 수 있습니다. 마이그레이션 프로세스의 이 단계에서 스키마가 필요한 경우 조직에서 Audience Manager XDM 스키마를 사용해야 합니다. 이 스키마를 사용하면 향후 조직에서 자체 스키마를 사용하는 것이 더 어려워집니다.</li></ul> | <ul><li>**구현 기술 부채**: 이 방법은 기존 구현의 수정된 형식을 사용하므로 구현 논리를 추적하고 필요한 경우 나중에 변경을 수행하는 것이 더 어려울 수 있습니다.</li><li>**데이터를 플랫폼에 보내려면 매핑이 필요합니다**: 조직에서 Real-Time CDP을 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. 이 작업을 수행하려면 `data` 개체의 모든 필드가 XDM 스키마 필드에 할당하는 데이터 스트림 매핑 도구의 항목이어야 합니다. 매핑은 이 워크플로우에 대해 한 번만 수행하면 되며 구현 변경을 수반하지 않습니다. 그러나 XDM 개체에서 데이터를 전송할 때는 필요하지 않은 추가 단계입니다.</li></ul> |

Adobe은 다음 시나리오에서 이 구현 경로를 따를 것을 권장합니다.

* Adobe Analytics AppMeasurement JavaScript 라이브러리를 사용하는 기존 구현이 있습니다. Audience Manager 태그 확장을 사용하는 구현이 있는 경우 대신 [Audience Manager 태그 확장에서 Web SDK 태그 확장으로 마이그레이션](dil-extension-to-web-sdk.md)을 따르십시오.
* 나중에 Real-Time CDP을 사용할 예정이지만 Audience Manager 구현을 처음부터 웹 SDK 구현으로 바꾸지는 않을 것입니다. 웹 SDK에서 구현을 처음부터 교체하려면 가장 많은 노력이 필요하지만 가장 실행 가능한 장기 구현 아키텍처도 제공합니다. 조직에서 깔끔한 웹 SDK 구현을 수행하려는 경우 자세한 내용은 [웹 SDK 설명서](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home)를 참조하십시오.

## 웹 SDK로 마이그레이션하는 데 필요한 단계

다음 단계에는 구체적인 작업 목표가 포함되어 있습니다. 각 단계를 클릭하여 수행 방법에 대한 자세한 지침을 확인하십시오.

+++**1. 데이터 스트림 만들기 및 구성**

Adobe Experience Platform 데이터 수집에서 데이터 스트림을 만듭니다. 이 데이터 스트림으로 데이터를 전송하면 데이터가 Audience Manager으로 전달됩니다. 향후에 이와 동일한 데이터스트림이 데이터를 Real-Time CDP에 전달합니다.

1. [experience.adobe.com](https://experience.adobe.com)(으)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
1. **[!UICONTROL Data Collection]**(으)로 이동하려면 오른쪽 상단의 홈 페이지 또는 제품 선택기를 사용하십시오.
1. 왼쪽 탐색에서 **[!UICONTROL Datastreams]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL New Datastream]**&#x200B;을(를) 선택합니다.
1. 원하는 이름을 입력한 다음 **[!UICONTROL Save]**&#x200B;을(를) 선택합니다.
1. 데이터 스트림이 만들어지면 **[!UICONTROL Add Service]**&#x200B;을(를) 선택합니다.
1. 서비스 드롭다운 메뉴에서 **[!UICONTROL Audience Manager]**&#x200B;을(를) 선택합니다.

   ![Audience Manager 서비스 추가](assets/add-service.png) {style="border:1px solid lightslategray"}

이제 데이터 스트림이 데이터를 받아서 Audience Manager에 전달할 준비가 되었습니다. 코드에서 웹 SDK를 구성할 때 이 ID가 필요하므로 데이터 스트림 ID를 참고하십시오.

+++

+++**2. 웹 SDK JavaScript 라이브러리 설치**

자세한 내용 및 사용할 코드 블록은 [JavaScript 라이브러리를 사용하여 웹 SDK 설치](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library)를 참조하십시오. 메서드 호출을 사용할 수 있도록 `alloy.js`의 최신 버전을 참조합니다.

+++

+++**3. 웹 SDK 구성**

Web SDK [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 명령을 사용하여 1단계에서 만든 데이터 스트림을 가리키도록 구현을 설정하십시오. 라이브러리 설치 코드와 함께 `configure` 명령을 포함할 수 있도록 모든 페이지에서  명령을 설정해야 합니다.

Web SDK `configure` 명령 내에서 [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) 및 [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) 속성을 사용합니다.

* `edgeConfigId`을(를) 이전 단계에서 검색한 데이터 스트림 ID로 설정합니다.
* `orgId`을(를) 조직의 IMS 조직 ID로 설정합니다.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

조직의 구현 요구 사항에 따라 [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 명령에서 다른 속성을 선택적으로 설정할 수 있습니다.

+++

+++**4. JSON 페이로드를 사용하도록 코드 논리 업데이트**

`AppMeasurement.js` 또는 `s` 개체에 의존하지 않도록 Audience Manager 구현을 변경하십시오. 대신 변수를 올바른 형식의 JavaScript 개체로 설정하십시오. 이 개체는 Adobe으로 전송될 때 JSON 개체로 변환됩니다. 사이트에 [데이터 레이어](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer)가 있으면 동일한 값을 계속 참조할 수 있으므로 값을 설정할 때 많은 도움이 됩니다.

데이터를 Audience Manager에 보내려면 웹 SDK 페이로드에서 `data.__adobe.audiencemanager`을(를) 이 개체 내에 설정된 모든 분석 변수와 함께 사용해야 합니다. 이 개체 내의 변수는 AppMeasurement 변수 상대가 공유하는 것과 동일한 이름과 형식을 공유합니다. 예를 들어 `products` 변수를 설정하는 경우 XDM을 사용하는 것처럼 개별 개체로 분할하지 마십시오. 대신 `s.products` 변수를 설정하는 경우 문자열로 포함하십시오.

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

궁극적으로 이 페이로드에는 원하는 값이 모두 포함되어 있으며 구현의 `s` 개체에 대한 모든 참조가 제거됩니다. 개별 값을 설정하는 점 표기법을 포함하여 JavaScript에서 제공하는 모든 리소스를 사용하여 이 페이로드 개체를 설정할 수 있습니다.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. 웹 SDK를 사용하도록 메서드 호출을 업데이트합니다**

[`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) 및 [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method)을(를) 호출하는 모든 인스턴스를 업데이트하여 [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) 명령으로 바꿉니다. 고려해야 할 세 가지 시나리오가 있습니다.

* **페이지 보기 추적**: 페이지 보기 추적 호출을 웹 SDK `sendEvent` 명령으로 바꿉니다.

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **자동 링크 추적**: [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) 구성 속성이 기본적으로 활성화되어 있습니다. 올바른 링크 추적 변수를 자동으로 설정하여 데이터를 Audience Manager으로 전송합니다. 자동 링크 추적을 사용하지 않도록 설정하려면 [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) 명령 내에서 이 속성을 `false`(으)로 설정하십시오.

* **수동 링크 추적**: 웹 SDK에는 pageview 호출과 pageview가 아닌 호출 사이에 별도의 명령이 없습니다. 페이로드 객체 내에 해당 구분을 제공합니다.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. 변경 내용 확인 및 게시**

AppMeasurement 및 `s` 개체에 대한 모든 참조를 제거했으면 변경 내용을 개발 환경에 게시하여 새 구현이 작동하는지 확인하십시오. 모든 것이 올바르게 작동하는지 확인했으면 프로덕션에 업데이트를 게시할 수 있습니다.

올바르게 마이그레이션되면 사이트에 `AppMeasurement.js`이(가) 더 이상 필요하지 않으며 이 스크립트에 대한 모든 참조를 제거할 수 있습니다.

+++

이 시점에서 Audience Manager 구현은 Web SDK로 완전히 마이그레이션되며 향후 Real-Time CDP으로 이동할 준비가 되었습니다.
