---
description: 이러한 사양에 따라 Audience Optimization 메타데이터 파일의 이름을 지정합니다.
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: 메타데이터 파일에 대한 이름 지정 규칙
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
TQID: 'https://experienceleague.adobe.com/8NiHEhLXJHHdYfO4LjwpEjpLqFHsHAW3BnI9q4K8zt4'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: f15e67cf-b90e-44f4-ae50-f1fb9f866a27
    internal-label: Log files
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 2%
---
# 메타데이터 파일에 대한 이름 지정 규칙{#naming-conventions-for-metadata-files}

이러한 사양에 따라 Audience Optimization 메타데이터 파일의 이름을 지정합니다.

## 구문 및 ID 범주 {#syntax}

다음 구문은 올바른 형식의 메타데이터 파일 이름의 구조를 정의합니다. *기울임꼴*&#x200B;은(는) 변수 자리 표시자를 나타냅니다. 다른 요소는 상수이며 변경되지 않습니다.

**구문:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*메타데이터 파일(.txt 또는 기타)에서 파일 확장자를 사용하지 마십시오*.

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* 중간 구성 요소 **0**&#x200B;은(는) 엄밀히 말하면 레거시 필드인 상위 ID입니다. 값은 항상 **0**(으)로 설정해야 합니다.
* 하위 ID는 차원에 따라 1과 10 사이의 값을 가질 수 있습니다. 아래를 참조하십시오.

## 하위 ID 차원 {#child-dimension}

메타데이터 파일 이름에서 하위 ID는 파일의 데이터 유형을 분류하여 계층에 배치하는 식별자입니다. 파일 이름의 하위 ID에 다음 범주 ID로 태그를 지정할 수 있습니다.

1. 캠페인
1. Creative
1. 배치
1. Exchange
1. Site
1. 광고주([데이터 원본](../../../features/manage-datasources.md#details)에서 통합 코드를 사용하는 경우)
1. 삽입 순서(IO)
1. 수직 (즉, &quot;컴퓨터&quot;, &quot;자동차&quot;, &quot;부동산&quot; 등과 같은 특정 산업 또는 비즈니스 범주)
1. 전술
1. 비즈니스 단위 또는 브랜드

## 예 {#example}

Creative 메타데이터 파일의 경우 파일 이름은 20190115_0_2일 수 있습니다.

<!--
Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`.
-->
