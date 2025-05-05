---
title: Audience Manager 태그 확장에서 웹 SDK 태그 확장으로 마이그레이션
description: Audience Manager 태그 확장에서 Web SDK 태그 확장으로 Audience Manager을 위한 데이터 수집 라이브러리를 업데이트하는 절차에 대해 알아봅니다
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Audience Manager 태그 확장에서 웹 SDK 태그 확장으로 Audience Manager을 위한 데이터 수집 라이브러리 업데이트

## 의도한 대상

이 페이지는 [Audience Manager 태그 확장](https://experienceleague.adobe.com/ko/docs/experience-platform/tags/extensions/client/audience-manager/overview)을 사용하여 웹 수집 데이터를 Audience Manager으로 가져오는 Audience Manager 고객을 위한 것입니다. AppMeasurement JavaScript 라이브러리를 사용하는 고객의 경우 AppMeasurement JavaScript 라이브러리에서 Web SDK JavaScript 라이브러리로 [Audience Manager의 데이터 수집 라이브러리를 업데이트하는 방법](appmeasurement-to-web-sdk.md)에 대한 안내서를 참조하십시오.

## 이 구현 경로의 장단점

이러한 마이그레이션 접근 방식을 사용하면 장점과 단점이 모두 있습니다. 각 옵션을 신중히 평가하여 조직에 가장 적합한 접근 방식을 결정하십시오.

| 장점 | 단점 |
| --- | --- |
| <ul><li>**사이트에 코드가 변경되지 않음**: 구현에 이미 태그가 설치되어 있으므로 태그 인터페이스에서 모든 마이그레이션 업데이트를 수행할 수 있습니다.</li><li>**기존 구현을 사용**: 이 방법에서는 완전히 새로운 구현이 필요하지 않습니다. 새로운 규칙 작업이 필요하지만 최소한의 변경으로 기존 데이터 요소와 규칙 조건을 재사용할 수 있습니다.</li><li>**스키마가 필요하지 않습니다**: Web SDK로 마이그레이션하는 이 단계에서는 XDM 스키마가 필요하지 않습니다. 대신 Adobe Audience Manager으로 직접 데이터를 보내는 `data` 개체를 채울 수 있습니다. 웹 SDK로의 마이그레이션이 완료되면 조직에 대한 스키마를 만들고 데이터스트림 매핑을 사용하여 적용 가능한 XDM 필드를 채울 수 있습니다. 마이그레이션 프로세스의 이 단계에서 스키마가 필요한 경우 조직에서 Adobe Audience Manager XDM 스키마를 사용해야 합니다. 이 스키마를 사용하면 향후 조직에서 자체 스키마를 사용하는 것이 더 어려워집니다.</li></ul> | <ul><li>**구현 기술 부채**: 이 방법은 기존 구현의 수정된 형식을 사용하므로 구현 논리를 추적하고 필요한 경우 변경을 수행하는 것이 더 어려울 수 있습니다. 사용자 지정 코드는 특히 디버깅하기 어려울 수 있습니다.</li><li>**데이터를 플랫폼에 보내려면 매핑이 필요합니다**: 조직에서 Real-Time CDP을 사용할 준비가 되면 Adobe Experience Platform의 데이터 세트로 데이터를 보내야 합니다. 이 작업을 수행하려면 `data` 개체의 모든 필드가 XDM 스키마 필드에 할당하는 데이터 스트림 매핑 도구의 항목이어야 합니다. 매핑은 이 워크플로우에 대해 한 번만 수행하면 되며 구현 변경을 수반하지 않습니다. 그러나 XDM 개체에서 데이터를 전송할 때는 필요하지 않은 추가 단계입니다.</li></ul> |

Adobe Adobe Audience Manager 태그 확장을 사용하는 기존 구현이 있는 경우 이 구현 경로를 따르는 것이 좋습니다.

## 웹 SDK로 마이그레이션하는 데 필요한 단계

다음 단계에는 구체적인 작업 목표가 포함되어 있습니다. 각 단계를 선택하여 이를 수행하는 방법에 대한 자세한 지침을 확인하십시오.

+++**1. 데이터 스트림 만들기 및 구성**

Adobe Experience Platform 데이터 수집에서 데이터 스트림을 생성하려면 아래 지침을 따르십시오. 이 데이터 스트림으로 데이터를 전송하면 데이터가 Audience Manager으로 전달됩니다. 향후에 이와 동일한 데이터스트림이 데이터를 Real-Time CDP에 전달합니다.

1. [experience.adobe.com](https://experience.adobe.com)(으)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
1. **[!UICONTROL Data Collection]**(으)로 이동하려면 오른쪽 상단의 홈 페이지 또는 제품 선택기를 사용하십시오.
1. 왼쪽 탐색에서 **[!UICONTROL Datastreams]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL New Datastream]**&#x200B;을(를) 선택합니다.
1. 원하는 이름을 입력한 다음 **[!UICONTROL Save]**&#x200B;을(를) 선택합니다.
1. 데이터 스트림이 만들어지면 **[!UICONTROL Add Service]**&#x200B;을(를) 선택합니다.
1. 서비스 드롭다운 메뉴에서 **[!UICONTROL Adobe Audience Manager]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Enable XDM Flattened Fields]** 옵션이 선택 취소되어 있는지 확인하십시오.

   ![Audience Manager 서비스 추가](assets/add-service.png) {style="border:1px solid lightslategray"}

