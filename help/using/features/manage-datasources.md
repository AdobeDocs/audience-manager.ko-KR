---
description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가를 클릭하고 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
keywords: CDF; 사용자 지정 데이터 피드
seo-description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가를 클릭하고 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
seo-title: 데이터 소스 만들기
solution: Audience Manager
title: 데이터 소스 만들기
uuid: 4 DF 65 BCB -9 AD 9-4 B 72-A 71 E -8918 B 43 D 4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. 데이터 소스를 만들려면 관리자 권한이 필요합니다.

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. 데이터 소스의 이름을 지정합니다.
1. *(선택 사항)* 데이터 소스를 설명합니다. 간결한 설명은 데이터 소스의 역할이나 목적을 정의하는 데 도움이 됩니다.
1. 통합 코드를 제공합니다. 일반적으로 통합 코드는 선택 사항입니다. 다음과 같은 경우에 필요합니다.

   * [장치 간 데이터 소스를 만듭니다](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * [Experience Cloud ID 서비스](https://marketing.adobe.com/resources/help/en_US/mcvid/)사용
   * [프로필 병합 규칙을](../features/profile-merge-rules/merge-rules-start.md)사용한 작업

1. **[!UICONTROL ID Type]** 을 선택합니다. ID 유형 옵션은 다음과 같습니다.

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (a [!UICONTROL Profile Merge Rule]를 만들어야 합니다.) Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. **[!UICONTROL ID Definition]** 옵션을 선택합니다. 옵션은 다음과 같습니다.

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기 컨트롤은](../features/data-export-controls.md) 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 이러한 행위는 해당 행동이 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우에 사용자가 대상에 데이터를 전송하지 못하도록 합니다. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

이러한 설정은 데이터 소스의 식별, 사용 및 공유 방법을 결정합니다. 인바운드 데이터 파일에 대한 오류 보고를 활성화할 수도 있습니다. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. 클릭 **[!UICONTROL Save]**.

>[!MORE_ like_ this]
>
>* [데이터 소스 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

더 이상 필요하지 않은 데이터 소스를 삭제합니다.

>[!NOTE]
>
>다음 제한 사항을 참고하십시오.
>
>* [활성 대상 또는 데이터 소스 동기화된 트레이트는 삭제할 수](../features/traits/client-activity-synced-audience-traits.md)없습니다.
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. [핵심 서비스를](https://marketing.adobe.com/resources/help/en_US/mcloud/) 사용하여 이러한 데이터 소스를 매핑하십시오.


1. **[!UICONTROL Audience Data]****[!UICONTROL Data Sources]**&gt;를 클릭합니다.
1. 하나 이상의 데이터 소스 옆에 있는 확인란을 선택합니다.
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.