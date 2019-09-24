---
description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가로 이동하여 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
keywords: 데이터 소스 관리 데이터 소스 관리
seo-description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가로 이동하여 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
seo-title: 데이터 소스 만들기
solution: Audience Manager
title: 데이터 소스 관리
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

새 데이터 소스를 만들려면 여기에서 설명하는 각 섹션의 단계를 **[!UICONTROL Audience Data > Data Sources > Add New]** 완료하십시오. 데이터 소스를 만들려면 관리자 권한이 필요합니다.

<!-- create-datasource.xml -->

>[!TIP]
>
>이러한 [다른 컨트롤에 대한 설명은 데이터](../features/datasources-list-and-settings.md#settings-menu-options) 소스 설정 및 메뉴 옵션을 참조하십시오.

## 데이터 소스 세부 사항 {#details}

섹션을 완료하려면 [!UICONTROL Data Source Details] 다음을 수행하십시오.

1. 데이터 소스의 이름을 지정합니다.
1. *(선택 사항)* 데이터 소스를 설명합니다. 간결한 설명은 데이터 소스의 역할이나 목적을 정의하는 데 도움이 됩니다.
1. 통합 코드를 제공합니다. 일반적으로 통합 코드는 선택 사항입니다. 이러한 요구 사항은 다음과 같습니다.

   * [크로스 디바이스 데이터 소스를](../features/profile-merge-rules/merge-rules-start.md#create-data-source)만듭니다.
   * Experience [Cloud ID 서비스를](https://marketing.adobe.com/resources/help/en_US/mcvid/)사용합니다.
   * 프로필 병합 [규칙](../features/profile-merge-rules/merge-rules-start.md)사용

1. 원하는 **[!UICONTROL ID Type]**&#x200B;항목을 선택합니다. ID 유형 옵션은 다음과 같습니다.

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (을(를) 만드는 [!UICONTROL Profile Merge Rule]데 필요). 일부 고객의 경우 이 옵션을 선택하면 **[!UICONTROL ID Definition]** 옵션이 표시됩니다.

1. Choose an **[!UICONTROL ID Definition]** option. 옵션은 다음과 같습니다.

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기](../features/data-export-controls.md) 컨트롤은 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 이러한 동작을 통해 데이터 개인 정보 보호 또는 사용 계약을 위반할 경우 데이터가 대상으로 전송되지 않도록 합니다. 사용하지 않는 경우 이 섹션을 건너뜁니다 [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

이러한 설정에 따라 데이터 소스가 식별, 사용 및 공유되는 방식이 결정됩니다. You can also enable error reporting for inbound data files. 섹션을 완료하려면 [!UICONTROL Data Source Settings] 다음을 수행하십시오.

1. 데이터 소스에 옵션을 적용하려면 [!UICONTROL Data Source Setting] 확인란을 선택합니다.
2. 클릭 **[!UICONTROL Save]**.

>[!MORE_LIKE_THIS]
>
>* [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Delete a data source that you no longer need.

>[!NOTE]
>
>Please note the following restrictions:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the Core Service to unmap these data sources.[](https://marketing.adobe.com/resources/help/en_US/mcloud/)


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. 하나 이상의 데이터 소스 옆의 확인란을 선택합니다.
You can use the  box to locate the desired data sources if you have a long list.[!UICONTROL Search]
1. Click  , then confirm the deletion.![](assets/icon_trash.png)