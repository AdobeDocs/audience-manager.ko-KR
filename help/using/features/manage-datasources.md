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
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---

# 채널 및 솔루션에서 일관되게 [!UICONTROL Data Sources] {#manage-data-sources}

## 웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!UICONTROL Data Source] {#create-data-source}

새로 만들려면 [!UICONTROL data source]로 이동합니다. **[!UICONTROL Audience Data > Data Sources > Add New]** 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 을(를) 만들려면 관리자 권한이 필요합니다. [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>다음을 참조하십시오 [데이터 소스 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options) 이러한 다른 컨트롤에 대한 설명입니다.

## [!UICONTROL Data Source] 세부 사항 {#details}

다음을 완료하려면 [!UICONTROL Data Source Details] 섹션:

1. 이름 지정 [!UICONTROL data source].
1. *(선택 사항)* 설명 [!UICONTROL data source]. 간략한 설명은 의 역할이나 목적을 정의하는 데 도움이 됩니다. [!UICONTROL data source].
1. 다음을 제공하십시오. [!UICONTROL integration code]. 일반적으로, [!UICONTROL integration codes] 선택 사항입니다. 다음 작업을 수행할 때 필요합니다.

   * [크로스 디바이스 데이터 소스 만들기](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * 사용 [Adobe Experience Platform ID 서비스](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * 로 작업 [프로필 병합 규칙](../features/profile-merge-rules/merge-rules-start.md).

1. 선택 **[!UICONTROL ID Type]**. [!UICONTROL ID Type] 옵션은 다음과 같습니다.

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (다음을 만드는 데 필요) [!UICONTROL Profile Merge Rule]). 참고: 일부 고객의 경우 이 옵션을 선택하면 **[!UICONTROL ID Definition]** 옵션.

   >[!NOTE]
   >
   >두 앱 간에 세그먼트 공유를 설정하지 않았더라도 Audience Manager 및 Experience Platform에 대해 프로비저닝된 각 조직에 대해 교차 장치 데이터 소스를 만들 때 해당 [id 네임스페이스](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) 은(는) Experience Platform에서 생성됩니다.

1. 선택 **[!UICONTROL ID Definition]** 옵션을 선택합니다. 옵션은 다음과 같습니다.

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[데이터 내보내기 제어](../features/data-export-controls.md) 은 다음에 적용할 수 있는 선택적 분류 규칙입니다. [!UICONTROL data source] 및 [!UICONTROL destination]. 이 옵션을 사용하면 데이터가 [!UICONTROL destination] 해당 작업이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우. 사용하지 않는 경우 이 섹션을 건너뜁니다. [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] 설정 {#settings}

이 설정에 따라 [!UICONTROL data source] 는 식별, 사용 및 공유됩니다. 인바운드 데이터 파일에 대한 오류 보고를 활성화할 수도 있습니다. 다음을 완료하려면 [!UICONTROL Data Source Settings] 섹션:

1. 선택 [!UICONTROL Data Source Setting] 에 옵션을 적용하려면 확인란 [!UICONTROL data source].
2. 클릭 **[!UICONTROL Save]**.

## 데이터 소스 삭제 {#delete-data-source}

<!-- t_datasource_delete.xml -->

삭제 [!UICONTROL data source] 더 이상 필요하지 않습니다.

>[!NOTE]
>
>다음 제한 사항에 유의하십시오.
>
>* 은(는) 삭제할 수 없습니다. [활성 대상자 또는 데이터 소스 동기화된 트레이트](../features/traits/client-activity-synced-audience-traits.md).
>* Adobe Analytics을 사용하는 고객의 경우: Audience Manager에서 자동으로 생성된 데이터 소스를 삭제할 수 없습니다. [!DNL Analytics] 보고서 세트. 사용 [핵심 서비스](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) 를 클릭하여 이러한 데이터 소스의 매핑을 해제합니다.


1. 클릭 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 하나 이상의 데이터 소스 옆에 있는 확인란을 선택합니다.
다음을 사용할 수 있습니다. [!UICONTROL Search] 긴 목록이 있는 경우 원하는 데이터 소스를 찾는 상자입니다.
1. 클릭  ![](assets/icon_trash.png)을 클릭한 다음 삭제를 확인합니다.


>[!MORELIKETHIS]
>
>* [데이터 소스 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)

