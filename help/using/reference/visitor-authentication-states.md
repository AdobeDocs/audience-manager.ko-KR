---
description: Audience Manager의 방문자 인증 상태는 새 특성 정보가 방문자의 인증된 프로필 또는 데이터가 수집되는 장치 프로필에 기록되었는지 여부를 결정합니다. Audience Manager은 같은 방식으로 방문자 ID 인증 상태 UNKNOWN 및 LOGGED_OUT을 이벤트 호출에서 처리합니다.
keywords: dpm.demdex.net
seo-description: Audience Manager의 방문자 인증 상태는 새 특성 정보가 방문자의 인증된 프로필 또는 데이터가 수집되는 장치 프로필에 기록되었는지 여부를 결정합니다. Audience Manager은 같은 방식으로 방문자 ID 인증 상태 UNKNOWN 및 LOGGED_OUT을 이벤트 호출에서 처리합니다.
seo-title: Audience Manager의 방문자 인증 상태
solution: Audience Manager
title: Audience Manager의 방문자 인증 상태
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 5%

---


# Audience Manager의 방문자 인증 상태{#visitor-authentication-states-in-audience-manager}

Audience Manager의 방문자 인증 상태는 새 특성 정보가 방문자의 인증된 프로필 또는 데이터가 수집되는 장치 프로필에 기록되었는지 여부를 결정합니다. Audience Manager은 같은 방식으로 방문자 ID 인증 상태 UNKNOWN 및 LOGGED_OUT을 이벤트 호출에서 처리합니다.

ID [!DNL Experience Cloud] 서비스 v1.5+부터 이 `setCustomerID` 메서드에는 선택적 `AuthState` 개체가 포함됩니다. `AuthState` 인증 상태에 따라 방문자를 [식별합니다](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). [!DNL Audience Manager] 호출에서 전달된 인증 상태와 세그멘테이션에 사용하는 [프로필 병합 규칙에](../features/profile-merge-rules/merge-rules-dashboard.md) 따라 실현된 특성을 다르게 처리합니다.

## 인증 상태:알 수 없음 {#auth-status-unknown}

| 요청 값 | **인증된 프로필에서 정보 읽기** | **인증된 프로필에** 새 트레이트 쓰기 |
---------|----------|---------
| 0 | <ul><li>예, 인증된 옵션 병합 규칙 = &quot;마지막으로 인증된 프로필&quot;인 경우.</li><li>아니요, 인증된 옵션 병합 규칙 = &quot;현재 인증된 프로필&quot; 또는 &quot;인증된 프로필 없음&quot;인 경우.</li></ul> | 장치 프로필에 트레이트 데이터가 추가됩니다. |


샘플 호출(인증 상태에 해당하는 요청 값 강조 표시):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## 인증 상태:인증됨 {#auth-status-authenticated}

| 요청 값 | **인증된 프로필에서 정보 읽기** | **인증된 프로필에** 새 트레이트 쓰기 |
---------|----------|---------
| 1 | <ul><li>예, 인증된 옵션 병합 규칙 = &quot;현재 인증된 프로필&quot; 또는 &quot;마지막 인증된 프로필&quot;인 경우.</li><li>아니요, 인증된 옵션 병합 규칙 = &quot;인증된 프로필 없음&quot;인 경우.</li></ul> | 예, 특성 데이터는 인증된 프로필에 추가됩니다. |

샘플 호출(인증 상태에 해당하는 요청 값 강조 표시):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## 인증 상태:LOGGED_OUT {#auth-status-logged-out}

| 요청 값 | **인증된 프로필에서 정보 읽기** | **인증된 프로필에** 새 트레이트 쓰기 |
---------|----------|---------
| 2 | <ul><li>예, 인증된 옵션 병합 규칙 = &quot;마지막으로 인증된 프로필&quot;</li><li>아니요, 인증된 옵션 병합 규칙 = &quot;현재 인증된 프로필&quot; 또는 &quot;인증된 프로필 없음&quot;인 경우</li></ul> | 아니오, 특성 데이터는 장치 프로필에 기록됩니다. |

샘플 호출(인증 상태에 해당하는 요청 값 강조 표시):

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] 세 가지 경우 모두 [CID와 UUID](../reference/ids-in-aam.md) 간의 ID 동기화를 수행합니다.

>[!MORELIKETHIS]
>
>* [고객 ID 및 인증 상태](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

