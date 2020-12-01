---
description: 데이터 내보내기 레이블은 데이터 소스에 설정한 내보내기 컨트롤과 함께 작동합니다. 데이터 내보내기 레이블을 사용하면 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 못합니다. 여러 내보내기 레이블을 새 쿠키 또는 기존 쿠키 또는 URL 대상으로 설정할 수 있습니다.
seo-description: 데이터 내보내기 레이블은 데이터 소스에 설정한 내보내기 컨트롤과 함께 작동합니다. 데이터 내보내기 레이블을 사용하면 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 못합니다. 여러 내보내기 레이블을 새 쿠키 또는 기존 쿠키 또는 URL 대상으로 설정할 수 있습니다.
seo-title: 대상에 데이터 내보내기 컨트롤 추가
solution: Audience Manager
title: 대상에 데이터 내보내기 컨트롤 추가
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---



# 대상 {#add-data-export-labels}에 데이터 내보내기 레이블 추가

[!DNL Data Export Labels] 데이터 소스 [!DNL Export Controls] 에서 설정한 작업 [!DNL Data Export Labels] 세그먼트에 제한된 트레이트를 추가하고 세그먼트 데이터를 대상에 보내지 않도록 합니다. 여러 내보내기 레이블을 새 또는 기존 [!DNL cookie] 또는 [!DNL URL] 대상으로 설정할 수 있습니다.

>[!NOTE]
>
>내보내기 레이블을 추가하려면 대상을 만들거나 편집할 수 있는 관리자 권한 *또는* 권한이 필요합니다.

<!-- t_export_labels.xml -->

대상에 내보내기 레이블을 추가하려면:

1. 클릭 **[!UICONTROL Audience Data]**:
   * 새 대상:**[!UICONTROL Create New Destination]**&#x200B;을 클릭합니다. 데이터 내보내기 레이블을 선택하기 전에 [!UICONTROL Basic Information] 섹션을 완료합니다. 자세한 내용은 [쿠키 대상 만들기](../../features/destinations/create-cookie-destination.md) 또는 [URL 대상 만들기](../../features/destinations/create-url-destination.md)를 참조하십시오.
   * 기존 대상의 경우:[!DNL Search] 상자를 사용하여 대상을 찾거나 목록을 스크롤한 다음 대상 이름을 클릭하여 엽니다.
1. [!DNL Data Export Label]을 선택합니다. 내보내기 제한을 설정하지 않으려면 확인란을 비워 둡니다. 내보내기 레이블에는 다음 옵션이 포함됩니다.
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >데이터 원본에 [일치하는 내보내기 컨트롤](../../features/data-export-controls.md)을 설정하지 않으면 내보내기 제한이 작동하지 않습니다.
1. 클릭 **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [데이터 소스 만들기](../../features/manage-datasources.md#create-data-source)