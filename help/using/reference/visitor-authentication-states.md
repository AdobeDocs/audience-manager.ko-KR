---
description: Audience Manager의 방문자 인증 상태는 새 트레이트 정보가 방문자의 인증된 프로필에 기록되었는지 아니면 데이터를 수집한 장치 프로필에 기록되었는지 결정합니다. Audience Manager은 이벤트 호출에서 방문자 ID 인증 상태 UNKNOWN 및 LOGGED_OUT을 동일한 방식으로 처리합니다.
keywords: dpm.demdex.net
seo-description: The visitor authentication status in Audience Manager determines if the new trait information is written to the visitor's authenticated profile or to the device profile, where the data was collected from. Audience Manager handles the visitor ID authentication statuses UNKNOWN and LOGGED_OUT in event calls in the same way.
seo-title: Visitor Authentication States in Audience Manager
solution: Audience Manager
title: Audience Manager의 방문자 인증 상태
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: Reference
exl-id: 55aec28d-02f6-4e6d-9be1-4ce40deb8dc3
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 6%

---

# Audience Manager의 방문자 인증 상태{#visitor-authentication-states-in-audience-manager}

Audience Manager의 방문자 인증 상태는 새 트레이트 정보가 방문자의 인증된 프로필에 기록되었는지 아니면 데이터를 수집한 장치 프로필에 기록되었는지 결정합니다. Audience Manager은 이벤트 호출에서 방문자 ID 인증 상태 UNKNOWN 및 LOGGED_OUT을 동일한 방식으로 처리합니다.

시작 문자 [!DNL Experience Cloud] ID 서비스 v1.5+, `setCustomerID` 메서드에는 선택 사항이 포함됩니다 `AuthState` 개체. `AuthState` 은 방문자에 따라 방문자를 식별합니다 [인증 상태](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] 는 호출에서 전달된 인증 상태 및 [프로필 병합 규칙](../features/profile-merge-rules/merge-rules-dashboard.md) 을 세그먼테이션에 사용합니다.

## 인증 상태: 알 수 없음 {#auth-status-unknown}

| 요청 값 | 인증된 프로필에서 정보 읽기 | 인증된 프로필에 새 트레이트 작성 |
|---|---|---|
| 0 | <ul><li>예, [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>아니요, [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 또는 [!UICONTROL No Authenticated Profile].</li></ul> | 아니요. 트레이트 데이터가 장치 프로필에 추가됩니다. |

샘플 호출(인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 인증 상태: 인증됨 {#auth-status-authenticated}

| 요청 값 | 인증된 프로필에서 정보 읽기 | 인증된 프로필에 새 트레이트 작성 |
|---|---|---|
| 1 | <ul><li>예, [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 또는 [!UICONTROL Last Authenticated Profiles].</li><li>아니요, [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL No Authenticated Profile].</li></ul> | 예. 트레이트 데이터가 인증된 프로필에 추가됩니다. |

샘플 호출(인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 인증 상태: LOGGED_OUT {#auth-status-logged-out}

| 요청 값 | 인증된 프로필에서 정보 읽기 | 인증된 프로필에 새 트레이트 작성 |
|---|---|---|
| 2 | <ul><li>예, [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Last Authenticated Profiles].</li><li>아니요, [!UICONTROL Authenticated Option Merge Rule] = [!UICONTROL Current Authenticated Profiles] 또는 [!UICONTROL No Authenticated Profile].</li></ul> | 아니요. 트레이트 데이터는 장치 프로필에 기록됩니다. |

샘플 호출(인증 상태에 해당하는 요청 값이 강조 표시됨):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 다음 기간 동안 ID 동기화를 수행합니다. [CID 및 UUID](../reference/ids-in-aam.md) 세 가지 경우 모두.

>[!MORELIKETHIS]
>
>* [고객 ID 및 인증 상태](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html)

