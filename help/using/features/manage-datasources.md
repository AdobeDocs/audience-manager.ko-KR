---
description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가로 이동하고 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
keywords: data sources;manage data source;audience manager data source
seo-description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가로 이동하고 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
seo-title: 데이터 소스 만들기
solution: Audience Manager
title: 데이터 소스 관리
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

새 데이터 소스를 만들려면 이동 **[!UICONTROL Audience Data > Data Sources > Add New]** 으로 이동하여 여기에 설명된 각 섹션에 대한 단계를 완료하십시오. 데이터 소스를 만들려면 관리자 권한이 필요합니다.

<!-- create-datasource.xml -->

>[!TIP]
>
>이러한 다른 컨트롤에 대한 설명은 [데이터 소스 설정 및](../features/datasources-list-and-settings.md#settings-menu-options) 메뉴 옵션을 참조하십시오.

## 데이터 소스 세부 사항 {#details}

섹션을 완료하려면 [!UICONTROL Data Source Details] 다음을 수행하십시오.

1. 데이터 소스의 이름을 지정합니다.
1. *(선택 사항)* 데이터 소스를 설명합니다. 간결한 설명은 데이터 소스의 역할이나 목적을 정의하는 데 도움이 됩니다.
1. 통합 코드를 제공합니다. 일반적으로 통합 코드는 선택 사항입니다. 다음과 같은 경우에 필요합니다.

   * [크로스 디바이스 데이터 소스를 만듭니다](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Adobe [Experience Platform Identity Service를 사용하십시오](https://docs.adobe.com/content/help/en/id-service/using/home.html).
   * 프로필 병합 [규칙](../features/profile-merge-rules/merge-rules-start.md)사용

1. 원하는 구성 요소를 **[!UICONTROL ID Type]**&#x200B;선택합니다. ID 유형 옵션은 다음과 같습니다.

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (만드는 데 [!UICONTROL Profile Merge Rule]필요). 일부 고객의 경우 이 옵션을 선택하면 옵션이 **[!UICONTROL ID Definition]** 표시됩니다.

1. Choose an **[!UICONTROL ID Definition]** option. 옵션은 다음과 같습니다.

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## 데이터 내보내기 제어 {#export-controls}

[데이터 내보내기 컨트롤은](../features/data-export-controls.md) 데이터 소스 및 대상에 적용할 수 있는 선택적 분류 규칙입니다. 이러한 조치를 통해 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 데이터를 대상에 보내지 못합니다. 사용하지 않는 경우 이 섹션을 건너뜁니다 [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

이러한 설정에 따라 데이터 소스를 식별하고 사용하며 공유하는 방법이 결정됩니다. 인바운드 데이터 파일에 대한 오류 보고를 활성화할 수도 있습니다. 섹션을 완료하려면 [!UICONTROL Data Source Settings] 다음을 수행하십시오.

1. 데이터 소스에 옵션을 적용하려면 [!UICONTROL Data Source Setting] 확인란을 선택합니다.
2. 클릭 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [데이터 소스 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)


## 데이터 소스 삭제 {#delete-data-source}

<!-- t_datasource_delete.xml -->

더 이상 필요하지 않은 데이터 소스를 삭제합니다.

>[!NOTE]
>
>다음 제한 사항을 참고하십시오.
>
>* 활성 대상 또는 데이터 [소스 동기화된 트레이트는 삭제할 수 없습니다](../features/traits/client-activity-synced-audience-traits.md).
>* Adobe Analytics를 사용하는 고객의 경우 Audience Manager에서는 [!DNL Analytics] 보고서 세트에서 자동으로 생성된 데이터 소스를 삭제할 수 없습니다. 핵심 서비스 [를](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) 사용하여 이러한 데이터 소스를 매핑을 해제합니다.


1. 클릭 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 하나 이상의 데이터 소스 옆의 확인란을 선택합니다.
목록이 긴 경우 [!UICONTROL Search] 상자를 사용하여 원하는 데이터 소스를 찾을 수 있습니다.
1. 을 ![](assets/icon_trash.png)클릭하고 삭제를 확인합니다.