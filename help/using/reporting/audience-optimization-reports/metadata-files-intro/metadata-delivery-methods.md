---
description: Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하여 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-description: Audience Manager 계정에 대한 특수 Amazon S3 디렉토리로 메타데이터 파일을 전송하여 메타데이터 파일을 전송하거나 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.
seo-title: 메타데이터 파일에 대한 전달 방법
solution: Audience Manager
title: 메타데이터 파일에 대한 전달 방법
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: 로그 파일
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---

# 메타데이터 파일에 대한 전달 방법{#delivery-methods-for-metadata-files}

Audience Manager 계정의 특수 [!DNL Amazon S3] 디렉토리로 메타데이터 파일을 전송하여 메타데이터 파일을 전송 또는 업데이트합니다. 배달/디렉토리 경로, 파일 처리 시간 및 업데이트에 대한 자세한 내용은 이 섹션을 참조하십시오.

>[!IMPORTANT]
>
> 메타데이터 파일을 시작하기 위해 Audience Manager 컨설턴트나 고객 지원 센터에 문의하십시오.[!DNL Amazon S3]

## 배달 경로 구문 및 예 {#syntax}

데이터는 [!DNL Amazon S3] 디렉토리에 각 고객에 대한 별도의 네임스페이스에 저장됩니다. 파일 경로는 아래에 표시된 구문을 따릅니다. 참고: 꺾쇠 괄호 `<>`는 변수 자리 표시자를 나타냅니다. 다른 요소는 상수이며 변경되지 않습니다.

**구문:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**예:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

다음 표는 파일 배달 경로에서 이러한 요소 각각을 정의합니다.


| 파일 매개 변수 | 설명 |
---------|----------|
| `.../log_ingestion/` | 디렉토리 저장소 경로의 시작입니다. 모든 것이 설정되면 전체 경로를 받게 됩니다. |
| `pid=<AAM ID>` | 이 키-값 쌍에는 Audience Manager 고객 ID가 포함되어 있습니다. |
| `dpid=<d_src>` | 이 키-값 쌍은 이벤트 호출에서 전달된 데이터 소스 ID를 포함합니다. 데이터 소스 ID는 파일의 모든 내용을 실제 데이터가 속하는 데이터에 연결하는 값입니다. </br> 예를 들어 ID 123과 이름이 &quot;광고주 크리에이티브 A&quot;인 크리에이티브가 있다고 가정해 보십시오. 이벤트 호출이 ID에만 전달되므로 메타데이터 파일에 &quot;광고주 크리에이티브 A&quot;를 포함해야 합니다. 캠페인과 크리에이티브는 데이터 소스에 속합니다. 데이터 소스 ID는 이러한 항목을 결합하는 것으로, 이벤트 호출 시 전송된 ID에 파일 내용을 정확하게 연결할 수 있도록 해줍니다. [이벤트 호출 ID가 파일 이름, 콘텐츠 및 전달 경로를 결정하는 방법](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names)을 참조하십시오. |
| `<yyyymmdd_0_child ID>` | 파일 이름입니다. 메타데이터 파일에 대한 [이름 지정 규칙](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md)을 참조하십시오. |

## 파일 처리 시간 및 업데이트 {#processing-times}

메타데이터 파일은 정기적으로 하루에 4회 처리됩니다.

메타데이터 레코드를 업데이트하려면 새 정보가 포함된 파일을 보내기만 하면 됩니다. 매번 전체 업데이트를 보낼 필요가 없습니다.
