---
description: 데이터 내보내기 레이블은 데이터 소스에 설정한 내보내기 컨트롤과 함께 작동합니다. 데이터 내보내기 레이블 을 사용하면 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 못합니다. 여러 내보내기 레이블을 새 또는 기존 쿠키 또는 URL 대상에 설정할 수 있습니다.
seo-description: 데이터 내보내기 레이블은 데이터 소스에 설정한 내보내기 컨트롤과 함께 작동합니다. 데이터 내보내기 레이블 을 사용하면 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 못합니다. 여러 내보내기 레이블을 새 또는 기존 쿠키 또는 URL 대상에 설정할 수 있습니다.
seo-title: 대상에 데이터 내보내기 컨트롤 추가
solution: Audience Manager
title: 대상에 데이터 내보내기 컨트롤 추가
feature: 데이터 내보내기 제어
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

---

# 대상에 데이터 내보내기 레이블 추가 {#add-data-export-labels}

[!DNL Data Export Labels] 데이터 소스 [!DNL Export Controls] 에서 설정한 을 사용하여 작업합니다. [!DNL Data Export Labels] 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 않도록 합니다. 여러 내보내기 레이블을 새 또는 기존 [!DNL cookie] 또는 [!DNL URL] 대상으로 설정할 수 있습니다.

>[!NOTE]
>
>내보내기 레이블을 추가하려면 대상을 만들거나 편집할 수 있는 관리자 권한 *또는* 권한이 필요합니다.

<!-- t_export_labels.xml -->

대상에 내보내기 레이블을 추가하려면 다음을 수행하십시오.

1. 클릭 **[!UICONTROL Audience Data]**:
   * 새 대상:**[!UICONTROL Create New Destination]** 을 클릭합니다. 데이터 내보내기 레이블을 선택하기 전에 [!UICONTROL Basic Information] 섹션을 완료합니다. 자세한 내용은 [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md) 또는 [URL 대상 만들기](../../features/destinations/create-url-destination.md)를 참조하십시오.
   * 기존 대상의 경우:[!DNL Search] 상자를 사용하여 대상을 찾거나 목록을 스크롤한 다음 대상 이름을 클릭하여 엽니다.
1. [!DNL Data Export Label] 을 선택합니다. 내보내기 제한을 설정하지 않으려면 확인란을 비워 둡니다. 레이블 내보내기에는 다음 옵션이 포함됩니다.
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >데이터 소스에 일치하는 내보내기 제어](../../features/data-export-controls.md)를 설정하지 않으면 내보내기 제한이 작동하지 않습니다.[
1. 클릭 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [데이터 소스 만들기](../../features/manage-datasources.md#create-data-source)

