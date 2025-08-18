---
description: 이는 대응 가능 대상에서 사용하는 특수 트레이트입니다. 활성 대상 및 데이터 Source 동기화된 트레이트는 대상 데이터 > 트레이트 > 대상 트레이트에 있습니다.
seo-description: These are special traits used by Addressable Audiences. Active Audience and Data Source Synced Traits are located in Audience Data > Traits > Audience Traits.
seo-title: Active Audience Traits and Data Source Synced Traits
solution: Audience Manager
title: 활성 대상 트레이트 및 데이터 Source 동기화된 트레이트
uuid: b4f145ab-f343-4d71-86d1-5d03f7b03809
feature: Traits
exl-id: 8fa4ea24-1beb-40cb-bdec-540a3f7c2573
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---

# 활성 대상 트레이트 및 데이터 Source 동기화된 트레이트 {#active-audience-traits-and-data-source-synced-traits}

[!UICONTROL Addressable Audiences]에서 사용하는 특수 특성입니다. [!UICONTROL Active Audience] 및 [!UICONTROL Data Source Synced Traits]이(가) [!UICONTROL Audience Data > Traits > Audience Traits]에 있습니다.

>[!NOTE]
>
>액세스하려면 관리자 권한이 필요합니다.

## 활성 대상 트레이트 {#active-audience-traits}

[!UICONTROL Active Audience] 트레이트에 [!DNL Audience Manager] 계정에서 관리 중인 모든 장치가 포함되어 있습니다. 세그먼트를 작성하거나 편집할 때 다른 트레이트처럼 [!UICONTROL Active Audience Trait]을(를) 사용할 수 있습니다. 또한 [대응 가능 대상](../../features/addressable-audiences.md)에서는 중복 데이터를 생성하기 위해 이 특성이 필요합니다. 기본적으로 모든 계정에 [!UICONTROL Active Audience] 특성이 있습니다. 이 트레이트는 삭제할 수 없습니다.

## 데이터 Source 동기화된 트레이트 {#data-source-synced-traits}

[!UICONTROL Data Source Synced Traits]데이터 원본을 만들거나 편집[!UICONTROL Audience Traits]할 때 [이(가) ](../../features/manage-datasources.md#create-data-source) 폴더에 나타나고 다음 설정 중 하나를 적용합니다.

![](assets/datasource_synced.png)

[!UICONTROL Data Source Synced Traits]에서 데이터 원본과 연결된 모든 사용자를 추적합니다. 세그먼트를 작성하거나 편집할 때 다른 트레이트처럼 [!UICONTROL Data Source Synched Trait]을(를) 사용할 수 있습니다. [!UICONTROL Data Source Synced Trait]을(를) 만들 때 특성 이름이 데이터 원본에서 사용하는 이름과 일치합니다. 데이터 소스를 편집하여 트레이트 이름을 변경합니다. 이러한 트레이트는 삭제할 수 없습니다.

>[!TIP]
>
>[!UICONTROL Data Source Synced Traits]은(는) 문제 해결에 유용합니다. 트레이트 요약 페이지에서 지표를 확인하려면 트레이트 이름을 클릭합니다. 선택한 트레이트가 데이터를 반환하면 ID 동기화 프로세스가 제대로 설정되고 데이터를 [!DNL Audience Manager]&#x200B;(으)로 푸시함을 나타냅니다.

>[!MORELIKETHIS]
>
>* [대응 가능 대상자](../../features/addressable-audiences.md)
