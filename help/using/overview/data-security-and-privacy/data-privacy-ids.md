---
description: 이 문서에서는 데이터 개인 정보 보호 요청에 사용할 수 있는 Audience Manager ID 유형에 대해 설명합니다.
seo-description: This document covers the types of Audience Manager IDs that you can use in data privacy requests.
seo-title: Audience Manager Identifiers (IDs)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, 개인 정보, AAM ID
title: Audience Manager 식별자(ID)
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 96%

---

# Audience Manager 식별자(ID) {#aam-ids}

Adobe Audience Manager에 [데이터 개인 정보 보호 요청](data-privacy-requests.md)을 제출할 때는 아래에 나열된 식별자(ID) 중 하나를 포함해야 합니다. ID 형식에 대한 자세한 내용은 [Audience Manager ID 색인](../../reference/ids-in-aam.md)에 있습니다.

## Adobe Audience Manager 고유 사용자 ID

* **사용자 ID**: `aam_uuid`
* **정의**: Adobe Audience Manager 고유 사용자 ID
* **네임스페이스 ID**: 0

**JSON 예**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>[!DNL CORE] 네임스페이스를 사용할 수도 있습니다.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **사용자 ID**: `mid`
* **정의**: [!DNL Adobe Experience Cloud ID] (이전에는 [!DNL Visitor ID] 또는 [!DNL Marketing Cloud ID]라고 함)
* **네임스페이스 ID**: 4

>[!NOTE]
>
>[!DNL ECID] 네임스페이스를 사용할 수도 있습니다. 두 번째 [!DNL JSON] 예를 참조하십시오.

**JSON 예**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## 고객 ID

**사용자 ID**: `cid`

**정의**: 익명의 사이트 방문자에 대해 설정한 쿠키나 오프라인 시스템 또는 해시된 사용자 이름의 [!DNL CRM] ID와 같은 고객 ID

**네임스페이스 ID**: 고객별로 다름. Audience Manager 인스턴스에서 찾으십시오.

**JSON 예**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## 모바일 광고 ID

**사용자 ID**: `d_cid`

**정의**: 모바일 광고 ID.

**네임스페이스 ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

자세한 내용은 [글로벌 데이터 소스](../../features/global-data-sources.md)를 참조하십시오.

>[!IMPORTANT]
>
> Mobile [!DNL SDK]를 사용 중이라면 전체 액세스 및 삭제 응답을 위해 모바일 광고 ID와 함께 Experience Cloud ID(`MID`)도 전송해야 합니다.

**JSON 예**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## 통합 코드

**사용자 ID**: `d_cid_ic`

**정의**: 데이터 소스에 대한 통합 코드. [!DNL Adobe Experience Cloud Privacy Core Service]에 제출하는 [!DNL API] 요청에서 데이터 소스 ID / 네임스페이스 ID 대신 사용할 수 있습니다.

**네임스페이스 ID**: 해당 사항 없음

**JSON 예**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