이제 데이터 스트림이 데이터를 받아서 Audience Manager에 전달할 준비가 되었습니다.

+++

+++**2. Web SDK 확장을 태그 속성에 추가**

이 섹션에서는 다음 단계에서 수행되는 대량의 마이그레이션 작업에 대해 태그를 준비합니다.

1. Adobe Experience Platform 인터페이스 왼쪽 상단에서 햄버거 아이콘을 선택한 다음 **[!UICONTROL Tags]**&#x200B;을(를) 선택합니다.
1. 원하는 태그 속성을 선택합니다.
1. 태그 속성의 왼쪽 탐색에서 **[!UICONTROL Extensions]**&#x200B;을(를) 선택합니다.
1. 사용 가능한 모든 확장 목록을 보려면 상단 근처에 있는 **[!UICONTROL Catalog]**&#x200B;을(를) 선택하십시오.
1. **[!UICONTROL Adobe Experience Platform Web SDK]** 확장을 검색하여 선택한 다음 오른쪽에서 **[!UICONTROL Install]**&#x200B;을(를) 선택합니다.

   ![카탈로그](assets/catalog.png) {style="border:1px solid lightslategray"}

1. 확장 구성 설정이 나타납니다. **[!UICONTROL Datastreams]** 섹션을 찾아 사용 중인 샌드박스와 이전 단계에서 만든 데이터 스트림을 선택합니다.

   ![데이터 스트림 선택](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. **[!UICONTROL Save]**&#x200B;을(를) 선택합니다.

이제 태그 속성에 웹 SDK가 설치됩니다.

+++

+++**3. 데이터 개체 데이터 요소** 만들기

데이터 개체 데이터 요소는 Web SDK가 데이터 스트림으로 전송하는 데 사용하는 페이로드를 구성하는 직관적인 프레임워크를 제공합니다. 다음 단계에서 업데이트하는 대부분의 규칙은 이 데이터 요소와 상호 작용합니다.

1. 태그 인터페이스의 왼쪽 탐색에서 **[!UICONTROL Data Elements]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Add Data Element]** 선택
1. 데이터 요소에 다음 설정을 지정합니다.
   * **[!UICONTROL Name]**: &quot;데이터 레이어&quot; 또는 &quot;데이터 개체&quot;와 같이 원하는 모든 항목
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * 확인란은 그대로 남아 있을 수 있습니다.
1. 오른쪽에서 다음 설정을 선택합니다.
   * 속성 라디오 단추: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. **[!UICONTROL Save]**&#x200B;을(를) 선택합니다.

   ![데이터 요소 만들기](assets/create-data-element.png) {style="border:1px solid lightslategray"}

이제 태그 속성에 각 규칙을 업데이트하는 데 필요한 모든 것이 있습니다.

+++

+++**4. Audience Manager 확장** 대신 웹 SDK 확장을 사용하도록 규칙을 업데이트합니다.

이 단계에는 Web SDK로 마이그레이션하는 데 필요한 많은 작업이 포함되어 있으며 구현 작동 방식에 대한 지식이 필요합니다. 다음은 일반적인 태그 규칙을 편집하는 방법에 대한 예입니다. 구현의 모든 태그 규칙을 업데이트하여 Audience Manager 확장에 대한 모든 참조를 웹 SDK 확장으로 바꿉니다.

