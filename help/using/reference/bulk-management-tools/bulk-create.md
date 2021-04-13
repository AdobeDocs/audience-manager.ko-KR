---
description: 벌크 만들기를 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 구성할 수 있습니다. 다음 지침에 따라 일괄 생성을 요청합니다.
seo-description: 벌크 만들기를 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 구성할 수 있습니다. 다음 지침에 따라 일괄 생성을 요청합니다.
seo-title: 벌크 만들기
solution: Audience Manager
title: 벌크 만들기
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# 벌크 만들기{#bulk-create}

벌크 만들기를 사용하면 단일 작업으로 여러 데이터 소스, 파생된 신호, 세그먼트, 트레이트 및 기타 항목을 구성할 수 있습니다. 다음 지침에 따라 일괄 생성을 요청합니다.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[UI](../../features/administration/administration-overview.md) 에 할당된 RBAC 그룹  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools]권한은

>[!CAUTION]
>
>벌크 작성 요청에 개체 유형을 혼합하지 마십시오. 각 개체의 헤더는 고유하며 결합할 수 없습니다. 워크시트를 지우고 다른 항목에 대해 별도의 요청을 수행합니다.

개체를 대량으로 만들려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Headers]** 탭을 클릭하고 추가할 항목의 만들기 헤더를 복사합니다.
2. **[!UICONTROL Create]** 탭을 클릭합니다.
3. 머리말 만들기를 업데이트 워크시트의 첫 번째 행에 붙여넣습니다.
4. 변경할 데이터를 머리글 레이블을 기반으로 해당 열로 붙여넣거나 입력합니다.
5. 워크시트 도구 모음에서 업데이트 중인 항목과 일치하는 만들기 단추를 클릭합니다.
이 작업을 수행하면 [!UICONTROL Account Information] 대화 상자가 열립니다.
6. 필수 [로그온 정보](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs)를 입력하고 **[!UICONTROL Submit]**&#x200B;를 클릭합니다.

워크시트는 [!UICONTROL Results] 열을 만듭니다. [!UICONTROL Results] 열은 성공적인 작업에 대한 JSON 응답을 반환합니다. 예제는 [REST API](../../api/rest-api-main/rest-api-main.md)를 참조하십시오. 데이터를 입력하기 전에 벌크 작성 워크시트는 다음 예와 비슷해야 합니다. 참고, 다른 모든 만들기 옵션은 여기에 표시되지 않습니다. 완료된 워크시트가 어떤 모습일지 이해하는 데 도움이 됩니다.

![](assets/cretetraits.png)

벌크 업데이트가 오류를 반환하거나 실패하는 경우 [벌크 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하십시오.
