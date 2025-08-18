---
description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가 로 이동하여 여기에 설명된 각 섹션에 대한 단계를 완료하십시오. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
keywords: 데이터 소스;데이터 소스 관리;audience manager 데이터 소스
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: 데이터 소스 관리
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# [!UICONTROL Data Sources] 관리 {#manage-data-sources}

## [!UICONTROL Data Source] 만들기 {#create-data-source}

새 [!UICONTROL data source]을(를) 만들려면 **[!UICONTROL Audience Data > Data Sources > Add New]**(으)로 이동하여 여기에 설명된 각 섹션의 단계를 완료하십시오. [!UICONTROL data source]을(를) 만들려면 관리자 권한이 필요합니다.

<!-- create-datasource.xml -->

>[!TIP]
>
>이러한 다른 컨트롤에 대한 설명은 [데이터 Source 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)을 참조하세요.

## [!UICONTROL Data Source] 세부 정보 {#details}

[!UICONTROL Data Source Details] 섹션을 완료하려면 다음 필드를 입력하십시오.

1. **[!UICONTROL Name]**: 데이터 원본의 이름을 입력하십시오.
1. **[!UICONTROL Description]**(선택 사항): 데이터 원본의 역할이나 목적을 정의하는 데 도움이 되도록 데이터 원본에 대한 설명을 입력하십시오.
1. **[!UICONTROL Integration Code]**(선택 사항): 통합 코드를 입력합니다. 다음 코드를 원하는 경우 필요합니다.
   * [장치 간 데이터 원본 만들기](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=ko)를 사용하십시오.
   * [프로필 병합 규칙](../features/profile-merge-rules/merge-rules-start.md)을 사용하여 작업합니다.
1. **[!UICONTROL Namespace]**(읽기 전용): 이 필드는 읽기 전용이며 데이터 원본을 저장할 때 자동으로 생성됩니다. Audience Manager에서 Experience Platform으로 세그먼트를 내보내려면 Experience Platform에서 자동으로 생성된 값을 네임스페이스 [ID 심볼](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=ko#manage-namespaces)&#x200B;(으)로 사용하여 Experience Platform에서 해당 [ID 네임스페이스](https://experienceleague.adobe.com/ko/docs/experience-platform/identity/features/namespaces#components-of-a-namespace)를 만들어야 합니다.
1. **[!UICONTROL ID Type]**: 이 데이터 원본에 포함할 ID 유형 선택:
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]**([!UICONTROL Profile Merge Rule]을(를) 만드는 데 필요). 일부 고객의 경우 이 옵션을 선택하면 **[!UICONTROL ID Definition]** 옵션이 표시됩니다.
1. **[!UICONTROL ID Definition]** 옵션을 선택하십시오. 옵션은 다음과 같습니다.

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[데이터 내보내기 제어](../features/data-export-controls.md)는 [!UICONTROL data source] 및 [!UICONTROL destination]에 적용할 수 있는 선택적 분류 규칙입니다. 이 옵션을 사용하면 해당 작업이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 [!UICONTROL destination]에 데이터를 보내지 못합니다. [!UICONTROL Data Export Controls]을(를) 사용하지 않는 경우 이 섹션을 건너뜁니다.

## [!UICONTROL Data Source] 설정 {#settings}

이 설정은 [!UICONTROL data source]의 식별, 사용 및 공유 방법을 결정합니다. 인바운드 데이터 파일에 대한 오류 보고를 활성화할 수도 있습니다. [!UICONTROL Data Source Settings] 섹션을 완료하려면

1. [!UICONTROL Data Source Setting]에 옵션을 적용하려면 [!UICONTROL data source] 확인란을 선택하세요.
2. **[!UICONTROL Save]** 아이콘을 클릭합니다.

## 데이터 Source 삭제 {#delete-data-source}

<!-- t_datasource_delete.xml -->

더 이상 필요하지 않은 [!UICONTROL data source]을(를) 삭제합니다.

>[!NOTE]
>
>다음 제한 사항에 유의하십시오.
>
>* [활성 대상 또는 데이터 Source 동기화된 트레이트](../features/traits/client-activity-synced-audience-traits.md)는 삭제할 수 없습니다.
>* Adobe Analytics을 사용하는 고객의 경우: Audience Manager에서는 [!DNL Analytics] 보고서 세트에서 자동으로 생성된 데이터 소스를 삭제할 수 없습니다. [핵심 서비스](https://experienceleague.adobe.com/ko/docs/core-services/interface/services/customer-attributes/attributes)를 사용하여 이러한 데이터 원본 매핑을 해제하세요.

1. **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**&#x200B;을(를) 클릭합니다.
1. 하나 이상의 데이터 소스 옆에 있는 확인란을 선택합니다.
목록이 길면 [!UICONTROL Search] 상자를 사용하여 원하는 데이터 원본을 찾을 수 있습니다.
1. ![](assets/icon_trash.png)을(를) 클릭한 다음 삭제를 확인합니다.


>[!MORELIKETHIS]
>
>* [데이터 Source 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)
