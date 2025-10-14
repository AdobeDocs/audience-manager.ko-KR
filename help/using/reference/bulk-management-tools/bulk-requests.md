---
description: 벌크 요청은 업데이트, 만들기, 예상 및 삭제 워크시트의 여러 헤더와 함께 사용할 수 있는 데이터를 반환합니다.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: 대량 요청
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# 대량 요청{#bulk-requests}

벌크 요청은 업데이트, 만들기, 예상 및 삭제 워크시트의 여러 헤더와 함께 사용할 수 있는 데이터를 반환합니다.

>[!IMPORTANT]
>
>벌크 관리 도구는 공식적으로 지원되는 Adobe 제품이 아닙니다. 고객 지원 센터를 통한 문제 해결 및 지원은 사안별로 처리됩니다.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[&#x200B; UI에 할당된 &#x200B;](../../features/administration/administration-overview.md)RBAC 그룹 권한[!DNL Audience Manager]이(가) [!UICONTROL Bulk Management Tools]에서 허용됩니다.

[!UICONTROL Request] 워크시트에는 고유한 열 머리글 집합이 없으므로 ID를 열에 복사할 필요가 없습니다. 대신 도구 모음에서 클릭하는 작업 단추에 따라 데이터가 반환됩니다. 또한 선택적 보고 기능은 픽셀 실행 횟수와 고정된 여러 시간 간격 동안의 고유 사용자 수를 반환합니다.

대량 요청을 수행하려면 [!UICONTROL Bulk Management Tools] 워크시트를 열고 다음을 수행합니다.

1. **[!UICONTROL Request]** 탭을 클릭합니다.
2. 워크시트 상단의 도구 모음에서 작업할 데이터에 해당하는 요청 단추를 클릭합니다. 다음을 요청할 수 있습니다.

   * 알고리즘 모델
   * 데이터 소스
   * 파생 신호
   * 대상 매핑
   * 알고리즘, 규칙 기반 및 온보딩된 트레이트
   * 세그먼트
   * 트레이트 및 세그먼트 폴더 ID

   [!DNL Audience Manager] API가 [!UICONTROL Request] 워크시트에 대량 데이터를 다시 씁니다.

>[!NOTE]
>
>결과에서 `createTime` 및 `updateTime` 열은 지수 표기법으로 데이터를 반환합니다. 기본 날짜/타임스탬프는 UNIX UTC 시간으로 기록됩니다. 현재 워크시트는 읽을 수 있는 형식으로 날짜/타임스탬프를 반환할 수 없습니다.

벌크 업데이트가 오류를 반환하거나 실패한 경우 [대량 관리 도구 문제 해결](../../reference/bulk-management-tools/bulk-troubleshooting.md)을 참조하세요.
