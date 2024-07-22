---
description: 세그먼트 빌더를 사용하여 활성 세그먼트를 일시 중지하거나 삭제할 때 세그먼트화된 사용자, 데이터 및 대상에 미치는 영향에 대해 설명합니다.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: 일시 중지 및 삭제된 세그먼트
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# 일시 중지 및 삭제된 세그먼트 {#paused-and-deleted-segments}

[!UICONTROL Segment Builder]을(를) 사용하여 활성 세그먼트를 일시 중지하거나 삭제할 때 세그먼트화된 사용자, 데이터 및 대상에 미치는 영향을 설명합니다.

## 일시 중지 및 삭제 컨트롤에 액세스

[!UICONTROL Actions] 열의 **[!UICONTROL pause]** 및 **[!UICONTROL delete]** 아이콘을 표시하려면 세그먼트 목록의 세그먼트 이름 위에 마우스를 가져갑니다. 이러한 기능은 아래 설명된 대로 세그먼트에 영향을 줍니다.

## 일시 중지된 세그먼트 기능

일시 중지된(비활성화된) 세그먼트:

* 자격이 있는 신규 사용자를 세그먼트화하는 것을 중지합니다.
* 사용자의 세그먼테이션 상태/멤버십을 유지합니다(세그먼트에서 사용자를 제거하지 않음).
* 는 세그먼트 목록에 남아 있으며 다시 활성화할 수 있습니다.
* 연결된 대상으로 데이터를 전송하지 않습니다.
* 사용 가능한 보고서(비활성화 날짜까지)의 데이터를 반환합니다.

## 삭제된 세그먼트 기능

삭제된 세그먼트:

* 자격이 있는 신규 사용자를 세그먼트화하는 것을 중지합니다.
* 세그먼트 멤버십에서 적격 사용자를 제거합니다.
* 세그먼트 목록에서 제거됩니다.
* 삭제 취소할 수 없습니다.
* 연결된 대상으로 데이터를 전송하지 않습니다.
* 사용 가능한 보고서에서 데이터를 반환하지 않습니다.

>[!NOTE]
>
>[!DNL API] 메서드를 사용하여 세그먼트를 일시 중지하고 삭제할 수도 있습니다. 자세한 내용은 [REST API](../../api/rest-api-main/rest-api-main.md)를 참조하십시오.
