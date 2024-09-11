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
source-git-commit: e41dddd022b6fa02cab3e16bd21536d41584975f
workflow-type: tm+mt
source-wordcount: '0'
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

[!UICONTROL Data Source Details] 섹션을 완료하려면

1. [!UICONTROL data source] 이름을 지정합니다.
1. *(선택 사항)*&#x200B;에서 [!UICONTROL data source]을(를) 설명합니다. 간략한 설명을 통해 [!UICONTROL data source]의 역할이나 목적을 정의할 수 있습니다.
1. [!UICONTROL integration code] 입력. 일반적으로 [!UICONTROL integration codes]은(는) 선택 사항입니다. 다음 작업을 수행할 때 필요합니다.

   * [장치 간 데이터 원본 만들기](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html)를 사용하십시오.
   * [프로필 병합 규칙](../features/profile-merge-rules/merge-rules-start.md)을 사용하여 작업합니다.

1. **[!UICONTROL ID Type]** 선택. [!UICONTROL ID Type] 옵션은 다음과 같습니다.

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]**([!UICONTROL Profile Merge Rule]을(를) 만드는 데 필요). 일부 고객의 경우 이 옵션을 선택하면 **[!UICONTROL ID Definition]** 옵션이 표시됩니다.

   >[!NOTE]
   >
   >Audience Manager 및 Experience Platform을 위해 프로비저닝된 각 조직에 대해 두 앱 간에 세그먼트 공유를 설정하지 않았더라도 교차 장치 데이터 소스를 만들 때 해당 [ID 네임스페이스](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces)가 Experience Platform에 만들어집니다.

1. **[!UICONTROL ID Definition]** 옵션을 선택하십시오. 옵션은 다음과 같습니다.

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[데이터 내보내기 제어](../features/data-export-controls.md)는 [!UICONTROL data source] 및 [!UICONTROL destination]에 적용할 수 있는 선택적 분류 규칙입니다. 이 옵션을 사용하면 해당 작업이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 [!UICONTROL destination]에 데이터를 보내지 못합니다. [!UICONTROL Data Export Controls]을(를) 사용하지 않는 경우 이 섹션을 건너뜁니다.

## [!UICONTROL Data Source] 설정 {#settings}

이 설정은 [!UICONTROL data source]의 식별, 사용 및 공유 방법을 결정합니다. 인바운드 데이터 파일에 대한 오류 보고를 활성화할 수도 있습니다. [!UICONTROL Data Source Settings] 섹션을 완료하려면

1. [!UICONTROL data source]에 옵션을 적용하려면 [!UICONTROL Data Source Setting] 확인란을 선택하세요.
2. **[!UICONTROL Save]** 아이콘을 클릭합니다.

## 데이터 Source 삭제 {#delete-data-source}

<!-- t_datasource_delete.xml -->

더 이상 필요하지 않은 [!UICONTROL data source]을(를) 삭제합니다.

>[!NOTE]
>
>다음 제한 사항에 유의하십시오.
>
>* [활성 대상 또는 데이터 Source 동기화된 트레이트](../features/traits/client-activity-synced-audience-traits.md)는 삭제할 수 없습니다.
>* Adobe Analytics을 사용하는 고객의 경우: Audience Manager에서 [!DNL Analytics] 보고서 세트에서 자동으로 생성된 데이터 소스를 삭제할 수 없습니다. [핵심 서비스](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes)를 사용하여 이러한 데이터 원본 매핑을 해제하세요.

1. **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**&#x200B;을(를) 클릭합니다.
1. 하나 이상의 데이터 소스 옆에 있는 확인란을 선택합니다.
목록이 길면 [!UICONTROL Search] 상자를 사용하여 원하는 데이터 원본을 찾을 수 있습니다.
1. ![](assets/icon_trash.png)을(를) 클릭한 다음 삭제를 확인합니다.


>[!MORELIKETHIS]
>
>* [데이터 Source 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)
