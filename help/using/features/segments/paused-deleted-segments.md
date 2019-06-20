---
description: 세그먼트 빌더를 사용하여 활성 세그먼트를 일시 중지하거나 삭제할 때 세그먼트화된 사용자, 데이터 및 대상에 대한 효과를 설명합니다.
seo-description: 세그먼트 빌더를 사용하여 활성 세그먼트를 일시 중지하거나 삭제할 때 세그먼트화된 사용자, 데이터 및 대상에 대한 효과를 설명합니다.
seo-title: 일시 중지되거나 삭제된 세그먼트
solution: Audience Manager
title: 일시 중지되거나 삭제된 세그먼트
uuid: 88 EFE 4 AF-F 9 A 4-4 BCE -920 A -352 BD 4 D 505 DD
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## 일시 중지 및 삭제 컨트롤에 액세스

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). 이러한 기능은 아래 설명된 대로 세그먼트에 영향을 줍니다.

## 일시 중지된 세그먼트 기능

일시 중지된 (비활성화) 세그먼트:

* 자격이 있는 새 사용자 세그먼트화를 중지합니다.
* 사용자의 세그멘테이션 상태/구성원을 유지합니다 (세그먼트에서 사용자를 제거하지 않음).
* 세그먼트 목록에 유지되며 다시 활성화할 수 있습니다.
* 연결된 대상에 데이터를 보내지 않습니다.
* 사용 가능한 보고서 (비활성화 날짜까지) 의 데이터를 반환합니다.

## 삭제된 세그먼트 기능

삭제된 세그먼트:

* 자격이 있는 새 사용자 세그먼트화를 중지합니다.
* 세그먼트 멤버십에서 자격을 갖춘 사용자를 제거합니다.
* 가 세그먼트 목록에서 제거됩니다.
* 삭제할 수 없습니다.
* 연결된 대상에 데이터를 보내지 않습니다.
* 사용 가능한 보고서에서 데이터를 반환하지 않습니다.

>[!NOTE]
>
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).