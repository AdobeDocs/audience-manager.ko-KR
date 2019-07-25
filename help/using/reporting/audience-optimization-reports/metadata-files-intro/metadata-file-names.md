---
description: 다음 사양에 따라 대상 최적화 메타데이터 파일을 지정합니다.
seo-description: 다음 사양에 따라 대상 최적화 메타데이터 파일을 지정합니다.
seo-title: 메타데이터 파일에 대한 이름 지정 규칙
solution: Audience Manager
title: 메타데이터 파일에 대한 이름 지정 규칙
uuid: CAB 55 B 2 A -2 E 54-45 F 6-AEEA -3735 B 911 F 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Naming Conventions for Metadata Files{#naming-conventions-for-metadata-files}

다음 사양에 따라 대상 최적화 메타데이터 파일을 지정합니다.

## Syntax and ID Categories {#syntax}

다음 구문은 잘 구성된 메타데이터 파일 이름의 구조를 정의합니다. *기울임꼴은* 변수 자리 표시자를 나타냅니다. 다른 요소는 상수이며 변경되지 않습니다.

**구문:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*메타데이터 파일에서 파일 확장자를* 사용하지 마십시오 (.txt.

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* The middle component **0** is technically the Parent ID, which is a legacy field. The value should always be set as **0**.
* 하위 ID는 차원에 따라 1와 10 사이의 값을 가질 수 있습니다. 아래를 참조하십시오.

## Child ID dimensions {#child-dimension}

메타데이터 파일 이름에서 하위 ID는 파일의 데이터 유형을 분류한 후 계층에 배치하는 식별자입니다. 파일 이름에서 하위 ID에 다음 카테고리 ID를 태그로 지정할 수 있습니다.

1. 캠페인
1. 크리에이티브
1. 배치
1. Exchange
1. 사이트
1. Advertiser (if using integration codes in a [data source](../../../features/manage-datasources.md#details))
1. 삽입 순서 (IO)
1. 수직 (예: "컴퓨터", "자동차", "부동산" 등 특정 산업 또는 비즈니스 카테고리)
1. 전술
1. 사업부 또는 브랜드

## 예 {#example}

크리에이티브 메타데이터 파일의 경우 파일 이름은 20190115_ 0_ 2 입니다.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