1. 태그 인터페이스의 왼쪽 탐색에서 **[!UICONTROL Rules]**&#x200B;을(를) 선택합니다.
1. 편집할 규칙을 선택합니다.
1. **[!UICONTROL Audience Manager - Set Variables]** 작업 선택
1. 이 규칙 내에 설정된 모든 Audience Manager 변수를 확인합니다. 드롭다운 메뉴에 설정된 변수와 사용자 지정 코드 내에 설정된 변수를 모두 포함합니다.
1. [!UICONTROL Action Configuration]을(를) 다음 설정으로 변경합니다.
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: 변수 업데이트
1. 3단계에서 만든 데이터 개체가 **[!UICONTROL Data element]** 필드의 오른쪽 드롭다운에서 선택되어 있는지 확인합니다.
1. Audience Manager 키-값 쌍을 Audience Manager 확장에 구성된 것과 동일한 해당 값으로 설정합니다.
1. 웹 SDK 확장을 사용하여 모든 규칙 논리가 복제되면 **[!UICONTROL Keep Changes]**&#x200B;을(를) 선택합니다.
1. Audience Manager 태그 확장을 사용하여 값을 설정하는 모든 작업 구성에 대해 이 단계를 반복합니다.

위의 단계는 값을 설정하는 규칙에만 적용됩니다. 다음 단계는 [!UICONTROL Action Configuration] [!UICONTROL Send Event]을(를) 사용하는 모든 작업을 대체합니다.

1. 웹 SDK 이벤트를 보내는 규칙을 선택합니다.
1. 작업 유형 **[!UICONTROL Send Event]**&#x200B;을(를) 선택하십시오.
1. [!UICONTROL Action Configuration]을(를) 다음 설정으로 변경합니다.
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. 오른쪽에서 작업 설정을 다음과 같이 변경합니다.
   * **[!UICONTROL Type]**: **[!UICONTROL Web Webpagedetails Page Views]** 사용
   * **[!UICONTROL Data]**: 3단계에서 만든 데이터 개체를 선택합니다.
1. **[!UICONTROL Keep Changes]**&#x200B;을(를) 선택합니다.
1. Audience Manager을 사용하여 이벤트를 전송하는 모든 작업 구성에 대해 이 단계를 반복합니다.

+++

+++**5. Publish에서 규칙을 업데이트했습니다**

업데이트된 규칙을 게시하는 것은 태그 구성에 대한 다른 변경 사항과 동일한 워크플로우를 따릅니다.

1. 태그 인터페이스의 왼쪽 탐색에서 **[!UICONTROL Publishing Flow]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Add Library]**&#x200B;을(를) 선택합니다.
1. 이 태그 커밋에 &quot;Web SDK로 업그레이드&quot;와 같은 이름을 지정합니다.
1. **[!UICONTROL Add All Changed Resources]**&#x200B;을(를) 선택합니다.
1. **[!UICONTROL Save]**&#x200B;을(를) 선택합니다.
1. 게시 작업 과정에는 작성 중임을 나타내는 주황색 점이 표시됩니다. 점이 녹색으로 바뀌면 개발 환경에서 변경 사항을 사용할 수 있습니다.
1. 개발 환경에서 변경 사항을 테스트하여 모든 규칙이 올바르게 실행되는지, 그리고 데이터 개체가 예상 값으로 채워지는지 확인합니다.
1. 준비가 되면 승인을 위해 라이브러리를 제출하고 스테이징으로 빌드한 다음 최종적으로 승인하고 프로덕션에 게시합니다.

   ![게시 흐름](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Audience Manager 확장 사용 안 함**

태그 구현이 Web SDK로 완전히 마이그레이션되면 Audience Manager 확장을 비활성화할 수 있습니다.

1. 태그 인터페이스의 왼쪽 탐색에서 **[!UICONTROL Extensions]**&#x200B;을(를) 선택합니다.
1. [!UICONTROL Audience Manager] 확장을 찾아 선택합니다. 오른쪽에서 **[!UICONTROL Disable]**&#x200B;을(를) 선택합니다.
1. 위의 동일한 게시 작업 과정을 따라 [!UICONTROL Audience Manager] 확장 제거를 게시하십시오.
1. 프로덕션에서 확장이 비활성화되면 완전히 제거할 수 있습니다. 확장을 선택하고 오른쪽에 있는 점 3개 메뉴를 선택한 다음 **[!UICONTROL Uninstall]**&#x200B;을(를) 선택합니다.
1. 위의 동일한 게시 작업 과정을 따라 이러한 변경 사항을 프로덕션에 게시하십시오.

+++

이 시점에서 Audience Manager 구현은 Web SDK로 완전히 마이그레이션되며 향후 Real-Time CDP으로 이동할 준비가 되었습니다.
