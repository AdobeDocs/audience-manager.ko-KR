---
description: 메타데이터 파일을 Audience Manager 계정의 특수 Amazon S3 디렉토리에 전송하여 전송하거나 업데이트합니다. 배달/디렉터리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: 메타데이터 파일에 대한 전달 방법
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# 메타데이터 파일에 대한 전달 방법{#delivery-methods-for-metadata-files}

메타데이터 파일을 Audience Manager 계정의 특수 [!DNL Amazon S3] 디렉터리로 보내 보내거나 업데이트합니다. 배달/디렉터리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

>[!IMPORTANT]
>
> 메타데이터 파일에 대한 [!DNL Amazon S3] 디렉터리를 시작하고 설정하려면 Audience Manager 컨설턴트 또는 고객 지원 센터에 문의하십시오.

## 게재 경로 구문 및 예 {#syntax}

데이터는 [!DNL Amazon S3] 디렉터리의 각 고객에 대해 별도의 네임스페이스에 저장됩니다. 파일 경로는 아래에 표시된 구문을 따릅니다. 꺾쇠 괄호 `<>`은(는) 변수 자리 표시자를 나타냅니다. 다른 요소는 상수이며 변경되지 않습니다.

**구문:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**예:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

다음 표는 파일 전달 경로의 이러한 각 요소를 정의합니다.


| 파일 매개 변수 | 설명 |
|---------|----------|
| `.../log_ingestion/` | 디렉토리 스토리지 경로의 시작입니다. 모든 것이 설정되면 전체 경로를 받게 됩니다. |
| `pid=<AAM ID>` | 이 키-값 쌍에는 Audience Manager 고객 ID가 포함되어 있습니다. |
| `dpid=<d_src>` | 이 키-값 쌍에는 이벤트 호출 시 전달된 데이터 소스 ID가 포함되어 있습니다. 데이터 소스 ID는 파일의 모든 컨텐츠를 해당 데이터가 속한 실제 데이터에 연결하는 값입니다. </br> 예를 들어 ID가 123이고 이름이 &quot;Advertiser Creative A&quot;인 크리에이티브가 있다고 가정합니다. 이벤트 호출은 ID만 전달하므로 메타데이터 파일에 &quot;Advertiser Creative A&quot;를 포함해야 합니다. 캠페인 및 크리에이티브는 데이터 소스에 속합니다. 데이터 소스 ID는 이러한 ID를 함께 결합하고 파일 컨텐츠를 이벤트 호출 시 전송된 ID에 정확하게 연결할 수 있는 것입니다. [이벤트 호출 ID가 파일 이름, 내용 및 게재 경로를 결정하는 방법](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)을 참조하십시오. |
| `<yyyymmdd_0_child ID>` | 파일 이름입니다. [메타데이터 파일에 대한 이름 지정 규칙](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)을 참조하십시오. |

## 파일 처리 시간 및 업데이트 {#processing-times}

메타데이터 파일은 정기적으로 하루에 네 번 처리됩니다.

메타데이터 레코드를 업데이트하려면 새 정보가 포함된 파일을 보내면 됩니다. 매번 전체 업데이트를 보낼 필요가 없습니다.
