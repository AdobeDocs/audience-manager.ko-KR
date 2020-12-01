---
description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가로 이동하고 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
keywords: data sources;manage data source;audience manager data source
seo-description: 새 데이터 소스를 만들려면 대상 데이터 > 데이터 소스 > 새로 추가로 이동하고 여기에 설명된 각 섹션에 대한 단계를 완료합니다. 데이터 소스를 만들려면 관리자 권한이 필요합니다.
seo-title: 데이터 소스 만들기
solution: Audience Manager
title: 데이터 소스 관리
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---


# 채널 및 솔루션에서 일관되게 [!UICONTROL Data Sources] {#manage-data-sources}

## 웹 사이트에 있는 각각의 고유한 랜딩 위치에 대해 [!UICONTROL Data Source] {#create-data-source}

새 [!UICONTROL data source]을(를) 만들려면 **[!UICONTROL Audience Data > Data Sources > Add New]**&#x200B;로 이동하여 여기에 설명된 각 섹션에 대한 단계를 완료하십시오. [!UICONTROL data source]을(를) 만들려면 관리자 권한이 필요합니다.

<!-- create-datasource.xml -->

>[!TIP]
>
>이러한 다른 컨트롤에 대한 설명은 [데이터 소스 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)을 참조하십시오.

## [!UICONTROL Data Source] 세부 사항 {#details}

[!UICONTROL Data Source Details] 섹션을 완료하려면

1. [!UICONTROL data source] 이름을 지정합니다.
1. *(선택 사항)* 을  [!UICONTROL data source]설명합니다. 간결한 설명은 [!UICONTROL data source]의 역할이나 목적을 정의하는 데 도움이 됩니다.
1. [!UICONTROL integration code]을(를) 제공합니다. 일반적으로 [!UICONTROL integration codes]은 선택 사항입니다. 이러한 요구 사항은 다음과 같습니다.

   * [크로스 디바이스 데이터 소스를 만듭니다](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * [Adobe Experience Platform ID 서비스](https://docs.adobe.com/content/help/ko-KR/id-service/using/home.html)를 사용하십시오.
   * [프로필 병합 규칙](../features/profile-merge-rules/merge-rules-start.md)으로 작업합니다.

1. **[!UICONTROL ID Type]**&#x200B;을 선택합니다. [!UICONTROL ID Type] 옵션:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (만드는 데  [!UICONTROL Profile Merge Rule]필요). 참고, 일부 고객의 경우 이 선택 사항은 **[!UICONTROL ID Definition]** 옵션을 노출합니다.

1. **[!UICONTROL ID Definition]** 옵션을 선택합니다. 옵션은 다음과 같습니다.

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[데이터 내보내기 ](../features/data-export-controls.md) 컨트롤은  [!UICONTROL data source] 및 [!UICONTROL destination]에 적용할 수 있는 선택적 분류 규칙입니다. 이 때문에 데이터 개인 정보 보호 또는 사용 계약을 위반하는 경우 데이터가 [!UICONTROL destination]에 전송되지 않습니다. [!UICONTROL Data Export Controls]을(를) 사용하지 않으면 이 섹션을 건너뜁니다.

## [!UICONTROL Data Source] 설정 {#settings}

이러한 설정에 따라 [!UICONTROL data source]이(가) 어떻게 식별, 사용 및 공유되는지 결정됩니다. 인바운드 데이터 파일에 대한 오류 보고를 활성화할 수도 있습니다. [!UICONTROL Data Source Settings] 섹션을 완료하려면

1. [!UICONTROL Data Source Setting] 확인란을 선택하여 [!UICONTROL data source]에 옵션을 적용합니다.
2. 클릭 **[!UICONTROL Save]**.

## 데이터 소스 {#delete-data-source} 삭제

<!-- t_datasource_delete.xml -->

더 이상 필요하지 않은 [!UICONTROL data source]을 삭제합니다.

>[!NOTE]
>
>다음 제한 사항을 참고하십시오.
>
>* [활성 대상 또는 데이터 소스 동기화된 특성](../features/traits/client-activity-synced-audience-traits.md)은 삭제할 수 없습니다.
>* Adobe Analytics을 사용하는 고객의 경우:Audience Manager에서는 [!DNL Analytics] 보고서 세트에서 자동으로 생성된 데이터 소스를 삭제할 수 없습니다. [핵심 서비스](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html)를 사용하여 이러한 데이터 소스를 매핑을 해제합니다.


1. 클릭 **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. 하나 이상의 데이터 소스 옆의 확인란을 선택합니다.
목록이 긴 경우 [!UICONTROL Search] 상자를 사용하여 원하는 데이터 소스를 찾을 수 있습니다.
1. ![](assets/icon_trash.png)을 클릭한 다음 삭제를 확인합니다.


>[!MORELIKETHIS]
>
>* [데이터 소스 설정 및 메뉴 옵션](../features/datasources-list-and-settings.md#settings-menu-options)