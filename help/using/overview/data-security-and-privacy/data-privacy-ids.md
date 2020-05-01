---
description: 이 문서에서는 데이터 개인 정보 요청에 사용할 수 있는 Audience Manager ID 유형에 대해 설명합니다.
seo-description: 이 문서에서는 데이터 개인 정보 요청에 사용할 수 있는 Audience Manager ID 유형에 대해 설명합니다.
seo-title: Audience Manager 식별자(ID)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Audience Manager 식별자(ID)
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Audience Manager 식별자(ID) {#aam-ids}

Adobe Audience Manager에 [데이터 개인 정보 보호 요청을](data-privacy-requests.md) 제출할 때는 아래에 나열된 식별자(ID) 중 하나를 포함해야 합니다. ID 형식에 대한 자세한 내용은 Audience Manager ID의 [색인을 참조하십시오](../../reference/ids-in-aam.md).

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
>You can also use the [!DNL CORE] namespace.

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
* **정의**: [!DNL Adobe Experience Cloud ID], 이전에 [!DNL Visitor ID] or [!DNL Marketing Cloud ID]
* **네임스페이스 ID**: 4

>[!NOTE]
>
>You can also use the [!DNL ECID] namespace. 두 번째 [!DNL JSON] 예를 참조하십시오.

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

## Customer ID

**사용자 ID**: `cid`

**정의**: 익명의 사이트 방문자를 위해 설정한 쿠키나 오프라인 시스템 또는 해시된 사용자 이름의 [!DNL CRM] ID입니다.

**네임스페이스 ID**: 고객별 Audience Manager 인스턴스에서 찾으십시오.

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

자세한 내용은 [전역](../../features/global-data-sources.md) 데이터 소스를 참조하십시오.

>[!IMPORTANT]
>
> Mobile을 사용 중인 경우 [!DNL SDK]전체 액세스 및 삭제 응답을 위해 Experience Cloud ID(`MID`모바일 광고 ID)와 함께 전송해야 합니다.

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

**정의**: 데이터 소스에 대한 통합 코드입니다. 데이터 소스 ID/네임스페이스 ID 대신 사용할 수 [!DNL API] 있습니다 [!DNL Adobe Experience Cloud Privacy Core Service].

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
